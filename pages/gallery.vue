<template>
  <div class="min-h-screen bg-[#131517]">
    <!-- Hero Section -->
    <div class="px-4">
      <div class="text-center py-16">
        <h1 class="text-4xl md:text-5xl font-bold mb-6 text-[#f08330]">
          Project Gallery
        </h1>
        <p class="text-xl text-gray-200 max-w-3xl mx-auto">
          Browse through our recent projects to see the Flip Fixer difference.
          From full home remodels to quick handyman fixes, our gallery showcases
          the quality workmanship and attention to detail we bring to every job.
        </p>
      </div>
    </div>

    <!-- Before & After Section -->
    <section class="py-16 px-4">
      <div class="container mx-auto max-w-6xl">
        <h2 class="text-3xl font-bold text-[#f08330] text-center mb-12">
          Before & After Transformations
        </h2>
        <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
          <div class="gallery-card group">
            <div class="relative overflow-hidden">
              <img
                src="https://placehold.co/800x600/f08330/white?text=Kitchen"
                alt="Kitchen Transformation"
                class="w-full h-64 object-cover transition-transform duration-500 group-hover:scale-110"
              />
              <div
                class="absolute inset-0 bg-black bg-opacity-40 flex items-center justify-center opacity-0 group-hover:opacity-100 transition-opacity duration-300"
              >
                <Kitchen class="w-12 h-12 text-white" />
              </div>
            </div>
            <div class="p-6">
              <h3 class="text-xl font-semibold mb-3">Kitchen Overhauls</h3>
              <p class="text-gray-300">
                See how we've turned outdated kitchens into modern culinary
                spaces.
              </p>
            </div>
          </div>

          <div class="gallery-card group">
            <div class="relative overflow-hidden">
              <img
                src="https://placehold.co/800x600/f08330/white?text=Bathroom"
                alt="Bathroom Transformation"
                class="w-full h-64 object-cover transition-transform duration-500 group-hover:scale-110"
              />
              <div
                class="absolute inset-0 bg-black bg-opacity-40 flex items-center justify-center opacity-0 group-hover:opacity-100 transition-opacity duration-300"
              >
                <Shower class="w-12 h-12 text-white" />
              </div>
            </div>
            <div class="p-6">
              <h3 class="text-xl font-semibold mb-3">Bathroom Upgrades</h3>
              <p class="text-gray-300">
                Check out our sleek tile work, updated vanities, and
                contemporary fixtures.
              </p>
            </div>
          </div>

          <div class="gallery-card group">
            <div class="relative overflow-hidden">
              <img
                src="https://placehold.co/800x600/f08330/white?text=Exterior"
                alt="Exterior Transformation"
                class="w-full h-64 object-cover transition-transform duration-500 group-hover:scale-110"
              />
              <div
                class="absolute inset-0 bg-black bg-opacity-40 flex items-center justify-center opacity-0 group-hover:opacity-100 transition-opacity duration-300"
              >
                <Home class="w-12 h-12 text-white" />
              </div>
            </div>
            <div class="p-6">
              <h3 class="text-xl font-semibold mb-3">Exterior Improvements</h3>
              <p class="text-gray-300">
                Discover the power of fresh paint, new siding, and roof repairs
                in boosting curb appeal.
              </p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Project Spotlights -->
    <section class="py-16 px-4 bg-stone-900">
      <div class="container mx-auto max-w-6xl">
        <h2 class="text-3xl font-bold text-[#f08330] text-center mb-12">
          Project Spotlights
        </h2>
        <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
          <div class="spotlight-card group">
            <div class="relative overflow-hidden">
              <img
                src="https://placehold.co/1200x800/f08330/white?text=Complete+Renovation"
                alt="Complete Home Renovation"
                class="w-full h-80 object-cover transition-transform duration-500 group-hover:scale-110"
              />
              <div
                class="absolute inset-0 bg-black bg-opacity-40 flex items-center justify-center opacity-0 group-hover:opacity-100 transition-opacity duration-300"
              >
                <Building class="w-16 h-16 text-white" />
              </div>
            </div>
            <div class="p-6">
              <h3 class="text-xl font-semibold mb-3">
                Complete Home Renovations
              </h3>
              <p class="text-gray-300">
                We'll highlight a few notable projects where we handled every
                aspect—design to final touches.
              </p>
            </div>
          </div>

          <div class="spotlight-card group">
            <div class="relative overflow-hidden">
              <img
                src="https://placehold.co/1200x800/f08330/white?text=Custom+Work"
                alt="Custom Creations"
                class="w-full h-80 object-cover transition-transform duration-500 group-hover:scale-110"
              />
              <div
                class="absolute inset-0 bg-black bg-opacity-40 flex items-center justify-center opacity-0 group-hover:opacity-100 transition-opacity duration-300"
              >
                <Hammer class="w-16 h-16 text-white" />
              </div>
            </div>
            <div class="p-6">
              <h3 class="text-xl font-semibold mb-3">Custom Creations</h3>
              <p class="text-gray-300">
                Show off special projects like custom furniture pieces,
                pet-friendly installations, or artistic finishes.
              </p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- More Projects Section -->
    <section class="py-16 px-4">
      <div class="container mx-auto max-w-6xl">
        <h2 class="text-3xl font-bold text-[#f08330] text-center mb-12">
          More Projects
        </h2>
        <div class="columns-1 sm:columns-2 lg:columns-3 gap-4 space-y-4">
          <div
            v-for="(image, index) in projectImages"
            :key="index"
            class="break-inside-avoid cursor-pointer group"
            @click="openModal(index)"
          >
            <div class="relative overflow-hidden rounded-lg">
              <img
                :src="image.src"
                :alt="image.alt"
                class="w-full object-cover transition-transform duration-500 group-hover:scale-105"
              />
              <div
                class="absolute inset-0 bg-black bg-opacity-40 flex items-center justify-center opacity-0 group-hover:opacity-100 transition-opacity duration-300"
              >
                <Maximize2 class="w-8 h-8 text-white" />
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Modal for expanded view -->
      <div
        v-if="selectedImage !== null"
        class="fixed inset-0 bg-black bg-opacity-90 z-50 flex items-center justify-center p-4"
        @click="closeModal"
      >
        <button
          class="absolute top-4 right-4 text-white hover:text-[#f08330] transition-colors"
          @click="closeModal"
        >
          <X class="w-8 h-8" />
        </button>
        <button
          v-if="selectedImage > 0"
          class="absolute left-4 text-white hover:text-[#f08330] transition-colors"
          @click.stop="previousImage"
        >
          <ChevronLeft class="w-8 h-8" />
        </button>
        <button
          v-if="selectedImage < projectImages.length - 1"
          class="absolute right-4 text-white hover:text-[#f08330] transition-colors"
          @click.stop="nextImage"
        >
          <ChevronRight class="w-8 h-8" />
        </button>
        <div class="max-w-4xl max-h-full" @click.stop>
          <img
            :src="projectImages[selectedImage]?.src"
            :alt="projectImages[selectedImage]?.alt"
            class="max-h-[80vh] w-auto mx-auto"
          />
          <p class="text-white text-center mt-4">
            {{ projectImages[selectedImage]?.description }}
          </p>
        </div>
      </div>
    </section>

    <!-- CTA Section -->
    <section class="py-16 px-4 bg-stone-900">
      <div class="container mx-auto max-w-4xl text-center">
        <h2 class="text-3xl font-bold text-[#f08330] mb-6">
          Love What You See?
        </h2>
        <p class="text-xl text-gray-200 mb-8">
          We'd love to make your vision come to life. Contact us to discuss your
          next project and let's add your transformation to our gallery!
        </p>
        <NuxtLink
          to="/contact"
          class="inline-block bg-[#d4681b] hover:bg-[#ca5e11] text-white font-semibold py-4 px-8 rounded-lg transition-colors duration-300"
        >
          Contact Us
        </NuxtLink>
      </div>
    </section>
  </div>
