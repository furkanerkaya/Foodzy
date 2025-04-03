<template >
    <div class="hidden sm:flex lg:mx-48 md:mx-24 sm:10 mx-2 mt-4">
      <div class="">
        <div class="hidden border-[1px] border-[#E9E9E9] p-1 max-w-fit rounded-md">
            <NuxtImg src="/images/icons/category-toogle.svg" class="w-4 h-4"/>
        </div>
      </div>
      <div class="flex col-span-5 mx-auto">
        <div>
          Home
        </div>

        <div class="mx-2">
            <div ref="categoryDropDownContainer">
                <button id="categoryDropdownNavbarLink" @click="toggleDropdown('categoryDropDown')" class="flex items-center justify-between w-full px-3 text-black rounded-sm font-sans">
                    Category 
                    <div class="transition" :class="dropdownList[0].isOpen == true ? 'rotate-180 ml-3 mt-2': ''">
                        <svg class="w-2.5 h-2.5 ms-3 mt-1" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 10 6">
                            <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="m1 1 4 4 4-4"/>
                        </svg>
                    </div>
                </button>
                <div v-if="dropdownList[0].isOpen" class="z-10 font-normal bg-white divide-y divide-gray-100 rounded-lg shadow-sm w-44 dark:bg-gray-700 dark:divide-gray-600 absolute mt-2">
                    <ul class="py-2 text-sm text-gray-700 dark:text-gray-200">
                    <li><a href="#" class="block px-4 py-2 hover:bg-gray-100 dark:hover:bg-gray-600 dark:hover:text-white">Category 1</a></li>
                    <li><a href="#" class="block px-4 py-2 hover:bg-gray-100 dark:hover:bg-gray-600 dark:hover:text-white">Category 2</a></li>
                    <li><a href="#" class="block px-4 py-2 hover:bg-gray-100 dark:hover:bg-gray-600 dark:hover:text-white">Category 3</a></li>
                    </ul>
                </div>
            </div>
        </div>

        <div class="mx-2">

        <div ref="productsDropDownContainer">
            <button id="productsDropdownNavbarLink" @click="toggleDropdown('productsDropDown')" class="flex items-center justify-between w-full px-3 text-black rounded-sm" >
                Products
                <div class="transition" :class="dropdownList[1].isOpen == true ? 'rotate-180 ml-3 mt-2': ''">
                    <svg class="w-2.5 h-2.5 ms-3 mt-1" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 10 6">
                        <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="m1 1 4 4 4-4"/>
                    </svg>
                </div>
            </button>
            <div v-if="dropdownList[1].isOpen" class="z-10 font-normal bg-white divide-y divide-gray-100 rounded-lg shadow-sm w-44 dark:bg-gray-700 dark:divide-gray-600 absolute mt-2">
                <ul class="py-2 text-sm text-gray-700 dark:text-gray-200">
                    <li>
                        <a href="#" class="block px-4 py-2 hover:bg-gray-100 dark:hover:bg-gray-600 dark:hover:text-white">Product 1</a>
                    </li>
                    <li>
                        <a href="#" class="block px-4 py-2 hover:bg-gray-100 dark:hover:bg-gray-600 dark:hover:text-white">Product 2</a>
                    </li>
                    <li>
                        <a href="#" class="block px-4 py-2 hover:bg-gray-100 dark:hover:bg-gray-600 dark:hover:text-white">Product 3</a>
                    </li>
                </ul>
            </div>
        </div>
            
        </div>

        <div class="mx-2">
            <div ref="pagesDropDownContainer">
                <button id="pagesDropdownNavbarLink" @click="toggleDropdown('pagesDropDown')" class="flex items-center justify-between w-full px-3 text-black rounded-sm">
                    Pages 
                    <div class="transition" :class="dropdownList[2].isOpen == true ? 'rotate-180 ml-3 mt-2': ''">
                        <svg class="w-2.5 h-2.5 ms-3 mt-1" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 10 6">
                            <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="m1 1 4 4 4-4"/>
                        </svg>
                    </div>
                </button>
                <div v-if="dropdownList[2].isOpen" class="z-10 font-normal bg-white divide-y divide-gray-100 rounded-lg shadow-sm w-44 dark:bg-gray-700 dark:divide-gray-600 absolute mt-2">
                    <ul class="py-2 text-sm text-gray-700 dark:text-gray-200">
                    <li><a href="#" class="block px-4 py-2 hover:bg-gray-100 dark:hover:bg-gray-600 dark:hover:text-white">Page 1</a></li>
                    <li><a href="#" class="block px-4 py-2 hover:bg-gray-100 dark:hover:bg-gray-600 dark:hover:text-white">Page 2</a></li>
                    <li><a href="#" class="block px-4 py-2 hover:bg-gray-100 dark:hover:bg-gray-600 dark:hover:text-white">Page 3</a></li>
                    </ul>
                </div>
            </div>
        </div>
        <div class="mx-2">
            <div ref="blogDropDownContainer">
                <button id="blogDropdownNavbarLink" @click="toggleDropdown('blogDropDown')" class="flex items-center justify-between w-full px-3 text-black rounded-sm">
                    Blog 
                    <div class="transition" :class="dropdownList[3].isOpen == true ? 'rotate-180 ml-3 mt-2': ''">
                        <svg class="w-2.5 h-2.5 ms-3 mt-1" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 10 6">
                            <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="m1 1 4 4 4-4"/>
                        </svg>
                    </div>
                </button>
                <div v-if="dropdownList[3].isOpen" class="z-10 font-normal bg-white divide-y divide-gray-100 rounded-lg shadow-sm w-44 dark:bg-gray-700 dark:divide-gray-600 absolute mt-2">
                    <ul class="py-2 text-sm text-gray-700 dark:text-gray-200">
                    <li><a href="#" class="block px-4 py-2 hover:bg-gray-100 dark:hover:bg-gray-600 dark:hover:text-white">Blog 1</a></li>
                    <li><a href="#" class="block px-4 py-2 hover:bg-gray-100 dark:hover:bg-gray-600 dark:hover:text-white">Blog 2</a></li>
                    <li><a href="#" class="block px-4 py-2 hover:bg-gray-100 dark:hover:bg-gray-600 dark:hover:text-white">Blog 3</a></li>
                    </ul>
                </div>
            </div>
        </div>
        <div>
            <div ref="elementsDropDownContainer">
                <button id="elementsDropdownNavbarLink" @click="toggleDropdown('elementsDropDown')" class="flex items-center justify-between w-full px-3 text-black rounded-sm">
                    Elements 
                    <div class="transition" :class="dropdownList[4].isOpen == true ? 'rotate-180 ml-3 mt-2': ''">
                        <svg class="w-2.5 h-2.5 ms-3 mt-1" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 10 6">
                            <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="m1 1 4 4 4-4"/>
                        </svg>
                    </div>
                </button>
                <div v-if="dropdownList[4].isOpen" class="z-10 font-normal bg-white divide-y divide-gray-100 rounded-lg shadow-sm w-44 dark:bg-gray-700 dark:divide-gray-600 absolute mt-2">
                    <ul class="py-2 text-sm text-gray-700 dark:text-gray-200">
                    <li><a href="#" class="block px-4 py-2 hover:bg-gray-100 dark:hover:bg-gray-600 dark:hover:text-white">Elements 1</a></li>
                    <li><a href="#" class="block px-4 py-2 hover:bg-gray-100 dark:hover:bg-gray-600 dark:hover:text-white">Elements 2</a></li>
                    <li><a href="#" class="block px-4 py-2 hover:bg-gray-100 dark:hover:bg-gray-600 dark:hover:text-white">Elements 3</a></li>
                    </ul>
                </div>
            </div>
        </div>
        
        
      </div>
      <div class=" flex col-span-2 col-start-8">
        <NuxtImg src="/images/icons/phone.svg" class="w-4 h-4 mt-1"/>
        <p> +123 ( 456 ) ( 7890 )</p>
      </div>

      
    </div>
    <button class="block sm:hidden ml-auto mt-2 mr-2 border-[1px] border-[#E9E9E9] p-1 max-w-fit rounded-md" @click="respMenu = !respMenu" v-show="!respMenu">
        <NuxtImg src="/images/icons/category-toogle.svg" class="w-8 h-8"/>
    </button>
    <div class="w-screen h-screen bg-white z-[99] fixed sm:hidden" v-show="respMenu"> 
        <div class="float-right py-2 px-3 shadow-lg rounded-md mr-2  text-4xl" @click="respMenu = !respMenu">
            x
        </div>
        <div class="flex">
        <NuxtImg src="/images/logo/foodzy-logo.svg" class="w-20"/>
            <div class="my-auto">
                <p class="font-black text-3xl">Foodzy</p>
                <p class="font-semibold text-sm">A Treasure of Tastes</p>
            </div>
        </div>
        <div class="mt-20">
            <div class="px-4 mx-2 border-b-[1px] text-lg border-gray-400">
                Home    
            </div>

            <div class="mx-2 mt-4 border-b-[1px] text-lg border-gray-400">
                <div ref="categoryDropDownContainer">
                    <button id="categoryDropdownNavbarLink" @click="toggleDropdown('categoryDropDown')" class="flex items-center justify-between w-full px-3 text-black rounded-sm font-sans">
                        Category 
                        <div class="transition" :class="dropdownList[0].isOpen == true ? 'rotate-180 ml-3 mt-2': ''">
                            <svg class="w-2.5 h-2.5 ms-3 mt-1" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 10 6">
                                <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="m1 1 4 4 4-4"/>
                            </svg>
                        </div>
                    </button>
                    <div v-if="dropdownList[0].isOpen" class="z-10 font-normal bg-white divide-y divide-gray-100 rounded-lg shadow-md w-full dark:bg-gray-700 dark:divide-gray-600 relative transition mt-2">
                        <ul class="py-2 text-sm text-gray-700 dark:text-gray-200">
                        <li><a href="#" class="block px-4 py-2 hover:bg-gray-100 dark:hover:bg-gray-600 dark:hover:text-white">Category 1</a></li>
                        <li><a href="#" class="block px-4 py-2 hover:bg-gray-100 dark:hover:bg-gray-600 dark:hover:text-white">Category 2</a></li>
                        <li><a href="#" class="block px-4 py-2 hover:bg-gray-100 dark:hover:bg-gray-600 dark:hover:text-white">Category 3</a></li>
                        </ul>
                    </div>
                </div>
            </div>

            <div class="mx-2 border-b-[1px] text-lg border-gray-400 mt-4">

            <div ref="productsDropDownContainer">
                <button id="productsDropdownNavbarLink" @click="toggleDropdown('productsDropDown')" class="flex items-center justify-between w-full px-3 text-black rounded-sm" >
                    Products
                    <div class="transition" :class="dropdownList[1].isOpen == true ? 'rotate-180 ml-3 mt-2': ''">
                        <svg class="w-2.5 h-2.5 ms-3 mt-1" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 10 6">
                            <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="m1 1 4 4 4-4"/>
                        </svg>
                    </div>
                </button>
                <div v-if="dropdownList[1].isOpen" class="z-10 font-normal bg-white divide-y divide-gray-100 rounded-lg shadow-md w-full dark:bg-gray-700 dark:divide-gray-600 relative mt-2">
                    <ul class="py-2 text-sm text-gray-700 dark:text-gray-200">
                        <li>
                            <a href="#" class="block px-4 py-2 hover:bg-gray-100 dark:hover:bg-gray-600 dark:hover:text-white">Product 1</a>
                        </li>
                        <li>
                            <a href="#" class="block px-4 py-2 hover:bg-gray-100 dark:hover:bg-gray-600 dark:hover:text-white">Product 2</a>
                        </li>
                        <li>
                            <a href="#" class="block px-4 py-2 hover:bg-gray-100 dark:hover:bg-gray-600 dark:hover:text-white">Product 3</a>
                        </li>
                    </ul>
                </div>
            </div>
                
            </div>

            <div class="mx-2 border-b-[1px] text-lg border-gray-400 mt-4">
                <div ref="pagesDropDownContainer">
                    <button id="pagesDropdownNavbarLink" @click="toggleDropdown('pagesDropDown')" class="flex items-center justify-between w-full px-3 text-black rounded-sm">
                        Pages 
                        <div class="transition" :class="dropdownList[2].isOpen == true ? 'rotate-180 ml-3 mt-2': ''">
                            <svg class="w-2.5 h-2.5 ms-3 mt-1" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 10 6">
                                <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="m1 1 4 4 4-4"/>
                            </svg>
                        </div>
                    </button>
                    <div v-if="dropdownList[2].isOpen" class="z-10 font-normal bg-white divide-y divide-gray-100 rounded-lg shadow-md w-full dark:bg-gray-700 dark:divide-gray-600 relative mt-2">
                        <ul class="py-2 text-sm text-gray-700 dark:text-gray-200">
                        <li><a href="#" class="block px-4 py-2 hover:bg-gray-100 dark:hover:bg-gray-600 dark:hover:text-white">Page 1</a></li>
                        <li><a href="#" class="block px-4 py-2 hover:bg-gray-100 dark:hover:bg-gray-600 dark:hover:text-white">Page 2</a></li>
                        <li><a href="#" class="block px-4 py-2 hover:bg-gray-100 dark:hover:bg-gray-600 dark:hover:text-white">Page 3</a></li>
                        </ul>
                    </div>
                </div>
            </div>
            <div class="mx-2 border-b-[1px] text-lg border-gray-400 mt-4">
                <div ref="blogDropDownContainer">
                    <button id="blogDropdownNavbarLink" @click="toggleDropdown('blogDropDown')" class="flex items-center justify-between w-full px-3 text-black rounded-sm">
                        Blog 
                        <div class="transition" :class="dropdownList[3].isOpen == true ? 'rotate-180 ml-3 mt-2': ''">
                            <svg class="w-2.5 h-2.5 ms-3 mt-1" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 10 6">
                                <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="m1 1 4 4 4-4"/>
                            </svg>
                        </div>
                    </button>
                    <div v-if="dropdownList[3].isOpen" class="z-10 font-normal bg-white divide-y divide-gray-100 rounded-lg shadow-sm w-44 dark:bg-gray-700 dark:divide-gray-600 relative mt-2">
                        <ul class="py-2 text-sm text-gray-700 dark:text-gray-200">
                        <li><a href="#" class="block px-4 py-2 hover:bg-gray-100 dark:hover:bg-gray-600 dark:hover:text-white">Blog 1</a></li>
                        <li><a href="#" class="block px-4 py-2 hover:bg-gray-100 dark:hover:bg-gray-600 dark:hover:text-white">Blog 2</a></li>
                        <li><a href="#" class="block px-4 py-2 hover:bg-gray-100 dark:hover:bg-gray-600 dark:hover:text-white">Blog 3</a></li>
                        </ul>
                    </div>
                </div>
            </div>
            <div class="mx-2 mt-4 border-b-[1px] text-lg border-gray-400">
                <div ref="elementsDropDownContainer">
                    <button id="elementsDropdownNavbarLink" @click="toggleDropdown('elementsDropDown')" class="flex items-center justify-between w-full px-3 text-black rounded-sm">
                        Elements 
                        <div class="transition" :class="dropdownList[4].isOpen == true ? 'rotate-180 ml-3 mt-2': ''">
                            <svg class="w-2.5 h-2.5 ms-3 mt-1" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 10 6">
                                <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="m1 1 4 4 4-4"/>
                            </svg>
                        </div>
                    </button>
                    <div v-if="dropdownList[4].isOpen" class="z-10 font-normal bg-white divide-y divide-gray-100 rounded-lg shadow-md w-full dark:bg-gray-700 dark:divide-gray-600 relative mt-2">
                        <ul class="py-2 text-sm text-gray-700 dark:text-gray-200">
                        <li><a href="#" class="block px-4 py-2 hover:bg-gray-100 dark:hover:bg-gray-600 dark:hover:text-white">Elements 1</a></li>
                        <li><a href="#" class="block px-4 py-2 hover:bg-gray-100 dark:hover:bg-gray-600 dark:hover:text-white">Elements 2</a></li>
                        <li><a href="#" class="block px-4 py-2 hover:bg-gray-100 dark:hover:bg-gray-600 dark:hover:text-white">Elements 3</a></li>
                        </ul>
                    </div>
                </div>
            </div>

        </div>

        <div class="border-t-[1px] border-[#E9E9E9] mt-28 w-full">
            <div class="flex mt-10 mx-auto max-w-fit">
                <div class="bg-white p-2 rounded-md shadow-lg">
                    <NuxtImg src="/images/footer/facebook.svg" class="w-4 "/>                        
                </div>
                <div class="bg-white p-2 rounded-md ml-2 shadow-lg">
                    <NuxtImg src="/images/footer/x.svg" class="w-4 "/>                        
                </div>
                <div class="bg-white p-2 rounded-md ml-2 shadow-lg">
                    <NuxtImg src="/images/footer/Icon.svg" class="w-4 "/>                        
                </div>
                <div class="bg-white p-2 rounded-md ml-2 shadow-lg">
                    <NuxtImg src="/images/footer/instagram.svg" class="w-4 "/>                        
                </div>
            </div>
            <div class="mt-2 mx-auto flex max-w-fit">
                <!-- <NuxtImg src="/images/icons/phone.svg" class="w-4 h-4 mt-1"/> -->
                <p> +123 ( 456 ) ( 7890 )</p>
            </div>
        </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
        return {
            dropdownList: [
                {
                    name: 'categoryDropDown',
                    isOpen: false
                },
                {
                    name: 'productsDropDown',
                    isOpen: false
                },
                {
                    name: 'pagesDropDown',
                    isOpen: false
                },
                {
                    name: 'blogDropDown',
                    isOpen: false
                },
                {
                    name: 'elementsDropDown',
                    isOpen: false
                }
            ],
            respMenu: false
        
        }
    },
    methods: {
        toggleDropdown(value) {
            for(let i=0; i<this.dropdownList.length; i++){
                if(this.dropdownList[i].name == value){
                    this.dropdownList[i].isOpen = !this.dropdownList[i].isOpen 
                }
                else{
                    this.dropdownList[i].isOpen = false
                }
            }
        },
        handleClickOutside(event) {
            for(let i=0; i<this.dropdownList.length; i++){
                const dropdownElement = this.$refs[this.dropdownList[i].name + 'Container'];                
                if (this.dropdownList[i].isOpen && dropdownElement && !dropdownElement.contains(event.target)) {
                    this.dropdownList[i].isOpen = false;
                }
            }
            
        }
    },
    mounted() {
        document.addEventListener('click', this.handleClickOutside)
    },
    beforeUnmount() {
        document.removeEventListener('click', this.handleClickOutside)
    }
}
  </script>
  