<template>
  <div class="flex flex-col shadow-md rounded-lg border border-slate-300 w-full">
    <div class="-my-2 overflow-x-auto sm:-mx-6 lg:-mx-8 ">
      <div class="py-2 align-middle inline-block min-w-full sm:px-6 lg:px-8 ">
        <div class="shadow overflow-hidden border-b border-gray-200 sm:rounded-lg ">
          <table class="min-w-full divide-y divide-gray-200 ">
            <thead class="bg-white">
              <tr class="">
                <th scope="col" class="px-6 py-3 text-left text-sm font-medium text-slate-700  tracking-wider">
                  <div class="form-check">
                    <input class="form-check-input appearance-none h-4 w-4 border border-gray-300 rounded bg-white checked:bg-blue-600 checked:border-blue-600 focus:outline-none transition duration-200 mt-1 align-top bg-no-repeat bg-center bg-contain float-left mr-2 cursor-pointer" type="checkbox" value="" id="flexCheckIndeterminate">
                    <label class="form-check-label inline-block text-gray-800" for="flexCheckIndeterminate">
                      Company
                    </label>
                  </div>
                  </th>
                <th scope="col" class="px-6 py-3 text-left text-sm font-medium text-slate-700  tracking-wider">License use</th>
                <th scope="col" class="px-6 py-3 text-left text-sm font-medium text-slate-700  tracking-wider">Status</th>
                <th scope="col" class="px-6 py-3 text-left text-sm font-medium text-slate-700  tracking-wider">Users</th>
                <th scope="col" class="px-6 py-3 text-left text-sm font-medium text-slate-700  tracking-wider">About</th>
                <th scope="col" class="relative px-6 py-3">
                  <span class="sr-only">Edit</span>
                </th>
              </tr>
            </thead>
            <tbody class="bg-white divide-y divide-gray-200">
              <tr v-for="company in companies" :key="company.email" class="odd:bg-white even:bg-gray-50">
                <td class="px-6 py-4 whitespace-nowrap flex items-center">
                    <input class="form-check-input appearance-none h-4 w-4 border border-gray-300 rounded bg-white checked:bg-blue-600 checked:border-blue-600 focus:outline-none transition duration-200 mt-1 align-top bg-no-repeat bg-center bg-contain float-left mr-2 cursor-pointer" type="checkbox" value="" id="flexCheckIndeterminate">
                  <div class="flex items-center">
                    <div class="flex-shrink-0 h-10 w-10">
                      <img class="h-10 w-10 rounded-full" :src="company.image" alt="" />
                    </div>
                    <div class="ml-4">
                      <div class="text-sm font-medium text-gray-900">
                        {{ company.company }}
                      </div>
                      <div class="text-sm text-gray-500">
                        {{ company.domain }}
                      </div>
                    </div>
                  </div>
                </td>
                <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500">
                  <div class="w-full bg-gray-100 rounded-full h-1.5 dark:bg-gray-700">
                  <div class="bg-purple-600 h-1.5 rounded-full" :style="{width: company.license + '%'}"></div>
                  </div>
                </td>
                <td class="px-6 py-4 whitespace-nowrap">
                  <span class="px-2 inline-flex text-xs leading-5 font-semibold rounded-full bg-green-100 text-green-800" :class="['']"> {{company.status}} </span>
                </td>
                <td class="text-sm text-gray-500 inline-block text-start" >
                  <div class=" flex -space-x-4 items-center" >
                    <div  v-for="(user, index) in company.users.slice(0, 5)" :key="index" class="rounded-full h-10 w-10 ">
                      <img class="inline-block h-8 w-8 rounded-full ring-2 ring-white" :src="user" alt="user-profiles">
                    </div>
                    <div class="rounded-full h-6 w-6 bg-purple-50 text-purple-700 ring-2 ring-white flex items-center text-xs font-semibold" v-if="company.users.length > 5" >
                      +{{(company.users.length) - 5}}
                    </div>
                  </div>
                  
                </td>

                <td class="px-6 py-4 whitespace-nowrap">
                  <div class="text-sm text-slate-700 font-semibold">{{ company.title }}</div>
                  <div class="text-sm text-gray-500">{{ company.description }}</div>
                </td>
                <td class="px-6 py-4 whitespace-nowrap text-right text-sm text-gray-400 flex flex-wrap items-center ">
                  <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 7l-.867 12.142A2 2 0 0116.138 21H7.862a2 2 0 01-1.995-1.858L5 7m5 4v6m4-6v6m1-10V4a1 1 0 00-1-1h-4a1 1 0 00-1 1v3M4 7h16" />
                  </svg>
                  <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 ml-2" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15.232 5.232l3.536 3.536m-2.036-5.036a2.5 2.5 0 113.536 3.536L6.5 21.036H3v-3.572L16.732 3.732z" />
                  </svg>
                </td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