</template>

<script setup>
import {
  Home,
  Building,
  Hammer,
  Maximize2,
  X,
  ChevronLeft,
  ChevronRight,
} from "lucide-vue-next";
import { ref, onMounted, onUnmounted } from "vue";

// Sample project images - replace with actual project images
const projectImages = [
  {
    src: "https://placehold.co/600x800/f08330/white?text=Kitchen+1",
    alt: "Modern Kitchen Renovation",
    description: "Complete kitchen remodel with custom cabinets and island",
  },
  {
    src: "https://placehold.co/800x600/f08330/white?text=Bathroom+1",
    alt: "Luxury Bathroom",
    description: "Master bathroom renovation with custom tile work",
  },
  {
    src: "https://placehold.co/600x900/f08330/white?text=Living+Room",
    alt: "Living Room Transformation",
    description: "Open concept living room with custom built-ins",
  },
  {
    src: "https://placehold.co/900x600/f08330/white?text=Exterior+1",
    alt: "Home Exterior",
    description: "Complete exterior renovation with new siding and windows",
  },
  {
    src: "https://placehold.co/600x600/f08330/white?text=Custom+Work+1",
    alt: "Custom Carpentry",
    description: "Custom built entertainment center with hidden storage",
  },
  {
    src: "https://placehold.co/800x1000/f08330/white?text=Deck",
    alt: "Outdoor Living",
    description: "Custom deck with built-in seating and pergola",
  },
  {
    src: "https://placehold.co/700x500/f08330/white?text=Small+Project",
    alt: "Small Project",
    description: "Quick turnaround bathroom update",
  },
  {
    src: "https://placehold.co/600x800/f08330/white?text=Kitchen+2",
    alt: "Kitchen Update",
    description: "Kitchen refresh with new countertops and backsplash",
  },
  {
    src: "https://placehold.co/800x800/f08330/white?text=Custom+Work+2",
    alt: "Custom Work",
    description: "Custom built-in office space with storage solutions",
  },
];

