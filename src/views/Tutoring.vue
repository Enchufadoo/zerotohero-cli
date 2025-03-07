<template>
  <div class="main pt-5 pb-5">
    <div class="container">
      <div class="row">
        <div class="col-sm-12">
          <h1 class="mb-5">Online Tutoring Lesson Kit</h1>
          <div>
            <p>
              <b>About this kit:</b>When you are having a lesson with either a free language exchange partner or a paid tutor through services such as
              <a
                href="https://www.tandem.net/"
              >Tandem</a>,
              <a href="https://amikumu.com/">Amikumu</a>,
              <a href="https://www.italki.com/">iTalki</a>,
              <a href="https://www.hellotalk.com/">HelloTalk</a> or
              <a href="https://preply.com/">Preply</a>, you can make use of this lesson kit to give structure and content to your lesson.
            </p>
            <p>
              The kit is based around the Cambridge
              <em>Touchstone</em> and
              <em>Viewpoint</em> series of American English textbooks.
            </p>
          </div>
        </div>
      </div>
    </div>
    <div class="container-fluid">
      <div class="row">
        <div class="col-sm-12">
          <div class="tabs text-center">
            <a :href="`#/${$l1.code}/${$l2.code}/tutoring/`" class="link-unstyled tab bg-dark">All</a>
            <template v-if="$l2.code === 'zh'">
              <a
                v-for="n in 7"
                :href="`#/${$l1.code}/${$l2.code}/tutoring/${n}`"
                class="tab link-unstyled"
                :data-bg-level="n < 7 ? n : 'outside' "
              >{{ Helper.level(n, $l2) }}</a>
            </template>
            <template v-else>
              <a
                v-for="n in 7"
                :href="`#/${$l1.code}/${$l2.code}/tutoring/${n}`"
                class="tab link-unstyled"
                :data-bg-level="Helper.level(n).replace('-', '')"
              >{{ Helper.level(n, $l2) }}</a>
            </template>
            <div v-if="$l2.code === 'zh'"
              style="height: 0.5rem"
              :class="level ? `bg-level${level}` : `bg-dark`"></div>
            <div
              v-else
              style="height: 0.5rem"
              :class="level ? `bg-level${Helper.level(level).replace('-', '')}` : `bg-dark`"
            ></div>
          </div>
          <table v-if="lessons && lessons.length > 0" class="table table-responsive lessons-table">
            <thead>
              <tr>
                <th class="text-center">ID</th>
                <th>Topic</th>
                <th>Read Together</th>
                <th>Free Talk</th>
                <th>Writing</th>
              </tr>
            </thead>
            <tbody>
              <tr
                v-for="row in lessons"
                :class="{
                  'lessons-table-row': true,
                  hidden: !(level === undefined || row.level === level)
                }"
                @click="goto(row.id)"
              >
                <td class="text-center">{{ row.id }}</td>
                <td>{{ row.name }}</td>
                <td v-html="row.reading || ''"></td>
                <td v-html="row.free_talk || '' + '<p>• Describe a picture</p>'"></td>
                <td v-html="row.writing || ''"></td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Helper from '@/lib/helper'
import Config from '@/lib/config'

export default {
  props: ['level'],
  data() {
    return {
      Helper,
      lessons: undefined
    }
  },
  async created() {
    let response = await $.getJSON(
      `${Config.wiki}items/tutoring_kit?fields=id,name,reading,free_talk,writing,level`
    )
    this.lessons = response.data || []
  },
  methods: {
    goto(id) {
      location.hash = `/${this.$l1.code}/${this.$l2.code}/tutoring/lesson/${id}`
    }
  }
}
</script>

<style>
.lessons-table-row {
  cursor: pointer;
}
.lessons-table-row:hover {
  background-color: #eee;
}
</style>