<template>
  <div class="flex min-h-screen flex-col">
    <header class="container mx-auto flex items-center justify-between py-4">
      <div class="font-bold">Logo</div>
      <nav class="hidden md:flex items-center space-x-6">
        <a href="#" class="text-sm">Destination</a>
        <a href="#" class="text-sm">Last Call</a>
        <a href="#" class="text-sm">Travel Gear</a>
        <a href="#" class="text-sm">Offers</a>
        <a href="#" class="text-sm">Blog</a>
      </nav>
      <div class="flex items-center space-x-4">
        <button class="hidden md:flex items-center text-sm">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            width="16"
            height="16"
            viewBox="0 0 24 24"
            fill="none"
            stroke="currentColor"
            stroke-width="2"
            stroke-linecap="round"
            stroke-linejoin="round"
            class="mr-1"
          >
            <circle cx="11" cy="11" r="8" />
            <path d="m21 21-4.3-4.3" />
          </svg>
          Search
        </button>
        <button
          class="rounded-full bg-black text-white text-xs px-4 py-1 h-auto"
        >
          LOGIN
        </button>
      </div>
    </header>

    <main class="flex-1">
      <section class="container mx-auto py-12">
        <div class="grid grid-cols-1 md:grid-cols-2 gap-8 items-center">
          <div class="space-y-4">
            <h1 class="text-4xl font-bold leading-tight">
              Discover the World's Hidden Wonders
            </h1>
            <p class="text-sm text-gray-600">
              Find all the unique, hidden gems, places to visit, and things to
              do in your next travel destination. We've curated the best travel
              experiences for you to explore and enjoy.
            </p>
            <button class="rounded-full bg-black text-white px-6 py-2">
              Explore now
            </button>
          </div>
          <div class="grid grid-cols-2 gap-4">
            <div
              class="aspect-[3/4] bg-gray-200 rounded-lg flex items-center justify-center"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                width="24"
                height="24"
                viewBox="0 0 24 24"
                fill="none"
                stroke="currentColor"
                stroke-width="2"
                stroke-linecap="round"
                stroke-linejoin="round"
                class="text-gray-400"
              >
                <rect width="18" height="18" x="3" y="3" rx="2" ry="2" />
                <circle cx="9" cy="9" r="2" />
                <path d="m21 15-3.086-3.086a2 2 0 0 0-2.828 0L6 21" />
              </svg>
            </div>
            <div class="grid grid-rows-2 gap-4">
              <div
                class="aspect-[4/3] bg-gray-200 rounded-lg flex items-center justify-center"
              >
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  width="24"
                  height="24"
                  viewBox="0 0 24 24"
                  fill="none"
                  stroke="currentColor"
                  stroke-width="2"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  class="text-gray-400"
                >
                  <rect width="18" height="18" x="3" y="3" rx="2" ry="2" />
                  <circle cx="9" cy="9" r="2" />
                  <path d="m21 15-3.086-3.086a2 2 0 0 0-2.828 0L6 21" />
                </svg>
              </div>
              <div
                class="aspect-[4/3] bg-gray-200 rounded-lg flex items-center justify-center"
              >
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  width="24"
                  height="24"
                  viewBox="0 0 24 24"
                  fill="none"
                  stroke="currentColor"
                  stroke-width="2"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  class="text-gray-400"
                >
                  <rect width="18" height="18" x="3" y="3" rx="2" ry="2" />
                  <circle cx="9" cy="9" r="2" />
                  <path d="m21 15-3.086-3.086a2 2 0 0 0-2.828 0L6 21" />
                </svg>
              </div>
            </div>
          </div>
        </div>
      </section>

      <section class="container mx-auto py-12">
        <div
          class="flex flex-col md:flex-row md:items-center justify-between mb-6"
        >
          <h2 class="text-2xl font-bold mb-4 md:mb-0">Top Destinations</h2>
          <div class="flex flex-wrap items-center">
            <div
              class="flex overflow-x-auto pb-2 md:pb-0 space-x-2 md:space-x-4"
            >
              <button
                v-for="(tab, index) in tabs"
                :key="index"
                @click="activeTab = tab"
                :class="[
                  'text-xs px-2 py-1',
                  activeTab === tab ? 'font-bold underline' : '',
                ]"
              >
                {{ tab }}
              </button>
            </div>
            <button
              class="ml-4 text-xs rounded-full border border-gray-300 px-4 py-1"
            >
              Explore all destinations
            </button>
          </div>
        </div>
        <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-4 gap-4">
          <div
            v-for="(destination, index) in destinations"
            :key="index"
            class="bg-gray-200 rounded-lg overflow-hidden"
          >
            <div class="aspect-[3/4] flex items-center justify-center">
              <svg
                xmlns="http://www.w3.org/2000/svg"
                width="24"
                height="24"
                viewBox="0 0 24 24"
                fill="none"
                stroke="currentColor"
                stroke-width="2"
                stroke-linecap="round"
                stroke-linejoin="round"
                class="text-gray-400"
              >
                <rect width="18" height="18" x="3" y="3" rx="2" ry="2" />
                <circle cx="9" cy="9" r="2" />
                <path d="m21 15-3.086-3.086a2 2 0 0 0-2.828 0L6 21" />
              </svg>
            </div>
            <div class="p-3">
              <h3 class="font-medium text-sm">{{ destination.name }}</h3>
              <p class="text-xs text-gray-500">{{ destination.location }}</p>
            </div>
          </div>
        </div>
      </section>

      <section class="container mx-auto py-12">
        <div class="flex items-center justify-between mb-6">
          <h2 class="text-2xl font-bold">Latest Stories</h2>
          <button class="text-xs rounded-full border border-gray-300 px-4 py-1">
            See more stories
          </button>
        </div>
        <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
          <div
            class="col-span-1 md:col-span-2 bg-gray-100 rounded-lg overflow-hidden"
          >
            <div
              class="aspect-video bg-gray-200 flex items-center justify-center"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                width="24"
                height="24"
                viewBox="0 0 24 24"
                fill="none"
                stroke="currentColor"
                stroke-width="2"
                stroke-linecap="round"
                stroke-linejoin="round"
                class="text-gray-400"
              >
                <rect width="18" height="18" x="3" y="3" rx="2" ry="2" />
                <circle cx="9" cy="9" r="2" />
                <path d="m21 15-3.086-3.086a2 2 0 0 0-2.828 0L6 21" />
              </svg>
            </div>
            <div class="p-4">
              <p class="text-xs text-gray-500 mb-1">Travel and Stories</p>
              <h3 class="text-lg font-bold mb-2">
                Los Angeles food & drink guide: 10 things to try in Los Angeles,
                California
              </h3>
              <p class="text-xs text-gray-500 mb-4">
                Explore the city's diverse culinary scene with our guide to the
                best food and drinks in Los Angeles. From street tacos to craft
                cocktails, we've got you covered.
              </p>
              <div class="flex items-center text-xs text-gray-500">
                <span>Published on 7 July 2023</span>
                <span class="mx-2">•</span>
                <span>5 min read</span>
              </div>
            </div>
          </div>
          <div class="col-span-1 space-y-4">
            <div
              v-for="(article, index) in sideArticles"
              :key="index"
              class="grid grid-cols-3 gap-4 items-center"
            >
              <div
                class="col-span-1 aspect-square bg-gray-200 rounded-lg flex items-center justify-center"
              >
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  width="24"
                  height="24"
                  viewBox="0 0 24 24"
                  fill="none"
                  stroke="currentColor"
                  stroke-width="2"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  class="text-gray-400"
                >
                  <rect width="18" height="18" x="3" y="3" rx="2" ry="2" />
                  <circle cx="9" cy="9" r="2" />
                  <path d="m21 15-3.086-3.086a2 2 0 0 0-2.828 0L6 21" />
                </svg>
              </div>
              <div class="col-span-2">
                <p class="text-xs text-gray-500 mb-1">
                  {{ article.date }} • {{ article.readTime }}
                </p>
                <h3 class="text-sm font-bold">{{ article.title }}</h3>
              </div>
            </div>
          </div>
        </div>
      </section>

      <section class="container mx-auto py-12">
        <h2 class="text-2xl font-bold mb-6">Trekker's Highlights</h2>
        <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
          <div class="flex gap-4">
            <div class="w-12 h-12 rounded-full bg-gray-200 flex-shrink-0"></div>
            <div class="flex-1">
              <div class="flex items-center mb-1">
                <h3 class="font-bold">Maria Angelica</h3>
                <span class="text-xs text-gray-500 ml-2"
                  >Travel Enthusiast</span
                >
              </div>
              <div class="flex text-yellow-400 mb-2">
                <svg
                  v-for="n in 5"
                  :key="n"
                  xmlns="http://www.w3.org/2000/svg"
                  width="16"
                  height="16"
                  viewBox="0 0 24 24"
                  fill="currentColor"
                  stroke="currentColor"
                  stroke-width="2"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                >
                  <polygon
                    points="12 2 15.09 8.26 22 9.27 17 14.14 18.18 21.02 12 17.77 5.82 21.02 7 14.14 2 9.27 8.91 8.26 12 2"
                  />
                </svg>
              </div>
              <p class="text-sm mb-4">
                An unforgettable journey through Turkey! The blend of ancient
                history and modern culture was captivating. From the bustling
                streets of Istanbul to the surreal landscapes of Cappadocia,
                every moment was magical. The hospitality of the locals made me
                feel right at home. The organized tours were informative and
                well-paced, allowing enough time to soak in the beauty of each
                destination. I'll definitely be returning to explore more of
                this fascinating country!
              </p>
              <p class="text-xs text-gray-500">Posted on June 15, 2023</p>
            </div>
          </div>
          <div class="relative">
            <div
              class="aspect-video bg-gray-200 rounded-lg flex items-center justify-center"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                width="24"
                height="24"
                viewBox="0 0 24 24"
                fill="none"
                stroke="currentColor"
                stroke-width="2"
                stroke-linecap="round"
                stroke-linejoin="round"
                class="text-gray-400"
              >
                <rect width="18" height="18" x="3" y="3" rx="2" ry="2" />
                <circle cx="9" cy="9" r="2" />
                <path d="m21 15-3.086-3.086a2 2 0 0 0-2.828 0L6 21" />
              </svg>
            </div>
            <div class="absolute bottom-4 left-4">
              <h3 class="text-white font-bold">
                Discover Los Angeles You'll Never Forget
              </h3>
              <button class="mt-2 text-xs bg-white px-4 py-1 rounded-full">
                Learn more about Los Angeles
              </button>
            </div>
            <div
              class="absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2"
            >
              <div
                class="w-12 h-12 rounded-full bg-white/80 flex items-center justify-center"
              >
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  width="24"
                  height="24"
                  viewBox="0 0 24 24"
                  fill="none"
                  stroke="currentColor"
                  stroke-width="2"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                >
                  <polygon points="5 3 19 12 5 21 5 3" />
                </svg>
              </div>
            </div>
          </div>
        </div>
      </section>

      <section class="bg-gray-200 py-12">
        <div class="container mx-auto text-center">
          <h2 class="text-2xl font-bold mb-2">Get Your Travel Inspiration</h2>
          <h3 class="text-xl font-bold mb-6">Straight to Your Inbox</h3>
          <div class="flex max-w-md mx-auto gap-2 mb-4">
            <input
              type="email"
              placeholder="Email address"
              class="rounded-full bg-white px-4 py-2 flex-1"
            />
            <button class="rounded-full bg-gray-800 text-white px-4 py-2">
              SUBSCRIBE
            </button>
          </div>
          <p class="text-xs text-gray-600">
            Subscribe to our newsletter to receive exclusive travel promotions.
            Read our privacy policy.
          </p>
        </div>
      </section>
    </main>

    <footer class="bg-gray-100 py-12">
      <div class="container mx-auto">
        <div class="grid grid-cols-2 md:grid-cols-5 gap-8 mb-8">
          <div>
            <h3 class="font-bold mb-4">Logo</h3>
            <div class="flex space-x-2 mb-4">
              <a
                v-for="(social, index) in socials"
                :key="index"
                href="#"
                class="w-6 h-6 rounded-full bg-gray-300 flex items-center justify-center"
              >
                <span class="sr-only"
                  ><font-awesome-icon icon="fa-brands fa-facebook"
                /></span>
              </a>
            </div>
            <p class="text-xs text-gray-600">© 2023 All Rights Reserved</p>
          </div>
          <div v-for="(column, index) in footerColumns" :key="index">
            <h3 class="font-bold mb-4">{{ column.title }}</h3>
            <ul class="space-y-2 text-sm">
              <li v-for="(link, linkIndex) in column.links" :key="linkIndex">
                <a href="#">{{ link }}</a>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </footer>
  </div>
