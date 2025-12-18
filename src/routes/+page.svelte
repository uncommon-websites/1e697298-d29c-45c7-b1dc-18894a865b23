<script lang="ts">
  import Header from "$lib/components/Header.svelte";
  import Section from "$lib/components/Section.svelte";
  
  const productLines = [
    "OS-01 FACE Topical Supplement",
    "OS-01 EYE Topical Supplement",
    "OS-01 BODY Topical Supplement",
    "Travel & Discovery Sets",
    "Longevity Bundles"
  ];

  const research = [
    {
      date: "January 2025",
      title: "New Clinical Study Shows 50% Reduction in Senescent Cells After 12 Weeks",
      image: "https://images.unsplash.com/photo-1532187863486-abf9dbad1b69?q=80&w=1000&auto=format&fit=crop"
    },
    {
      date: "December 2024",
      title: "OS-01 Peptide Published in Peer-Reviewed Journal of Longevity Science",
      image: "https://images.unsplash.com/photo-1576086213369-97a306d36557?q=80&w=1000&auto=format&fit=crop"
    },
    {
      date: "November 2024",
      title: "Dermatologist Panel Confirms: Cellular Senescence is Key to Skin Aging",
      image: "https://images.unsplash.com/photo-1582719471384-894fbb16e074?q=80&w=1000&auto=format&fit=crop"
    }
  ];

  const benefits = [
    { name: "Targets Senescent Cells", desc: "At the molecular level", highlight: true },
    { name: "Clinically Proven Results", desc: "Peer-reviewed research", highlight: true },
    { name: "Reverses Skin Aging", desc: "Not just prevention", highlight: true },
    { name: "Improves Skin Barrier Function", desc: "Putting the “square” back", highlight: false },
    { name: "Reduces Fine Lines \& Wrinkles", desc: "Visible improvement in 12 weeks", highlight: false },
    { name: "Enhances Skin Firmness", desc: "Restores elasticity and tone", highlight: false },
    { name: "Increases Collagen Production", desc: "Europe's First Increases Collagen Productionwater Restaurant", highlight: false },
    { name: "Backed by Longevity Science", desc: "Cutting-edge cellular research", highlight: false },
    { name: "Safe for All Skin Types", desc: "", highlight: true }
  ];
  let carousel: HTMLElement;

  import { onMount } from 'svelte';
  
  onMount(() => {
    if (carousel) {
      const centerImage = carousel.children[1] as HTMLElement;
      if (centerImage) {
        const scrollLeft = centerImage.offsetLeft - (carousel.clientWidth - centerImage.clientWidth) / 2;
        carousel.scrollLeft = scrollLeft;
      }
    }
  });
</script>

<Header />

