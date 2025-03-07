<template>
  <div>
    <div class="text-center">
      <Loader class="mb-5" />
    </div>
    <div
      class="d-flex"
      style="margin: 0 auto 3rem auto"
      v-if="grammar && grammar.length > 0"
      v-cloak
    >
      <div class="input-group" style="flex: 1">
        <input
          v-model="search"
          type="text"
          class="form-control lookup"
          placeholder="Filter by keywords"
        />
        <div class="input-group-append">
          <button class="btn btn-danger lookup-button" type="button">
            <i class="glyphicon glyphicon-filter"></i> Filter
          </button>
        </div>
      </div>
      <a
        href="/data/grammar.csv.txt"
        class="ml-2 btn btn-primary"
        download="Chinese Zero to Hero Grammar Chart.csv"
        ><i class="fa fa-download mr-1" />Download CSV</a
      >
    </div>
    <div class="tabs text-center">
      <button @click="level = undefined" class="tab text-light bg-dark">
        All 🤦
      </button>
      <button
        v-for="n in 6"
        class="tab text-dark"
        :data-bg-level="n"
        @click="level = n"
      >
        HSK {{ n }}
      </button>
      <div
        style="height: 0.5rem"
        :class="level ? `bg-hsk${level}` : `bg-dark`"
      ></div>
    </div>
    <table
      v-if="grammar && grammar.length > 0"
      class="table table-responsive grammar-table"
    >
      <thead>
        <tr>
          <th class="text-center">Lesson</th>
          <th>Structure</th>
          <th>English</th>
          <th>Example</th>
          <th>Example Translation</th>
        </tr>
      </thead>
      <tbody>
        <tr
          v-for="row in grammar"
          :class="{
            'grammar-table-row': true,
            hidden: !(
              (!search ||
                row.structure.includes(search) ||
                row.english.includes(search)) &&
              (level === undefined ||
                row.book === level)
            )
          }"
          @click="grammarRowClick(row)"
        >
          <td class="text-center align-middle">
            <span
              ><a
                :href="`${row.url}`"
                class="btn btn-secondary"
                style="white-space: nowrap;"
                ><i class="glyphicon glyphicon-facetime-video"></i>
                {{ row.code }}</a
              >
            </span>
          </td>
          <td class="align-middle">
            <Annotate
              v-html="
                Helper.highlightMultiple(row.structure, row.words, row.book)
              "
              :showTranslate="true"
            ></Annotate>
          </td>
          <td class="align-middle">
            <span>{{ row.english }}</span>
          </td>
          <td class="align-middle">
            <Annotate
              v-html="
                Helper.highlightMultiple(row.example, row.words, row.book)
              "
              :showTranslate="true"
            ></Annotate>
          </td>
          <td class="align-middle">
            <span>{{ row.exampleTranslation }}</span>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
import Helper from '@/lib/helper'
export default {
  data() {
    return {
      Helper,
      search: '',
      level: undefined,
      grammar: []
    }
  },
  methods: {
    grammarRowClick(row) {
      location.hash = `#/${this.$l1.code}/${this.$l2.code}/grammar/view/${row.id}`
    }
  },
  async mounted() {
    this.$grammar.then(grammar => {
      this.grammar = grammar._grammarData
    })
  }
}
</script>

<style lang="scss">
.grammar-table {
  color: #666;

  .grammar-table-row:hover {
    background-color: #f1f1f1;
    cursor: pointer;
  }
}

.grammar-table [data-level] {
  font-weight: bold;
}
</style>