</template>

<script setup>
import { ref } from "vue";

const activeTab = ref("Popular");
const tabs = [
  "Popular",
  "Asia",
  "Europe",
  "Africa & Middle East",
  "Americas & The Pacific",
  "Oceania",
  "More",
];

const destinations = [
  { name: "Golden Bridge, Ba Na Hills", location: "Vietnam" },
  { name: "Borobudur", location: "Indonesia" },
  { name: "Jeju Air Balloon Capsule Hotel", location: "Korea" },
  { name: "Sydney Harbour Bridge", location: "Australia" },
];

const sideArticles = [
  {
    title: "15 South London Markets You'll Love: Best Markets in South",
    date: "Aug 10, 2023",
    readTime: "3 min read",
  },
  {
    title:
      "10 incredible tourist spots in the world you can visit with virtual reality",
    date: "Aug 8, 2023",
    readTime: "4 min read",
  },
  {
    title: "Visiting Chicago on a Budget: Affordable Eats and Attractions",
    date: "Aug 5, 2023",
    readTime: "3 min read",
  },
];

const socials = ["facebook", "twitter", "instagram", "youtube", "pinterest"];

const footerColumns = [
  {
    title: "About Us",
    links: [
      "About Our Team",
      "Our Story",
      "Careers",
      "Press",
      "Guidelines",
      "How We Work",
      "Contact Us",
    ],
  },
  {
    title: "Travel Advice",
    links: [
      "Destinations",
      "Articles",
      "Experiences",
      "Travel Guides",
      "Travel Tips",
      "Travel Gear",
      "Travel News",
    ],
  },
  {
    title: "Top Destinations",
    links: [
      "Europe",
      "Asia",
      "Africa",
      "Americas",
      "Oceania",
      "Middle East",
      "Antarctica",
    ],
  },
  {
    title: "Quick Links",
    links: [
      "Privacy Policy",
      "Terms of Service",
      "Cookie Policy",
      "Sitemap",
      "Accessibility",
      "Advertise with Us",
      "Affiliate Program",
    ],
  },
];
</script>

<style>
/* @tailwind base;
@tailwind components;
@tailwind utilities; */

/* .container {
  @apply px-4 mx-auto max-w-7xl;
} */
</style>
