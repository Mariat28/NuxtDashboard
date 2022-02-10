<template>
  <div class="p-4 bg-white h-30 fixed top-0 flex items-center justify-between container inset-x-0 xl:mx-auto">
    <!-- leftside menu  -->
    <div class="flex items-center">
      <!-- logo  -->
      <div class="flex items-center">
          <div class="rounded-sm h-10 w-10 bg-blue-100">
            <!-- icon div  -->
          </div>
          <span class="text-black font-semibold text-base ml-2">Untitled UI</span>
      </div>
      <!-- navlinks  -->
      <div class="ml-4 text-sm text-black">
        <NuxtLink to="/" >Home</NuxtLink>
        <NuxtLink to="/dashboard" class="pl-2">Dashboard</NuxtLink>
        <NuxtLink to="/projects" class="pl-2">Projects</NuxtLink>
        <NuxtLink to="/tasks" class="pl-2">Tasks</NuxtLink>
        <NuxtLink to="/reports" class="pl-2">Reporting</NuxtLink>
        <NuxtLink to="/users" class="pl-2">Users</NuxtLink>
      </div>
    </div>
      <!-- rightside menu  -->
      <div class="flex items-center p-1">
        <button class="bg-white border border-gray-300 rounded p-2  pl-2 pr-3 flex items-center">
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
</template>
