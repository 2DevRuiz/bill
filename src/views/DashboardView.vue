<template>
  <div
      class="min-h-screen flex flex-col flex-auto flex-shrink-0 antialiased bg-white dark:bg-gray-700 text-black dark:text-white">
    <!--start:header-->
    <div class="fixed w-full flex items-center justify-between text-white z-10">
      <header
          class="w-full flex items-center justify-between px-6 py-4 bg-white border-b-2 border-gray-100 z-20 shadow-lg">
        <div class="flex items-center">
          <!-- start: button bars -->
          <button type="button" @click="isOpen = !isOpen"
                  class="text-gray-500 focus:outline-none ms-1 text-base flex items-center hover:text-green-600 p-2 place-content-center ">
            <svg xmlns="http://www.w3.org/2000/svg" class="w-7 h-7 " viewBox="0 0 24 24" fill="currentColor">
              <path
                  d="M21.376 4.504H7.688a0.184 0.184 0 0 0 -0.184 0.184V6c0 0.104 0.088 0.184 0.184 0.184h13.688A0.184 0.184 0 0 0 21.56 6V4.688a0.184 0.184 0 0 0 -0.184 -0.184m0 6.656H7.688a0.184 0.184 0 0 0 -0.184 0.184v1.312c0 0.104 0.088 0.184 0.184 0.184h13.688a0.184 0.184 0 0 0 0.184 -0.184v-1.312a0.184 0.184 0 0 0 -0.184 -0.184m0 6.656H7.688a0.184 0.184 0 0 0 -0.184 0.184v1.312c0 0.104 0.088 0.184 0.184 0.184h13.688a0.184 0.184 0 0 0 0.184 -0.184V18a0.184 0.184 0 0 0 -0.184 -0.184M2.44 5.344a1.312 1.312 0 1 0 2.624 0 1.312 1.312 0 1 0 -2.624 0m0 6.656a1.312 1.312 0 1 0 2.624 0 1.312 1.312 0 1 0 -2.624 0m0 6.656a1.312 1.312 0 1 0 2.624 0 1.312 1.312 0 1 0 -2.624 0"/>
            </svg>

          </button>
          <!-- end: button bars -->
          <!--start: logo -->
          <div class="flex justify-center items-center w-56 py-1 ">
            <a href="#" class="flex items-center ">
              <img src="https://placehold.co/40x40" alt="" class="w-10 h-10 rounded object-cover">
              <span class="text-xl place-content-center font-bold text-black ml-3 hidden md:block">Sonata Billing</span>
            </a>
          </div>
          <!-- end: logo -->

        </div>
        <!-- start: right side -->
        <div class="flex items-center justify-center place-items-center">
          <!-- start: notification -->
          <div class="flex items-center">
            <div class="relative">
              <button @click="notificationOpen = !notificationOpen"
                      class="flex mx-4 text-gray-600 focus:outline-none rounded-full p-2 hover:text-green-700 hover:bg-green-200/20">
                <svg class="w-7 h-7" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path
                      d="M15 17H20L18.5951 15.5951C18.2141 15.2141 18 14.6973 18 14.1585V11C18 8.38757 16.3304 6.16509 14 5.34142V5C14 3.89543 13.1046 3 12 3C10.8954 3 10 3.89543 10 5V5.34142C7.66962 6.16509 6 8.38757 6 11V14.1585C6 14.6973 5.78595 15.2141 5.40493 15.5951L4 17H9M15 17V18C15 19.6569 13.6569 21 12 21C10.3431 21 9 19.6569 9 18V17M15 17H9"
                      stroke="currentColor" stroke-width="1" stroke-linecap="round" stroke-linejoin="round"/>
                </svg>
              </button>

              <!-- notification Menu-->
              <div v-show="notificationOpen" @click="notificationOpen = false"
                   class="fixed inset-0 h-full w-full z-20 "></div>

              <div v-show="notificationOpen"
                   class=" absolute right-0 mt-6 w-80 bg-white rounded-lg shadow-xl overflow-hidden z-30"
                   style="width: 20rem">
                <a href="#"
                   class=" flex items-center px-4 py-3 text-gray-600 hover:text-white hover:bg-indigo-600 -mx-2 ">
                  <img class="h-8 w-8 rounded-full object-cover mx-1"
                       src="https://images.unsplash.com/photo-1552774021-9ebbb764f03e?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1000&q=80"
                       alt="avatar"/>
                  <p class="text-sm mx-2">
                    <span class="font-bold" href="#">Evan Josh</span> replied on the
                    <span class="font-bold text-indigo-400" href="#">Upload Image</span>
                    article . 2m
                  </p>
                </a>
                <a href="#"
                   class=" flex items-center px-4 py-3 text-gray-600 hover:text-white hover:bg-indigo-600 -mx-2 ">
                  <img class="h-8 w-8 rounded-full object-cover mx-1"
                       src="https://images.unsplash.com/photo-1531427186611-ecfd6d936c79?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=634&q=80"
                       alt="avatar"/>
                  <p class="text-sm mx-2">
                    <span class="font-bold" href="#">Slick Net</span> start
                    following you . 45m
                  </p>
                </a>
                <a href="#"
                   class=" flex items-center px-4 py-3 text-gray-600 hover:text-white hover:bg-indigo-600 -mx-2 ">
                  <img class="h-8 w-8 rounded-full object-cover mx-1"
                       src="https://images.unsplash.com/photo-1450297350677-623de575f31c?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=334&q=80"
                       alt="avatar"/>
                  <p class="text-sm mx-2">
                    <span class="font-bold" href="#">Jane Doe</span> Like Your reply
                    on
                    <span class="font-bold text-indigo-400" href="#">Test with TDD</span>
                    artical . 1h
                  </p>
                </a>
                <a href="#"
                   class=" flex items-center px-4 py-3 text-gray-600 hover:text-white hover:bg-indigo-600 -mx-2">
                  <img class="h-8 w-8 rounded-full object-cover mx-1"
                       src="https://images.unsplash.com/photo-1580489944761-15a19d654956?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=398&q=80"
                       alt="avatar"/>
                  <p class="text-sm mx-2">
                    <span class="font-bold" href="#">Abigail Bennett</span>
                    start following you . 3h
                  </p>
                </a>
              </div>
            </div>
            <!-- end: notification -->
          </div>
          <!-- end: notification -->
          <!-- start:user menu -->
          <div class="relative">
            <button @click="dropdownOpen = !dropdownOpen"
                    class=" relative z-10 block w-12 h-12 overflow-hidden rounded-full shadow focus:outline-none border-2 border-green-400  hover:border-green-700 hover:bg-green-50 ">
              <img class="object-cover w-full h-full"
                   src="https://images.unsplash.com/photo-1528892952291-009c663ce843?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=296&q=80"
                   alt="Your avatar"/>
            </button>

            <div v-show="dropdownOpen" @click="dropdownOpen = false" class="fixed inset-0 z-10 w-full h-screen "></div>

            <transition enter-active-class="transition duration-150 ease-out transform"
                        enter-from-class="scale-95 opacity-0" enter-to-class="scale-100 opacity-100"
                        leave-active-class="transition duration-150 ease-in transform"
                        leave-from-class="scale-100 opacity-100" leave-to-class="scale-95 opacity-0">
              <div v-show="dropdownOpen"
                   class=" absolute right-0 z-20 w-48 py-1 mt-6 bg-white rounded-lg shadow-xl">
                <a href="#"
                   class=" px-4 py-2 flex rounded-md text-sm text-gray-700 hover:bg-indigo-600 hover:text-white ">
                  <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 mr-1" fill="none" viewBox="0 0 24 24"
                       stroke="currentColor" stroke-width="2">
                    <path stroke-linecap="round" stroke-linejoin="round"
                          d="M16 7a4 4 0 11-8 0 4 4 0 018 0zM12 14a7 7 0 00-7 7h14a7 7 0 00-7-7z"/>
                  </svg>
                  Profile</a>
                <a href="#"
                   class=" flex rounded-md px-4 py-2 text-sm text-gray-700 hover:bg-indigo-600 hover:text-white">
                  <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 mr-1" fill="none" viewBox="0 0 24 24"
                       stroke="currentColor" stroke-width="2">
                    <path stroke-linecap="round" stroke-linejoin="round"
                          d="M10.325 4.317c.426-1.756 2.924-1.756 3.35 0a1.724 1.724 0 002.573 1.066c1.543-.94 3.31.826 2.37 2.37a1.724 1.724 0 001.065 2.572c1.756.426 1.756 2.924 0 3.35a1.724 1.724 0 00-1.066 2.573c.94 1.543-.826 3.31-2.37 2.37a1.724 1.724 0 00-2.572 1.065c-.426 1.756-2.924 1.756-3.35 0a1.724 1.724 0 00-2.573-1.066c-1.543.94-3.31-.826-2.37-2.37a1.724 1.724 0 00-1.065-2.572c-1.756-.426-1.756-2.924 0-3.35a1.724 1.724 0 001.066-2.573c-.94-1.543.826-3.31 2.37-2.37.996.608 2.296.07 2.572-1.065z"/>
                    <path stroke-linecap="round" stroke-linejoin="round"
                          d="M15 12a3 3 0 11-6 0 3 3 0 016 0z"/>
                  </svg>
                  Settings</a>
                <router-link to="/"
                             class=" flex px-4 py-2 rounded-md text-sm text-gray-700 hover:bg-indigo-600 hover:text-white">
                  <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 mr-1" fill="none" viewBox="0 0 24 24"
                       stroke="currentColor" stroke-width="2">
                    <path stroke-linecap="round" stroke-linejoin="round"
                          d="M17 16l4-4m0 0l-4-4m4 4H7m6 4v1a3 3 0 01-3 3H6a3 3 0 01-3-3V7a3 3 0 013-3h4a3 3 0 013 3v1"/>
                  </svg>
                  Log out
                </router-link>
              </div>
            </transition>
          </div>
          <!-- end:user menu -->
        </div>
        <!-- end: right side -->
      </header>
    </div>

    <!-- end:header-->

    <!-- start:sidebar-->
