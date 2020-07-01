<template>
    <div
        class="bg-gray-300 text-gray-800 antialiased min-h-screen flex flex-col justify-end"
    >
        <div
            v-on-clickaway="hideMenu"
            class="bg-gray-400 px-8 py-8 flex justify-center"
        >
            <ul class="absolute -mt-32 space-y-2" style="bottom: 124px">
                <transition v-for="email in emails" :key="email.id" name="fade">
                    <li
                        v-show="visible"
                        class="transform"
                        :class="email.classes"
                    >
                        <a
                            href="#"
                            class="bg-white hover:bg-gray-100 w-80 shadow-md border rounded-lg px-4 py-4 flex items-center"
                        >
                            <img
                                :src="email.image"
                                alt="avatar"
                                class="rounded-full w-10 h-10"
                            />
                            <div class="ml-4">
                                <div class="font-semibold">
                                    {{ email.subject }}
                                </div>
                                <div class="text-left text-gray-700">
                                    {{ email.sender }}
                                </div>
                            </div>
                        </a>
                    </li>
                </transition>
            </ul>
            <button
                @click="visible = !visible"
                class="bg-white hover:bg-gray-100 w-80 shadow-md border rounded-lg px-4 py-4 flex items-center -mt-16 focus:outline-none"
            >
                <img
                    src="https://s3.amazonaws.com/uifaces/faces/twitter/chanpory/128.jpg"
                    alt="avatar"
                    class="rounded-full w-10 h-10"
                />
                <div class="ml-4">
                    <div class="font-semibold">New Invite</div>
                    <div class="text-left text-gray-700">Tyrone Mckenzie</div>
                </div>
            </button>
        </div>
    </div>
</template>

<script>
import { mixin as clickaway } from 'vue-clickaway';

export default {
    mixins: [clickaway],
    name: 'App',
    data() {
        return {
            visible: true,
            emails: [
                {
                    id: 1,
                    subject: "Tonight's Run",
                    sender: 'Kendrick Slater',
                    image:
                        'https://s3.amazonaws.com/uifaces/faces/twitter/alterchuca/128.jpg',
                    classes: 'translate-x-16 rotate-12',
                },
                {
                    id: 2,
                    subject: '1 New Email',
                    sender: 'Jaidon Vang',
                    image:
                        'https://s3.amazonaws.com/uifaces/faces/twitter/tanveerrao/128.jpg',
                    classes: 'translate-x-10 rotate-10',
                },
                {
                    id: 3,
                    subject: 'Most Recent Tweets',
                    sender: 'Darien Quintana',
                    image:
                        'https://s3.amazonaws.com/uifaces/faces/twitter/ifarafonow/128.jpg',
                    classes: 'translate-x-6 rotate-8',
                },
                {
                    id: 4,
                    subject: 'Latest News',
                    sender: 'Aislinn Whitmore',
                    image:
                        'https://s3.amazonaws.com/uifaces/faces/twitter/allagringaus/128.jpg',
                    classes: 'translate-x-4 rotate-6',
                },
                {
                    id: 5,
                    subject: '30% discount on all Vue courses!',
                    sender: 'Leland Glover',
                    image:
                        'https://s3.amazonaws.com/uifaces/faces/twitter/lowie/128.jpg',
                    classes: 'translate-x-2 rotate-4',
                },
                {
                    id: 6,
                    subject: 'Upcoming Thailand Trip',
                    sender: 'Sacha Medrano',
                    image:
                        'https://s3.amazonaws.com/uifaces/faces/twitter/emileboudeling/128.jpg',
                    classes: 'translate-x-1 rotate-2',
                },
            ],
        };
    },
    methods: {
        hideMenu() {
            this.visible = false;
        },
    },
};
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}

.fade-enter-active,
.fade-leave-active {
    transition: all 0.15s ease-in;
}
.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
    transform: translate(0px, 100px) rotate(0deg) !important;
    opacity: 0;
}
</style>
