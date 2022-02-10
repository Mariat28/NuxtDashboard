<template>
  <div class=" bg-white h-screen overflow-hidden">
    <!-- navbar section  -->
    <div class="relative">
      <TopBar/>
    </div>
    <!-- semi topnav -->
    <div class="bg-white h-full overflow-y-auto">
      <div class=" p-4 pr-0 lg:mt-24 xl:mx-auto container invisible lg:visible">
        <div class=" flex justify-between">
          <div class="text-sm flex items-center  pl-0">
            <div class="bg-gray-100 rounded p-2"><NuxtLink to="/" >Overview</NuxtLink></div>
            <NuxtLink to="/" class="pl-3" >Notifications</NuxtLink>
            <NuxtLink to="/" class="pl-3" >Analytics</NuxtLink>
            <NuxtLink to="/" class="pl-3" >Saved Reports</NuxtLink>
            <NuxtLink to="/" class="pl-3" >Trade history</NuxtLink>
            <NuxtLink to="/" class="pl-3" >User reports</NuxtLink>
          </div>
          <!-- right search  -->
          <div class="input-group relative w-72 ml-10 mr-2 flex  items-center rounded border border-solid border-gray-300 focus-within:border-blue-600 focus-within:outline-none">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 ml-2" fill="none" viewBox="0 0 24 24" stroke="#C1C1C1">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z" />
            </svg>
            <input type="search" class="form-control relative flex-auto min-w-0 block w-full px-3 py-1.5 text-base font-normal text-gray-700 bg-neutral-50 bg-clip-padding  rounded-sm transition ease-out m-0 focus:bg-white focus:border-blue-600 focus:outline-none" placeholder="Search">
          </div>
        </div>

      </div>
      <hr class="invisible lg:visible"/>
      <!-- content section  -->
      <div class="lg:container lg:mx-auto lg:mt-4 mt-12">
        <!-- content header  -->
        <div class="flex md:justify-between flex-wrap items-center ml-2 lg:ml-0">
          <!-- greeting  -->
          <div class="flex flex-col ">
            <h4 class="md:text-2xl text-xl">Welcome Back, Olivia</h4>
            <span class="text-gray-400 text-sm font-normal">Track, manage and forecast your customers and orders.</span>
          </div>
          <div class="flex mt-4 lg:mt-0">
            <button class="rounded bg-white border border-gray-400 pl-3 pr-3 p-1 text-sm flex items-center text-black">
              <svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4  mr-2" fill="none" viewBox="0 0 24 24" stroke="#303030">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M7 16a4 4 0 01-.88-7.903A5 5 0 1115.9 6L16 6a5 5 0 011 9.9M15 13l-3-3m0 0l-3 3m3-3v12" />
              </svg>
              Import</button>
              <button class="rounded bg-purple-700 border border-gray-400 pl-2 pr-3 p-1 text-sm flex items-center text-white ml-3 font-light">
              <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 font-light" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 6v6m0 0v6m0-6h6m-6 0H6" />
              </svg>
              Add</button>
          </div>
        </div>
      </div>

      <div>

      </div>
    </div>

  </div>
</template>
