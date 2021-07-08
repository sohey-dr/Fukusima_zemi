<template>
  <div class="container mx-auto my-60 w-full max-w-xs">
    <form class="bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4">
      <div class="mb-4">
        <label
          class="block text-gray-700 text-sm font-bold mb-2"
          for="username"
        >
          調査対象の母集団の数
        </label>
        <input
          v-model="populationNumber"
          class="
            shadow
            appearance-none
            border
            rounded
            w-full
            py-2
            px-3
            text-gray-700
            leading-tight
            focus:outline-none
            focus:shadow-outline
          "
          id="username"
          type="text"
          placeholder="数を入力"
        />
      </div>
      <div class="w-28 mx-auto flex items-center justify-between">
        <button
          @click="calculation({ populationNumber })"
          class="
            bg-blue-500
            hover:bg-blue-700
            text-white
            font-bold
            py-2
            px-4
            rounded
            focus:outline-none
            focus:shadow-outline
          "
          type="button"
        >
          計算する
        </button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  data: {
    populationNumber: null,
  },
  methods: {
    calculation({ populationNumber }) {
      var f_child = 0.05 / 1.96
      var s_child = (populationNumber - 1) / 0.25

      var children = f_child * f_child * s_child + 1
      var answer = populationNumber / children

      window.alert(Math.round(answer) + '人(個)程度必要です')
    },
  },
}
</script>
