<template>
    <div>
        <header class="flex ">
            <div class="w-screen">
                <div class="relative shadow-2xl-thick sm:overflow-hidden rounded-md">
                    <div class="absolute inset-0">
                        <img class="h-full w-full object-cover" src="https://i.pinimg.com/originals/45/cf/a8/45cfa8e8fef45c356253cf9938a4cc9c.jpg" alt="">
                        <div class="absolute inset-0 bg-indigo-100" style="mix-blend-mode: multiply;"></div>
                    </div>
                    <div class="relative px-4 py-16 sm:px-6 sm:py-24 lg:py-32 lg:px-8">
                        <h1 class="text-4xl font-extrabold tracking-tight sm:text-5xl lg:text-6xl">
                            The world wide web.
                        </h1>
                        <p class="mt-6 max-w-lg text-xl sm:max-w-3xl">
                            Websites en webapplicaties zijn belangrijke dingen voor moderne bedrijven.<br/>
                            Een goede website kan je bedrijf beter zichtbaar maken
                        </p>
                    </div>
                </div>
            </div>
        </header>
    </div>
</template>

<script>
    //import HelloWorld from './components/HelloWorld.vue';

    export default {
        name: 'App',
        components: {
            //HelloWorld
        }
    };
</script>
