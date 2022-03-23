<script>
    import {usePrograms} from "$lib/use/content/programs";

    const {Programs, Additions} = usePrograms
</script>

<div class="bg-black">


    <div class="pt-12 sm:pt-16 lg:pt-24">
        <div class="max-w-7xl mx-auto text-center px-4 sm:px-6 lg:px-8">
            <div class="max-w-3xl mx-auto space-y-2 lg:max-w-none">
                <!--                <h2 class="text-lg leading-6 font-semibold text-gray-300 uppercase tracking-wider">Цены на наши программы</h2>-->
                <h2 class="text-3xl font-extrabold text-white sm:text-4xl lg:text-5xl">Цены на наши программы</h2>
                <p class="text-xl text-gray-300">Цены на наши программы Цены на наши программы Цены на наши программы
                    Цены на наши программы</p>
            </div>
        </div>
    </div>


    <div class="mt-8 pb-12 bg-black sm:mt-12 sm:pb-16 lg:mt-16 lg:pb-24">

        <div class="relative">
            <div class="absolute inset-0 h-3/4 bg-black"></div>
            <div class="relative z-10 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="max-w-md mx-auto space-y-4 lg:max-w-5xl lg:grid lg:grid-cols-2 lg:gap-5 lg:space-y-0">

                    {#each Programs as {title, description, price, time, services}}
                        <div class="flex flex-col rounded-lg shadow-lg overflow-hidden">
                            <div class="px-6 py-8 bg-white sm:p-10 sm:pb-6">
                                <div>
                                    <h3 class="inline-flex px-4 py-1 rounded-full text-xl font-semibold tracking-wide uppercase bg-red-200 text-red-700"
                                        id="tier-standard"> {title} </h3>
                                </div>
                                <div class="mt-4 flex items-baseline text-6xl font-extrabold">{price}
                                    <span class="ml-1 text-2xl font-medium text-gray-500"> ₽ </span>
                                </div>
                                <p class="mt-5 text-lg text-gray-500"> {description} </p>
                            </div>
                            <div class="flex-1 flex flex-col justify-between px-6 pt-6 pb-8 bg-gray-50 space-y-6 sm:p-10 sm:pt-6">
                                <ul role="list" class="space-y-4">
                                    {#each services as {description}}
                                        <li class="flex items-start">
                                        <div class="flex-shrink-0">
                                            <!-- Heroicon name: outline/check -->
                                            <svg class="h-6 w-6 text-green-500" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke="currentColor" aria-hidden="true">
                                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
                                            </svg>
                                        </div>
                                        <p class="ml-3 text-base text-gray-700"> {description} </p>
                                    </li>
                                    {/each}
                                </ul>
                                <div class="rounded-md shadow">
                                    <span class="flex items-center justify-center px-5 py-3 border border-transparent text-base font-medium rounded-md text-white bg-red-900 hover:bg-gray-900" aria-describedby="tier-standard"> Дополнения </span>
                                </div>
                            </div>
                        </div>
                    {/each}
                </div>
            </div>
        </div>
        <div class="mt-4 relative max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 lg:mt-5">
            <div class="max-w-md mx-auto lg:max-w-5xl">
                <div class="rounded-lg bg-gray-100 px-6 py-8 sm:p-10 lg:flex lg:items-center">
                        <div class="flex-1">
                            <div>
                                <h3 class="inline-flex px-4 py-1 rounded-full text-sm font-semibold tracking-wide uppercase bg-black text-red-500">
                                    Важно</h3>
                            </div>
                            <div class="mt-4 text-lg text-gray-600">Салон не оказывает интимные услуги! При попытке
                                нарушения данного правила программа останавливается без возврата оплаченного сеанса.
                                Надеемся на понимание.
                            </div>
                        </div>
                </div>
            </div>
        </div>
    </div>
</div>


