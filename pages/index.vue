<template >
  <div class="border-t-2 mt-4">

    <div class="sm:flex lg:mx-48 md:mx-24 sm:10 mx-2 mt-4 justify-between">
      <div class="flex">
        <div class="flex">
          <NuxtImg src="/images/logo/foodzy-logo.svg" class="w-16"/>
          <div class="my-auto">
            <p class="font-black text-2xl">Foodzy</p>
            <p class="font-semibold text-xs">A Treasure of Tastes</p>
          </div>
        </div>

        <div class="flex sm:hidden">
          <div class="flex my-auto">
            <NuxtImg src="/images/icons/account.svg" class="w-6 h-6" /> 
            <p>Account</p>
          </div>
          <div class="flex my-auto ml-4">
            <NuxtImg src="/images/icons/wishlist.svg" class="w-6 h-6" /> 
            <p>Wishlist</p>
          </div>
          <div class="flex my-auto ml-4">
            <NuxtImg src="/images/icons/cart.svg" class="w-6 h-6" /> 
            <p>Cart</p>
          </div>
        
        </div>

      </div>

      <div class="mt-2 py-4 sm:w-1/2 flex">
            <input type="text" id="search" class="border-[1px]  border-[#64B496] text-gray-900 text-xs rounded-l-md block w-full p-2.5" placeholder="Search For items..." required />
            <div ref="categoryDropDownContainer">
                <button id="categoryDropdownNavbarLink" @click="toggleDropdown()" class="flex border-t-[1px] border-b-[1px] border-[#64B496]  items-center justify-between w-full px-3 text-gray-400 rounded-sm font-sans text-xs min-w-max my-auto h-full">
                    All Categories 
                    <svg class="w-2.5 h-2.5 ms-3 mt-1" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 10 6">
                    <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="m1 1 4 4 4-4"/>
                    </svg>
                </button>
                <div v-if="categoryisOpen" class="z-10 font-normal bg-white divide-y divide-gray-100 rounded-lg shadow-sm w-44 dark:bg-gray-700 dark:divide-gray-600 absolute mt-2">
                    <ul class="py-2 text-sm text-gray-700 dark:text-gray-200">
                    <li><a href="#" class="block px-4 py-2 hover:bg-gray-100 dark:hover:bg-gray-600 dark:hover:text-white">Category 1</a></li>
                    <li><a href="#" class="block px-4 py-2 hover:bg-gray-100 dark:hover:bg-gray-600 dark:hover:text-white">Category 2</a></li>
                    <li><a href="#" class="block px-4 py-2 hover:bg-gray-100 dark:hover:bg-gray-600 dark:hover:text-white">Category 3</a></li>
                    </ul>
                </div>
            </div>
            <div>
              <button class="bg-black block h-full px-3 rounded-r-md">
                <NuxtImg src="/images/icons/search.svg" class="w-8"/>
              </button>
            </div>

      </div>
      <div class="sm:flex hidden ml-4">
        <div class="flex my-auto">
          <NuxtImg src="/images/icons/account.svg" class="w-6 h-6" /> 
          <p>Account</p>
        </div>
        <div class="flex my-auto ml-4">
          <NuxtImg src="/images/icons/wishlist.svg" class="w-6 h-6" /> 
          <p>Wishlist</p>
        </div>
        <div class="flex my-auto ml-4">
          <NuxtImg src="/images/icons/cart.svg" class="w-6 h-6" /> 
          <p>Cart</p>
        </div>
      
      </div>
    </div>

    <div class="mt-2">
      <NuxtImg src="/images/roast-turkey.svg" class="w-full" />
    </div>

    <div class="lg:mx-36 md:mx-18 sm:mx-8 mt-16 text-center">
      <div class="text-[#F53E32] text-xl font-bold ">CUSTOMER FAVORITES</div>
      <div class="text-black text-6xl font-bold mt-4">Popular Catagories</div>
      <div class="sm:flex justify-between mt-20">
        <FavCategoriesCard
          
          v-for="(item, index) in favList"
          :key="index"
          :image="item.image"
          :title="item.title"
          :description="item.description"
        />
      </div>
    </div>

    <div class="lg:mx-36 md:mx-18 sm:mx-8 text-center mt-20">
    <div class="sm:flex justify-between">
      <div class="text-[#253D4E] pl-2 sm:pl-0 text-3xl">
        Daily Best Sells
      </div>
      <div class="flex">
        <div class="mb-4 b w-full sm:">
          <ul class="flex flex-wrap -mb-px text-sm font-medium sm:text-center justify-end" id="default-tab" role="tablist">
            <li  role="presentation">
              <button class="inline-block p-4 rounded-t-lg text-[#253D4E] text-xs" id="featured-tab" data-tabs-target="#featured" type="button" role="tab" aria-controls="featured" aria-selected="false">
                Featured
              </button>
            </li>
            <li  role="presentation">
              <button class="inline-block p-4 rounded-t-lg text-[#253D4E] text-xs" id="dashboard-tab" data-tabs-target="#dashboard" type="button" role="tab" aria-controls="dashboard" aria-selected="false">
                Popular
              </button>
            </li>
            <li  role="presentation">
              <button class="inline-block p-4 rounded-t-lg text-[#253D4E] text-xs" id="new-added-tab" data-tabs-target="#new-added" type="button" role="tab" aria-controls="new-added" aria-selected="false">
                New Added
              </button>
            </li>
          </ul>
        </div>
      </div>
    </div>

    <div class="flex">
      <div class="w-1/5 h-full">
        <NuxtImg src="/images/daily-best-saller.svg" class="w-full h-full hidden sm:block"/>
      </div>
      <div id="default-tab-content" class="sm:w-4/5 w-full">
        <div class="hidden sm:pl-4 pl-2 rounded-lg flex overflow-hidden w-full " id="featured" role="tabpanel" aria-labelledby="featured-tab">
          <BestSellerSlider :totalItems="bestSellerlist.length" :itemsPerPage="itemsPerPageBestSeller" :showDots="false" :autoplay="false">
            <BestSellerCard
              v-for="product in bestSellerlist"
              :key="product.title"
              :color="product.color"
              :tagText="product.tagText"
              :image="product.image"
              :title="product.title"
              :description="product.description"
              :newPrice="product.newPrice"
              :oldPrice="product.oldPrice"
              :sold="product.sold"
              :stock="product.stock"
              :rating="product.rating"
              class="w-1/4"
            />
          </BestSellerSlider>
          
          <div class="">
            <BestSeller
              :items="bestSellerlist" 
            />
          </div>
        </div>
        <div class="hidden px-4 rounded-lg flex" id="dashboard" role="tabpanel" aria-labelledby="dashboard-tab">
          <BestSeller class="ml-4 w-1/4"
            v-for="(item, index) in bestSellerlist"
            :key="index"
            :image="item.image"
            :title="item.title"
            :description="item.description"
            :color= "item.color"
            :tagText= "item.tagText"
            :newPrice= "item.newPrice"
            :oldPrice= "item.oldPrice"
            :sold= "item.sold"
            :stock= "item.stock"
            :rating= "item.rating"
          />
        </div>
        <div class="hidden px-4 rounded-lg flex" id="new-added" role="tabpanel" aria-labelledby="new-added-tab">
          <BestSeller class="ml-4 w-1/4"
            v-for="(item, index) in bestSellerlist"
            :key="index"
            :image="item.image"
            :title="item.title"
            :description="item.description"
            :color= "item.color"
            :tagText= "item.tagText"
            :newPrice= "item.newPrice"
            :oldPrice= "item.oldPrice"
            :sold= "item.sold"
            :stock= "item.stock"
            :rating= "item.rating"
          />
        </div>
      </div>
    </div>


    </div>

    <div class="lg:mx-36 md:mx-18 sm:mx-8 text-center mt-40">
      <div class="text-[#F53E32] mx-4 text-xl font-bold float-left ">CUSTOMER FAVORITES</div>
        <SpecialDishesSlider :totalItems="specialDishes.length" :itemsPerPage="itemsPerPageSpecialDishes" :showDots="false" :autoplay="false" class="sm:py-8 sm:mt-8">
          <div class="flex justify-between w-full pt-10 rounded-xl">
            <SpecialDishesCard
            v-for="(item, index) in specialDishes"
            :key="index"
            :image="item.image"
            :title="item.title"
            :description="item.description"
            :fav="item.fav"
            class="w-full mx-4"
            />
          </div>
        </SpecialDishesSlider>

    </div>

    <div class="lg:mx-36 md:mx-18 sm:mx-8 text-center mt-20">
      <div class="flex justify-between mx-4">
        <div class="text-[#253D4E] font-bold text-3xl">Deals Of The Day</div>
        <div class="text-[#7E7E7E] text-sm font-normal">
          All Deals >
        </div>
      </div>
      <div class="sm:flex mt-10">
        <DealsOfTheDay
            v-for="(item, index) in dealsList"
            :key="index"
            :image="item.image"
            :title="item.title"
            :score="item.score"
            :owner="item.owner"
            :newPrice="item.newPrice"
            :oldPrice="item.oldPrice"
            class="sm:w-1/4 mx-4"
            />
      </div>  
    </div>

    <div class="lg:mx-40 md:mx-18 sm:mx-8 text-center mt-20 px-2 sm:px-0 flex">
      <div class="sm:w-2/5 sm:p-4">
        <NuxtImg src="/images/choose-us/choose-us.svg" class="w-full rounded-xl hidden sm:block"/>
      </div>
      <div class="sm:w-3/5 pt-4">
        <div class="text-[#2D2D2D] font-bold text-5xl">
          Why People Choose us?
        </div>
        <div class="mt-4">
          <ChooseUs
            v-for="(item, index) in chooselist"
            :key="index"
            :image="item.image"
            :title="item.title"
            :description="item.description"
          />
        </div>

      </div>
    </div>

    <div class="bg-black lg:mx-36 md:mx-18 sm:mx-8 text-center mt-20 flex relative rounded-xl">
      <NuxtImg src="./images/Glow.svg" class="w-full rounded-xl"/>
      <div class="w-1/2 absolute sm:pt-16 sm:px-16 px-4 text-left">
        <div class="font-bold xl:text-4xl lg:text-3xl md:text-2xl sm:text-xl text-sm  text-white">Stay home & get your daily needs from our shop</div>
        <div class="font-normal flex sm:text-sm text-[0.5rem] text-gray-400 sm:mt-4 mt-2">
          <p>Start You'r Daily Shopping with </p>
          <p class="text-[#3BB77E] ml-1">Nest Mart</p>
        </div>
        <div class="bg-white rounded-full sm:mt-8 mt-2 flex sm:pr-4 pr-1 items-center">
          <NuxtImg src="/images/paperplane.jpg" class="w-4 h-4 sm:w-4 sm:h-4 ml-2"/>
          <input type="text" id="mail" class="text-gray-900 text-xs rounded-full block w-full border-0 focus:border-0 sm:p-2.5 p-1" placeholder="Your email address" required />
          <button class="bg-[#F53E32] flex rounded-full sm:px-4 px-2 sm:py-2.5 py-1">        
            <p class="text-white text-xs sm:text-lg">Subscribe</p>
          </button>
        </div>
      </div>
      <div class="absolute max-w-fit bottom-0 sm:right-16 right-4">
        <NuxtImg src="/images/stay-home-man.svg" class="xl:w-[500px] lg:w-[400px] md:w-[300px] sm:w-[200px] w-[150px]"/>
      </div>
    </div>

    <div class="lg:mx-36 md:mx-18 sm:mx-8 text-center mt-10 flex">
      <div class="sm:flex w-full">
        <TopFooterComp
            v-for="(item, index) in topFooterList"
            :key="index"
            :image="item.image"
            :title="item.title"
            :description="item.description"
            class="mx-1"
          />
      </div>
    </div>


  
    
  </div>
  </template>
  
  <script>

  export default {
    data() {
        return {
            categoryisOpen: false,
            favList: [
              {
                image: '/images/main-dish.svg',
                title: 'Main Dish',
                description: '86 dishes',
              },
              {
                image: '/images/break-fast.svg',
                title: 'Break Fast',
                description: '12 break fast',
              },
              {
                image: '/images/dessert.svg',
                title: 'Dessert',
                description: '48 dessert',
              },
              {
                image: '/images/browse-all.svg',
                title: 'Browse All',
                description: '255 Items',
              },
              {
                image: '/images/breakfast-food.svg',
                title: 'Breakfast Food',
                description: '205 Items',
              }
            ],
            bestSellerlist: [
              {
                color: 'bg-[#3BB77E]',
                tagText: 'Save 35%',
                image: '/images/chicken-meatballs.svg',
                title: 'Hodo Foods',
                description: 'All Natural Italian-Style Chicken Meatballs',
                newPrice: 238.85,
                oldPrice: 245.8,
                sold: 90,
                stock: 120,
                rating: 4
              },
              {
                color: 'bg-[#67BCEE]',
                tagText: 'Sale',
                image: '/images/boomchickapop.svg',
                title: 'Hodo Foods',
                description: 'Angie’s Boomchickapop Sweet and womnies',
                newPrice: 238.85,
                oldPrice: 245.8,
                sold: 60,
                stock: 120,
                rating: 1
              },
              {
                color: 'bg-[#F59758]',
                tagText: 'Best sale',
                image: '/images/crispy.svg',
                title: 'Hodo Foods',
                description: 'Foster Farms Takeout Crispy Classic',
                newPrice: 238.85,
                oldPrice: 245.8,
                sold: 90,
                stock: 120,
                rating: 1
              },
              {
                color: 'bg-[#F74B81]',
                tagText: 'Save 15%',
                image: '/images/lightly-salted.svg',
                title: 'Hodo Foods',
                description: 'Blue Diamond Almonds Lightly Salted',
                newPrice: 238.85,
                oldPrice: 245.8,
                sold: 90,
                stock: 120,
                rating: 1
              },
              {
                color: 'bg-[#F59758]',
                tagText: 'Best sale',
                image: '/images/crispy.svg',
                title: 'Hodo Foods',
                description: 'Foster Farms Takeout Crispy Classic',
                newPrice: 238.85,
                oldPrice: 245.8,
                sold: 90,
                stock: 120,
                rating: 1
              },
              {
                color: 'bg-[#F74B81]',
                tagText: 'Save 15%',
                image: '/images/lightly-salted.svg',
                title: 'Hodo Foods',
                description: 'Blue Diamond Almonds Lightly Salted',
                newPrice: 238.85,
                oldPrice: 245.8,
                sold: 90,
                stock: 120,
                rating: 1
              },
              {
                color: 'bg-[#F59758]',
                tagText: 'Best sale',
                image: '/images/crispy.svg',
                title: 'Hodo Foods',
                description: 'Foster Farms Takeout Crispy Classic',
                newPrice: 238.85,
                oldPrice: 245.8,
                sold: 90,
                stock: 120,
                rating: 1
              },
              {
                color: 'bg-[#F74B81]',
                tagText: 'Save 15%',
                image: '/images/lightly-salted.svg',
                title: 'Hodo Foods',
                description: 'Blue Diamond Almonds Lightly Salted',
                newPrice: 238.85,
                oldPrice: 245.8,
                sold: 90,
                stock: 120,
                rating: 1
              }
            ],
            specialDishes:[
              {
                image: '/images/salad/fattoush-salad.svg',
                title: 'Fattoush salad',
                description: 'Description of the item',
                fav: 'true'
              },
              {
                image: '/images/salad/vegetable-salad.svg',
                title: 'Vegetable salad',
                description: 'Description of the item',
                fav: 'false'
              },
              {
                image: '/images/salad/egg-salad.svg',
                title: 'Egg vegi salad',
                description: 'Description of the item',
                fav: 'true'
              },
              {
                image: '/images/salad/fattoush-salad.svg',
                title: 'Fattoush salad',
                description: 'Description of the item',
                fav: 'true'
              },
              {
                image: '/images/salad/vegetable-salad.svg',
                title: 'Vegetable salad',
                description: 'Description of the item',
                fav: 'false'
              },
              {
                image: '/images/salad/egg-salad.svg',
                title: 'Egg vegi salad',
                description: 'Description of the item',
                fav: 'false'
              }
            ],
            dealsList:[
              {
                image:'/images/deals/deals1.svg',
                title:'Seeds of Change Organic Quinoa, Brown, & Red Rice',
                score:'4.0',
                owner:'NestFood',
                newPrice:'32.85',
                oldPrice:'33.8'
              },
              {
                image:'/images/deals/deals2.svg',
                title:'Perdue Simply Smart Organics Gluten Free',
                score:'4.0',
                owner:'Old El Paso',
                newPrice:'24.85',
                oldPrice:'26.8'
              },
              {
                image:'/images/deals/deals3.svg',
                title:'Signature Wood-Fired Mushroom and Caramelized',
                score:'4.0',
                owner:'Progresso',
                newPrice:'12.85',
                oldPrice:'13.8'
              },
              {
                image:'/images/deals/deals4.svg',
                title:'Simply Lemonade with Raspberry Juice',
                score:'3.0',
                owner:'Yoplait',
                newPrice:'15.85',
                oldPrice:'16.8'
              }
            ],
            chooselist:[
              {
                image: '/images/choose-us/01.svg',
                title: 'Convenient and Reliable',
                description: 'Whether you dine in, take out, or order delivery, our service is convenient, fast, and reliable, making mealtime hassle-free.'
              },
              {
                image: '/images/choose-us/02.svg',
                title: 'Convenient and Reliable',
                description: 'From hearty meals to light snacks, we offer a wide range of options to suit every taste and craving.'
              },
              {
                image: '/images/choose-us/03.svg',
                title: 'Convenient and Reliable',
                description: 'Our burgers are grilled to perfection, with juicy patties and flavorful toppings that make every bite a delicious experience.'
              }

            ],
            topFooterList:[
              {
                image: '/images/best-price.svg',
                title: 'Best prices & offers',
                description: 'Orders $50 or more'
              },
              {
                image: '/images/free-delivery.svg',
                title: 'Free delivery',
                description: '24/7 amazing services'
              },
              {
                image: '/images/great-daily.svg',
                title: 'Great daily deal',
                description: 'When you sign up'
              },
              {
                image: '/images/wide.svg',
                title: 'Wide assortment',
                description: 'Mega Discounts'
              },
              {
                image: '/images/easy.svg',
                title: 'Easy returns',
                description: 'Within 30 days'
              }
            ],
            itemsPerPageBestSeller: 1,
            itemsPerPageSpecialDishes: 1

        }
    },
    methods: {
      setItemsPerPage() {
        console.log(window.innerWidth)
        if (window.innerWidth < 750) {
          
          this.itemsPerPageBestSeller = 1;
          this.itemsPerPageSpecialDishes = 1;
        } else {
          this.itemsPerPageBestSeller = 4;
          this.itemsPerPageSpecialDishes = 3;
        }
      },
      toggleDropdown() {
        this.categoryisOpen = !this.categoryisOpen       
      },
      handleClickOutside(event) {
              const dropdownElement = this.$refs['categoryDropDownContainer'];                
              if (this.categoryisOpen && dropdownElement && !dropdownElement.contains(event.target)) {
                  this.categoryisOpen = false;
              }
      }
    },
    mounted() {

      window.addEventListener('resize', this.setItemsPerPage);
      this.setItemsPerPage();
      

      document.addEventListener('click', this.handleClickOutside)
      const tabs = document.querySelectorAll('[role="tab"]');
      const tabContents = document.querySelectorAll('[role="tabpanel"]');

      tabs[0].setAttribute("aria-selected", "true");
      tabs[0].classList.add('text-[#3BB77E]')
      tabContents[0].classList.remove("hidden");

      tabs.forEach((tab) => {
        tab.addEventListener("click", (event) => {
          const targetTab = event.target;
          const targetContent = document.querySelector(
            targetTab.getAttribute("data-tabs-target")
          );

          tabs.forEach((item) => {
            item.setAttribute("aria-selected", "false");
            item.classList.remove('text-[#3BB77E]')

          });
          tabContents.forEach((content) => {
            content.classList.add("hidden");
          });

          targetTab.setAttribute("aria-selected", "true");
          targetTab.classList.add('text-[#3BB77E]')
          targetContent.classList.remove("hidden");
        });
      });
    },
    beforeDestroy() {
      window.removeEventListener('resize', this.setItemsPerPage);
    },
    beforeUnmount() {
        document.removeEventListener('click', this.handleClickOutside)
    },
  }
  </script>
  
  <style >
    #mail:focus {
      outline: none; 
      border: none; 
    }
    
    
  </style>