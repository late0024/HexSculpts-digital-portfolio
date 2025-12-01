<script setup></script>

<template>
  <section class="container py-5 services">
    <header class="mb-4">
      <p class="text-uppercase text-muted small mb-1">Offerings</p>
      <h1 class="h3 mb-2">Services</h1>
      <p class="lead text-secondary mb-0">
        From end-to-end builds to tailored commissions.
      </p>
    </header>

    <div class="row g-4">
      <div class="col-lg-6">
        <div class="service-block">
          <h2 class="h5 mb-3">Services</h2>
          <ul class="mb-0 services-list">
            <li>
              3D modeling, sculpting, and texturing for props and characters.
            </li>
            <li>Web design and front-end builds for landing pages and apps.</li>
            <li>Photo/video edits and motion spots for campaigns.</li>
          </ul>
        </div>
      </div>

      <div class="col-lg-6">
        <div class="service-block">
          <h2 class="h5 mb-3">Programs</h2>
          <div class="program-grid">
            <div class="program-card">
              <h4>3D</h4>
              <ul class="mb-0">
                <li>ZBrush</li>
                <li>Blender</li>
                <li>Substance Painter</li>
                <li>Marmoset</li>
              </ul>
            </div>
            <div class="program-card">
              <h4>Web</h4>
              <ul class="mb-0">
                <li>HTML/CSS/JS</li>
                <li>Vue/Nuxt</li>
                <li>React/Next</li>
                <li>Bootstrap</li>
                <li>Figma</li>
              </ul>
            </div>
            <div class="program-card">
              <h4>Photography/Video</h4>
              <ul class="mb-0">
                <li>Adobe Photoshop</li>
                <li>Adobe Lightroom</li>
                <li>Adobe Premiere Pro</li>
              </ul>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.service-block {
  padding: 1.5rem;
  border: 1px solid #146c43;
  border-radius: 16px;
  background: #198754;
  color: #ffffff;
  height: 100%;
}
.service-block ul {
  padding-left: 1.1rem;
  display: grid;
  gap: 0.45rem;
  color: #e6f4ea;
}
.service-block p {
  color: #e6f4ea;
}

.program-grid {
  display: grid;
  grid-template-columns: repeat(2, minmax(180px, 1fr));
  gap: 1rem;
  grid-auto-rows: 1fr;
}

.program-card {
  border: 1px solid rgba(255, 255, 255, 0.18);
  border-radius: 12px;
  padding: 1rem;
  background: rgba(255, 255, 255, 0.06);
  height: 100%;
}

.program-card h4 {
  margin: 0 0 0.5rem;
  color: #ffffff;
}

.program-card ul {
  padding-left: 1.1rem;
  margin: 0;
  display: grid;
  gap: 0.35rem;
  color: #e6f4ea;
}

@media (max-width: 640px) {
  .program-grid {
    grid-template-columns: 1fr;
  }
}
</style>
