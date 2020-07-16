<template>
  <div class="font-roboto">
    <div class="absolute h-screen w-full">
        <div class="absolute h-screen w-full">
            <splide :options="splide">
              <splide-slide>
                <img src="../assets/img/bg1.jpg" class="w-full h-screen object-cover">
              </splide-slide>
              <splide-slide>
                <img src="../assets/img/bg1.jpg" class="w-full h-screen object-cover">
              </splide-slide>
              <splide-slide>
                <img src="../assets/img/bg1.jpg" class="w-full h-screen object-cover">
              </splide-slide>
            </splide>
        </div>
    </div>
    <div class="flex flex-col h-screen object-cover relative">
        <div class="h-10vh flex">
            <div class="container mx-auto flex justify-between items-center h-full px-4">
                <div class="flex space-x-4 md:w-30vw">
                    <div class="flex flex-col items-end space-y-1 cursor-pointer">
                        <div class="bg-white h-1 w-8"></div>
                        <div class="bg-white h-1 w-6"></div>
                        <div class="bg-white h-1 w-8"></div>
                    </div>
                    <span class="text-white font-bold">MENU</span>
                </div>
                <img src="../assets/img/LOGO.png" class=" -md:hidden">
                <div class="flex space-x-6  md:w-30vw justify-end">
                    <div class="flex space-x-2 border-b pb-2 border-white">
                        <svg width="24" class="cursor-pointer" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                            <path class="text-white fill-current" fill-rule="evenodd" clip-rule="evenodd" d="M12 2C6.47998 2 2 6.48001 2 12C2 17.52 6.47998 22 12 22C17.52 22 22 17.52 22 12C22 6.48001 17.52 2 12 2ZM7.06995 18.28C7.5 17.38 10.12 16.5 12 16.5C13.88 16.5 16.5099 17.38 16.9299 18.28C15.5699 19.36 13.86 20 12 20C10.1399 20 8.42993 19.36 7.06995 18.28ZM12 14.5C13.46 14.5 16.9301 15.09 18.36 16.83C19.38 15.49 20 13.82 20 12C20 7.59 16.41 4 12 4C7.58997 4 4 7.59 4 12C4 13.82 4.62 15.49 5.64001 16.83C7.06995 15.09 10.54 14.5 12 14.5ZM12 6C10.0601 6 8.5 7.56 8.5 9.5C8.5 11.44 10.0601 13 12 13C13.9399 13 15.5 11.44 15.5 9.5C15.5 7.56 13.9399 6 12 6ZM10.5 9.5C10.5 10.33 11.17 11 12 11C12.83 11 13.5 10.33 13.5 9.5C13.5 8.67001 12.83 8 12 8C11.17 8 10.5 8.67001 10.5 9.5Z"/>
                        </svg>
                        <div class="flex space-x-2 -sm:hidden">
                            <span class="text-white cursor-pointer hover:text-blue-400">LOGIN</span>
                            <span class="text-white">or</span>
                            <span class="text-white cursor-pointer hover:text-blue-400">REGISTER</span>
                        </div>                            
                    </div>
                    <div class="relative" v-on-clickaway="away">
                        <div @click="laguage = !laguage" class="flex space-x-2 border-b cursor-pointer pb-2 border-white">
                            <img :src="laguageSelected" class="w-6">
                            <svg width="24" height="24" class="-sm:hidden" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                                <path class="text-white fill-current" d="M16.59 8.29501L12 12.875L7.41 8.29501L6 9.70501L12 15.705L18 9.70501L16.59 8.29501Z"/>
                            </svg>                
                        </div>
                         <div v-show="laguage" class="origin-top-right absolute right-0 mt-2 w-56 rounded-md shadow-lg">
                            <div class="rounded-md bg-white shadow-xs">
                                <div class="py-1" role="menu" aria-orientation="vertical" aria-labelledby="options-menu">
                                    <a href="#" @click="changelaguage('uk')" class="flex space-x-2 px-4 py-2 text-sm leading-5 text-gray-700 hover:bg-blue-200 hover:text-gray-900 focus:outline-none focus:bg-blue-200 focus:text-gray-900" role="menuitem"> <img src="../assets/img/uk.svg" class="w-6"><span>UK</span></a>
                                    <a href="#" @click="changelaguage('morocco')" class="flex space-x-2 px-4 py-2 text-sm leading-5 text-gray-700 hover:bg-blue-200 hover:text-gray-900 focus:outline-none focus:bg-blue-200 focus:text-gray-900" role="menuitem"> <img src="../assets/img/morocco.png" class="w-6"><span>Morocco</span></a>
                                    <a href="#" @click="changelaguage('norway')" class="flex space-x-2 px-4 py-2 text-sm leading-5 text-gray-700 hover:bg-blue-200 hover:text-gray-900 focus:outline-none focus:bg-blue-200 focus:text-gray-900" role="menuitem"> <img src="../assets/img/norway.png" class="w-6"><span>Norway</span></a>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div class="flex-1 px-4">
            <div class="-lg:container lg:w-70p mx-auto h-full flex flex-col justify-center items-center">
                <h1 class="text-4xl w-full text-white mb-2">Find your car</h1>
                <div class="w-full h-150p rounded p-5 -md:bg-white grid-cols-2 md:grid-cols-5 grid gap-5 relative">
                    <img src="../assets/img/s.png" class="absolute -md:hidden top-0 left-0 w-full bg-cover h-full">
                    <div class=" flex flex-col justify-center relative z-10">
                        <p class="text-sm text-gray-500 pb-1 -md:text-xs">Pick-up Location</p>
                        <v-select class="style-chooser"  placeholder="Pick-up Location" :options="options"></v-select>
                    </div>
                    <div class=" flex flex-col justify-center relative z-10">
                        <p class="text-sm text-gray-500 pb-1 -md:text-xs">Return Location</p>
                        <v-select placeholder="Return Location" :options="options"></v-select>
                    </div>
                    <div class=" flex flex-col justify-center relative z-10">
                        <p class="text-sm text-gray-500 pb-1 -md:text-xs">Pick-up Date-Time</p>
                        <flat-pickr placeholder="Pick Date" class="border border-gray-500 rounded px-2 py-1" :config="config1" v-model="date1"></flat-pickr>
                    </div>
                    <div class=" flex flex-col justify-center relative z-10">
                        <p class="text-sm text-gray-500 pb-1 -md:text-xs">Return Date-Time</p>
                        <flat-pickr placeholder="Pick Date" class="border border-gray-500 rounded px-2 py-1" :config="config2" v-model="date2"></flat-pickr>
                    </div>
                    <div class="flex flex-col justify-center relative z-10 -md:col-span-2">
                        <img src="../assets/img/button.png" class="absolute -md:hidden top-0 left-0 h-full w-full bg-cover">
                        <button class="px-4 relative md:w-90p z-20 py-2 -md:bg-blue-500 -md:hover:bg-blue-600 h-full focus:outline-none text-white font-semibold text-xl">Search</button>
                    </div>
                </div>
            </div>
        </div>
        <div class="h-10vh px-4">
            <div class="container mx-auto flex justify-between items-center h-full">
                <ul class="flex flex-col md:flex-row md:space-x-5 relative z-50">
                    <li class="text-white font-light -md:text-xs  hover:text-blue-400 cursor-pointer">Homepage</li>
                    <li class="text-white font-light -md:text-xs  hover:text-blue-400 cursor-pointer">Explore Vehicles</li>
                    <li class="text-white font-light -md:text-xs  hover:text-blue-400 cursor-pointer">Contact</li>
                </ul>
                <div class="flex flex-col font-light text-white items-end relative z-50">
                    <img src="../assets/img/sara.png" class="w-40p absolute right-0 top-0 -mt-12">
                    <p class="text-xs">Hello, I'm sara</p>
                    <p class="text-xs">How can I help you?</p>
                </div>
            </div>
        </div>
    </div>
  </div>
