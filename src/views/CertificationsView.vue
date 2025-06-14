<template>
  <div class="px-5 py-5 md:px-12 md:py-10 text-left text-amber-50 mx-3">
    <article data-page="about">
      <header>
        <div class="text-2xl font-bold text-white mb-10 fadein-bot title-section flex items-center justify-center flex-col">
          <h4>Certifications & Skills</h4>
          <h4 class="text-base font-normal text-transparent bg-clip-text bg-gradient-to-r from-slate-100 to-[#AE08FF]">
            My Certifications and Learning RoadMap.
          </h4>
        </div>
      </header>

      <!-- Certification tetap -->
      <section>
        <div>
          <div class="text-xl font-bold text-white mb-5">Certifications</div>
          <div class="relative">
            <div class="absolute left-1/2 w-0.5 h-full bg-gray-600"></div>
            <div
              v-for="(cert, index) in certifications"
              :key="cert.id"
              class="mb-8 flex justify-between items-center w-full"
              :class="{'flex-row-reverse': index % 2 === 0}"
            >
              <div class="order-1 w-5/12"></div>
              <div class="z-20 flex items-center order-1 bg-gray-800 shadow-xl w-8 h-8 rounded-full">
                <h1 class="mx-auto font-semibold text-lg text-white">{{ index + 1 }}</h1>
              </div>
              <div class="order-1 bg-gray-700 rounded-lg shadow-xl w-5/12 px-6 py-4">
                <div class="flex items-center mb-2">
                  <img :src="cert.logo" :alt="cert.issuer" class="w-8 h-8 mr-3" />
                  <h3 class="font-bold text-white text-lg">{{ cert.name }}</h3>
                  <span class="text-xs text-gray-400 ml-auto">{{ cert.date }}</span>
                </div>
                <p class="text-sm text-gray-300">{{ cert.issuer }}</p>
                <a :href="cert.link" class="text-sm text-custom-purple hover:underline" target="_blank">Verify</a>
              </div>
            </div>
          </div>
        </div>

        <!-- Learning Roadmap -->
        <div class="mt-16">
          <div class="text-xl font-bold text-white mb-5">Learning Roadmap</div>
          <div class="relative">
            <div class="absolute left-1/2 transform -translate-x-1/2 h-full w-0.5 bg-gray-600"></div>
            <div
              v-for="(step, index) in roadmap"
              :key="step.id"
              class="mb-10 flex justify-between items-center w-full"
              :class="{ 'flex-row-reverse': index % 2 === 0 }"
            >
              <div class="order-1 w-5/12"></div>
              <div class="z-20 flex items-center order-1 bg-gray-800 shadow-xl w-8 h-8 rounded-full">
                <h1 class="mx-auto font-semibold text-white">{{ index + 1 }}</h1>
              </div>
              <div class="order-1 bg-gray-700 rounded-lg shadow-xl w-5/12 px-6 py-4">
                <div class="flex items-center mb-2">
                  <img :src="step.icon" :alt="step.title" class="w-8 h-8 mr-3" />
                  <h3 class="font-bold text-white text-lg">{{ step.title }}</h3>
                </div>
                <p class="text-sm text-gray-300">{{ step.description }}</p>
                <a v-if="step.source" :href="step.source" target="_blank" class="text-sm text-custom-purple hover:underline">
                  Free Source
                </a>
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
  name: 'CertificationsView',
  data() {
    return {
      certifications: [
        {
          id: 1,
          name: 'Microsoft Azure Fundamentals',
          issuer: 'Microsoft',
          date: 'July 15, 2024',
          logo: '/img/microsoft.png',
          link: 'https://learn.microsoft.com/en-us/certifications/azure-fundamentals'
        },
        {
          id: 2,
          name: 'Docker Certified Associate',
          issuer: 'Docker',
          date: 'August 5, 2024',
          logo: '/img/docker cetif.png',
          link: 'https://www.docker.com/certify/dca/'
        },
        {
          id: 3,
          name: 'Responsive Web Design',
          issuer: 'freeCodeCamp',
          date: 'September 1, 2024',
          logo: '/img/freecodecamp logo.png',
          link: 'https://www.freecodecamp.org/certification'
        },
        {
          id: 4,
          name: 'Google Cloud Fundamentals',
          issuer: 'Google',
          date: 'October 10, 2024',
          logo: '/img/google certif.png',
          link: 'https://cloud.google.com/training/certifications'
        },
        {
          id: 5,
          name: 'AWS Certified Cloud Practitioner',
          issuer: 'Amazon Web Services',
          date: 'November 20, 2024',
          logo: '/img/aws certi.png',
          link: 'https://aws.amazon.com/certification/certified-cloud-practitioner/'
        }
      ],
      roadmap: [
        {
          id: 1,
          title: 'Start Learning',
          description: 'Basic introduction to software development and cloud computing',
          icon: 'https://cdn.jsdelivr.net/npm/simple-icons@v11/icons/openbadges.svg',
          source: 'https://www.freecodecamp.org/learn'
        },
        {
          id: 2,
          title: 'Cloud Specialization',
          description: 'Learn Cloud Platforms like AWS, Azure, and GCP',
          icon: 'https://cdn.jsdelivr.net/npm/simple-icons@v11/icons/azuredevops.svg',
          source: 'https://learn.microsoft.com/en-us/training/paths/azure-fundamentals/'
        },
        {
          id: 3,
          title: 'Kubernetes for Developers',
          description: 'Understand container orchestration with Kubernetes',
          icon: 'https://cdn.jsdelivr.net/npm/simple-icons@v11/icons/kubernetes.svg',
          source: 'https://www.kodekloud.com/p/kubernetes-for-developers'
        },
        {
          id: 4,
          title: 'DevOps with GitHub Actions',
          description: 'CI/CD workflows with GitHub Actions',
          icon: 'https://cdn.jsdelivr.net/npm/simple-icons@v11/icons/githubactions.svg',
          source: 'https://docs.github.com/en/actions'
        },
        {
          id: 5,
          title: 'CKA Preparation',
          description: 'Certified Kubernetes Administrator prep materials',
          icon: 'https://cdn.jsdelivr.net/npm/simple-icons@v11/icons/linuxfoundation.svg',
          source: 'https://training.linuxfoundation.org/certification/certified-kubernetes-administrator-cka/'
        },
        {
          id: 6,
          title: 'CI/CD Pipeline Projects',
          description: 'Build CI/CD projects across environments',
          icon: 'https://cdn.jsdelivr.net/npm/simple-icons@v11/icons/gitlab.svg',
          source: 'https://about.gitlab.com/solutions/ci-cd/'
        },
        {
          id: 7,
          title: 'AI & ML',
          description: 'Foundational knowledge in AI & Machine Learning',
          icon: 'https://cdn.jsdelivr.net/npm/simple-icons@v11/icons/tensorflow.svg',
          source: 'https://developers.google.com/machine-learning/crash-course'
        }
      ]
    };
  }
};
</script>

<style scoped>
/* Tailwind already handles most styling */
a {
  color: #AE08FF !important;
}
</style>
