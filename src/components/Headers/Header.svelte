<script lang="ts">
	import Tailwindcss from '../../Tailwindcss.svelte';
  export let duration = "300ms";

  let headerClass = "show";
  let y = 0;
  let lastY = 0;

  function deriveClass(y, dy) {
    if (y > 50) {
      return "hide";
    }
    return "show";
  }

  function updateClass(y) {
    const dy = lastY - y;
    lastY = y;
    return deriveClass(y, dy);
  }

  function setTransitionDuration(node) {
    node.style.transitionDuration = duration;
  }

  $: headerClass = updateClass(y);

</script>
<style>
  header {
    transition: all 300ms linear;
  }
  .show {
    /* transform: translateY(0%); */
    
    background-color: transparent;
  }
  .hide {
    background-color: #3e7f00;
    border: none

    /* transform: translateY(-100%); */
  }
</style>
<Tailwindcss/>
<header use:setTransitionDuration class={`fixed flex w-full border-b border-opacity-50 z-50 ${headerClass}`}>
    <div class="max-w-screen-xl w-full mx-auto flex flex-wrap p-5 flex-col md:flex-row items-center justify-between">
      <nav class="flex lg:w-2/5 flex-wrap items-center text-sm pt-2">
        <a href="/" class="mx-2.5 py-1.5 text-white hover:text-gray-900">풍경원소개</a>
        <a href="/" class="mx-2.5 py-1.5 text-white hover:text-gray-900">제품구입</a>
        <a href="/" class="mx-2.5 py-1.5 text-white hover:text-gray-900">고객문의</a>
        <!-- <a href="/" class="hover:text-gray-900">Fourth Link</a> -->
      </nav>
      <a href="/" class="flex order-first lg:order-none lg:w-28 w-24 title-font font-medium items-center justify-items-center  text-gray-900 lg:items-center lg:justify-center mb-4 md:mb-0">
        <img src="assets/images/logo/logo_with_text.png" alt="logo"/>
      </a>
      <div class="lg:w-2/5 inline-flex lg:justify-end ml-5  text-sm pt-2">
        <button class="mx-2.5 py-1.5 text-white hover:text-gray-900">
            로그인
        </button>
        <button class="mx-2.5 py-1.5 text-white hover:text-gray-900">
            회원가입
        </button>
      </div>
    </div>
  </header>

  <svelte:window bind:scrollY={y} />