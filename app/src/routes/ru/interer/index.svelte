<script>
    import {useSalon} from "$lib/use/content/salon";

    const {Salon} = useSalon
</script>

<div class="bg-black">
    <div aria-hidden="true" class="relative">
        <img src="https://wikicity.kz/fotos/Company_32092_kpPcpRGtM7hTveIN72P1XiJM.png" alt="интерьер" class="w-full h-96 object-center object-cover">
        <div class="absolute inset-0 bg-gradient-to-t from-black"></div>
    </div>

    <div class="relative -mt-12 max-w-7xl mx-auto pb-16 px-4 sm:pb-24 sm:px-6 lg:px-8">
        <div class="max-w-2xl mx-auto text-center lg:max-w-4xl">
            <h2 class="text-3xl font-extrabold tracking-tight text-gray-50 sm:text-4xl">Наш салон</h2>
            <p class="mt-4 text-gray-50">Organize is a system to keep your desk tidy and photo-worthy all day long. Procrastinate your work while you meticulously arrange items into dedicated trays.</p>
        </div>

        <dl class="mt-16 max-w-2xl mx-auto grid grid-cols-1 gap-x-6 gap-y-10 sm:grid-cols-2 sm:gap-y-16 lg:max-w-none lg:grid-cols-3 lg:gap-x-8">

            {#each Salon as {title, description}}
            <div class="border-t border-red-700 pt-4">
                <dt class="font-medium text-gray-200">{title}</dt>
                <dd class="mt-2 text-sm text-gray-50">{description}</dd>
            </div>
            {/each}

        </dl>
    </div>
</div>
