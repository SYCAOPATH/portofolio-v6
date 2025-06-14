<template>
  <div class="container mx-auto p-3 md:p-8">
    <div class="flex flex-col-reverse md:flex-row relative">
      <div class="w-full md:w-2/3">
        <div class="flex flex-col gap-4 md:px-20 fade-zoom-up">
          <!-- Category Tabs -->
          <div class="mb-6">
            <ul class="flex flex-wrap text-sm font-medium text-center text-gray-500 dark:text-gray-400">
              <li class="mr-2">
                <button class="inline-block px-4 py-2 rounded-lg text-white transition-all duration-300"
                  :class="{ 'bg-custom-purple': activeCategory === 'all', 'bg-[#1e1e1f] hover:bg-[#282828]': activeCategory !== 'all' }" 
                  @click="activeCategory = 'all'">All News</button>
              </li>
              <li class="mr-2">
                <button class="inline-block px-4 py-2 rounded-lg text-white transition-all duration-300"
                  :class="{ 'bg-custom-purple': activeCategory === 'cybersecurity', 'bg-[#1e1e1f] hover:bg-[#282828]': activeCategory !== 'cybersecurity' }" 
                  @click="activeCategory = 'cybersecurity'">Cybersecurity</button>
              </li>
              <li class="mr-2">
                <button class="inline-block px-4 py-2 rounded-lg text-white transition-all duration-300"
                  :class="{ 'bg-custom-purple': activeCategory === 'market', 'bg-[#1e1e1f] hover:bg-[#282828]': activeCategory !== 'market' }" 
                  @click="activeCategory = 'market'">Market Trends</button>
              </li>
              <li class="mr-2">
                <button class="inline-block px-4 py-2 rounded-lg text-white transition-all duration-300"
                  :class="{ 'bg-custom-purple': activeCategory === 'tech', 'bg-[#1e1e1f] hover:bg-[#282828]': activeCategory !== 'tech' }" 
                  @click="activeCategory = 'tech'">Tech News</button>
              </li>
            </ul>
          </div>
          
          <!-- Articles List -->
          <div class="space-y-4">
            <article v-for="article in filteredArticles" :key="article.id" 
              class="bg-[#1e1e1f] border border-[#383838] rounded-xl p-5">
              <div class="flex flex-col md:flex-row gap-4">
                <div class="md:w-1/4">
                  <img :src="article.urlToImage" alt="Article image" class="w-full h-40 object-cover rounded-lg">
                </div>
                <div class="md:w-3/4">
                  <div class="text-xs text-gray-400 mb-1">{{ formatDate(article.publishedAt) }} • {{ article.source.name }}</div>
                  <h3 class="text-lg font-bold text-custom-purple mb-2">{{ article.title }}</h3>
                  <p class="text-sm text-gray-300 mb-3">{{ article.description }}</p>
                  <div class="flex items-center">
                    <span class="px-2 py-1 text-xs rounded-full bg-[#282828] text-gray-300">
                      {{ article.category }}
                    </span>
                  </div>
                </div>
              </div>
            </article>
          </div>
          
          <!-- Cybersecurity Alerts -->
          <div class="mt-8">
            <h2 class="text-xl font-bold text-white mb-4">Cybersecurity Alerts</h2>
            <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
              <div v-for="(alert, index) in securityAlerts" :key="index" 
                class="bg-[#1e1e1f] border border-[#383838] rounded-xl p-5">
                <div class="flex items-start">
                  <div :class="`p-2 rounded-full mr-3 ${alert.level === 'Critical' ? 'bg-red-500/20' : alert.level === 'High' ? 'bg-orange-500/20' : 'bg-yellow-500/20'}`">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" 
                      :class="alert.level === 'Critical' ? 'text-red-500' : alert.level === 'High' ? 'text-orange-500' : 'text-yellow-500'"
                      fill="none" viewBox="0 0 24 24" stroke="currentColor">
                      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" 
                        d="M12 9v2m0 4h.01m-6.938 4h13.856c1.54 0 2.502-1.667 1.732-3L13.732 4c-.77-1.333-2.694-1.333-3.464 0L3.34 16c-.77 1.333.192 3 1.732 3z" />
                    </svg>
                  </div>
                  <div>
                    <div class="flex items-center mb-1">
                      <span :class="`text-xs px-2 py-0.5 rounded mr-2 ${alert.level === 'Critical' ? 'bg-red-500/20 text-red-500' : alert.level === 'High' ? 'bg-orange-500/20 text-orange-500' : 'bg-yellow-500/20 text-yellow-500'}`">
                        {{ alert.level }}
                      </span>
                      <span class="text-xs text-gray-400">{{ formatDate(alert.date) }}</span>
                    </div>
                    <h3 class="text-sm md:text-md text-white font-bold mb-1">{{ alert.title }}</h3>
                    <p class="text-sm text-gray-300">{{ alert.description }}</p>
                  </div>
                </div>
              </div>
            </div>
          </div>
          
          <!-- Market Trends -->
          <div class="mt-8">
            <h2 class="text-xl font-bold text-white mb-4">Market Trends</h2>
            <div class="bg-[#1e1e1f] border border-[#383838] rounded-xl p-5">
              <div class="flex justify-between items-center mb-4">
                <h3 class="text-md text-custom-purple font-bold">Tech Stock Highlights</h3>
              </div>
              
              <!-- Stock Highlights -->
              <div class="grid grid-cols-2 md:grid-cols-4 gap-3 mt-4">
                <div v-for="stock in stockHighlights" :key="stock.symbol" 
                  class="bg-[#282828] p-3 rounded-lg flex flex-col">
                  <div class="flex justify-between items-center">
                    <span class="font-bold text-white">{{ stock.symbol }}</span>
                    <span :class="stock.change >= 0 ? 'text-green-500' : 'text-red-500'">
                      {{ stock.change >= 0 ? '+' : '' }}{{ stock.change }}%
                    </span>
                  </div>
                  <span class="text-xs text-gray-400">{{ stock.price }}</span>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      
      <!-- Sidebar -->
      <div class="w-full md:w-1/3 h-fit p-4 md:sticky md:top-24">
        <div class="flex flex-col text-left">
          <div class="bg-clip-text bg-gradient-to-r from-slate-100 to-custom-purple text-transparent">
            Stay updated with the latest tech news and developer insights
          </div>
          <div class="h-[1px] mt-7 mb-7 w-20 bg-custom-purple"></div>
          
          <!-- Search Box -->
          <div class="mb-7">
            <div class="relative">
              <input type="text" v-model="searchQuery" placeholder="Search articles..." 
                class="w-full bg-[#1e1e1f] border border-[#383838] rounded-lg py-2 px-4 text-white text-sm focus:outline-none focus:border-custom-purple">
              <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 absolute right-3 top-2.5 text-gray-400" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z" />
              </svg>
            </div>
          </div>
          
          <!-- Trending Technologies -->
          <div class="mt-7 bg-[#1e1e1f] border border-[#383838] rounded-xl p-4">
            <h3 class="text-white text-md font-semibold mb-3">Trending Technologies</h3>
            <div class="space-y-3">
              <div v-for="(trend, index) in trendingTech" :key="index" class="flex items-center">
                <div class="w-8 h-8 rounded-full bg-[#282828] flex items-center justify-center mr-3">
                  <span class="text-xs font-bold text-custom-purple">{{ index + 1 }}</span>
                </div>
                <div>
                  <div class="text-sm text-white">{{ trend.name }}</div>
                  <div class="text-xs text-gray-400">{{ trend.growth }}% growth</div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      articles: [],
      activeCategory: 'all',
      activeTopic: null,
      searchQuery: '',
      stockHighlights: [
        { symbol: 'AAPL', price: '$182.63', change: 1.25 },
        { symbol: 'MSFT', price: '$415.32', change: 0.78 },
        { symbol: 'GOOGL', price: '$142.89', change: -0.45 },
        { symbol: 'AMZN', price: '$178.75', change: 2.13 }
      ],
      securityAlerts: [
        {
          level: 'Critical',
          title: 'Zero-Day Vulnerability in Popular Framework',
          description: 'A critical zero-day vulnerability has been discovered in a widely used web framework that could allow remote code execution.',
          date: new Date(Date.now() - 2 * 24 * 60 * 60 * 1000) // 2 days ago
        },
        {
          level: 'High',
          title: 'Ransomware Campaign Targeting Healthcare',
          description: 'A new ransomware campaign is specifically targeting healthcare organizations through phishing emails with malicious attachments.',
          date: new Date(Date.now() - 5 * 24 * 60 * 60 * 1000) // 5 days ago
        },
        {
          level: 'Medium',
          title: 'Authentication Bypass in Cloud Service',
          description: 'Researchers have identified an authentication bypass vulnerability in a popular cloud service that could expose sensitive data.',
          date: new Date(Date.now() - 7 * 24 * 60 * 60 * 1000) // 7 days ago
        }
      ],
      trendingTech: [
        { name: 'AI & Machine Learning', growth: 42 },
        { name: 'Web3 & Blockchain', growth: 38 },
        { name: 'Edge Computing', growth: 27 },
        { name: 'Quantum Computing', growth: 21 }
      ]
    };
  },
  computed: {
    filteredArticles() {
      let filtered = this.articles;
      
      // Filter by category
      if (this.activeCategory !== 'all') {
        filtered = filtered.filter(article => 
          article.category?.toLowerCase() === this.activeCategory.toLowerCase());
      }
      
      // Filter by topic
      if (this.activeTopic) {
        filtered = filtered.filter(article => 
          article.title.toLowerCase().includes(this.activeTopic.toLowerCase()) || 
          article.description?.toLowerCase().includes(this.activeTopic.toLowerCase()));
      }
      
      // Filter by search query
      if (this.searchQuery) {
        const query = this.searchQuery.toLowerCase();
        filtered = filtered.filter(article => 
          article.title.toLowerCase().includes(query) || 
          article.description?.toLowerCase().includes(query));
      }
      
      return filtered;
    }
  },
  methods: {
    formatDate(date) {
      if (!date) return '';
      const d = new Date(date);
      return d.toLocaleDateString('en-US', { year: 'numeric', month: 'short', day: 'numeric' });
    },
    filterByTopic(topic) {
      this.activeTopic = this.activeTopic === topic ? null : topic;
    },
    async fetchArticles() {
      try {
        // For now, just use mock data
        this.useMockData();
      } catch (error) {
        console.error("Error fetching articles:", error);
        this.useMockData();
      }
    },
    assignCategory(title, description) {
      const text = (title + ' ' + (description || '')).toLowerCase();
      if (text.includes('security') || text.includes('vulnerability') || text.includes('hack')) {
        return 'cybersecurity';
      } else if (text.includes('market') || text.includes('stock') || text.includes('economy')) {
        return 'market';
      } else {
        return 'tech';
      }
    },
    useMockData() {
      // Mock data with relevant images for each article
      this.articles = [
        {
          id: 1,
          title: "New JavaScript Framework Promises 10x Performance Boost",
          description: "A revolutionary new JavaScript framework claims to offer significant performance improvements over existing solutions.",
          publishedAt: new Date(Date.now() - 1 * 24 * 60 * 60 * 1000),
          source: { name: "TechCrunch" },
          url: "#",
          urlToImage: "https://images.unsplash.com/photo-1579468118864-1b9ea3c0db4a?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60",
          category: "tech"
        },
        {
          id: 2,
          title: "Major Security Vulnerability Found in Popular Database System",
          description: "Security researchers have discovered a critical vulnerability affecting millions of database installations worldwide.",
          publishedAt: new Date(Date.now() - 2 * 24 * 60 * 60 * 1000),
          source: { name: "The Verge" },
          url: "#",
          urlToImage: "https://images.unsplash.com/photo-1563206767-5b18f218e8de?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60",
          category: "cybersecurity"
        },
        {
          id: 3,
          title: "Tech Giants Announce Collaboration on AI Ethics Standards",
          description: "Leading technology companies have formed a coalition to develop ethical guidelines for artificial intelligence development.",
          publishedAt: new Date(Date.now() - 3 * 24 * 60 * 60 * 1000),
          source: { name: "Wired" },
          url: "#",
          urlToImage: "https://images.unsplash.com/photo-1531746790731-6c087fecd65a?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60",
          category: "tech"
        },
        {
          id: 4,
          title: "Cloud Computing Spending Expected to Reach $500 Billion in 2023",
          description: "Industry analysts predict record growth in cloud infrastructure investments as businesses accelerate digital transformation.",
          publishedAt: new Date(Date.now() - 4 * 24 * 60 * 60 * 1000),
          source: { name: "Forbes" },
          url: "#",
          urlToImage: "https://images.unsplash.com/photo-1551288049-bebda4e38f71?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60",
          category: "market"
        },
        {
          id: 5,
          title: "New Ransomware Variant Targets Healthcare Organizations",
          description: "Cybersecurity experts warn of sophisticated ransomware attacks specifically designed to exploit vulnerabilities in healthcare systems.",
          publishedAt: new Date(Date.now() - 5 * 24 * 60 * 60 * 1000),
          source: { name: "ZDNet" },
          url: "#",
          urlToImage: "https://images.unsplash.com/photo-1576444356170-66073046b1bc?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60",
          category: "cybersecurity"
        }
      ];
    }
  },
  mounted() {
    this.fetchArticles();
  }
}
</script>

