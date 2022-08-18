<template lang="">
  <nav class="w-full md:flex justify-between">
    <div class="flex items-center">
        <img src=""/>
        <h1>LaslesVPN</h1>
    </div>    
    <span class="absolute md:hidden right-6 top-1.5  text-4xl">
    <button class="cursor-pointer" v-on:click="MenuOPen">btn
        <i :class="[open ?'bi bi-filter' : 'bi bi-filter-left']"></i>
    </button>
    </span>  
    <div class='md:flex justify-between w-96 md:items-center px-3 md:px-0 pb-10 
        md:pb-0 md:static absolute md:w-auto top-14 duration-700 easi-in'
        :class="[open ? 'left-0' : 'left-[100%]']">
        <ul class="md:mx-4 md:my-0 my-6 " v-for="link in Links" :key="link.name">
            <li class="text-bold">
                <a :href="link.link">{{link.name}}</a>
            </li>
        </ul>
        <div>
      <div class="flex justify-between w-40 lg:ml-80 md:ml-20">
      <button>Sign In</button>
      <button class="box-border last:w-24 h-8 border border-3 border-red-500 rounded-2xl ">
        <p class="text-red-500">Sign Up</p>
        </button>
      </div>
      </div>
    </div>
    
  </nav>
</template>
<script>
import { ref } from 'vue';


export default {
    setup() {
        let open = ref(false)
        let Links = [
            { name: 'About', link: '#' },
            { name: 'About', link: '#' },
            { name: 'About', link: '#' },
            { name: 'About', link: '#' },
            { name: 'About', link: '#' },
        ]

        return { Links, open, }
    },
    methods: {
        MenuOpen() {
            open.value = !open.value
            console.log('clicked');
        }

    },
}
</script>
<style lang="">
    
</style>