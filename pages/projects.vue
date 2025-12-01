<script setup lang="ts">
import { computed, ref } from "vue";
import laceImage from "~/assets/lace.jpg";
import sakuraImage from "~/assets/sakura.jpg";
import shutaraImage from "~/assets/shutara.jpg";
import raniaImage from "~/assets/Rania.jpg";
import notificationsImage from "~/assets/notifications.png";
import seussImage from "~/assets/seussAPI.png";
import tshirtsImage from "~/assets/t-shirts.png";

const tabs = [
  {
    id: "3d",
    label: "3D Work",
    blurb: "Sculpts, props, and renders.",
    items: [
      {
        title: "Hard surface",
        subtitle: "ZBrush + Blender",
        desc: "Lace from silksong learning hard surface modeling techniques.",
        image: laceImage,
      },
      {
        title: "Organic sculpt",
        subtitle: "Zbrush",
        desc: "Sakura from Street Fighter 6 full body sculpt.",
        image: sakuraImage,
      },
      {
        title: "Hero Prop Render",
        subtitle: "Cycles",
        desc: "Photoreal render with layered materials and decals.",
        image: shutaraImage,
      },
    ],
  },
  {
    id: "photo",
    label: "Photo & Video",
    blurb: "Campaigns, edits, and motion.",
    items: [
      {
        title: "Portrait Series",
        subtitle: "Lightroom + Photoshop",
        desc: "Cinematic grading and skin retouch workflow.",
        image: raniaImage,
      },
    ],
  },
  {
    id: "web",
    label: "Web Design",
    blurb: "Interfaces and interactive prototypes.",
    items: [
      {
        title: "Portfolio Refresh",
        subtitle: "Nuxt + Tailwind",
        desc: "Case study-led layout with bold typography.",
        image: notificationsImage,
      },
      {
        title: "SaaS Dashboard",
        subtitle: "Vue + D3",
        desc: "Data-rich UI with clean cards and charts.",
        image: seussImage,
      },
      {
        title: "Landing Page",
        subtitle: "Figma",
        desc: "Hero-first story with staggered feature blocks.",
        image: tshirtsImage,
      },
    ],
  },
];

const activeTab = ref(tabs[0].id);

const currentItems = computed(() => {
  const tab = tabs.find((t) => t.id === activeTab.value);
  return tab ? tab.items : [];
});

const currentBlurb = computed(() => {
  const tab = tabs.find((t) => t.id === activeTab.value);
  return tab?.blurb ?? "";
});
</script>

<template>
  <section class="container-fluid py-4">
    <div class="mb-3">
      <p class="text-uppercase text-muted small mb-1">Selected work</p>
      <h1 class="h3 mb-1">Projects</h1>
      <p class="text-secondary mb-0">
        Pick a category on the left, view cards on the right, click to open
        details.
      </p>
    </div>

    <div class="row">
      <aside class="col-md-3 mb-3">
        <div class="list-group tabs-stack">
          <button
            v-for="tab in tabs"
            :key="tab.id"
            type="button"
            class="list-group-item list-group-item-action"
            :class="{ active: tab.id === activeTab }"
            @click="activeTab = tab.id"
          >
            <div class="fw-semibold">{{ tab.label }}</div>
            <small class="text-muted">{{ tab.blurb }}</small>
          </button>
        </div>
      </aside>

      <div class="col-md-9">
        <div class="work-wrap">
          <p class="text-secondary mb-3">{{ currentBlurb }}</p>
          <div class="row g-3">
            <div
              v-for="item in currentItems"
              :key="item.title"
              class="col-md-4 col-sm-6"
            >
              <article class="card h-100 shadow-sm">
                <div class="img-holder">
                  <img v-if="item.image" :src="item.image" :alt="item.title" />
                  <div v-else class="img-placeholder">Image</div>
                </div>
                <div class="card-body">
                  <p class="card-subtitle mb-1 text-muted">
                    {{ item.subtitle }}
                  </p>
                  <h5 class="card-title mb-2">{{ item.title }}</h5>
                  <p class="card-text">{{ item.desc }}</p>
                </div>
              </article>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.img-holder {
  width: 100%;
  aspect-ratio: 4 / 3;
  border-radius: 10px;
  overflow: hidden;
  background: #f0f0f0;
  border: 1px solid #146c43;
  display: grid;
  place-items: center;
}

.img-holder img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: center;
  display: block;
}

.img-placeholder {
  color: #e6f4ea;
  font-weight: 600;
}

.work-wrap {
  background: #ffffff;
  border: 1px solid #e5e7eb;
  border-radius: 16px;
  padding: 1rem 1.25rem;
  box-shadow: 0 12px 28px rgba(0, 0, 0, 0.06);
}
.tabs-stack {
  display: grid;
  gap: 2rem;
}
.card {
  background: #198754;
  border: 1px solid #146c43;
  color: #ffffff;
}
.card-subtitle {
  color: #e6f4ea !important;
}
.card-text {
  color: #e6f4ea;
}
.tabs-stack .list-group-item.active {
  background-color: #198754;
  border-color: #198754;
  color: #ffffff;
}
.tabs-stack .list-group-item.active small,
.tabs-stack .list-group-item.active p {
  color: #e6f4ea;
}
</style>