const companies = [
  {
    company: 'Catalog',
    domain: ' catalogApp.io',
    status:'customer',
    license: 75,
    image:
      'https://images.unsplash.com/photo-1494790108377-be9c29b29330?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=4&w=256&h=256&q=60',
    title: 'Content Curating App',
    description: 'Brings all your news into one place',
    users: [
      'https://media.istockphoto.com/photos/headshot-studio-portrait-of-a-woman-in-profile-looking-at-the-camera-picture-id1305462732?k=20&m=1305462732&s=612x612&w=0&h=PSb7E99OQKJZ1XVr4BD_708517mNagc0adFFX_FfFGc=',
      'https://media.istockphoto.com/photos/overjoyed-pretty-asian-woman-look-at-camera-with-sincere-laughter-picture-id1311084168?b=1&k=20&m=1311084168&s=170667a&w=0&h=mE8BgXPgcHO1UjSmdWYa21NIKDzJvMrjOffy39Ritpo=',
      'https://media.istockphoto.com/photos/pleasant-young-indian-woman-freelancer-consult-client-via-video-call-picture-id1300972573?k=20&m=1300972573&s=612x612&w=0&h=Tiwi8Y0q8FBg8nL0i5GL_GslELTVLKkEB2e6m63Jlcg=',
      'https://media.istockphoto.com/photos/headshot-portrait-of-smiling-female-employee-posing-in-office-picture-id1318858332?k=20&m=1318858332&s=612x612&w=0&h=MQk8yiNlqpigOKaC6Uam8bhAir5HKpHzQLYRwCnUCLM=',
      'https://media.istockphoto.com/photos/young-woman-wearing-casual-red-sweater-over-isolated-background-away-picture-id1127788799?k=20&m=1127788799&s=612x612&w=0&h=9WIDo4rWeAVslYoDpKGRwP5HcIvzDFlh2kErQr7aiGo=',
      'https://media.istockphoto.com/photos/portrait-of-successful-black-male-modern-day-student-holding-picture-id1311634222?k=20&m=1311634222&s=612x612&w=0&h=1a0XDWnZNPjk_5n7maZdzowaDfBcBohwoiZZF69qS9A=',
      'https://media.istockphoto.com/photos/smile-girl-at-beach-picture-id477151294?k=20&m=477151294&s=612x612&w=0&h=iyF969N8EY2J23HlWC2K-Calrcsqgmh3e-AjYfbioVg=',
      'https://media.istockphoto.com/photos/millennial-male-team-leader-organize-virtual-workshop-with-employees-picture-id1300972574?b=1&k=20&m=1300972574&s=170667a&w=0&h=2nBGC7tr0kWIU8zRQ3dMg-C5JLo9H2sNUuDjQ5mlYfo=',
      'https://media.istockphoto.com/photos/headshot-portrait-of-smiling-ethnic-businessman-in-office-picture-id1300512215?b=1&k=20&m=1300512215&s=170667a&w=0&h=LsZL_-vvAHB2A2sNLHu9Vpoib_3aLLkRamveVW3AGeQ=',
      'https://images.unsplash.com/photo-1438761681033-6461ffad8d80?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxzZWFyY2h8MTB8fG1hbiUyMHByb2ZpbGUlMjBpbWFnZXxlbnwwfHwwfHw%3D&auto=format&fit=crop&w=600&q=60',
      'https://media.istockphoto.com/photos/headshot-portrait-of-smiling-ethnic-businessman-in-office-picture-id1300512215?b=1&k=20&m=1300512215&s=170667a&w=0&h=LsZL_-vvAHB2A2sNLHu9Vpoib_3aLLkRamveVW3AGeQ=',
      'https://media.istockphoto.com/photos/portrait-of-a-girl-picture-id938709362?b=1&k=20&m=938709362&s=170667a&w=0&h=7kbyEr_hujTNDsvQ629eb1mQbYCBTdIFy-Fb24DjTg4=',
      'https://images.unsplash.com/photo-1494790108377-be9c29b29330?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxzZWFyY2h8Mnx8cHJvZmlsZSUyMGltYWdlfGVufDB8fDB8fA%3D%3D&auto=format&fit=crop&w=600&q=60'
    ]
  },
    {
    company: 'Circooles',
    domain: ' getCircooles.com',
    status:'churned',
    license: 45,
    image:
      'https://images.unsplash.com/photo-1494790108377-be9c29b29330?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=4&w=256&h=256&q=60',
    title: 'Design Software',
    description: 'Super light weight design app',
      users: [
        'https://images.unsplash.com/photo-1494790108377-be9c29b29330?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxzZWFyY2h8Mnx8cHJvZmlsZSUyMGltYWdlfGVufDB8fDB8fA%3D%3D&auto=format&fit=crop&w=600&q=60',
        'https://images.unsplash.com/photo-1556157382-97eda2d62296?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxzZWFyY2h8NXx8cHJvZmlsZSUyMGltYWdlfGVufDB8fDB8fA%3D%3D&auto=format&fit=crop&w=600&q=60',
        'https://media.istockphoto.com/photos/millennial-male-team-leader-organize-virtual-workshop-with-employees-picture-id1300972574?b=1&k=20&m=1300972574&s=170667a&w=0&h=2nBGC7tr0kWIU8zRQ3dMg-C5JLo9H2sNUuDjQ5mlYfo=',
        'https://media.istockphoto.com/photos/headshot-portrait-of-smiling-ethnic-businessman-in-office-picture-id1300512215?b=1&k=20&m=1300512215&s=170667a&w=0&h=LsZL_-vvAHB2A2sNLHu9Vpoib_3aLLkRamveVW3AGeQ=',
        'https://images.unsplash.com/photo-1438761681033-6461ffad8d80?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxzZWFyY2h8MTB8fG1hbiUyMHByb2ZpbGUlMjBpbWFnZXxlbnwwfHwwfHw%3D&auto=format&fit=crop&w=600&q=60',
        'https://media.istockphoto.com/photos/headshot-portrait-of-smiling-ethnic-businessman-in-office-picture-id1300512215?b=1&k=20&m=1300512215&s=170667a&w=0&h=LsZL_-vvAHB2A2sNLHu9Vpoib_3aLLkRamveVW3AGeQ=',
        'https://media.istockphoto.com/photos/portrait-of-a-girl-picture-id938709362?b=1&k=20&m=938709362&s=170667a&w=0&h=7kbyEr_hujTNDsvQ629eb1mQbYCBTdIFy-Fb24DjTg4=',
        'https://images.unsplash.com/photo-1494790108377-be9c29b29330?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxzZWFyY2h8Mnx8cHJvZmlsZSUyMGltYWdlfGVufDB8fDB8fA%3D%3D&auto=format&fit=crop&w=600&q=60',
        'https://media.istockphoto.com/photos/headshot-portrait-of-smiling-ethnic-businessman-in-office-picture-id1300512215?b=1&k=20&m=1300512215&s=170667a&w=0&h=LsZL_-vvAHB2A2sNLHu9Vpoib_3aLLkRamveVW3AGeQ=',
        'https://media.istockphoto.com/photos/portrait-of-a-girl-picture-id938709362?b=1&k=20&m=938709362&s=170667a&w=0&h=7kbyEr_hujTNDsvQ629eb1mQbYCBTdIFy-Fb24DjTg4=',
      
    ]
  },
    {
    company: 'Command+R',
    domain: 'cmdr.io',
    status:'customer',
    license: 25,
    image:
      'https://images.unsplash.com/photo-1494790108377-be9c29b29330?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=4&w=256&h=256&q=60',
    title: 'Data prediction',
    description: 'AI and machine learning data',
    users: [
      'https://images.unsplash.com/photo-1558203728-00f45181dd84?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxzZWFyY2h8MTB8fHByb2ZpbGUlMjBpbWFnZXxlbnwwfHwwfHw%3D&auto=format&fit=crop&w=600&q=60',
      'https://images.unsplash.com/photo-1600275669283-4bf2bb8a990c?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxzZWFyY2h8MTZ8fHByb2ZpbGUlMjBpbWFnZXxlbnwwfHwwfHw%3D&auto=format&fit=crop&w=600&q=60',
      'https://media.istockphoto.com/photos/millennial-male-team-leader-organize-virtual-workshop-with-employees-picture-id1300972574?b=1&k=20&m=1300972574&s=170667a&w=0&h=2nBGC7tr0kWIU8zRQ3dMg-C5JLo9H2sNUuDjQ5mlYfo=',
      'https://media.istockphoto.com/photos/headshot-portrait-of-smiling-ethnic-businessman-in-office-picture-id1300512215?b=1&k=20&m=1300512215&s=170667a&w=0&h=LsZL_-vvAHB2A2sNLHu9Vpoib_3aLLkRamveVW3AGeQ=',
      'https://images.unsplash.com/photo-1438761681033-6461ffad8d80?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxzZWFyY2h8MTB8fG1hbiUyMHByb2ZpbGUlMjBpbWFnZXxlbnwwfHwwfHw%3D&auto=format&fit=crop&w=600&q=60',
      'https://media.istockphoto.com/photos/headshot-portrait-of-smiling-ethnic-businessman-in-office-picture-id1300512215?b=1&k=20&m=1300512215&s=170667a&w=0&h=LsZL_-vvAHB2A2sNLHu9Vpoib_3aLLkRamveVW3AGeQ=',
      'https://media.istockphoto.com/photos/portrait-of-a-girl-picture-id938709362?b=1&k=20&m=938709362&s=170667a&w=0&h=7kbyEr_hujTNDsvQ629eb1mQbYCBTdIFy-Fb24DjTg4=',
      'https://images.unsplash.com/photo-1494790108377-be9c29b29330?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxzZWFyY2h8Mnx8cHJvZmlsZSUyMGltYWdlfGVufDB8fDB8fA%3D%3D&auto=format&fit=crop&w=600&q=60'
    
    ]
  },
      {
    company: 'Hourglass',
    domain: 'hourglass.app',
    status:'customer',
    license: 75,
    image:
      'https://images.unsplash.com/photo-1582558008094-75a4f90a8553?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=435&q=80',
    title: 'Productivity app',
    description: 'Time management and productivity',
    users: [
      'https://media.istockphoto.com/photos/millennial-male-team-leader-organize-virtual-workshop-with-employees-picture-id1300972574?b=1&k=20&m=1300972574&s=170667a&w=0&h=2nBGC7tr0kWIU8zRQ3dMg-C5JLo9H2sNUuDjQ5mlYfo=',
      'https://media.istockphoto.com/photos/headshot-portrait-of-smiling-ethnic-businessman-in-office-picture-id1300512215?b=1&k=20&m=1300512215&s=170667a&w=0&h=LsZL_-vvAHB2A2sNLHu9Vpoib_3aLLkRamveVW3AGeQ=',
      'https://images.unsplash.com/photo-1438761681033-6461ffad8d80?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxzZWFyY2h8MTB8fG1hbiUyMHByb2ZpbGUlMjBpbWFnZXxlbnwwfHwwfHw%3D&auto=format&fit=crop&w=600&q=60',
      'https://media.istockphoto.com/photos/headshot-portrait-of-smiling-ethnic-businessman-in-office-picture-id1300512215?b=1&k=20&m=1300512215&s=170667a&w=0&h=LsZL_-vvAHB2A2sNLHu9Vpoib_3aLLkRamveVW3AGeQ=',
      'https://media.istockphoto.com/photos/portrait-of-a-girl-picture-id938709362?b=1&k=20&m=938709362&s=170667a&w=0&h=7kbyEr_hujTNDsvQ629eb1mQbYCBTdIFy-Fb24DjTg4=',
    
    ]
  },
      {
    company: 'Layers',
    domain: 'getlayers.io',
    status:'churned',
    license: 25,
    image:
      'https://images.unsplash.com/photo-1494790108377-be9c29b29330?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=4&w=256&h=256&q=60',
    title: 'Web app integrations',
    description: 'Connect web apps seamlessly',
    users: [
      'https://media.istockphoto.com/photos/head-shot-portrait-of-smiling-businesswoman-intern-looking-at-camera-picture-id1329936184?k=20&m=1329936184&s=612x612&w=0&h=gPfefUqxMNKnTO6EA_MoGA198uiC6w_UfzYYxCkysEI=',
      'https://media.istockphoto.com/photos/millennial-male-team-leader-organize-virtual-workshop-with-employees-picture-id1300972574?b=1&k=20&m=1300972574&s=170667a&w=0&h=2nBGC7tr0kWIU8zRQ3dMg-C5JLo9H2sNUuDjQ5mlYfo=',
      'https://media.istockphoto.com/photos/headshot-portrait-of-smiling-ethnic-businessman-in-office-picture-id1300512215?b=1&k=20&m=1300512215&s=170667a&w=0&h=LsZL_-vvAHB2A2sNLHu9Vpoib_3aLLkRamveVW3AGeQ=',
      'https://images.unsplash.com/photo-1438761681033-6461ffad8d80?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxzZWFyY2h8MTB8fG1hbiUyMHByb2ZpbGUlMjBpbWFnZXxlbnwwfHwwfHw%3D&auto=format&fit=crop&w=600&q=60',
      'https://media.istockphoto.com/photos/headshot-portrait-of-smiling-ethnic-businessman-in-office-picture-id1300512215?b=1&k=20&m=1300512215&s=170667a&w=0&h=LsZL_-vvAHB2A2sNLHu9Vpoib_3aLLkRamveVW3AGeQ=',
      'https://media.istockphoto.com/photos/portrait-of-a-girl-picture-id938709362?b=1&k=20&m=938709362&s=170667a&w=0&h=7kbyEr_hujTNDsvQ629eb1mQbYCBTdIFy-Fb24DjTg4=',
    
    ]
  },
      {
    company: 'Quotient',
    domain: 'quotient.co',
    status:'customer',
    license: 15,
    image:
      'https://images.unsplash.com/photo-1494790108377-be9c29b29330?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=4&w=256&h=256&q=60',
    title: 'Sales CRM',
    description: 'Web-based sales doc management',
    users: [
      'https://media.istockphoto.com/photos/portrait-of-happy-thoughtful-young-business-woman-leader-entrepreneur-picture-id1335027342?k=20&m=1335027342&s=612x612&w=0&h=vgUWY5q6NwxQ-t_LC3Meu9Dv44_0bJOG5EgyoEJ_uYo=',
      'https://media.istockphoto.com/photos/millennial-male-team-leader-organize-virtual-workshop-with-employees-picture-id1300972574?b=1&k=20&m=1300972574&s=170667a&w=0&h=2nBGC7tr0kWIU8zRQ3dMg-C5JLo9H2sNUuDjQ5mlYfo=',
      'https://media.istockphoto.com/photos/headshot-portrait-of-smiling-ethnic-businessman-in-office-picture-id1300512215?b=1&k=20&m=1300512215&s=170667a&w=0&h=LsZL_-vvAHB2A2sNLHu9Vpoib_3aLLkRamveVW3AGeQ=',
      'https://images.unsplash.com/photo-1438761681033-6461ffad8d80?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxzZWFyY2h8MTB8fG1hbiUyMHByb2ZpbGUlMjBpbWFnZXxlbnwwfHwwfHw%3D&auto=format&fit=crop&w=600&q=60',
      'https://media.istockphoto.com/photos/headshot-portrait-of-smiling-ethnic-businessman-in-office-picture-id1300512215?b=1&k=20&m=1300512215&s=170667a&w=0&h=LsZL_-vvAHB2A2sNLHu9Vpoib_3aLLkRamveVW3AGeQ=',
      'https://media.istockphoto.com/photos/portrait-of-a-girl-picture-id938709362?b=1&k=20&m=938709362&s=170667a&w=0&h=7kbyEr_hujTNDsvQ629eb1mQbYCBTdIFy-Fb24DjTg4=',
      'https://images.unsplash.com/photo-1494790108377-be9c29b29330?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxzZWFyY2h8Mnx8cHJvZmlsZSUyMGltYWdlfGVufDB8fDB8fA%3D%3D&auto=format&fit=crop&w=600&q=60',
      'https://images.unsplash.com/photo-1438761681033-6461ffad8d80?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxzZWFyY2h8MTB8fG1hbiUyMHByb2ZpbGUlMjBpbWFnZXxlbnwwfHwwfHw%3D&auto=format&fit=crop&w=600&q=60',
      'https://media.istockphoto.com/photos/headshot-portrait-of-smiling-ethnic-businessman-in-office-picture-id1300512215?b=1&k=20&m=1300512215&s=170667a&w=0&h=LsZL_-vvAHB2A2sNLHu9Vpoib_3aLLkRamveVW3AGeQ=',
      'https://media.istockphoto.com/photos/portrait-of-a-girl-picture-id938709362?b=1&k=20&m=938709362&s=170667a&w=0&h=7kbyEr_hujTNDsvQ629eb1mQbYCBTdIFy-Fb24DjTg4=',
      'https://images.unsplash.com/photo-1494790108377-be9c29b29330?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxzZWFyY2h8Mnx8cHJvZmlsZSUyMGltYWdlfGVufDB8fDB8fA%3D%3D&auto=format&fit=crop&w=600&q=60'
    
    ]
  },
      {
    company: 'Sisyphus',
    domain: 'Sisyphus.com',
    status:'customer',
    license: 45,
    image:
      'https://images.unsplash.com/photo-1494790108377-be9c29b29330?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=facearea&facepad=4&w=256&h=256&q=60',
    title: 'Automation and work flow',
    description: 'Time tracking, invoicing and expenses',
    users: [
      'https://media.istockphoto.com/photos/millennial-male-team-leader-organize-virtual-workshop-with-employees-picture-id1300972574?b=1&k=20&m=1300972574&s=170667a&w=0&h=2nBGC7tr0kWIU8zRQ3dMg-C5JLo9H2sNUuDjQ5mlYfo=',
      'https://media.istockphoto.com/photos/headshot-portrait-of-smiling-ethnic-businessman-in-office-picture-id1300512215?b=1&k=20&m=1300512215&s=170667a&w=0&h=LsZL_-vvAHB2A2sNLHu9Vpoib_3aLLkRamveVW3AGeQ=',
      'https://images.unsplash.com/photo-1438761681033-6461ffad8d80?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxzZWFyY2h8MTB8fG1hbiUyMHByb2ZpbGUlMjBpbWFnZXxlbnwwfHwwfHw%3D&auto=format&fit=crop&w=600&q=60',
      'https://media.istockphoto.com/photos/headshot-portrait-of-smiling-ethnic-businessman-in-office-picture-id1300512215?b=1&k=20&m=1300512215&s=170667a&w=0&h=LsZL_-vvAHB2A2sNLHu9Vpoib_3aLLkRamveVW3AGeQ=',
      'https://media.istockphoto.com/photos/portrait-of-a-girl-picture-id938709362?b=1&k=20&m=938709362&s=170667a&w=0&h=7kbyEr_hujTNDsvQ629eb1mQbYCBTdIFy-Fb24DjTg4=',
      'https://images.unsplash.com/photo-1494790108377-be9c29b29330?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxzZWFyY2h8Mnx8cHJvZmlsZSUyMGltYWdlfGVufDB8fDB8fA%3D%3D&auto=format&fit=crop&w=600&q=60',
            'https://media.istockphoto.com/photos/headshot-portrait-of-smiling-ethnic-businessman-in-office-picture-id1300512215?b=1&k=20&m=1300512215&s=170667a&w=0&h=LsZL_-vvAHB2A2sNLHu9Vpoib_3aLLkRamveVW3AGeQ=',
      'https://media.istockphoto.com/photos/portrait-of-a-girl-picture-id938709362?b=1&k=20&m=938709362&s=170667a&w=0&h=7kbyEr_hujTNDsvQ629eb1mQbYCBTdIFy-Fb24DjTg4=',
      'https://images.unsplash.com/photo-1494790108377-be9c29b29330?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxzZWFyY2h8Mnx8cHJvZmlsZSUyMGltYWdlfGVufDB8fDB8fA%3D%3D&auto=format&fit=crop&w=600&q=60'
    
    ]
  },
  // More companies...
]

export default {
  company: 'Table',
  data() {
    return {
      companies,
    }
  },
  mounted(){
  const checkbox = document.getElementById("flexCheckIndeterminate");
  checkbox.indeterminate = true;
  },
  methods:{
    toggleCheck() {
    this.$refs.indeterminatecheck.indeterminate = true;

    }
  }
}
</script>
