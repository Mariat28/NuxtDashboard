<template>
  <div class="p-0 bg-white h-24 fixed top-0  inset-x-0 w-screen flex flex-col justify-center">
    <div class="xl:container xl:mx-auto flex items-center justify-between p-1">
      <!-- leftside menu  -->
      <div class="flex items-center">
        <!-- logo  -->
          <div class="flex items-center">
            <div class="rounded-sm h-10 w-10 bg-blue-100">
              <!-- icon div  -->
            </div>
            <div class="text-black font-semibold text-base ml-2 min-w-fit flex">
             <span>Untitled</span>
             <span class="ml-2">UI</span>
            </div>
          </div>
        <!-- hamburger menu -->

          <div class="flex flex-col justify-center items-center" >
            <div class=" lg:invisible flex flex-col mr-2 visible absolute right-0 " @click="openMenu" v-if="!isOpen">
              <div class=" lg:invisible flex flex-col mr-2 visible absolute right-0">
              <span class="h-0.5 border-none w-6 outline-none bg-black"></span>
              <span class="h-0.5 border-none w-4 outline-none bg-black mt-2"></span>
              <span class="h-0.5 border-none w-6 outline-none bg-black mt-2"></span>
              </div>
            </div>
          <div class=" lg:invisible flex flex-col mr-2 visible absolute right-0"  @click="closeMenu" v-else>
            <span class="h-4  w-6 outline-none text-black text-4xl cursor-pointer" >x</span>
          </div>
            <!-- expanded nav  -->
            <div class="h-64 w-64 shadow-lg bg-white rounded-md absolute right-0 top-16 mr-2 flex flex-col justify-between text-lg transition ease-in-out delay-150 duration-300" v-if="isOpen" :class="[isOpen ? 'transition-y-6' : '']">
              <NuxtLink to="/" class="p-2 text-center cursor-pointer hover:text-blue-900 hover:animate-pulse">Home</NuxtLink>
              <NuxtLink to="/dashboard" class="p-2 text-center hover:text-blue-900">Dashboard</NuxtLink>
              <NuxtLink to="/projects" class="p-2 text-center hover:text-blue-900">Projects</NuxtLink>
              <NuxtLink to="/tasks" class="p-2 text-center hover:text-blue-900">Tasks</NuxtLink>
              <NuxtLink to="/reports" class="p-2 text-center hover:text-blue-900">Reporting</NuxtLink>
              <NuxtLink to="/users" class="p-2 text-center hover:text-blue-900">Users</NuxtLink>
            </div>
          </div>
        <!-- navlinks  -->
        <div class="ml-4 text-sm text-black invisible lg:visible">
          <NuxtLink to="/" >Home</NuxtLink>
          <NuxtLink to="/dashboard" class="pl-2">Dashboard</NuxtLink>
          <NuxtLink to="/projects" class="pl-2">Projects</NuxtLink>
          <NuxtLink to="/tasks" class="pl-2">Tasks</NuxtLink>
          <NuxtLink to="/reports" class="pl-2">Reporting</NuxtLink>
          <NuxtLink to="/users" class="pl-2">Users</NuxtLink>
        </div>
      </div>
        <!-- rightside menu  -->
          <div class="flex items-center p-0 invisible lg:visible">
            <button class="bg-white border mr-6 border-gray-300 rounded p-2  pl-2 pr-3 flex items-center">
              <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 mr-1 text-gray-500 text-sm font-normal" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 10V3L4 14h7v7l9-11h-7z" />
              </svg>
              <span class="text-black text-base ">Upgrade now</span>
            </button>
            <div>
              <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 ml-4 text-gray-500 text-sm font-normal" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10.325 4.317c.426-1.756 2.924-1.756 3.35 0a1.724 1.724 0 002.573 1.066c1.543-.94 3.31.826 2.37 2.37a1.724 1.724 0 001.065 2.572c1.756.426 1.756 2.924 0 3.35a1.724 1.724 0 00-1.066 2.573c.94 1.543-.826 3.31-2.37 2.37a1.724 1.724 0 00-2.572 1.065c-.426 1.756-2.924 1.756-3.35 0a1.724 1.724 0 00-2.573-1.066c-1.543.94-3.31-.826-2.37-2.37a1.724 1.724 0 00-1.065-2.572c-1.756-.426-1.756-2.924 0-3.35a1.724 1.724 0 001.066-2.573c-.94-1.543.826-3.31 2.37-2.37.996.608 2.296.07 2.572-1.065z" />
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 12a3 3 0 11-6 0 3 3 0 016 0z" />
              </svg>
            </div>
            <div>
              <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 ml-4 text-gray-500 text-sm font-normal" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 17h5l-1.405-1.405A2.032 2.032 0 0118 14.158V11a6.002 6.002 0 00-4-5.659V5a2 2 0 10-4 0v.341C7.67 6.165 6 8.388 6 11v3.159c0 .538-.214 1.055-.595 1.436L4 17h5m6 0v1a3 3 0 11-6 0v-1m6 0H9" />
              </svg>
            </div>
            <div class="rounded-full h-12 w-12  ml-4 overflow-hidden flex justify-center">
              <img src="../assets/images/profile.png" alt="profile Image" class="rounded-full"/>
            </div>
          </div>

    </div>
    <hr class="md:mt-4 -mt-4 w-full">
  </div>
</template>
<script>
export default {
  name: 'TopBar',
  data() {
    return {
      isOpen: false,
    }
  },
  methods:{
    openMenu() {
      this.isOpen = true;
    },
    closeMenu() {
      this.isOpen = false;

    }
  }
}
</script>
