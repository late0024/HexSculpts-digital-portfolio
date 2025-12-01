<script setup lang="ts">
import { computed, onBeforeUnmount, onMounted, ref, watch } from "vue";
import laceImage from "~/assets/lace.jpg";
import sakura from "~/assets/sakura.jpg";
import shutara from "~/assets/shutara.jpg";
import tshirts from "~/assets/t-shirts.png";
import notis from "~/assets/notifications.png";
import seuss from "~/assets/seussAPI.png";
import rania from "~/assets/rania.jpg";

definePageMeta({ layout: "home" });

type CarouselCard = {
  id: number;
  image: string;
  badge: string;
  title: string;
  copy: string;
};

const cards: CarouselCard[] = [
  {
    id: 1,
    image: laceImage,
    badge: "3D",
    title: "Lace sculpt",
    copy: "Full body sculpt of lace from silksong",
  },
  {
    id: 2,
    image: sakura,
    badge: "3D",
    title: "Street Fighter 6 Sakura",
    copy: "Sakura body sculpt and practice",
  },
  {
    id: 3,
    image: shutara,
    badge: "3D",
    title: "Bleach Shutara Senjumaru",
    copy: "Shutara senjumaru full body sculpt and pose practice",
  },
  {
    id: 4,
    image: tshirts,
    badge: "Web",
    title: "T-shirt Store Concept",
    copy: "E-commerce t-shirt store functionality prototype",
  },
  {
    id: 5,
    image: notis,
    badge: "Web",
    title: "Notification system UI prototype",
    copy: "a notification system user interface prototype that can be integrated into web applications",
  },
  {
    id: 6,
    image: seuss,
    badge: "Web",
    title: "Dr suess book finder API",
    copy: "An API that fetches Dr Seuss books and displays them based on user search input",
  },
  {
    id: 7,
    image: rania,
    badge: "Photography",
    title: "Psychology office professional shoot",
    copy: "This image is a thumbnail of the full album of the photoshoot",
  },
];

const placeholderImage = "/placeholder.png";

// this is the carousel logic dont touch
const currentIndex = ref(0);
const perView = ref(3);
const maxIndex = computed(() => Math.max(cards.length - perView.value, 0));

const syncPerView = () => {
  if (typeof window === "undefined") return;
  const width = window.innerWidth;
  if (width <= 640) {
    perView.value = 1;
  } else if (width <= 960) {
    perView.value = 2;
  } else {
    perView.value = 3;
  }
};

onMounted(() => {
  syncPerView();
  window.addEventListener("resize", syncPerView);
});

onBeforeUnmount(() => {
  if (typeof window === "undefined") return;
  window.removeEventListener("resize", syncPerView);
});

const next = () => {
  currentIndex.value =
    currentIndex.value >= maxIndex.value ? 0 : currentIndex.value + 1;
};

const prev = () => {
  currentIndex.value =
    currentIndex.value <= 0 ? maxIndex.value : currentIndex.value - 1;
};

watch(perView, () => {
  currentIndex.value = Math.min(currentIndex.value, maxIndex.value);
});
</script>

<template>
  <section class="hero-banner container-fluid py-5">
    <div class="row align-items-center g-4 px-4 px-lg-5">
      <div class="col-12 col-lg-6">
        <p class="text-uppercase fw-semibold hero-kicker mb-2 hero-kicker-top">
          Portfolio Showcase
        </p>
        <h1 class="display-5 fw-bold mb-3 text-white">
          Hexsculpts Digital Workshop
        </h1>
        <p class="lead mb-4 text-white-50">
          This is where I showcase my work and give you an idea of who I am and
          what I do.
        </p>
        <div class="d-flex flex-wrap gap-2">
          <NuxtLink class="btn btn-success btn-lg px-4" to="/projects">
            View Projects
          </NuxtLink>
          <NuxtLink class="btn btn-outline-success btn-lg px-4" to="/contacts">
            Get in Touch
          </NuxtLink>
        </div>
      </div>
    </div>
  </section>

  <!-- this is the carousel system dont touch -->
  <section class="card-carousel">
    <div class="carousel-head">
      <div>
        <p class="eyebrow">Featured Work</p>
        <h2>Projects in Rotation</h2>
        <p>Glance through a rotating set of placeholder projects.</p>
      </div>
      <div class="carousel-actions">
        <button
          class="nav-btn"
          type="button"
          @click="prev"
          aria-label="Previous cards"
        >
          ‹
        </button>
        <button
          class="nav-btn"
          type="button"
          @click="next"
          aria-label="Next cards"
        >
          ›
        </button>
      </div>
    </div>

    <div class="carousel-shell">
      <div class="carousel-window" aria-label="Portfolio card carousel">
        <div
          class="carousel-track"
          :style="{ '--offset': currentIndex, '--card-per-view': perView }"
          role="list"
          aria-live="polite"
        >
          <article
            class="carousel-card"
            v-for="card in cards"
            :key="card.id"
            role="listitem"
          >
            <div class="card-media">
              <img :src="card.image || placeholderImage" :alt="card.title" />
              <span class="media-badge">{{ card.badge }}</span>
            </div>
            <div class="card-body">
              <h3>{{ card.title }}</h3>
              <p>{{ card.copy }}</p>
            </div>
          </article>
        </div>
      </div>
    </div>
  </section>

  <div class="container my-4">
    <section class="p-4 rounded-4 bg-dark text-white future-plans">
      <h2>Future Plans</h2>
      <ul class="future-plans-list">
        <li>Introduce Sewing and outfit design into workflow</li>
        <li>Create End to End pipeline of 3D models ready for game and film</li>
        <li>(Long Term) Create a full animated movie</li>
      </ul>
    </section>
  </div>
