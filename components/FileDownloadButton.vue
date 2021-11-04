<template>
  <div class="my-page">
    <button v-on:click="downloadFile()">ダウンロードする</button>
  </div>
</template>

<script>
export default {
  methods: {
    async downloadFile() {
      // TODO: エンドポイントのURLを修正する
      await this.$axios.$post("http://localhost:8080/", { responseType: 'blob' })
        .then(response => {
          console.log(response);
          const blob = new Blob([response], { type: response.type })
          const link = document.createElement('a')
          link.href = URL.createObjectURL(blob)
          link.download = "sphero.ts";
          link.click()
          URL.revokeObjectURL(link.href)
        }).catch(console.error)
    }
  },
}
</script>
