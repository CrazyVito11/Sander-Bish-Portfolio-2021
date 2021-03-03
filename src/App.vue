<template>
    <div>
        <header class="flex">
            <div class="w-screen">
                <div class="relative shadow-2xl-thick overflow-hidden">
                    <div class="absolute inset-0">
                        <img class="h-full w-full object-cover" src="./assets/background.svg" alt="Background image from Freepik.com">
                        <div class="absolute inset-0 bg-indigo-100" style="mix-blend-mode: multiply;"></div>
                    </div>
                    <div class="relative max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 flex flex-wrap">
                        <div class="w-full md:w-2/3 py-16 sm:py-24 lg:py-32">
                            <typing-text text-to-type="The world wide web." text-classes="text-4xl font-extrabold tracking-tight sm:text-5xl lg:text-6xl"></typing-text>

                            <p class="mt-6 max-w-lg text-xl sm:max-w-3xl">
                                Websites en webapplicaties zijn steeds belangrijker voor moderne bedrijven.<br/>
                                Een goede website maakt je bedrijf beter zichtbaar en maakt het verschil.
                            </p>

                            <div class="flex flex-wrap mt-4">
                                <div class="transition-colors duration-200 ease-in-out w-full sm:w-1/3 md:w-auto bg-indigo-700 hover:bg-indigo-900 p-2 rounded flex cursor-pointer mb-2 sm:mb-0 md:mr-2">
                                    <a class="text-white mx-auto" href="#section-my-skills"><i class="fas fa-list-ul"></i> Bekijk mijn skills</a>
                                </div>

                                <div class="transition-colors duration-200 ease-in-out w-full sm:w-1/3 md:w-auto bg-indigo-700 hover:bg-indigo-900 p-2 rounded flex cursor-pointer sm:ml-auto md:ml-0">
                                    <a class="text-white mx-auto" href="#"><i class="fas fa-briefcase"></i> Bekijk mijn vorige werk</a>
                                </div>
                            </div>
                        </div>

                        <div class="w-full md:w-1/3 flex">
                            <img alt="Een foto van Sander Bish" src="./assets/Sander_Bish.png" class="w-8/12 sm:w-1/2 md:w-9/12 mx-auto mt-auto" style="margin-bottom: -130px;">
                        </div>
                    </div>
                </div>
            </div>
        </header>

        <div class="py-12 bg-white">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="lg:text-center">
                    <p class="mt-2 text-3xl leading-8 font-extrabold tracking-tight text-indigo-600 sm:text-4xl">
                        Wie ben ik?
                    </p>
                    <p class="mt-4 max-w-2xl text-xl text-gray-500 lg:mx-auto">
                        Is allemaal wel aardig, maar wie ben ik nou eigenlijk?
                    </p>
                </div>

                <div class="mt-10">
                    <dl class="space-y-10 md:space-y-0 md:grid md:grid-cols-2 md:gap-x-8 md:gap-y-10">
                        <div v-for="aboutPoint in aboutMeList" :key="aboutPoint.title" class="flex">
                            <div class="flex-shrink-0">
                                <div class="flex items-center justify-center h-12 w-12 rounded-md bg-indigo-500 text-white">
                                    <i class="text-xl" :class="aboutPoint.fontAwesomeIcon"></i>
                                </div>
                            </div>
                            <div class="ml-4">
                                <dt class="text-lg leading-6 font-medium text-gray-900">
                                    {{ aboutPoint.title }}
                                </dt>
                                <dd class="mt-2 text-base text-gray-500">
                                    {{ aboutPoint.description }}
                                </dd>
                            </div>
                        </div>
                    </dl>
                </div>
            </div>
        </div>

        <div id="section-my-skills" class="py-12">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="lg:text-center">
                    <p class="mt-2 text-3xl leading-8 font-extrabold tracking-tight text-indigo-600 sm:text-4xl">
                        Wat zijn mijn skills?
                    </p>
                    <p class="mt-4 max-w-2xl text-xl text-gray-500 lg:mx-auto">
                        Wat kan ik allemaal? Wat zijn de punten waar ik het sterkste in ben?
                    </p>
                </div>

                <div class="mt-10">
                    <div class="flex flex-wrap">
                        <div v-for="skill in skillsList" :key="skill.title" class="w-full sm:w-1/2 px-2 py-4">
                            <div class="bg-gray-200 rounded-lg">
                                <div class="flex w-full">
                                    <div class="flex items-center justify-center h-12 w-12 -mt-4 mx-auto rounded-md bg-pink-500 text-white">
                                        <i
                                                v-if="skill.fontAwesomeIcon"
                                                class="text-2xl"
                                                :class="skill.fontAwesomeIcon"
                                        ></i>

                                        <svg
                                                v-else-if="skill.SVGData"
                                                class="text-white"
                                                :class="skill.SVGClasses"
                                                fill="currentColor"
                                                v-html="skill.SVGData"
                                        ></svg>
                                    </div>
                                </div>
                                <div class="p-8 pt-2">
                                    <h3 class="text-lg leading-6 font-bold text-center">
                                        {{ skill.title }}
                                    </h3>
                                    <p class="mt-2 text-base text-gray-700 text-center">
                                        {{ skill.description }}
                                    </p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import TypingText from "./components/TypingText";

    export default {
        name: 'App',
        components: {
            TypingText
        },
        data() {
            return {
                aboutMeList: [
                    {
                        title: 'VMBO-T en MBO afgerond',
                        fontAwesomeIcon: 'fas fa-graduation-cap',
                        description: 'Ik heb een VMBO-T en MBO Applicatie en Media ontwikkelaar diploma op zak.'
                    },
                    {
                        title: 'Vriendelijk',
                        fontAwesomeIcon: 'fas fa-thumbs-up',
                        description: 'Een vriendelijk persoon waar je ook gewoon een gesprek mee kan houden en grappen mee kan maken.'
                    },
                    {
                        title: 'Kwaliteit over kwantiteit',
                        fontAwesomeIcon: 'fas fa-check',
                        description: 'Ik voer alles liever in een keer goed uit, dan steeds snelle oplossingen die half werken en later voor problemen kunnen zorgen.'
                    },
                    {
                        title: 'Full stack developer',
                        fontAwesomeIcon: 'fas fa-laptop-code',
                        description: 'Kan niet alleen het gezichtje maken van de website, maar ook de innerlijke werking er van.'
                    },
                    {
                        title: 'Passie voor programmeren',
                        fontAwesomeIcon: 'far fa-heart',
                        description: 'Al vanaf jongs af aan gegrepen door programmeren en ook al lang gehad als hobby'
                    },
                    {
                        title: 'Katten liefhebber',
                        fontAwesomeIcon: 'fas fa-cat',
                        description: 'Wees eens eerlijk, wie houdt er nou niet van katten?'
                    },
                ],
                skillsList: [
                    {
                        title: 'VueJS',
                        fontAwesomeIcon: 'fab fa-vuejs',
                        description: 'Ik kan met gemak nette VueJS components maken en kan ook ingewikkelde Javascript dingen realiseren met VueJS.'
                    },
                    {
                        title: 'Laravel',
                        fontAwesomeIcon: 'fab fa-laravel',
                        description: 'Ik werk het liefste met Laravel als het gaat om backend development, ik kan hier best snel functionaliteit realiseren voor de website of webapplicatie.'
                    },
                    {
                        title: 'TailwindCSS',
                        SVGData: '<path fill-rule="evenodd" clip-rule="evenodd" d="M15 0c-4 0-6.5 2-7.5 6 1.5-2 3.25-2.75 5.25-2.25 1.141.285 1.957 1.113 2.86 2.03C17.08 7.271 18.782 9 22.5 9c4 0 6.5-2 7.5-6-1.5 2-3.25 2.75-5.25 2.25-1.141-.285-1.957-1.113-2.86-2.03C20.42 1.728 18.718 0 15 0zM7.5 9C3.5 9 1 11 0 15c1.5-2 3.25-2.75 5.25-2.25 1.141.285 1.957 1.113 2.86 2.03C9.58 16.271 11.282 18 15 18c4 0 6.5-2 7.5-6-1.5 2-3.25 2.75-5.25 2.25-1.141-.285-1.957-1.113-2.86-2.03C12.92 10.729 11.218 9 7.5 9z"></path>',
                        SVGClasses: 'h-6 w-8 my-auto',
                        description: 'Ik ben pas recent overgestapt naar TailwindCSS, en ik kan er nu al fantastisch mee werken. Het gaat sneller en is netter dan Bootstrap.'
                    },
                    {
                        title: 'Bootstrap',
                        fontAwesomeIcon: 'fab fa-bootstrap',
                        description: 'Ik kan met Bootstrap snel designs realiseren die ook gelijk goed responsive zijn op verschillende apparaten.'
                    },
                    {
                        title: 'HTML',
                        fontAwesomeIcon: 'fab fa-html5',
                        description: 'Lijkt me natuurlijk vanzelfsprekend dat ik zonder problemen hele webpagina\'s in elkaar kan zetten die ook responsive is.'
                    },
                    {
                        title: 'CSS',
                        fontAwesomeIcon: 'fab fa-css3-alt',
                        description: 'Meestal is TailwindCSS al genoeg, soms kan het toch gebeuren dat je CSS moet maken op maat, en ook dat kan ik netjes doen door de BEM methode.'
                    },
                ]
            }
        }
    };
</script>
