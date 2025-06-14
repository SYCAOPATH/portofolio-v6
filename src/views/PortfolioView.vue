<script>
export default {
  data() {
    return {
      activeTab: 1,
      items: [
        {
          id: 1,
          name: 'Personal Website',
          imageUrl: 'home-profile',
          status: 'My personal website, I created this website to display my profile, skills and projects. As well as my place to try new technology.',
          tech: 'VueJS 3, Tailwind',
          demo: 'https://symphonious-strudel-708f8f.netlify.app/',
          github: 'https://github.com/SYCAOPATH/portofolio-v2',
          icon: 'M12 19l9 2-9-18-9 18 9-2zm0 0v-8' 
        },
        {
          id: 2,
          name: 'Anime Store',
          imageUrl: 'porto-anime',
          status: 'An e-commerce application for selling anime merchandise, featuring Midtrans payment gateway, Raja Ongkir shipping calculation, and a shopping cart.',
          tech: 'Laravel, Bootstrap',
          demo: 'null',
          github: 'null',
          icon: 'M3 3h2l.4 2M7 13h10l4-8H5.4M7 13L5.4 5M7 13l-2.293 2.293c-.63.63-.184 1.707.707 1.707H17m0 0a2 2 0 100 4 2 2 0 000-4zm-8 2a2 2 0 11-4 0 2 2 0 014 0z' // Shopping cart icon
        },
        {
          id: 3,
          name: 'SMANELKU',
          imageUrl: 'porto-smanelku',
          status: 'A web-based school management application built with Laravel, featuring a school website, new student registration, library, tuition payment system, and an alumni portal.',
          tech: 'Laravel, Bootstrap',
          github: 'https://github.com/SYCAOPATH/aplikasi-smanelku/tree/master',
          demo: 'null',
          icon: 'M12 14l9-5-9-5-9 5 9 5zm0 0l6.16-3.422a12.083 12.083 0 01.665 6.479A11.952 11.952 0 0012 20.055a11.952 11.952 0 00-6.824-2.998 12.078 12.078 0 01.665-6.479L12 14zm-4 6v-7.5l4-2.222' // Academic/school icon
        },
        {
          id: 4,
          name: 'SPP Payment Application',
          imageUrl: 'porto-spp',
          status: 'An open-source tuition payment application built for a college course, featuring three user roles (Administrator, Officer, and Student) for managing payments.',
          tech: 'Laravel, Bootstrap, SweetAlert',
          github: 'https://github.com/SYCAOPATH/spp-laravel10-smaneljambi',
          demo: 'null',
          icon: 'M17 9V7a2 2 0 00-2-2H5a2 2 0 00-2 2v6a2 2 0 002 2h2m2 4h10a2 2 0 002-2v-6a2 2 0 00-2-2H9a2 2 0 00-2 2v6a2 2 0 002 2zm7-5a2 2 0 11-4 0 2 2 0 014 0z' // Payment/wallet icon
        },
        {
          id: 5,
          name: 'Sribu Landing Page',
          imageUrl: 'porto-sribu',
          status: 'A responsive landing page for a freelance marketplace platform.',
          tech: 'HTML, CSS, JavaScript',
          github: 'https://github.com/SYCAOPATH/Sribu-Landing-Page',
          demo: 'null',
          icon: 'M21 13.255A23.931 23.931 0 0112 15c-3.183 0-6.22-.62-9-1.745M16 6V4a2 2 0 00-2-2h-4a2 2 0 00-2 2v2m4 6h.01M5 20h14a2 2 0 002-2V8a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z' // Briefcase/work icon
        }
      ],
      confidentialProjects: [
        {
          id: 1,
          title: "Cloud-Based Warehouse Management",
          tech: "ASP.NET Core, React, Azure",
          status: "Pending Approval",
          icon: "M5 12h14M5 12a2 2 0 01-2-2V6a2 2 0 012-2h14a2 2 0 012 2v4a2 2 0 01-2 2M5 12a2 2 0 00-2 2v4a2 2 0 002 2h14a2 2 0 002-2v-4a2 2 0 00-2-2m-2-4h.01M17 16h.01" // Server/cloud icon
        },
        {
          id: 2,
          title: "AI-Powered Support Chatbot",
          tech: "Node.js, OpenAI API",
          status: "Pending Approval",
          icon: "M8 10h.01M12 10h.01M16 10h.01M9 16H5a2 2 0 01-2-2V6a2 2 0 012-2h14a2 2 0 012 2v8a2 2 0 01-2 2h-5l-5 5v-5z" // Chat/message icon
        },
        {
          id: 3,
          title: "School ERP Mini System",
          tech: "Laravel, Bootstrap, MySQL",
          status: "Pending Approval",
          icon: "M9 5H7a2 2 0 00-2 2v12a2 2 0 002 2h10a2 2 0 002-2V7a2 2 0 00-2-2h-2M9 5a2 2 0 002 2h2a2 2 0 002-2M9 5a2 2 0 012-2h2a2 2 0 012 2" // Document/clipboard icon
        },
        {
          id: 4,
          title: "Healthcare Appointment System",
          tech: "ASP.NET Core, Blazor, PostgreSQL",
          status: "Restricted",
          icon: "M4.318 6.318a4.5 4.5 0 000 6.364L12 20.364l7.682-7.682a4.5 4.5 0 00-6.364-6.364L12 7.636l-1.318-1.318a4.5 4.5 0 00-6.364 0z" // Heart/healthcare icon
        },
        {
          id: 5,
          title: "Client Project Portal Dashboard",
          tech: "ReactJS, NodeJS",
          status: "Restricted",
          icon: "M9 19v-6a2 2 0 00-2-2H5a2 2 0 00-2 2v6a2 2 0 002 2h2a2 2 0 002-2zm0 0V9a2 2 0 012-2h2a2 2 0 012 2v10m-6 0a2 2 0 002 2h2a2 2 0 002-2m0 0V5a2 2 0 012-2h2a2 2 0 012 2v14a2 2 0 01-2 2h-2a2 2 0 01-2-2z" // Chart/dashboard icon
        },
        {
          id: 6,
          title: "DevOps Monitoring & Deploy Board",
          tech: "ReactJS, NodeJS",
          status: "Restricted",
          icon: "M10 20l4-16m4 4l4 4-4 4M6 16l-4-4 4-4" // Code/DevOps icon
        }
      ]
    };
  },
  methods: {
    getImageUrl(imageName) {
      // Try different image paths to ensure we find the correct one
      const possiblePaths = [
        `/img/${imageName}.png`,
        `/public/img/${imageName}.png`,
        `https://raw.githubusercontent.com/SYCAOPATH/portofolio-v2/main/public/img/${imageName}.png`,
        // Fallback to a placeholder if image not found
        'https://via.placeholder.com/400x250?text=Project+Image'
      ];
      
      // For the first item (Personal Website), use the home profile image
      if (imageName === 'home-profile') {
        return 'https://ik.imagekit.io/portofoliosars/SARSnewProfile.jpg?updatedAt=1749812953629';
      }
      
      return possiblePaths[0]; // Start with the first path
    }
  }
}
</script>
<template>
  <div class="px-5 py-5 md:px-12 md:py-10 text-left text-amber-50 mx-3">
    <article data-page="about">
      <header>
        <div class="text-2xl font-bold text-white mb-10 fadein-bot title-section flex items-center justify-center flex-col">
          <h4>Past Project Experience</h4>
          <h4 class="text-base font-normal text-transparent bg-clip-text bg-gradient-to-r from-slate-100 to-custom-purple">
            Explore the projects I've worked on so far</h4>
        </div>
      </header>
      <section>
        <div>
          <div class="grid grid-cols-1 gap-4 pb-32 md:grid-cols-3 md:gap-3 xl:grid-cols-3 xl:gap-3 2xl:gap-5 fade-zoom-in">
            <div v-for="item in items" :key="item.id" class="project-card">
              <div class="item-card flex flex-col gap-2 rounded bg-[#1e1e1f] hover:bg-[#282828] border border-[#383838] rounded-xl text-amber-50 md:gap-3 px-5 py-5 lg:px-5">
                <div class="project-image-container w-full h-48 mb-4 overflow-hidden rounded-xl">
                  <img :alt="item.name" loading="lazy" decoding="async" 
                    class="w-full h-full object-cover"
                    :src="getImageUrl(item.imageUrl)">
                </div>
                <div class="w-full flex flex-col gap-2 items-start text-sm md:text-base lg:text-lg">
                  <div class="flex items-center w-full">
                    <div class="project-icon-container mr-3 bg-custom-purple/20 p-2 rounded-full">
                      <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 text-custom-purple" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                        <path stroke-linecap="round" stroke-linejoin="round" :d="item.icon" />
                      </svg>
                    </div>
                    <div class="title-text font-medium text-white text-xl">{{ item.name }}</div>
                  </div>
                  <div class="w-full text-left text-[10px] text-[#c1c1c1] md:text-xs lg:text-sm">
                    {{ item.status }}</div>
                  <div class="w-full mt-4 text-normal text-sm text-left text-custom-purple font-medium">
                    {{ item.tech }}
                  </div>
                  <div class="w-full flex justify-end mt-2">
                    <div class="flex cursor-pointer items-end gap-3 text-primary">
                      <a v-if="item.github !== 'null'"
                        :href="item.github" target="_blank" rel="noreferrer"
                        title="View github repository" class="transition-all hover:text-custom-purple">
                        <svg stroke="currentColor"
                          fill="none" stroke-width="2" viewBox="0 0 24 24" stroke-linecap="round" stroke-linejoin="round"
                          height="20" width="20" xmlns="http://www.w3.org/2000/svg">
                          <path
                            d="M9 19c-5 1.5-5-2.5-7-3m14 6v-3.87a3.37 3.37 0 0 0-.94-2.61c3.14-.35 6.44-1.54 6.44-7A5.44 5.44 0 0 0 20 4.77 5.07 5.07 0 0 0 19.91 1S18.73.65 16 2.48a13.38 13.38 0 0 0-7 0C6.27.65 5.09 1 5.09 1A5.07 5.07 0 0 0 5 4.77a5.44 5.44 0 0 0-1.5 3.78c0 5.42 3.3 6.61 6.44 7A3.37 3.37 0 0 0 9 18.13V22">
                          </path>
                        </svg>
                      </a>
                      <a v-if="item.demo !== 'null'" :href="item.demo" target="_blank" rel="noreferrer"
                        title="View finished project" class="transition-all hover:text-custom-purple">
                        <svg stroke="currentColor"
                          fill="none" stroke-width="2" viewBox="0 0 24 24" stroke-linecap="round" stroke-linejoin="round"
                          height="20" width="20" xmlns="http://www.w3.org/2000/svg">
                          <path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"></path>
                          <polyline points="15 3 21 3 21 9"></polyline>
                          <line x1="10" y1="14" x2="21" y2="3"></line>
                        </svg>
                      </a>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>
      
      <!-- Confidential Projects Section -->
      <header class="mt-20">
        <div class="text-2xl font-bold text-white mb-10 fadein-bot title-section flex items-center justify-center flex-col">
          <div class="flex items-center">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 mr-2 text-yellow-500" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 15v2m-6 4h12a2 2 0 002-2v-6a2 2 0 00-2-2H6a2 2 0 00-2 2v6a2 2 0 002 2zm10-10V7a4 4 0 00-8 0v4h8z" />
            </svg>
            <h4>Confidential Enterprise Projects</h4>
          </div>
          <h4 class="text-base font-normal text-transparent bg-clip-text bg-gradient-to-r from-red-400 to-yellow-500">
            Restricted Access - Client Confidentiality Agreement</h4>
        </div>
      </header>
      
      <section class="confidential-section bg-[#1e1e1f] border border-yellow-600/30 rounded-xl p-6 mb-20">
        <div class="flex flex-col items-center justify-center text-center mb-8">
          <div class="flex items-center justify-center w-20 h-20 bg-yellow-500/10 rounded-full mb-4">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-10 w-10 text-yellow-500" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 15v2m-6 4h12a2 2 0 002-2v-6a2 2 0 00-2-2H6a2 2 0 00-2 2v6a2 2 0 002 2zm10-10V7a4 4 0 00-8 0v4h8z" />
            </svg>
          </div>
          <h3 class="text-xl font-bold text-yellow-500 mb-2">RESTRICTED ACCESS</h3>
          <p class="text-gray-400 max-w-2xl">
            This section contains confidential enterprise projects developed under strict NDAs. 
            Client permission is required to view detailed information about these projects.
          </p>
        </div>
        
        <div class="grid grid-cols-1 md:grid-cols-2 gap-4 mb-8">
          <div class="bg-[#282828]/50 p-4 rounded-lg border border-yellow-600/20">
            <div class="flex items-center mb-2">
              <div class="w-3 h-3 rounded-full bg-yellow-500 mr-2 pulse-animation"></div>
              <span class="text-yellow-500 font-medium">Permission Status</span>
            </div>
            <div class="w-full bg-gray-700 rounded-full h-2.5">
              <div class="bg-yellow-500 h-2.5 rounded-full" style="width: 35%"></div>
            </div>
            <p class="text-xs text-gray-400 mt-2">Verification in progress (35%)</p>
          </div>
          
          <div class="bg-[#282828]/50 p-4 rounded-lg border border-yellow-600/20">
            <div class="flex items-center mb-2">
              <div class="w-3 h-3 rounded-full bg-red-500 mr-2"></div>
              <span class="text-red-400 font-medium">Security Level</span>
            </div>
            <p class="text-sm text-gray-300">Highly Confidential</p>
            <p class="text-xs text-gray-400 mt-1">Enterprise-grade projects with strict access control</p>
          </div>
        </div>
        
        <div class="overflow-x-auto">
          <table class="w-full text-sm text-left text-gray-400">
            <thead class="text-xs uppercase bg-[#282828] text-gray-400 border-b border-gray-700">
              <tr>
                <th scope="col" class="px-4 py-3">No</th>
                <th scope="col" class="px-4 py-3">Project Title</th>
                <th scope="col" class="px-4 py-3 hidden md:table-cell">Tech Stack</th>
                <th scope="col" class="px-4 py-3 hidden lg:table-cell">Status</th>
                <th scope="col" class="px-4 py-3">Access</th>
              </tr>
            </thead>
            <tbody>
              <tr v-for="(project, index) in confidentialProjects" :key="index" 
                  class="border-b border-gray-700 bg-[#1e1e1f] hover:bg-[#282828]">
                <td class="px-4 py-3">{{ project.id }}</td>
                <td class="px-4 py-3 font-medium text-white">
                  <div class="flex items-center">
                    <svg v-if="project.id <= 3" xmlns="http://www.w3.org/2000/svg" class="h-4 w-4 mr-2 text-yellow-500" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 16h-1v-4h-1m1-4h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z" />
                    </svg>
                    <svg v-else xmlns="http://www.w3.org/2000/svg" class="h-4 w-4 mr-2 text-red-500" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 15v2m-6 4h12a2 2 0 002-2v-6a2 2 0 00-2-2H6a2 2 0 00-2 2v6a2 2 0 002 2zm10-10V7a4 4 0 00-8 0v4h8z" />
                    </svg>
                    {{ project.title }}
                  </div>
                </td>
                <td class="px-4 py-3 hidden md:table-cell">{{ project.tech }}</td>
                <td class="px-4 py-3 hidden lg:table-cell">
                  <span :class="`px-2 py-1 rounded-full text-xs ${project.id <= 3 ? 'bg-yellow-500/20 text-yellow-400' : 'bg-red-500/20 text-red-400'}`">
                    {{ project.id <= 3 ? 'Pending Approval' : 'Restricted' }}
                  </span>
                </td>
                <td class="px-4 py-3">
                  <button class="text-gray-400 hover:text-yellow-500 transition-colors duration-200">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 15v2m-6 4h12a2 2 0 002-2v-6a2 2 0 00-2-2H6a2 2 0 00-2 2v6a2 2 0 002 2zm10-10V7a4 4 0 00-8 0v4h8z" />
                    </svg>
                  </button>
                </td>
              </tr>
            </tbody>
          </table>
        </div>
        
        <div class="mt-8 text-center">
          <p class="text-sm text-gray-400 mb-4">
            These projects showcase enterprise-level solutions developed for clients across various industries.
            Due to confidentiality agreements, detailed information is restricted.
          </p>
          <a href="https://wa.me/+6285177097445?text=Hello%20Kautsar,%20I'm%20interested%20in%20requesting%20access%20credentials%20for%20your%20confidential%20projects." 
             target="_blank" rel="noopener noreferrer"
             class="inline-block px-4 py-2 bg-yellow-500/10 text-yellow-500 rounded-lg border border-yellow-600/30 hover:bg-yellow-500/20 transition-all duration-300">
            Request Access Credentials
          </a>
        </div>
      </section>
    </article>
  </div>
</template>

<style>
.project-card {
  transition: all 0.3s ease;
}

.project-image-container {
  border-radius: 12px;
  overflow: hidden;
}

.item-card:hover {
  transition: transform 0.3s ease;
  transform: translateY(-8px);
  box-shadow: 0 10px 30px -15px rgba(174, 8, 255, 0.2);
}

svg:hover {
  stroke: #AE08FF;
}

@keyframes fadeZoomIn {
  0% {
    opacity: 0;
    transform: scale(0.5);
  }
  100% {
    opacity: 1;
    transform: scale(1);
  }
}

.fade-zoom-in {
  animation: fadeZoomIn 1s ease-in-out;
}

.title-text {
  font-weight: 600;
}
</style>





