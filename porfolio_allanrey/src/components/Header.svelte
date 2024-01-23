<script>
    export let y = 0

    export let tabs = [
        { name: "Projects ", link: "#projects" },
        { name: "About me", link: "#about" },
      
    ];
</script>

<header
    class={"sticky z-[10] top-0 duration-200 px-6 flex items-center justify-between border-b border-solid " +
        (y > 0
            ? " py-4 bg-slate-950 border-violet-950"
            : " py-6 bg-transparent border-transparent")}
>
    <h1 class="font-medium uppercase">
        <b class="font-bold montserrat">Allan rey</b> <span class="text-blue-600 font-bold">Macasaquit</span>
    </h1>
    <div class="sm:flex items-center gap-4 hidden">
        {#each tabs as tab, index}
            <a
                href={tab.link}
                class="duration-200 hover:text-slate-400"
                target={index === 2 ? "_blank" : ""}
            >
                <p>{tab.name}</p>
            </a>
        {/each}
        
        <button
            class="blueShadow relative overflow-hidden px-5 py-2 group rounded-full bg-white hover:text-white text-slate-950"
        >
            <div
                class="absolute top-0 right-full w-full h-full bg-blue-600 group-hover:translate-x-full z-0 duration-200"
            />
            <h4 class="relative z-9 ">Get in touch</h4>
        </button>
    </div>
</header>