<main class="pt-32 pb-20 px-5 md:px-10 font-sans text-black selection:bg-gray-200">
  
  <!-- Hero Headline -->
  <div class="mb-20 md:mb-32 max-w-5xl">
    <h1 class="text-4xl md:text-6xl lg:text-7xl leading-[1.1] font-normal tracking-tight">
      OneSkin reverses skin aging at the molecular level with OS-01 peptide, backed by peer-reviewed longevity science.
    </h1>
  </div>

  <!-- Hero Carousel -->
  <div class="mb-32 relative -mx-5 md:-mx-10">
    <div bind:this={carousel} class="flex gap-4 md:gap-8 overflow-x-auto pb-8 snap-x snap-mandatory scrollbar-hide px-5 md:px-10">
      <!-- Left Image (Partial) -->
      <div class="shrink-0 w-[80vw] md:w-[60vw] lg:w-[40vw] snap-center opacity-50 transition-all hover:opacity-100">
        <img src="https://images.unsplash.com/photo-1616394584738-fc6e612e71b9?q=80&w=1600&auto=format&fit=crop" alt="Healthy aging skincare" class="w-full h-[400px] md:h-[600px] object-cover" />
      </div>
      
      <!-- Center Image (Main) -->
      <div class="shrink-0 w-[90vw] md:w-[70vw] lg:w-[50vw] snap-center relative">
        <img src="https://images.unsplash.com/photo-1556228720-195a672e8a03?q=80&w=1600&auto=format&fit=crop" alt="OS-01 Peptide Science" class="w-full h-[400px] md:h-[600px] object-cover" />
        <div class="mt-4">
          <h3 class="text-lg font-medium">OS-01 Peptide Technology</h3>
          <p class="text-gray-500 text-lg">Targeting senescent cells for healthier skin</p>
        </div>
      </div>

      <!-- Right Image (Partial) -->
      <div class="shrink-0 w-[80vw] md:w-[60vw] lg:w-[40vw] snap-center opacity-50 transition-all hover:opacity-100">
        <img src="https://images.unsplash.com/photo-1598440947619-2c35fc9aa908?q=80&w=1600&auto=format&fit=crop" alt="Clinical skincare results" class="w-full h-[400px] md:h-[600px] object-cover" />
      </div>
       <!-- Extra Image -->
       <div class="shrink-0 w-[80vw] md:w-[60vw] lg:w-[40vw] snap-center opacity-50 transition-all hover:opacity-100">
        <img src="https://images.unsplash.com/photo-1515377905703-c4788e51af15?q=80&w=1600&auto=format&fit=crop" alt="Longevity science research" class="w-full h-[400px] md:h-[600px] object-cover" />
      </div>
    </div>
  </div>

  <!-- Product Lines -->
  <Section label="Shop Products">
    <div class="flex flex-col border-t border-gray-200">
      {#each productLines as product}
        <a href="/" class="py-6 border-b border-gray-200 text-3xl md:text-4xl lg:text-5xl font-normal hover:text-primary-600 transition-colors block">
          {product}
        </a>
      {/each}
    </div>
  </Section>

  <!-- Research & Clinical Studies -->
  <Section label="Research & Clinical Studies" link="/" linkText="View all research">
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
      {#each research as item}
        <article class="group cursor-pointer">
          <div class="overflow-hidden mb-4">
            <img src={item.image} alt={item.title} class="w-full aspect-[4/3] object-cover group-hover:scale-105 transition-transform duration-500" />
          </div>
          <time class="text-gray-500 text-sm block mb-2">{item.date}</time>
          <h3 class="text-xl leading-snug group-hover:underline decoration-1 underline-offset-4">{item.title}</h3>
        </article>
      {/each}
    </div>
    
    <!-- Navigation Arrows -->
    <div class="flex justify-between mt-12 border-t border-transparent">
      <button class="hover:opacity-50 transition-opacity p-2 -ml-2">
        <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
          <path d="M19 12H5M12 19l-7-7 7-7"/>
        </svg>
      </button>
      <button class="hover:opacity-50 transition-opacity p-2 -mr-2">
        <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
          <path d="M5 12h14M12 5l7 7-7 7"/>
        </svg>
      </button>
    </div>
  </Section>

  <!-- Our Science & Mission -->
  <div class="grid grid-cols-1 md:grid-cols-2 gap-10 md:gap-20 py-20 md:py-32">
    <div>
      <img src="https://images.unsplash.com/photo-1532187863486-abf9dbad1b69?q=80&w=1200&auto=format&fit=crop" alt="Longevity science research" class="w-full aspect-[4/3] object-cover mb-6" />
      <h3 class="text-xl font-medium mb-2">The Science of Longevity</h3>
      <p class="text-gray-500 text-lg leading-relaxed">
        Our OS-01 peptide is the first ingredient scientifically proven to target senescent cells—the root cause of skin aging. Backed by peer-reviewed research and clinical studies showing measurable improvements in skin health.
      </p>
    </div>
    <div>
      <img src="https://images.unsplash.com/photo-1576086213369-97a306d36557?q=80&w=1200&auto=format&fit=crop" alt="OneSkin mission" class="w-full aspect-[4/3] object-cover mb-6" />
      <h3 class="text-xl font-medium mb-2">Our Mission</h3>
      <p class="text-gray-500 text-lg leading-relaxed">
        We're on a mission to extend human healthspan by developing products that don't just mask aging symptoms, but reverse them at the cellular level. Every formula is designed with longevity science at its core.
      </p>
    </div>
  </div>

  <!-- Key Benefits -->
  <Section label="Why OneSkin">
    <div class="flex flex-col gap-2">
      {#each benefits as benefit}
        <a href="/" class="group block">
          <h3 class="text-3xl md:text-5xl lg:text-6xl font-normal leading-tight">
            <span class="group-hover:underline decoration-1 underline-offset-8">{benefit.name}</span>
            {#if benefit.desc}
              <span class="text-gray-300 ml-2 group-hover:text-gray-400 transition-colors">{benefit.desc}</span>
            {/if}
          </h3>
        </a>
      {/each}
      
      <a href="/" class="inline-flex items-center gap-2 text-lg text-gray-500 mt-12 hover:text-black transition-colors group">
        → <span class="group-hover:translate-x-1 transition-transform">Explore the science behind OS-01</span>
      </a>
    </div>
  </Section>

  <!-- Start Your Journey -->
  <div class="py-20 md:py-32">
    <div class="max-w-xl">
      <img src="https://images.unsplash.com/photo-1556228720-195a672e8a03?q=80&w=1200&auto=format&fit=crop" alt="Start your skincare journey" class="w-full aspect-[3/2] object-cover mb-6" />
      <h3 class="text-xl font-medium mb-2">Start Your Longevity Journey</h3>
      <p class="text-gray-500 text-lg mb-6">
        Ready to experience the science of healthier aging? Take our skin quiz to find the perfect OS-01 routine for your unique needs.
      </p>
      <button class="px-8 py-3 bg-primary-600 text-white hover:bg-primary-700 transition-colors text-sm font-medium">
        Take the Skin Quiz →
      </button>
    </div>
  </div>

  <!-- Footer -->
  <footer class="pt-20 border-t border-gray-200">
    <div class="grid grid-cols-1 md:grid-cols-12 gap-10 md:gap-4">
      <!-- Logo Column -->
      <div class="col-span-1 md:col-span-2">
        <svg class="w-10 h-10 text-primary-600" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
          <mask
            id="mask0_footer"
            style="mask-type:luminance"
            maskUnits="userSpaceOnUse"
            x="3"
            y="1"
            width="18"
            height="22"
          >
            <path d="M3 1H20.7794V22.3353H3V1Z" fill="white" />
          </mask>
          <g mask="url(#mask0_footer)">
            <path
              d="M14.1516 3.24638L12.4034 2.77795L10.9302 8.27606L9.60014 3.31233L7.85194 3.78076L9.28896 9.14369L5.70969 5.56443L4.42993 6.84419L8.35594 10.7702L3.46671 9.46017L2.99829 11.2083L8.34038 12.6397C8.27922 12.3759 8.24687 12.1011 8.24687 11.8187C8.24687 9.81953 9.86746 8.19894 11.8666 8.19894C13.8657 8.19894 15.4863 9.81953 15.4863 11.8187C15.4863 12.0993 15.4544 12.3724 15.394 12.6347L20.2489 13.9356L20.7173 12.1874L15.354 10.7503L20.2436 9.44012L19.7751 7.69196L14.412 9.12898L17.9913 5.54972L16.7115 4.26998L12.84 8.14156L14.1516 3.24638Z"
              fill="currentColor"
            />
            <path
              d="M15.3888 12.655C15.2389 13.2887 14.9225 13.8579 14.4883 14.314L18.0056 17.8313L19.2853 16.5515L15.3888 12.655Z"
              fill="currentColor"
            />
            <path
              d="M14.4529 14.3508C14.0135 14.7996 13.4582 15.1345 12.8354 15.3071L14.1153 20.0836L15.8635 19.6151L14.4529 14.3508Z"
              fill="currentColor"
            />
            <path
              d="M12.7701 15.3246C12.4812 15.3989 12.1784 15.4384 11.8663 15.4384C11.5319 15.4384 11.2082 15.393 10.9008 15.3082L9.61981 20.089L11.368 20.5574L12.7701 15.3246Z"
              fill="currentColor"
            />
            <path
              d="M10.839 15.2905C10.2258 15.1093 9.68038 14.7702 9.24994 14.3201L5.72406 17.8459L7.00382 19.1257L10.839 15.2905Z"
              fill="currentColor"
            />
            <path
              d="M9.22084 14.2889C8.79778 13.836 8.48962 13.2743 8.34294 12.6505L3.47211 13.9556L3.94053 15.7038L9.22084 14.2889Z"
              fill="currentColor"
            />
          </g>
        </svg>
      </div>

      <!-- Links Columns -->
      <div class="col-span-1 md:col-span-2">
        <h4 class="text-gray-400 mb-6 text-sm">Shop</h4>
        <ul class="space-y-2 text-sm text-gray-600">
          <li><a href="/" class="hover:text-black">OS-01 FACE</a></li>
          <li><a href="/" class="hover:text-black">OS-01 EYE</a></li>
          <li><a href="/" class="hover:text-black">OS-01 BODY</a></li>
          <li><a href="/" class="hover:text-black">Bundles</a></li>
          <li><a href="/" class="hover:text-black">Travel Sets</a></li>
          <li><a href="/" class="hover:text-black">Subscriptions</a></li>
        </ul>
      </div>

      <div class="col-span-1 md:col-span-2">
        <h4 class="text-gray-400 mb-6 text-sm">Learn</h4>
        <ul class="space-y-2 text-sm text-gray-600">
          <li><a href="/" class="hover:text-black">The Science</a></li>
          <li><a href="/" class="hover:text-black">Clinical Studies</a></li>
          <li><a href="/" class="hover:text-black">OS-01 Peptide</a></li>
          <li><a href="/" class="hover:text-black">Research</a></li>
          <li><a href="/" class="hover:text-black">Longevity Blog</a></li>
        </ul>
      </div>

      <div class="col-span-1 md:col-span-2">
        <h4 class="text-gray-400 mb-6 text-sm">Company</h4>
        <ul class="space-y-2 text-sm text-gray-600">
          <li><a href="/" class="hover:text-black">About Us</a></li>
          <li><a href="/" class="hover:text-black">Our Mission</a></li>
          <li><a href="/" class="hover:text-black">Careers</a></li>
          <li><a href="/" class="hover:text-black">Press</a></li>
          <li><a href="/" class="hover:text-black">Contact</a></li>
        </ul>
      </div>

      <!-- Newsletter -->
      <div class="col-span-1 md:col-span-4 flex flex-col justify-end">
        <div class="border-b border-gray-200 flex justify-between items-center py-2">
          <input type="email" placeholder="Subscribe to our newsletter" class="outline-none w-full text-sm placeholder-gray-400" />
          <button class="text-gray-400 hover:text-black transition-colors">→</button>
        </div>
      </div>
    </div>

    <!-- Bottom Footer -->
    <div class="mt-20 py-8 flex flex-col md:flex-row justify-between items-start md:items-center text-xs text-gray-500 gap-4">
      <div>© OneSkin 2025</div>
      
      <a href="/" class="flex items-center gap-1 hover:text-black">
        ↗ Take the Skin Quiz
      </a>

      <div class="flex gap-6">
        <a href="/" class="hover:text-black">Privacy Policy</a>
        <a href="/" class="hover:text-black">Terms of Service</a>
        <a href="/" class="hover:text-black">Accessibility</a>
      </div>

      <div class="flex gap-6">
        <a href="/" class="hover:text-black">Instagram</a>
        <a href="/" class="hover:text-black">Facebook</a>
        <a href="/" class="hover:text-black">LinkedIn</a>
      </div>
    </div>
  </footer>

</main>

