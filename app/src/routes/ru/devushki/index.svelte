<script>
    import {useGirls} from "$lib/use/content/girls";

    const {girls} = useGirls
</script>

<div class="bg-black">

    <div class="pt-12 sm:pt-16 lg:pt-24">
        <div class="max-w-7xl mx-auto text-center px-4 sm:px-6 lg:px-8">
            <div class="max-w-3xl mx-auto space-y-2 lg:max-w-none">
                <!--                <h2 class="text-lg leading-6 font-semibold text-gray-300 uppercase tracking-wider">Цены на наши программы</h2>-->
                <h2 class="text-3xl font-extrabold text-white sm:text-4xl lg:text-5xl">Наши мастерицы</h2>
                <p class="text-xl text-gray-300">Массажистки подарят вам незабываемые минуты расслабления и отдыха</p>
            </div>
        </div>
    </div>

    <div class="mx-auto py-12 px-4 max-w-7xl sm:px-6 lg:px-8 lg:py-24">
        <div class="space-y-12">
            <ul role="list" class="space-y-4 sm:grid sm:grid-cols-2 sm:gap-6 sm:space-y-0 lg:grid-cols-3 lg:gap-8">
                {#each girls as {id, name, old, growth, size, message, img}}
                <li class="py-10 px-6 bg-red-900 text-center rounded-lg xl:px-10 xl:text-left">
                    <div class="space-y-6 xl:space-y-10">
                        <img class="mx-auto h-40 w-40 rounded-full xl:w-56 xl:h-56 object-contain" src="/girls/{img}" alt="{name}">
                        <div class="space-y-2 xl:flex xl:items-center xl:justify-between">
                            <div class="font-medium text-base leading-6 space-y-1 text-gray-50">
                                <h3 class="text-4xl">{name}</h3>
                                <div class="pt-4">
                                    <p>Возраст: {old}</p>
                                    <p>Рост: {growth} см</p>
                                    <p>Размер груди: {size}</p>
                                </div>
                            </div>
                        </div>
                    </div>
                </li>
                {/each}
            </ul>
        </div>
    </div>
</div>