</template>

<style scoped>
.card-carousel {
  margin: 3rem auto;
  display: flex;
  flex-direction: column;
  gap: 1.25rem;
}

.hero-banner {
  background: #292a2a;
  color: #ffffff;
  width: 100vw;
  margin-left: calc(50% - 50vw);
  margin-right: calc(50% - 50vw);
  padding-left: clamp(1rem, 4vw, 3rem);
  padding-right: clamp(1rem, 4vw, 3rem);
  padding-top: 0;
}

.hero-kicker {
  letter-spacing: 0.08em;
  color: #d0d3ff;
}

.hero-kicker-top {
  padding-top: 1rem;
}

.hero-placeholder {
  background: rgba(255, 255, 255, 0.04);
  border-color: rgba(255, 255, 255, 0.12) !important;
}

.future-plans-list {
  list-style: none;
  padding-left: 0;
  margin: 0;
  display: grid;
  gap: 0.35rem;
  color: #ffffff;
}

.carousel-head {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 1rem;
}

.eyebrow {
  text-transform: uppercase;
  letter-spacing: 0.08em;
  font-weight: 600;
  font-size: 0.82rem;
  color: #6b7280;
  margin: 0;
}

.carousel-head h2 {
  margin: 0.15rem 0;
}

.carousel-head p {
  margin: 0;
  color: #4b5563;
}

.carousel-actions {
  display: flex;
  gap: 0.5rem;
}

.nav-btn {
  width: 44px;
  height: 44px;
  border-radius: 50%;
  border: 1px solid #e5e7eb;
  background: #fff;
  color: #0f172a;
  font-size: 1.5rem;
  line-height: 1;
  cursor: pointer;
  transition: box-shadow 150ms ease, transform 150ms ease;
}

.nav-btn:hover {
  box-shadow: 0 8px 18px rgba(0, 0, 0, 0.1);
  transform: translateY(-1px);
}

.carousel-shell {
  position: relative;
}

.carousel-window {
  overflow: hidden;
  width: 100%;
  border-radius: 18px;
}

.carousel-track {
  display: flex;
  gap: 1rem;
  --card-per-view: 3;
  --gap: 1rem;
  --card-width: calc(
    (100% - (var(--card-per-view) - 1) * var(--gap)) / var(--card-per-view)
  );
  transform: translateX(
    calc((var(--card-width) + var(--gap)) * -1 * var(--offset, 0))
  );
  transition: transform 250ms ease;
  padding: 0.25rem;
}

.carousel-card {
  flex: 0 0 var(--card-width);
  max-width: var(--card-width);
  background: #198754;
  border: 1px solid #146c43;
  border-radius: 16px;
  box-shadow: 0 16px 40px rgba(0, 0, 0, 0.1);
  overflow: hidden;
  display: flex;
  flex-direction: column;
}

.card-media {
  position: relative;
  width: 100%;
  aspect-ratio: 4 / 3;
  overflow: hidden;
  background: linear-gradient(135deg, #f3f4f6, #e5e7eb);
}

.card-media img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
}

.media-badge {
  position: absolute;
  top: 12px;
  left: 12px;
  padding: 0.35rem 0.75rem;
  background: #111827;
  color: #f9fafb;
  border-radius: 999px;
  font-size: 0.8rem;
}

.card-body {
  padding: 1rem 1rem 1.25rem;
  display: grid;
  gap: 0.35rem;
  color: #ffffff;
}

.card-body h3 {
  margin: 0;
}

.card-body p {
  margin: 0;
  color: #e8f5e9;
}

.card-foot {
  font-size: 0.85rem;
  color: #d1e7dd;
}

@media (max-width: 960px) {
  .carousel-track {
    --card-per-view: 2;
  }
}

@media (max-width: 640px) {
  .carousel-head {
    flex-direction: column;
    align-items: flex-start;
  }

  .carousel-actions {
    align-self: flex-end;
  }

  .carousel-track {
    --card-per-view: 1;
  }
}
</style>
