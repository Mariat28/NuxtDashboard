<template>
  <div class="p-4 bg-white shadow-md h-30 fixed top-0 container flex items-center justify-between">
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
      <div>
        <button class="bg-white border border-gray-300 rounded p-1 text-sm text-black pl-2 pr-3">Upgrade now</button>
      </div>

  </div>
</template>
