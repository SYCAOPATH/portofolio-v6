<template>
  <div
    class="bg-[#1e1e1f] px-5 py-5 md:px-12 md:py-10 text-left border border-[#383838] rounded-3xl text-amber-50 mx-3 mb-5">
    <article data-page="about">

      <header>
        <div class="text-2xl font-bold text-white mb-5 fadein-bot title-section flex items-center">
          About Me &nbsp;
          <div class="h-[1px] w-32 bg-custom-purple md:w-96 aos-init aos-animate" data-aos="zoom-in-left"
            data-aos-duration="600"></div>
        </div>
      </header>

      <section
        class="text-sm md:text-lg text-justify flex flex-col gap-4 md:flex-row md:gap-8 md:justify-left md:items-center">
        <div class="flex justify-center">
          <img alt="avatar" 
            class="w-12 h-12 md:w-12 md:h-12 rounded-full border-2 border-custom-purple" 
            style="width: 430px !important; height: 430px !important; max-width: 430px !important; max-height: 430px !important; box-shadow: 0px 0px 50px -9px rgba(174,8,255,0.44); object-fit: cover; object-position: center;"
            src="https://ik.imagekit.io/portofoliosars/SARSnewProfile.jpg?updatedAt=1749812953629">
        </div>
        <div class="md:w-7/12">
          <p class="mb-3 md:mb-7 fadein-left fadeins-1">
            &nbsp; &nbsp; &nbsp; Hi, I'm Yulkautsar. I'm a web developer passionate about building high-performance, scalable web solutions. My expertise spans both the .NET ecosystem (C#, ASP.NET Core, Azure) and the powerful Laravel framework. This dual specialization allows me to architect and develop robust applications tailored to unique project requirements.
          </p>
          <p class="mb-3 fadein-left fadeins-2">
            &nbsp; &nbsp; &nbsp; I enjoy tackling complex challenges, from integrating AI capabilities to optimizing DevOps workflows. My focus is always on creating applications that are not only functional and user-friendly but also maintainable and built to last. I'm driven by the process of turning a great idea into a tangible, impactful product.
          </p>
        </div>
      </section>

    </article>
  </div>

  <div class="px-5 py-5 md:px-12 md:py-10 text-left text-amber-50 mx-3">
    <article data-page="about">
      <header>
        <div class="text-2xl font-bold text-white mb-5 fadein-bot title-section flex items-center">
          <div class="h-[1px] w-10 bg-custom-purple md:w-20 aos-init aos-animate" data-aos="zoom-in-left"
            data-aos-duration="600"></div>
          &nbsp; Skills
        </div>
      </header>
      <section>
        <div>
          <ul class="flex flex-wrap text-sm font-medium text-center text-gray-500 dark:text-gray-400 mb-5">
            <li class="mr-4">
              <button class="inline-block px-6 py-3 rounded-lg text-white transition-all duration-300"
                :class="{ 'bg-custom-purple': activeTab === 1, 'bg-[#1e1e1f] hover:bg-[#282828]': activeTab !== 1 }" 
                @click="activeTab = 1">Tech Stack</button>
            </li>
            <li class="mr-4">
              <button class="inline-block px-6 py-3 rounded-lg text-white transition-all duration-300"
                :class="{ 'bg-custom-purple': activeTab === 2, 'bg-[#1e1e1f] hover:bg-[#282828]': activeTab !== 2 }" 
                @click="activeTab = 2">Tools</button>
            </li>
          </ul>
        </div>
        <div v-show="activeTab === 1">
          <div class="grid grid-cols-2 gap-4 pb-32 md:grid-cols-3 md:gap-8 xl:grid-cols-4 xl:gap-10 2xl:gap-12">
            <div v-for="item in tech" :key="item.id">
              <div
                class="item-tech flex cursor-pointer items-center gap-2 rounded border border-custom-purple px-2 py-2 hover:bg-custom-purple hover:bg-opacity-10 md:gap-3 lg:px-3">
                <div class="flex h-12 w-12 items-center justify-center p-0 lg:h-16 lg:w-16 lg:p-2 zoom-in">
                  <img alt="HTML" loading="lazy" width="32" height="32" decoding="async" data-nimg="1"
                    class="img-tech drop-shadow-xl transition-all duration-300 h-[65%] w-[65%] lg:h-[85%] lg:w-[85%]  "
                    :src="item.imageUrl" style="color: transparent;">
                </div>
                <div class="flex items-center text-sm md:text-base lg:text-lg">
                  <div class="tech font-medium text-secondary transition-all duration-300 translate-y-0 ">{{ item.name }}
                  </div>
                  <div
                    class="status-tech opacity-0 absolute mt-5 text-[10px] text-custom-purple transition-all duration-300 md:text-xs lg:text-sm">
                    {{ item.status }}</div>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div v-show="activeTab === 2">
          <div class="grid grid-cols-2 gap-4 pb-32 md:grid-cols-3 md:gap-8 xl:grid-cols-4 xl:gap-10 2xl:gap-12">
            <div v-for="item in tools" :key="item.id">
              <div
                class="item-tech flex cursor-pointer items-center gap-2 rounded border border-custom-purple px-2 py-2 hover:bg-custom-purple hover:bg-opacity-10 md:gap-3 lg:px-3">
                <div class="flex h-12 w-12 items-center justify-center p-0 lg:h-16 lg:w-16 lg:p-2 zoom-in">
                  <img alt="HTML" loading="lazy" width="32" height="32" decoding="async" data-nimg="1"
                    class="img-tech drop-shadow-xl transition-all duration-300 h-[65%] w-[65%] lg:h-[85%] lg:w-[85%]  "
                    :src="item.imageUrl" style="color: transparent;">
                </div>
                <div class="flex items-center text-sm md:text-base lg:text-lg">
                  <div class="tech font-medium text-secondary transition-all duration-300 translate-y-0 ">{{ item.name }}
                  </div>
                  <div
                    class="status-tech opacity-0 absolute mt-5 text-[10px] text-custom-purple transition-all duration-300 md:text-xs lg:text-sm">
                    {{ item.status }}</div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>
    </article>
  </div>
</template>

<script>
export default {
  data() {
    return {
      activeTab: 1,
      tech: [
        {
          id: 1,
          name: 'HTML',
          imageUrl: 'https://cdn-icons-png.flaticon.com/512/1051/1051277.png',
          status: 'Advanced'
        },
        {
          id: 2,
          name: 'CSS',
          imageUrl: 'https://cdn-icons-png.flaticon.com/512/732/732190.png',
          status: 'Advanced'
        },
        {
          id: 3,
          name: 'PHP',
          imageUrl: 'https://cdn.iconscout.com/icon/free/png-256/free-php-2038871-1720084.png',
          status: 'Advanced'
        },
        {
          id: 4,
          name: 'Javascript',
          imageUrl: 'https://cdn.icon-icons.com/icons2/2415/PNG/512/javascript_original_logo_icon_146455.png',
          status: 'Advanced'
        },
        {
          id: 5,
          name: 'Laravel',
          imageUrl: 'https://cdn.worldvectorlogo.com/logos/laravel-2.svg',
          status: 'Advanced'
        },
        {
          id: 6,
          name: 'Codeigniter',
          imageUrl: 'https://cdn.worldvectorlogo.com/logos/codeigniter.svg',
          status: 'Intermediate'
        },
        {
          id: 7,
          name: 'VueJS',
          imageUrl: 'https://cdn.iconscout.com/icon/free/png-256/free-vue-282497.png?f=webp',
          status: 'Intermediate'
        },
        {
          id: 8,
          name: 'AlpineJS',
          imageUrl: 'https://avatars.githubusercontent.com/u/59030169?s=200&v=4',
          status: 'Intermediate'
        },
        {
          id: 9,
          name: 'NodeJS',
          imageUrl: 'https://cdn.iconscout.com/icon/free/png-256/free-node-js-1174925.png',
          status: 'Intermediate'
        },
        {
          id: 10,
          name: 'Tailwind',
          imageUrl: 'https://upload.wikimedia.org/wikipedia/commons/d/d5/Tailwind_CSS_Logo.svg',
          status: 'Advanced'
        },
        {
          id: 11,
          name: 'Bootstrap',
          imageUrl: 'https://getbootstrap.com/docs/5.2/assets/brand/bootstrap-logo-shadow.png',
          status: 'Intermediate'
        },
        {
          id: 12,
          name: 'ReactJS',
          imageUrl: 'https://cdn4.iconfinder.com/data/icons/logos-3/600/React.js_logo-512.png',
          status: 'Intermediate'
        },
        {
          id: 13,
          name: 'Angular',
          imageUrl: 'https://angular.io/assets/images/logos/angular/angular.svg',
          status: 'Intermediate'
        },
        {
          id: 14,
          name: 'ASP.NET Core',
          imageUrl: 'https://upload.wikimedia.org/wikipedia/commons/thumb/e/ee/.NET_Core_Logo.svg/2048px-.NET_Core_Logo.svg.png',
          status: 'Intermediate'
        },
        {
          id: 15,
          name: 'Java',
          imageUrl: 'https://cdn.icon-icons.com/icons2/2415/PNG/512/java_original_wordmark_logo_icon_146459.png',
          status: 'Intermediate'
        },
        {
          id: 16,
          name: 'Python',
          imageUrl: 'https://upload.wikimedia.org/wikipedia/commons/thumb/c/c3/Python-logo-notext.svg/1869px-Python-logo-notext.svg.png',
          status: 'Advanced'
        }
      ],
      tools: [
        {
          id: 1,
          name: 'Git',
          imageUrl: 'https://git-scm.com/images/logos/downloads/Git-Icon-1788C.png',
          status: 'Version Control'
        },
        {
          id: 2,
          name: 'GitHub',
          imageUrl: 'https://cdn-icons-png.flaticon.com/512/25/25231.png',
          status: 'Git Hosting'
        },
        {
          id: 3,
          name: 'NPM',
          imageUrl: 'https://cdn.iconscout.com/icon/free/png-256/free-npm-3-1175132.png',
          status: 'Package Manager'
        },
        {
          id: 4,
          name: 'MySQL',
          imageUrl: 'https://cdn-icons-png.flaticon.com/512/5968/5968313.png',
          status: 'Database'
        },
        {
          id: 5,
          name: 'GitLab',
          imageUrl: 'https://about.gitlab.com/images/press/logo/png/gitlab-logo-500.png',
          status: 'Git Hosting'
        },
        {
          id: 6,
          name: 'Docker',
          imageUrl: 'https://www.docker.com/wp-content/uploads/2022/03/Moby-logo.png',
          status: 'Containerization'
        },
        {
          id: 7,
          name: 'MongoDB',
          imageUrl: 'https://cdn.icon-icons.com/icons2/2415/PNG/512/mongodb_original_wordmark_logo_icon_146425.png',
          status: 'Database'
        },
        {
          id: 8,
          name: 'AWS',
          imageUrl: 'https://upload.wikimedia.org/wikipedia/commons/thumb/9/93/Amazon_Web_Services_Logo.svg/1024px-Amazon_Web_Services_Logo.svg.png',
          status: 'Cloud Computing'
        },
        {
          id: 9,
          name: 'Azure',
          imageUrl: 'https://upload.wikimedia.org/wikipedia/commons/thumb/f/fa/Microsoft_Azure.svg/1200px-Microsoft_Azure.svg.png',
          status: 'Cloud Computing'
        },
        {
          id: 10,
          name: 'TensorFlow',
          imageUrl: 'https://upload.wikimedia.org/wikipedia/commons/thumb/2/2d/Tensorflow_logo.svg/1200px-Tensorflow_logo.svg.png',
          status: 'AI/ML'
        },
        {
          id: 11,
          name: 'PyTorch',
          imageUrl: 'https://upload.wikimedia.org/wikipedia/commons/thumb/1/10/PyTorch_logo_icon.svg/1200px-PyTorch_logo_icon.svg.png',
          status: 'AI/ML'
        },
        {
          id: 12,
          name: 'Kubernetes',
          imageUrl: 'https://upload.wikimedia.org/wikipedia/commons/thumb/3/39/Kubernetes_logo_without_workmark.svg/1200px-Kubernetes_logo_without_workmark.svg.png',
          status: 'Orchestration'
        }
      ]
    };
  }
}
</script>

<style>
.fadein-left {
  opacity: 0;
  animation: fadeInLeft 0.5s ease-out forwards;
}

@keyframes fadeInLeft {
  0% {
    opacity: 0;
    transform: translateX(100%);
  }

  100% {
    opacity: 1;
    transform: translateX(0);
  }
}

.fadeins-1 {
  animation-delay: 500ms;
}

.fadeins-2 {
  animation-delay: 800ms;
}

.img-tech,
.tech {
  transition: transform 0.3s ease;
}

.item-tech:hover .img-tech {
  transform: scale(1.3);
}

.item-tech:hover .tech {
  transform: translateY(-10px);
}

.item-tech:hover .status-tech {
  opacity: 1;
  color: white !important;
  font-weight: 600;
  text-shadow: 0 0 5px rgba(0, 0, 0, 0.8);
  background-color: rgba(174, 8, 255, 0.9);
  padding: 4px 10px;
  border-radius: 4px;
  margin-top: 35px; /* Increased to 35px to create more space */
  z-index: 10;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.3);
}

.status-tech {
  opacity: 0;
  position: absolute;
  transition: all 0.3s ease;
  transform: translateY(0);
  color: white !important;
}

button {
  font-weight: 500;
  letter-spacing: 0.5px;
}

.bg-custom-purple {
  background-color: #AE08FF !important;
  box-shadow: 0 0 15px rgba(174, 8, 255, 0.5);
}

.bg-[#1e1e1f]:hover {
  border: 1px solid #383838;
}
</style>
