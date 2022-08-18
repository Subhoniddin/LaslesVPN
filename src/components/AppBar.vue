<template>
  <div class=''>
    <nav class="
        container
        px-6
        py-8
        mx-auto
        md:flex md:justify-between md:items-center
      ">
      <div class="flex items-center justify-between">
        <div class="flex ">
          <img src="@/assets/Vector.png" alt="">
          <p class="font-bold text-xl m-2 ">
            LaslesVPN
          </p>
        </div>
        <!-- Mobile menu button -->
        <div @click="toggleNav" class="flex md:hidden">
          <button type="button" class="
              text-black-100
              hover:text-gray-200
              focus:outline-none focus:text-gray-400
            ">
            <svg viewBox="0 0 24 24" class="w-6 h-6 fill-current">
              <path fill-rule="evenodd"
                d="M4 5h16a1 1 0 0 1 0 2H4a1 1 0 1 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2z">
              </path>
            </svg>
          </button>
        </div>
      </div>
      <!-- Mobile Menu open: "block", Menu closed: "hidden" -->
      <ul :class="showMenu ? 'flex' : 'hidden'" class="
          flex-col
          mt-8
          space-y-4
          md:flex md:space-y-0 md:flex-row md:items-center md:space-x-10 md:mt-0" v-for="link in links"
        :key="link.name">
        <li class="text-black hover:text-black-400"><a class="block w-[150px]" :class="link.classes"
            :href="link.href">{{ link.name }}</a></li>
      </ul>
    </nav>
  </div>
</template>
<script>
import { ref } from 'vue';
export default {
  setup() {
    let showMenu = ref(false);
    let links = [
      { name: "About", href: "#", classes: '' },
      { name: "Features", href: "#", classes: '' },
      { name: "Pricing", href: "#", classes: '' },
      { name: "Testimonials", href: "#", classes: '' },
      { name: "Help", href: "#" },
      { name: "Sign In", href: "#", classes: '' },
      { name: "Sign Up", href: "#", classes: 'border border-3 rounded-full text-center border-red-500 text-red-500 ' },
    ];
    const toggleNav = () => {
      showMenu.value = !showMenu.value;
    }

    return { showMenu, links, toggleNav };
  },
};
</script>