<!--    <div class="flex  top-16">-->
    <div class="fixed flex flex-col top-20 left-0 h-[calc(100%-8.4%)]  bg-green-100 rounded-r-2xl mb-64">
      <aside
             class=" fixed inset-y-0 w-32  h-full  mb-24 z-10 flex flex-shrink-0 overflow-hidden bg-gray-600 lg:static transform duration-300 ease-in-out rounded-r-2xl items-center justify-center">
        <!--        main-->
        <div class="flex flex-col flex-shrink-0 h-full px-2 py-4  dark:border-primary-darker">
          <div class="flex flex-col flex-1 space-y-4">
            <!-- column icon-->
            <button
                @Click=""
            class="p-2 transition-colors duration-200
            text-primary-lighter  rounded
            hover:text-primary hover:bg-red-100 dark:hover:text-light dark:hover:bg-blue-900 dark:bg-dark
            focus:outline-none focus:bg-primary-100 dark:focus:bg-primary-dark focus:ring-primary-darker flex flex-col items-center"
            >
            <div class="flex flex-col items-center w-14 h-14">
              <svg class="w-8 h-8 text-blue-500" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path
                    d="M15 17H20L18.5951 15.5951C18.2141 15.2141 18 14.6973 18 14.1585V11C18 8.38757 16.3304 6.16509 14 5.34142V5C14 3.89543 13.1046 3 12 3C10.8954 3 10 3.89543 10 5V5.34142C7.66962 6.16509 6 8.38757 6 11V14.1585C6 14.6973 5.78595 15.2141 5.40493 15.5951L4 17H9M15 17V18C15 19.6569 13.6569 21 12 21C10.3431 21 9 19.6569 9 18V17M15 17H9"
                    stroke="currentColor" stroke-width="1" stroke-linecap="round" stroke-linejoin="round"/>
              </svg>
              <span>title</span>
            </div>
            </button>
            <button
                @Click=""
                class="p-2 transition-colors duration-200
            text-primary-lighter  rounded
            hover:text-primary hover:bg-red-100 dark:hover:text-light dark:hover:bg-blue-900 dark:bg-dark
            focus:outline-none focus:bg-primary-100 dark:focus:bg-primary-dark focus:ring-primary-darker flex flex-col items-center"
            >
              <div class="flex flex-col items-center w-14 h-14">
                <svg class="w-8 h-8 text-blue-500" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path
                      d="M15 17H20L18.5951 15.5951C18.2141 15.2141 18 14.6973 18 14.1585V11C18 8.38757 16.3304 6.16509 14 5.34142V5C14 3.89543 13.1046 3 12 3C10.8954 3 10 3.89543 10 5V5.34142C7.66962 6.16509 6 8.38757 6 11V14.1585C6 14.6973 5.78595 15.2141 5.40493 15.5951L4 17H9M15 17V18C15 19.6569 13.6569 21 12 21C10.3431 21 9 19.6569 9 18V17M15 17H9"
                      stroke="currentColor" stroke-width="1" stroke-linecap="round" stroke-linejoin="round"/>
                </svg>
                <span>title</span>
              </div>
            </button>
            <button
                @Click=""
                class="p-2 transition-colors duration-200
            text-primary-lighter  rounded
            hover:text-primary hover:bg-red-100 dark:hover:text-light dark:hover:bg-blue-900 dark:bg-dark
            focus:outline-none focus:bg-primary-100 dark:focus:bg-primary-dark focus:ring-primary-darker flex flex-col items-center"
            >
              <div class="flex flex-col items-center w-14 h-14">
                <svg class="w-8 h-8 text-blue-500" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path
                      d="M15 17H20L18.5951 15.5951C18.2141 15.2141 18 14.6973 18 14.1585V11C18 8.38757 16.3304 6.16509 14 5.34142V5C14 3.89543 13.1046 3 12 3C10.8954 3 10 3.89543 10 5V5.34142C7.66962 6.16509 6 8.38757 6 11V14.1585C6 14.6973 5.78595 15.2141 5.40493 15.5951L4 17H9M15 17V18C15 19.6569 13.6569 21 12 21C10.3431 21 9 19.6569 9 18V17M15 17H9"
                      stroke="currentColor" stroke-width="1" stroke-linecap="round" stroke-linejoin="round"/>
                </svg>
                <span>title</span>
              </div>
            </button>
            <!-- column icon-->
          </div>
        </div>
        <!--        main-->
      </aside>
    </div>
    <!-- end:sidebar-->
  </div>
</template>
<script lang="ts" setup>
import {ref} from 'vue'

const isOpen = ref(false)
const dropdownOpen = ref(false)
const notificationOpen = ref(false)
//other template
const isDark = ref(false)
const toggleTheme = () => {

}
</script>
<style scoped>
/* Custom style */
.header-right {
  width: calc(100% - 3.5rem);
}

.sidebar:hover {
  width: 16rem;
}

@media only screen and (min-width: 768px) {
  .header-right {
    width: calc(100% - 16rem);
  }
}
</style>