<template>
  <div class=" bg-white h-screen overflow-hidden">
    <!-- navbar section  -->
    <div class="relative">
      <TopBar/>
    </div>
    <!-- semi topnav -->
    <div class="bg-white h-full overflow-y-auto overflow-x-hidden -z-50">
      <div class=" p-2 pr-0 lg:mt-24 xl:mx-auto xl:container invisible lg:visible">
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
          <div class="input-group relative w-72 ml-10 mr-2 flex  items-center rounded-md border border-solid border-gray-300 focus-within:border-blue-600 focus-within:outline-none ">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 ml-2" fill="none" viewBox="0 0 24 24" stroke="#C1C1C1">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z" />
            </svg>
            <input type="search" class="form-control relative flex-auto min-w-0 block w-full px-3 py-1.5 text-base font-normal text-gray-700 bg-white bg-clip-padding  rounded-sm transition ease-out m-0 focus:bg-white focus:border-blue-600 focus:outline-none" placeholder="Search">
          </div>
        </div>

      </div>
      <hr class="invisible lg:visible"/>
      <!-- content section  -->
      <div class="xl:container xl:mx-auto lg:mt-4 mt-6 md:mt-12 p-1 ">
        <!-- content header  -->
        <div class="flex md:justify-between flex-wrap items-center ml-1 lg:ml-2 ">
          <!-- greeting  -->
          <div class="flex flex-col ">
            <h4 class="md:text-2xl text-xl">Welcome Back, Olivia</h4>
            <span class="text-gray-400 text-xs md:text-sm font-normal">Track, manage and forecast your customers and orders.</span>
          </div>
          <div class="flex mt-6 lg:mt-0">
            <button class="rounded bg-white border border-gray-400 px-2 py-1 text-sm flex items-center text-black">
              <svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4  mr-2" fill="none" viewBox="0 0 24 24" stroke="#303030">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M7 16a4 4 0 01-.88-7.903A5 5 0 1115.9 6L16 6a5 5 0 011 9.9M15 13l-3-3m0 0l-3 3m3-3v12" />
              </svg>
              Import</button>
              <button class="rounded bg-purple-700 border border-gray-400 px-2 py-1 text-sm flex items-center text-white ml-3 font-light">
              <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 font-light" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 6v6m0 0v6m0-6h6m-6 0H6" />
              </svg>
              Add</button>
          </div>
        </div>
        <!-- cards  -->
        <div class="grid grid-cols-1 md:grid-cols-3  gap-4  mt-6 p-1">
          <div class="shadow border border-gray-300 flex flex-col justify-between rounded p-4">
            <div class="flex justify-between text-sm items-center">
              <span class=" p-2">Total Customers</span>
              <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-gray-400" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 5v.01M12 12v.01M12 19v.01M12 6a1 1 0 110-2 1 1 0 010 2zm0 7a1 1 0 110-2 1 1 0 010 2zm0 7a1 1 0 110-2 1 1 0 010 2z" />
              </svg>
            </div>
            <div class="flex justify-between">
              <div class="flex flex-col">
                <div class="text-3xl p-2 font-semibold">2,420</div>
                <div class="flex text-xs md:text-sm items-center py-2">
                  <div class="text-green-500 flex items-center ">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M7 11l5-5m0 0l5 5m-5-5v12" />
                    </svg>
                    <span class="text-green-700">40%</span>
                  </div>
                  <span class="ml-2 text-gray-400">vs last month</span>
                </div>
              </div>
              <!-- curve div  -->
              <div class="flex flex-col relative min-h-full items-center">
                <div class="curve">
                  <Chart :chartdata="dataCollection"/>
                </div>
              </div>
            </div>

          </div>
           <!-- card two  -->
           <div class="shadow border border-gray-300 flex flex-col justify-between rounded p-4">
            <div class="flex justify-between text-sm items-center">
              <span class=" p-2">Members</span>
              <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-gray-400" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 5v.01M12 12v.01M12 19v.01M12 6a1 1 0 110-2 1 1 0 010 2zm0 7a1 1 0 110-2 1 1 0 010 2zm0 7a1 1 0 110-2 1 1 0 010 2z" />
              </svg>
            </div>
            <div class="flex justify-between">
              <div class="flex flex-col">
                <div class="text-3xl p-2 font-semibold">1,210</div>
                <div class="flex text-xs md:text-sm items-center">
                  <div class="text-red-500 flex items-center py-2">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17 13l-5 5m0 0l-5-5m5 5V6" />
                    </svg>
                    <span class="text-red-700" >10%</span>
                  </div>
                  <span class="ml-2 text-gray-400">vs last month</span>
                </div>
              </div>
              <!-- curve div  -->
              <div class="flex flex-col relative min-h-full items-center">
                <div class="curve">
                </div>
              </div>
            </div>

          </div>
          <!-- card three  -->
          <div class="shadow border border-gray-300 flex flex-col justify-between rounded p-4">
            <div class="flex justify-between text-sm items-center">
              <span class=" p-2">Active now</span>
              <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-gray-400" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 5v.01M12 12v.01M12 19v.01M12 6a1 1 0 110-2 1 1 0 010 2zm0 7a1 1 0 110-2 1 1 0 010 2zm0 7a1 1 0 110-2 1 1 0 010 2z" />
              </svg>
            </div>
            <div class="flex justify-between">
              <div class="flex flex-col">
                <div class="text-3xl p-2 font-semibold">316</div>
                <div class="flex text-xs md:text-sm items-center py-2">
                  <div class="text-green-500 flex items-center ">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M7 11l5-5m0 0l5 5m-5-5v12" />
                    </svg>
                    <span class="text-green-700">20%</span>
                  </div>
                  <span class="ml-2 text-gray-400">vs last month</span>
                </div>
              </div>
              <!-- curve div  -->
              <div class="flex flex-col relative min-h-full items-center">
                <div class="curve">
                </div>
              </div>
            </div>

          </div>

        </div>
        <!-- table options  -->
        <div class="md:flex md:justify-between  p-1 md:items-center md:grid-rows-none grid grid-rows-2">
          <!-- filters  -->
          <div class="md:flex order-last md:order-first md:grid-rows-none grid grid-rows-2  -mt-7 md:mt-0">
            <div class="flex md:order-first order-last">
              <button class="bg-purple-100 text-purple-500 rounded-2xl md:rounded-md text-xs flex items-center p-2 pt-0 pb-0  mt-4 font-light">
                <span>All time</span>
                <svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4 ml-1" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
                </svg>
              </button>
              <button  class="bg-purple-100 text-purple-500 rounded-2xl md:rounded-md text-xs flex items-center p-2  mt-4 ml-2 font-light">
                <span>AS, AU, +4</span>
                <svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4 ml-1" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
                </svg>
              </button>
            </div>
            <div>
              <button class="bg-white text-slate-600  rounded text-xs flex items-center justify-center md:justify-start p-3 mt-4 md:ml-2  border-slate-300 border md:w-fit w-full">
                <div class="flex flex-col items-center  ">
                  <span class="h-0.5 border-none w-3.5 outline-none bg-slate-600"></span>
                  <span class="h-0.5 border-none w-2.5 outline-none bg-slate-600 mt-1"></span>
                  <span class="h-0.5 border-none w-1.5 outline-none bg-slate-600 mt-1"></span>
                </div>
                <span class="ml-2">More filters</span>

              </button>
            </div>
          </div>
          <!-- search  -->
          <div class="input-group flex mb-6 md:mb-0  md:w-fit p-1 items-center rounded border border-solid border-gray-300   focus-within:border-blue-600 focus-within:outline-none md:mt-4  h-fit mt-6">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 ml-2" fill="none" viewBox="0 0 24 24" stroke="#C1C1C1">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z" />
            </svg>
            <input type="search" class="form-control relative flex-auto min-w-0 block w-full px-2 py-1 text-base font-normal text-gray-700 bg-white bg-clip-padding  rounded-sm transition ease-out m-0 focus:bg-white focus:border-blue-600 focus:outline-none" placeholder="Search">
          </div>

        </div>
        <!-- table area  -->
        <div class="mt-4 p-1 ">
          <Table/>
        </div>
      </div>

      <div>

      </div>
    </div>

  </div>
</template>
<script>

export default {
  name: 'Dashboard',

  data() {
    return {
      dataCollection: null
    }
  },
  mounted () {
    this.fillData()
  },
  methods: {
    fillData () {
      this.datacollection = {
        labels: [this.getRandomInt(), this.getRandomInt()],
        datasets: [
          {
            label: 'Data One',
            backgroundColor: '#f87979',
            data: [this.getRandomInt(), this.getRandomInt()]
          }, {
            label: 'Data One',
            backgroundColor: '#f87979',
            data: [this.getRandomInt(), this.getRandomInt()]
          }
        ]
      }
    },
    getRandomInt () {
      return Math.floor(Math.random() * (50 - 5 + 1)) + 5
    }
  }
}
</script>
