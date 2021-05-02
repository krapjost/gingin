<script lang="ts">
	import Tailwindcss from '../../Tailwindcss.svelte';
</script>

<Tailwindcss/>
<header class="absolute z-50 flex w-full border-b border-opacity-50">
    <div class="max-w-screen-xl w-full mx-auto flex flex-wrap p-5 flex-col md:flex-row items-center">
      <nav class="flex lg:w-2/5 flex-wrap items-center text-base md:ml-auto">
        <a href="/" class="mx-2.5 py-1.5 text-white hover:text-gray-900">풍경원소개</a>
        <a href="/" class="mx-2.5 py-1.5 text-white hover:text-gray-900">제품구입</a>
        <a href="/" class="mx-2.5 py-1.5 text-white hover:text-gray-900">고객문의</a>
        <!-- <a href="/" class="hover:text-gray-900">Fourth Link</a> -->
      </nav>
      <a href="/" class="flex order-first lg:order-none lg:w-1/5 title-font font-medium items-center text-gray-900 lg:items-center lg:justify-center mb-4 md:mb-0">
        <svg xmlns="http://www.w3.org/2000/svg" fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" class="w-12 h-12 text-white p-2 bg-green-500 rounded-full" viewBox="0 0 24 24">
          <path d="M12 2L2 7l10 5 10-5-10-5zM2 17l10 5 10-5M2 12l10 5 10-5"></path>
        </svg>
        <span class="ml-3 text-2xl font-bold text-white">풍경원</span>
      </a>
      <div class="lg:w-2/5 inline-flex lg:justify-end ml-5 lg:ml-0">
        <button class="mx-2.5 py-1.5 text-white hover:text-gray-900">
            로그인
        </button>
        <button class="mx-2.5 py-1.5 text-white hover:text-gray-900">
            회원가입
        </button>
      </div>
    </div>
  </header>