<template>
  <div class="container main pt-5 pb-5" id="book-index">
    <div class="row mb-5">
      <div class="col-sm-12">
        <SimpleSearch
          placeholder="Enter the URL of a book from a variety of eBook websites"
          :action="
            url => {
              location.hash = `#/${$l1.code}/${$l2.code}/book/index/${encodeURIComponent(url)}`
            }
          "
          ref="search"
        />
      </div>
    </div>
    <div class="row">
      <div class="col-sm-12 text-center" :key="'book-' + bookTitle">
        <img
          :src="
            bookThumbnail
              ? `${Config.imageProxy}?${bookThumbnail}`
              : `/img/book-thumb-${Math.floor(Math.random() * 10)}.jpg`
          "
          alt="Book cover"
          class="mb-4 shadow book-thumb"
        />
        <Annotate v-if="bookTitle" :showTranslate="true">
          <h6>
            <em>{{ bookTitle }}</em>
          </h6>
          <p>{{ bookAuthor }}</p>
        </Annotate>
        <div class="list-group text-left">
          <Annotate
            tag="a"
            v-for="chapter in chapters"
            :class="{
              'list-group-item': true,
              'link-unstyled': true,
              active:
                location.hash ===
                `#/${$l1.code}/${$l2.code}/book/chapter/${encodeURIComponent(chapter.url)}`
            }"
            :href="`#/${$l1.code}/${$l2.code}/book/chapter/${encodeURIComponent(chapter.url)}`"
          >
            <span>{{ chapter.title }}</span>
          </Annotate>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Config from '@/lib/config'
import Library from '@/lib/library'
import SimpleSearch from '@/components/SimpleSearch'

export default {
  props: {
    method: {
      type: String
    },
    args: {
      type: String
    }
  },
  components: {
    SimpleSearch
  },
  data() {
    return {
      Config,
      bookThumbnail: undefined,
      bookTitle: '',
      bookAuthor: '',
      libraryL2: undefined,
      chapters: [],
      location
    }
  },
  watch: {
    args() {
      this.updateURL()
    }
  },
  methods: {
    async updateURL() {
      this.bookThumbnail = ''
      this.bookTitle = ''
      this.bookAuthor = ''
      this.chapters = []
      let url = decodeURIComponent(this.args)
      this.$refs.search.text = url
      try {
        this.libraryL2 = await (await import(`@/lib/library-l2s/library-${this.$l2['iso639-3']}.js`)).default
        await Library.setLangSources(this.libraryL2.sources)
      } catch (err) {
        console.log(
          `Booklists for ${this.$l2['iso639-3']} is unavailable.`
        )
      }
      let book = await Library.getBook(url)
      if (book) {
        this.bookThumbnail = book.thumbnail
        this.bookTitle = book.title
        this.bookAuthor = book.author
        this.chapters =
          book.chapters && book.chapters.length > 0
            ? book.chapters
            : [
                {
                  title: 'Read',
                  url: encodeURIComponent(this.args)
                }
              ]
      } else {
        location.hash = `#/${this.$l1.code}/${this.$l2.code}/book/chapter/${encodeURIComponent(this.args)}`
      }
    }
  },
  async mounted() {
    this.updateURL()
  }
}
</script>

<style></style>
