<template>
  <div class="chinese">
    <div class="widget-title">Learning Chinese?</div>
    <div class="jumbotron-fluid bg-light p-4">
      <div v-if="words">
        <div v-for="word in words">
          <div>
            The Chinese word
            <a
              :href="
                `#/en/zh/view/cedict/${
                  word.traditional
                },${word.pinyin.replace(/ /g, '_')},${word.index}`
              "
              target="_blank"
              class="link-unstyled"
            >
              <b class="bigger" :data-level="word.hsk">{{ word.simplified }}</b>

              [{{ word.traditional }}] <span>({{ word.pinyin }})</span></a
            >
            means <em>{{ word.definitions }}</em
            >.
          </div>
        </div>
      </div>
      <div v-if="words.length === 0">
        We could not find any Chinese words with traditional characters matching
        “{{ text }}.”
      </div>
    </div>
  </div>
</template>

<script>
import Config from '@/lib/config'

export default {
  props: {
    text: {
      type: String
    }
  },
  data() {
    return {
      words: []
    }
  },
  methods: {
    async loadVariants() {
      let variants = await (await this.$unihan).variants(this.text)
      for (let variant of variants) {
        $.getJSON(
          `${Config.wiki}items/hsk_cedict?filter[traditional][eq]=${variant}`,
          response => {
            this.words = this.words.concat(response.data)
          }
        )
      }

    }
  },
  watch: {
    text() {
      if (this.text && this.words.length === 0) {
        this.loadVariants()
      }
    }
  },
  mounted() {
    if (this.text && this.words.length === 0) {
      this.loadVariants()
    }
  }
}
</script>

<style></style>