</template>

<script>
import flatPickr from 'vue-flatpickr-component';
import vSelect from 'vue-select'
import { Splide, SplideSlide } from '@splidejs/vue-splide';
import { mixin as clickaway } from 'vue-clickaway';
import 'flatpickr/dist/flatpickr.css';
import 'vue-select/dist/vue-select.css';
import '@splidejs/splide/dist/css/themes/splide-default.min.css';
import uk from '../assets/img/uk.svg'
import norway from '../assets/img/norway.png'
import morocco from '../assets/img/morocco.png'
export default {
  mixins: [ clickaway ],
  name: 'Hero',
  data () {
      return {
        laguageSelected : uk,
        laguage : false,
        date1: null,       
        date2: null,  
        config1 : {
          enableTime: true,
          dateFormat: "d.m.Y H:i",
          minDate: "today",
          minTime:  Date.now(),
        },  
        config2 : {
          enableTime: true,
          dateFormat: "d.m.Y H:i",
          minDate: new Date().fp_incr(1),
        },
        splide : {
          arrows : false,
          autoplay : true,
          type : 'loop'
        },
        options: [
          'foo',
          'bar',
          'baz'
        ]  
      }
  },
  methods: {
    away: function() {
      this.laguage = false
    },
    changelaguage : function(e){
        if(e == 'uk'){
            this.laguageSelected = uk
        }else if (e == 'morocco'){
            this.laguageSelected = morocco
        }else if (e == 'norway'){
            this.laguageSelected = norway
        }
        this.laguage = false
    }
  },
  components: {
      flatPickr,
      vSelect,
      Splide,
      SplideSlide,
  }
}
</script>