<script setup lang="ts">
import profileImg from "~/assets/MohammedLateef.jpg";
</script>

<template>
  <section class="about-layout container py-5">
    <div class="about-grid">
      <div class="left">
        <div class="text-block">
          <h2>Who am I</h2>
          <p>
            Hey, I'm Mohammed Lateef — the artist behind HexSculpts. I love
            discovering and working with different media. I work with 3D
            modelling, web design, and photo/video. My passion lies in bringing
            ideas to life, whether it's a detailed digital sculpt, a 3D-print
            sitting on my desk, or websites and videos of what inspires me.
          </p>
          <p>
            I'm all about creating things that feel real and lived-in. Sometimes
            that means sculpting expressive characters, and other times it
            means engineering big physical builds—like slicing, doweling, and
            assembling complex props for printing. I enjoy every part of the
            workflow, from concept to final render or real-world print.
            HexSculpts is the creative name fellow 3D peers know me by and it is
            where I get to push myself and experiment, and turn creative ideas
            into something tangible. For 3D I spend most of my time sculpting,
            texturing/shading, rendering on the digital side while I 3D Print,
            paint, and build on the physical side.
          </p>
          <p>
            While in web design I look to create frontend web applications and
            QA issues when I can; lastly I enjoy photographing and videoing
            different events.
          </p>
          <p>
            If you are looking to make your ideas real through 3D modeling, web
            design, or photo/video edits, feel free to reach out! I'm always
            excited to build something new with you.
          </p>
        </div>

        <div class="text-block">
          <h3>Skills</h3>
          <p>3D sculpting, texturing/shading, rendering, web UI, and QA.</p>
        </div>

        <div class="text-block">
          <h3>Tools</h3>
          <p>
            ZBrush, Blender, Lightroom, Premiere, Nuxt/Vue, and 3D print
            workflows.
          </p>
        </div>

        <div class="text-block">
          <h3>Interests</h3>
          <p>
            3D art, photography, videography, cooking, storytelling, and gaming.
          </p>
        </div>
      </div>

      <div class="right">
        <div class="profile-wrap">
          <img :src="profileImg" alt="Mohammed Lateef portrait" />
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.about-grid {
  display: grid;
  grid-template-columns: 1.1fr 0.9fr;
  gap: 2rem;
  align-items: start;
}

.text-block {
  margin-bottom: 1.5rem;
  background: #198754;
  border-radius: 14px;
  padding: 1rem 1.25rem;
  border: 1px solid #146c43;
  box-shadow: 0 8px 24px rgba(0, 0, 0, 0.1);
  color: #ffffff;
}

.text-block h2,
.text-block h3 {
  margin: 0 0 0.35rem;
}

.text-block p {
  margin: 0 0 0.65rem;
  color: #e6f4ea;
}

.profile-wrap {
  width: 100%;
  border-radius: 18px;
  overflow: hidden;
  box-shadow: 0 16px 40px rgba(0, 0, 0, 0.12);
  border: 1px solid rgba(0, 0, 0, 0.08);
}

.profile-wrap img {
  display: block;
  width: 100%;
  height: auto;
  object-fit: cover;
}

@media (max-width: 960px) {
  .about-grid {
    grid-template-columns: 1fr;
  }

  .profile-wrap {
    max-width: 520px;
    margin: 0 auto;
  }
}
</style>
