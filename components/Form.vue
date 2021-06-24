<template>
  <div class="container">
    <div class="w-full max-w-md">
      <form class="bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4">
        <div class="mb-4">
          <label
            class="block text-gray-700 text-sm font-bold mb-2"
            for="youtube_url"
          >
            YoutubeのURL
          </label>
          <input
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
            id="youtube_url"
            type="text"
            placeholder="https://www.youtube.com/hoge"
          />
        </div>
        <div class="mb-6">
          <label
            class="block text-gray-700 text-sm font-bold mb-2"
            for="picture_url"
          >
            写真のURL
          </label>
          <input
            class="
              shadow
              appearance-none
              border
              rounded
              w-full
              py-2
              px-3
              text-gray-700
              mb-3
              leading-tight
              focus:outline-none
              focus:shadow-outline
            "
            id="picture_url"
            type="picture_url"
            placeholder="https:picture.com"
          />
        </div>
        <div class="mb-6">
          <UploadInput />
        </div>
        <div class="flex items-center justify-between">
          <button
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
            送信
          </button>
          <a
            class="
              inline-block
              align-baseline
              font-bold
              text-sm text-blue-500
              hover:text-blue-800
            "
            href="#"
          >
            福島ゼミ生に問い合わせる
          </a>
        </div>
      </form>
      <p class="text-center text-gray-500 text-xs">
        &copy;2021 Sohei Hashimoto. All rights reserved.
      </p>
    </div>
  </div>
</template>

<style>
.NuxtLogo {
  animation: 1s appear;
  margin: auto;
}

@keyframes appear {
  0% {
    opacity: 0;
  }
}
</style>
