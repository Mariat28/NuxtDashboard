<template>
  <div class=" bg-white h-screen ">
    <!-- navbar section  -->
    <div class="relative">
      <TopBar/>
      <hr class="mt-24"/>
      <div class=" p-4 pl-8">
        <div class="  text-black mx-auto container text-base">
          <NuxtLink to="/" >Overview</NuxtLink>
          <NuxtLink to="/" class="pl-2" >Notifications</NuxtLink>
          <NuxtLink to="/" class="pl-2" >Analytics</NuxtLink>
          <NuxtLink to="/" class="pl-2" >Saved Reports</NuxtLink>
          <NuxtLink to="/" class="pl-2" >Trade history</NuxtLink>
          <NuxtLink to="/" class="pl-2" >User reports</NuxtLink>
        </div>
        <div>
        </div>
      </div>
    </div>
  </div>
</template>
