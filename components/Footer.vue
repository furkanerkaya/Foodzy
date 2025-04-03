<template>
    <div class="bg-[#F7F7F8] border-[1px] border-[#E9E9E9] pt-16 lg:px-52 md:px-24 sm:px-12 px-4 relative mt-16">
        <NuxtImg src="/images/footer/tomato.svg" class="absolute -top-4 lg:right-32 md:right-20 sm:right-12 right-2 w-16" />
        <NuxtImg src="/images/footer/pepper.svg" class="absolute bottom-4 lg:right-36 md:right-28 sm:right-14 right-3 w-24" />
        <NuxtImg src="/images/footer/lemon.svg" class="absolute top-1/2 left-2 w-16" />
        <div class="">
            <div class="sm:flex py-10">
                <div class="sm:w-1/3">
                    <div class="flex">
                        <NuxtImg src="/images/logo/foodzy-logo.svg" class="w-12"/>
                        <div class="my-auto">
                            <p class="font-black text-lg">Foodzy</p>
                            <p class="font-semibold text-[0.5rem]">A Treasure of Tastes</p>
                        </div>
                    </div>
                    <div class="text-[#7A7A7A] font-normal text-sm">
                        FoodTrove is the biggest market of grocery products. Get your daily needs from our store.
                    </div>
                    <div class="flex mt-4 items-start">
                        <NuxtImg src="/images/footer/location.svg" class="w-5 mt-1"/>
                        <div class="ml-2 text-[#777777] font-normal ">
                            51 Green St.Huntington ohaio beach ontario, NY 11746 KY 4783, USA.
                        </div>
                    </div>
                    <div class="flex mt-2">
                        <NuxtImg src="/images/footer/mail.svg" class="w-5"/>
                        <div class="ml-2 text-[#777777] font-normal ">
                            example@email.com
                        </div>
                    </div>
                    <div class="flex mt-2">
                        <NuxtImg src="/images/footer/footer-phone.svg" class="w-5"/>
                        <div class="ml-2 text-[#777777] font-normal ">
                            +91 123 4567890
                        </div>
                    </div>
                    
                </div>
                <div class="sm:w-1/3 flex ml-2 mt-4 sm:mt-0">
                    <div class="w-1/2 ">
                        <div>
                            <p class="font-black text-lg">Company</p>
                            <div class="text-[#7A7A7A] font-normal text-sm">
                                <p class="mt-3">About Us</p>
                                <p class="mt-3">Delivery Information</p>
                                <p class="mt-3">Privacy Policy</p>
                                <p class="mt-3">Terms & Conditions</p>
                                <p class="mt-3">Contact Us</p>
                                <p class="mt-3">Support Center</p>
                            </div>
                        </div>
                    </div>
                    <div class="w-1/2">
                        <div>
                            <p class="font-black text-lg">Category</p>
                            <div class="text-[#7A7A7A] font-normal text-sm">
                                <p class="mt-3">Dairy & Bakery</p>
                                <p class="mt-3">Fruits & Vegetable</p>
                                <p class="mt-3">Snack & Spice</p>
                                <p class="mt-3">Juice & Drinks</p>
                                <p class="mt-3">Chicken & Meat</p>
                                <p class="mt-3">Fast Food</p>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="sm:w-1/3 sm:mt-0 mt-4">
                    <div>
                        <p class="font-black text-lg">Subscribe Our Newsletter</p>
                        <div class="mt-3 bg-white flex rounded-md">
                            <input type="text" id="footerSearch" class="text-gray-900 text-xs rounded-md block w-full p-2.5" placeholder="Search here..." required />
                            <NuxtImg src="/images/footer/paperplane.svg" class="w-4 mr-2"/>
                        </div>
                        <div class="flex mt-4">
                            <div class="bg-white p-2 rounded-md">
                                <NuxtImg src="/images/footer/facebook.svg" class="w-4 "/>                        
                            </div>
                            <div class="bg-white p-2 rounded-md ml-2">
                                <NuxtImg src="/images/footer/x.svg" class="w-4 "/>                        
                            </div>
                            <div class="bg-white p-2 rounded-md ml-2">
                                <NuxtImg src="/images/footer/Icon.svg" class="w-4 "/>                        
                            </div>
                            <div class="bg-white p-2 rounded-md ml-2">
                                <NuxtImg src="/images/footer/instagram.svg" class="w-4 "/>                        
                            </div>
                        </div>
                        <div class="flex mt-4">
                            <div class="rounded-md w-1/5">
                                <NuxtImg src="/images/footer/1.svg" class="w-full rounded-md"/>                        
                            </div>
                            <div class="rounded-md w-1/5 ml-2">
                                <NuxtImg src="/images/footer/2.svg" class="w-full rounded-md"/>                        
                            </div>
                            <div class="rounded-md w-1/5 ml-2">
                                <NuxtImg src="/images/footer/3.svg" class="w-full rounded-md"/>                        
                            </div>
                            <div class="rounded-md w-1/5 ml-2">
                                <NuxtImg src="/images/footer/2.svg" class="w-full rounded-md"/>                        
                            </div>
                            <div class="rounded-md w-1/5 ml-2">
                                <NuxtImg src="/images/footer/5.svg" class="w-full rounded-md"/>                        
                            </div>
                            
                        </div>
                    </div>
                    
                </div>
            </div>
            <div class="border-t-[1px] border-[#E9E9E9] w-full flex justify-center py-4">
                <p class="text-xs font-normal text-black">© 2025</p>
                <p class="text-xs font-normal text-[#F53E32] ml-1">Foodzy</p>
                <p class="text-xs font-normal text-black">, All rights reserved.</p>
                
            </div>
        </div>
    </div>
</template>

<script>



</script>
<style>
    #footerSearch:focus {
      outline: none; 
      border: none; 
    }
</style>