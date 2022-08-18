<template>
  <div class='flex items-center'>
    <nav
      class="
        container
        px-6
        py-8
        mx-auto
        md:flex md:justify-between md:items-center
      "
    >
      <div class="flex items-center justify-between">
        <div class="flex ">
        <img src="@/assets/Vector.png" alt="">
         <p class="font-bold text-xl m-2 ">
         LaslesVPN
        </p>
      </div>
        <!-- Mobile menu button -->
        <div @click="toggleNav" class="flex md:hidden">
          <button
            type="button"
            class="
              text-black-100
              hover:text-gray-200
              focus:outline-none focus:text-gray-400
            "
          >
            <svg viewBox="0 0 24 24" class="w-6 h-6 fill-current">
              <path
                fill-rule="evenodd"
                d="M4 5h16a1 1 0 0 1 0 2H4a1 1 0 1 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2z"
              ></path>
            </svg>
          </button>
        </div>
      </div>

      <!-- Mobile Menu open: "block", Menu closed: "hidden" -->
      <ul
        :class="showMenu ? 'flex' : 'hidden'"
        class="
          flex-col
          mt-8
          space-y-4
          md:flex md:space-y-0 md:flex-row md:items-center md:space-x-10 md:mt-0"
          v-for="link in links"
          :key="link.name"
      >
        <li class="text-black hover:text-black-400"><a :href="link.href">{{ link.name }}</a></li>
      </ul>
     <div>
      <div class="flex justify-between w-40">
      <button>Sign In</button>
      <button class="box-border last:w-24 h-8 border border-3 border-red-500 rounded-2xl ">
        <p class="text-red-500">Sign Up</p>
        </button>
      </div>
      </div>
    </nav>
  </div>
</template>
<script>
import { ref } from 'vue';
export default {
  setup() {
    let showMenu = ref(false);
    let links = [
      { name: "About", href: "#" },
      { name: "Fitures", href: "#" },
      { name: "Fitures", href: "#" },
      { name: "Testiomonials", href: "#" },
      { name: "Help", href: "#" },
    ];
    const toggleNav = () =>  {
        showMenu.value = !showMenu.value;
    }

    return { showMenu, links, toggleNav };
  },
};
</script>























<!-- <template lang="">
  <nav class="w-full md:flex justify-between">
    <div class="flex items-center">
        <img src=""/>
        <h1>LaslesVPN</h1>
    </div>    
    <span class="absolute md:hidden right-6 top-1.5  text-4xl">
    <button class="cursor-pointer" v-on:click="menuOpen">btn
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
        let open = ref(true)
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
        menuOpen() {
            open.value = !open.value
            console.log('clicked');
        }

    },
}
</script>
<style lang="">
    
</style> -->