const selectedImage = ref(null);

const openModal = (index) => {
  selectedImage.value = index;
  document.body.style.overflow = "hidden"; // Prevent scrolling when modal is open
};

const closeModal = () => {
  selectedImage.value = null;
  document.body.style.overflow = ""; // Restore scrolling
};

const nextImage = () => {
  if (selectedImage.value < projectImages.length - 1) {
    selectedImage.value++;
  }
};

const previousImage = () => {
  if (selectedImage.value > 0) {
    selectedImage.value--;
  }
};

// Add keyboard navigation
onMounted(() => {
  const handleKeydown = (e) => {
    if (selectedImage.value === null) return;

    switch (e.key) {
      case "ArrowRight":
        nextImage();
        break;
      case "ArrowLeft":
        previousImage();
        break;
      case "Escape":
        closeModal();
        break;
    }
  };

  window.addEventListener("keydown", handleKeydown);
  onUnmounted(() => {
    window.removeEventListener("keydown", handleKeydown);
  });
});

useHead({
  title: "Project Gallery",
  meta: [
    {
      name: "description",
      content:
        "View our portfolio of completed projects. Before and after transformations of kitchens, bathrooms, and full home renovations.",
    },
  ],
});
</script>

<style scoped>
.gallery-hero {
  position: relative;
}

.gallery-hero::before {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)),
    url("https://placehold.co/1920x400/f08330/white?text=Gallery");
  background-size: cover;
  background-position: center;
  z-index: 0;
}

.gallery-hero > div {
  position: relative;
  z-index: 1;
}

.gallery-card,
.spotlight-card {
  background-color: #1a1d20;
  border: 1px solid #2d3238;
  border-radius: 0.5rem;
  overflow: hidden;
  transition: transform 0.3s ease;
}

.gallery-card:hover,
.spotlight-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 8px 12px rgba(0, 0, 0, 0.3);
}

h3 {
  color: #f08330;
}

.break-inside-avoid {
  break-inside: avoid;
}

/* Add smooth loading for images */
img {
  opacity: 0;
  animation: fadeIn 0.5s ease forwards;
}

@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

/* Optional: Add touch swipe support for mobile */
@media (hover: none) {
  .modal-content {
    touch-action: pan-y pinch-zoom;
  }
}
</style>
