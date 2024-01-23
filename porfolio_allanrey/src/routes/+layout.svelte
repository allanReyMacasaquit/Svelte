<script>
  import "../app.css"
	import Footer from "../components/Footer.svelte"
	import Header from "../components/Header.svelte"

  let y
  let innerHeight = 0
  let innerWidth = 0

  function topView() {
    document.body.scrollIntoView()
  }

</script>
<div class="relative flex flex-col max-w-[1400px] mx-auto w-full text-sm sm:text-base min-h-screen">
  <div class={"fix bottom-0 w-full duration-200 flex p-5 z-[10]" + ( y > 0 ? 'opacity-100 pointer-events-auto': 'pointer-events-none opacity-0')}>
    <button on:click={topView} class="ml-auto rounded-full bg-slate-600 text-violet-400 px-3 sm:px-4 hover:bg-slate-600 cursor-pointer aspect-square grid place-items-center">
      <i class="fa-solid fa-arrow-up"></i>
    </button>
  </div>

  <Header y = {y}/>
  <slot />
  <Footer/>
</div>

<svelte:window bind:scrollY={y} bind:innerHeight bind:innerWidth/>