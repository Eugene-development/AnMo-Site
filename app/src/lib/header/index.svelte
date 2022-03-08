<script>

    import {mobileMenu} from '../../stores.js';
    import {useHeader} from "$lib/use/content/header/index.js";
    import {useVisible} from "$lib/use/visible";
    import MobileMenu from "./mobile/index.svelte"

    const {invert} = useVisible;

    const changeVisibleMobileMenu = () => mobileMenu.update(invert);
    let visibleMobileMenu;
    mobileMenu.subscribe(value => visibleMobileMenu = value);

    const {menu, phone} = useHeader;
    let current;

</script>

<header>
    <div class="relative">
        <div class="bg-black p-4">
            <nav class="relative max-w-full mx-8 flex items-center justify-between px-1 sm:px-2" aria-label="Global">
                <div class="flex items-center flex-1">
                    <div class="flex items-center justify-between w-full md:w-auto">
                        <a href="/">
                            <span class="sr-only">Workflow</span>
                            <img class="h-6 w-auto sm:h-10"
                                 src="/Logo/logo1.svg" alt="">
                        </a>
                        <div class="-mr-2 flex items-center md:hidden">

                            <button on:click={changeVisibleMobileMenu} type="button"
                                    class="bg-gray-900 rounded-md p-2 inline-flex items-center justify-center text-gray-300 hover:bg-gray-800 focus:outline-none focus:ring-2 focus-ring-inset focus:ring-white"
                                    aria-expanded="false"><span class="mx-2">Меню</span>
                                <span class="sr-only">Open main menu</span>
                                <!-- Heroicon name: outline/menu -->
                                <svg class="h-6 w-6" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24"
                                     stroke="currentColor" aria-hidden="true">
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                                          d="M4 6h16M4 12h16M4 18h16"/>
                                </svg>
                            </button>
                        </div>
                    </div>
                    <nav class="hidden space-x-8 md:flex md:mx-6 ">
                        {#each menu as { value, link }, i}
                            <a class="text-base font-medium hover:text-gray-300 p-2 text-red-700"
                               href="/{link}">{value}
                            </a>
                            <!--                            <a class="text-sm font-medium hover:text-gray-300 p-2 {'/'+link === window.location.pathname ? 'text-red-500' : 'text-cyan-600'}"-->
                            <!--                               href="/{link}">{value}-->
                            <!--                            </a>-->
                            <!--                            <a class="text-sm font-medium text-white hover:text-gray-300 p-2"-->
                            <!--                               class:text-xl="{current === '/'+link}" on:click="{() => current = window.location.pathname}"-->
                            <!--                               href="/{link}">{value}-->
                            <!--                            </a>-->
                        {:else}
                            <p>Нет данных!</p>
                        {/each}
                    </nav>

                </div>
                <div class="hidden lg:flex md:items-center md:space-x-4 text-white">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-7 w-7" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                        <path stroke-linecap="round" stroke-linejoin="round" d="M21 3l-6 6m0 0V4m0 5h5M5 3a2 2 0 00-2 2v1c0 8.284 6.716 15 15 15h1a2 2 0 002-2v-3.28a1 1 0 00-.684-.948l-4.493-1.498a1 1 0 00-1.21.502l-1.13 2.257a11.042 11.042 0 01-5.516-5.517l2.257-1.128a1 1 0 00.502-1.21L9.228 3.683A1 1 0 008.279 3H5z" />
                    </svg>
                    <p class="text-xl font-medium  hover:text-gray-300 lg:text-2xl">
                        {phone}
                    </p>
                </div>
            </nav>
        </div>

        <MobileMenu/>
    </div>

</header>

