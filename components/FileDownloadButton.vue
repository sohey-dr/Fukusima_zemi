<template>
  <div class="my-page mx-auto text-center my-12">
    <button
      class="
        bg-green-500
        hover:bg-green-400
        text-white
        font-bold
        py-2
        px-4
        border-b-4 border-green-700
        hover:border-green-500
        rounded
      "
      v-on:click="downloadFile()"
    >
      コードをダウンロードする
    </button>
  </div>
</template>

<script>
export default {
  props: {
    programs: {
      type: Array,
      required: true,
    },
  },
  methods: {
    async downloadFile() {
      // TODO: エンドポイントのURLを修正する
      await this.$axios
        .$post('http://localhost:8080/', {
          responseType: 'blob',
          programs: this.programs.map(program => program["name"]),
        })
        .then((response) => {
          console.log(response)
          const blob = new Blob([response], { type: response.type })
          const link = document.createElement('a')
          link.href = URL.createObjectURL(blob)
          link.download = 'sphero.ts'
          link.click()
          URL.revokeObjectURL(link.href)
        })
        .catch(console.error)
    },
  },
}
</script>
