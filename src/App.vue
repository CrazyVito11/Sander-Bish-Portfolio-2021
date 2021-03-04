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
                                    <a class="text-white mx-auto" href="#section-my-skills" title="Bekijk mijn skills"><i class="fas fa-list-ul"></i> Bekijk mijn skills</a>
                                </div>

                                <div class="transition-colors duration-200 ease-in-out w-full sm:w-1/3 md:w-auto bg-indigo-700 hover:bg-indigo-900 p-2 rounded flex cursor-pointer sm:ml-auto md:ml-0">
                                    <a class="text-white mx-auto" href="#section-previous-work" title="Bekijk mijn vorige werk"><i class="fas fa-briefcase"></i> Bekijk mijn vorige werk</a>
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

        <div id="section-previous-work" class="py-12 bg-white">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="lg:text-center">
                    <p class="mt-2 text-3xl leading-8 font-extrabold tracking-tight text-indigo-600 sm:text-4xl">
                        Waar heb ik onder anderen aan gewerkt?
                    </p>
                    <p class="mt-4 max-w-2xl text-xl text-gray-500 lg:mx-auto">
                        Een taal of framework kennen is een ding, maar wat kan ik er nou eigenlijk mee?
                    </p>
                </div>

                <div class="mt-10">
                    <div class="flex flex-wrap">
                        <div v-for="project in projectsList" :key="project.title" class="w-full sm:w-1/2 px-2 py-4">
                            <div class="bg-gray-200 rounded-lg">
                                <div class="p-8">
                                    <img :src="project.imageUrl" :alt="project.imageAlt" class="max-h-80 mx-auto">

                                    <div class="-mt-6 flex">
                                        <div class="ml-auto flex">
                                            <div
                                                    v-for="item in project.madeWith"
                                                    :key="item"
                                                    class="rounded-full flex p-2 mr-2 border-4 border-white"
                                                    :class="frameworkBackgroundColors[item]"
                                            >
                                                <i
                                                        v-if="item === 'VUEJS'"
                                                        class="text-2xl fab fa-vuejs my-auto mx-auto text-white"
                                                ></i>

                                                <i
                                                        v-if="item === 'BOOTSTRAP'"
                                                        class="text-2xl fab fa-bootstrap my-auto mx-auto text-white"
                                                ></i>

                                                <i
                                                        v-if="item === 'LARAVEL'"
                                                        class="text-2xl fab fa-laravel my-auto mx-auto text-white"
                                                ></i>

                                                <svg
                                                        v-if="item === 'ARDUINO'"
                                                        class="h-6 text-white"
                                                        xmlns="http://www.w3.org/2000/svg"
                                                        viewBox="0 0 1000 1000"
                                                >
                                                        <g>
                                                            <path fill="currentColor" d="M185.3,480.1H326v42.5H185.3V480.1L185.3,480.1z"/>
                                                            <path fill="currentColor" d="M764.2,480.1v-50.5h-42.5v50.5h-50.5v42.5h50.5v47.8h42.5v-47.8h50.5v-42.5C801.4,480.1,764.2,480.1,764.2,480.1L764.2,480.1z"/>
                                                            <path fill="currentColor" d="M748.3,267.6c-85,0-175.3,42.5-249.6,148.7C427,310.1,334,267.6,249,267.6c-98.3,0-212.5,55.8-239,201.8v63.7c0,5.3,8,34.5,13.3,50.5C71.1,692.6,169.3,732.4,249,732.4c87.6,0,175.3-45.1,252.3-148.7C575.7,692.6,666,732.4,751,732.4c119.5,0,239-93,239-233.7C990,365.9,878.5,267.6,748.3,267.6L748.3,267.6z M429.6,538.5C368.5,618.2,315.4,650.1,249,650.1c-5.3,0-26.6-2.7-39.8-5.3c-50.5-2.7-116.9-82.3-116.9-114.2v-61.1c18.6-90.3,98.3-119.5,156.7-119.5c31.9,0,29.2-5.3,66.4,10.6c21.2,8,45.1,26.6,69.1,45.1c0,0,69.1,79.7,69.1,93C453.5,506.6,437.6,525.2,429.6,538.5L429.6,538.5z M751,650.1c-63.7,0-111.5-23.9-175.3-100.9c-10.6-15.9-26.6-42.5-26.6-50.5c0-5.3,15.9-31.9,26.6-47.8c53.1-74.4,111.5-100.9,175.3-100.9c85,0,159.3,61.1,159.3,148.7C910.3,591.6,828,650.1,751,650.1L751,650.1z"/>
                                                        </g>
                                                    </svg>

                                                <svg
                                                        v-if="item === 'TAILWINDCSS'"
                                                        class="h-4 text-white my-auto"
                                                        xmlns="http://www.w3.org/2000/svg"
                                                        x="0px"
                                                        y="0px"
                                                        viewBox="0 0 30 21"
                                                        xml:space="preserve"
                                                >
                                                        <path fill-rule="evenodd" clip-rule="evenodd" fill="currentColor" d="M15 0c-4 0-6.5 2-7.5 6 1.5-2 3.25-2.75 5.25-2.25 1.141.285 1.957 1.113 2.86 2.03C17.08 7.271 18.782 9 22.5 9c4 0 6.5-2 7.5-6-1.5 2-3.25 2.75-5.25 2.25-1.141-.285-1.957-1.113-2.86-2.03C20.42 1.728 18.718 0 15 0zM7.5 9C3.5 9 1 11 0 15c1.5-2 3.25-2.75 5.25-2.25 1.141.285 1.957 1.113 2.86 2.03C9.58 16.271 11.282 18 15 18c4 0 6.5-2 7.5-6-1.5 2-3.25 2.75-5.25 2.25-1.141-.285-1.957-1.113-2.86-2.03C12.92 10.729 11.218 9 7.5 9z"></path>
                                                    </svg>

                                                <svg
                                                        v-if="item === 'VBNET'"
                                                        class="h-6 text-white"
                                                        xmlns="http://www.w3.org/2000/svg"
                                                        viewBox="0 0 1000 1000"
                                                >
                                                    <g>
                                                        <g id="_x35_151e0c8492e5103c096af88a51ea5ef">
                                                            <path fill="currentColor" d="M575.4,619c1.6,7.9,2.4,21.8,2.4,41.7v155.4H535V662.3c0-17.5-1.7-30.5-5-39.2c-3.3-8.6-9.2-15.6-17.7-20.7c-8.5-5.2-18.4-7.7-29.9-7.7c-18.3,0-34,5.8-47.3,17.4c-13.3,11.6-19.9,33.6-19.9,65.9v138.1h-42.8V563.3H411v35.9c18.6-27.8,45.4-41.7,80.5-41.7c15.2,0,29.2,2.7,42,8.2c12.8,5.5,22.3,12.7,28.7,21.5C568.5,596.2,572.9,606.7,575.4,619z M990,817.6c-12.1,2.5-22.9,3.8-32.4,3.8c-15.6,0-27.6-2.5-36.2-7.4c-8.6-4.9-14.6-11.4-18.1-19.4c-3.5-8-5.2-24.9-5.2-50.6V591.4h-93c0.2,0.2,0.5,0.4,0.7,0.6c21.4,23,32.1,55.4,32.1,97.1c0,2.5-0.1,6.4-0.2,11.4H649.1c1.6,27.8,9.4,49,23.6,63.8c14.1,14.8,31.7,22.1,52.8,22.1c15.7,0,29.1-4.1,40.2-12.4c11.1-8.3,19.9-21.4,26.4-39.5l44.3,5.5c-7,25.9-19.9,45.9-38.8,60.2c-18.9,14.3-43,21.4-72.4,21.4c-37,0-66.3-11.4-88-34.2c-21.7-22.8-32.5-54.7-32.5-95.8c0-42.5,10.9-75.5,32.8-99c21.9-23.5,50.3-35.2,85.2-35.2c4.2,0,8.4,0.2,12.4,0.5h162.8v-54.8h42.6v54.8h43.1v33.3h-43.1v155c0,12.2,0.8,20.1,2.3,23.6c1.5,3.5,4,6.3,7.4,8.3c3.4,2.1,8.3,3.1,14.6,3.1c4.8,0,11-0.6,18.8-1.7L990,817.6z M792.7,665.4c-1.9-21.3-7.3-37.2-16.2-47.8c-13.6-16.5-31.3-24.8-53.1-24.8c-19.7,0-36.2,6.6-49.6,19.8c-13.4,13.2-20.8,30.8-22.3,52.8L792.7,665.4L792.7,665.4z M620.5,511c-8.5,5.2-21.4,9-38.7,11.4c-22.9,3.2-38.2,4.8-45.7,4.8H360.3V198.5L244.9,527.2H134.5L10,178.2h106.5l74.2,251.1L264,178.2h96.3h7.1H551c31.8,0,56.2,8.3,73.2,25c17,16.7,25.5,37.3,25.5,61.9c0,20.6-6.1,38.3-18.2,53.1c-8.1,9.8-19.9,17.6-35.5,23.3c23.7,6,41.1,16.4,52.3,31.1c11.2,14.7,16.8,33.1,16.8,55.3c0,18.1-4,34.4-11.9,48.8C645.1,491.2,634.3,502.6,620.5,511z M463,315.1h44.3c15.9,0,27-2.9,33.2-8.7c6.2-5.8,9.3-14.2,9.3-25.1c0-10.2-3.1-18.1-9.3-23.8c-6.2-5.7-17.1-8.6-32.5-8.6h-45L463,315.1L463,315.1z M562.9,415.8c0-10.3-3.6-18.6-10.7-24.9c-7.1-6.3-19.6-9.4-37.4-9.4H463v70.7h52c17.5,0,29.9-3.3,37.1-9.9C559.3,435.8,562.9,426.9,562.9,415.8z M311.4,764.6c-7.7,0-14.3,2.8-19.7,8.4c-5.4,5.6-8.1,12.3-8.1,20.2c0,7.7,2.7,14.4,8.1,20.1c5.4,5.6,12,8.5,19.7,8.5c7.9,0,14.7-2.8,20.3-8.5c5.6-5.6,8.3-12.4,8.3-20.1c0-7.8-2.8-14.5-8.3-20.1C326.1,767.4,319.3,764.6,311.4,764.6z"/></g></g>
                                                </svg>
                                            </div>
                                        </div>
                                    </div>

                                    <div class="pt-8">
                                        <h3 class="text-2xl leading-6 font-bold text-center">
                                            {{ project.title }}
                                        </h3>
                                        <h4 class="text-center font-medium">{{ project.year }}</h4>
                                        <p class="mt-2 text-base text-gray-700 text-center">
                                            {{ project.description }}
                                        </p>

                                        <div class="flex mt-4">
                                            <div v-if="project.gitUrl" class="transition-colors duration-200 ease-in-out w-full sm:w-4/5 md:w-auto bg-indigo-700 hover:bg-indigo-900 p-2 rounded flex cursor-pointer mx-auto">
                                                <a class="text-white mx-auto" :href="project.gitUrl" :title="'De code van ' + project.title + ' bekijken op Git'" target="_blank"><i class="fab fa-github"></i> Code bekijken</a>
                                            </div>

                                            <div v-if="!project.gitUrl" class="w-full sm:w-4/5 md:w-auto bg-indigo-300 p-2 rounded flex mx-auto">
                                                <span class="text-white mx-auto"><i class="fab fa-github"></i> Code bekijken</span>
                                            </div>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>

        <footer class="relative">
            <div class="absolute inset-0">
                <img class="h-full w-full object-cover" src="./assets/background.svg" alt="Background image from Freepik.com">
                <div class="absolute inset-0 bg-gray-800" style="mix-blend-mode: multiply;"></div>
            </div>
            <div class="relative max-w-7xl mx-auto py-12 px-4 sm:px-6 md:flex md:items-center md:justify-between lg:px-8">
                <div class="flex justify-center space-x-6 md:order-2">
                    <a href="https://github.com/CrazyVito11" title="Mijn Github account bekijken" target="_blank" class="text-gray-400 hover:text-gray-500 text-2xl">
                        <i class="fab fa-github"></i>
                    </a>
                </div>
                <div class="mt-8 md:mt-0 md:order-1">
                    <p class="text-center md:text-left text-base text-gray-400">
                        © 2021 Sander Bish
                    </p>
                    <p class="text-center md:text-left text-gray-600 text-sm">
                        Gemaakt met <a class="text-gray-500" href="https://vuejs.org/" title="VueJS website" target="_blank">VueJS</a> en <a class="text-gray-500" href="https://tailwindcss.com/" title="TailwindCSS website" target="_blank">TailwindCSS</a>
                    </p>
                </div>
            </div>
        </footer>
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
                frameworkBackgroundColors: {
                    'VUEJS': 'bg-green-400',
                    'TAILWINDCSS': 'bg-indigo-600',
                    'BOOTSTRAP': 'bg-purple-500',
                    'ARDUINO': 'bg-green-600',
                    'VBNET': 'bg-blue-400',
                    'LARAVEL': 'bg-red-600'
                },
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
                ],
                projectsList: [
                    {
                        title: 'Portfolio website',
                        year: '2021',
                        imageUrl: '/img/project_screenshots/portfolio-sander-bish-2021.jpg',
                        imageAlt: 'Screenshot van de portfolio website van mij',
                        gitUrl: 'https://github.com/CrazyVito11/Sander-Bish-Portfolio-2021',
                        description: 'De website waar je nu naar zit te kijken! Dit is mijn bijgewerkte portfolio website die perfect is voor mensen die meer over mij willen weten.',
                        madeWith: [
                            'VUEJS',
                            'TAILWINDCSS'
                        ]
                    },
                    {
                        title: 'ESPLED-RGB',
                        year: '2020-2021',
                        imageUrl: '/img/project_screenshots/espled-rgb.jpg',
                        imageAlt: 'Het logo van ESPLED-RGB op een achtergrond van LED strips',
                        gitUrl: 'https://github.com/CrazyVito11/ESPLED-RGB',
                        description: 'Met een ESP32 microcontroller makkelijk een RGB LED strip kunnen bedienen door middel van een websocket. Het kan ook nog uitgebreid worden met displays en andere optionele functies zoals OTA support.',
                        madeWith: [
                            'ARDUINO'
                        ]
                    },
                    {
                        title: 'ESPLED-RGB Web Controller',
                        year: '2020-2021',
                        imageUrl: '/img/project_screenshots/espled-rgb-web-controller.jpg',
                        imageAlt: 'Het logo van ESPLED-RGB Web Controller op een achtergrond van LED strips',
                        gitUrl: null,
                        description: 'Een website waarmee je een of meerdere ESPLED\'s mee kan bedienen via een website. Dit is nog in een vroege staat van ontwikkeling en staat op het moment nog niet klaar voor groot gebruik, maar is in actieve ontwikkeling.',
                        madeWith: [
                            'VUEJS',
                            'BOOTSTRAP'
                        ]
                    },
                    {
                        title: 'Marktplaats',
                        year: '2020',
                        imageUrl: '/img/project_screenshots/marktplaats-school-project.jpg',
                        imageAlt: 'Screenshot van de homepagina van het Marktplaats school project',
                        gitUrl: null,
                        description: 'Ik heb de basis van Marktplaats nagemaakt in Laravel voor een school project. Je kan een account aanmaken en dan kan je zelf ook producten uploaden. VueJS is voor het grootste gedeelte gebruikt voor de frontend.',
                        madeWith: [
                            'VUEJS',
                            'BOOTSTRAP',
                            'LARAVEL'
                        ]
                    },
                    {
                        title: 'Project NYU',
                        year: '2019',
                        imageUrl: '/img/project_screenshots/project-nyu.jpg',
                        imageAlt: 'Een screenshot van de game in actie',
                        gitUrl: null,
                        description: 'Een space shooter bullet hell game die gemaakt was op in een zelf geschreven engine. Dit project is uiteindelijk gestopt met productie, maar de game had al bijna alle basics erin zitten.',
                        madeWith: [
                            'VBNET'
                        ]
                    },
                    {
                        title: 'ArduOsu',
                        year: '2019',
                        imageUrl: '/img/project_screenshots/arduosu-hardware.jpg',
                        imageAlt: 'Foto van de ArduOsu hardware',
                        gitUrl: 'https://github.com/CrazyVito11/ArduOsu',
                        description: 'Een keypad die speciaal is bedoeld om voor ritme spellen een fijnere controller te geven. Gebouwd op de ATmega32u4 microcontroller met MX Red mechanische schakelaars en per toets achtergrondverlichting.',
                        madeWith: [
                            'ARDUINO'
                        ]
                    }
                ]
            }
        }
    };
</script>
