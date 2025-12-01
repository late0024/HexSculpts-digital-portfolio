<script setup></script>

<template>
  <div class="page">
    <header class="header-bar">
      <div>
        <h1>Hexsculpts - Mohammed Lateef</h1>
      </div>
      <div class="logo-wrap">
        <NuxtLink to="/" aria-label="Home">
          <img src="/Artboard1.png" aria-hidden="true" />
        </NuxtLink>
      </div>
      <nav class="navigation">
        <NuxtLink to="/">Home</NuxtLink>
        <NuxtLink to="/about">About</NuxtLink>
        <NuxtLink to="/projects">Projects</NuxtLink>
        <NuxtLink to="/services">Services</NuxtLink>
        <NuxtLink to="/contacts">Contact</NuxtLink>
      </nav>
    </header>
    <main class="main-content">
      <div class="main-inner">
        <NuxtPage />
      </div>
    </main>
    <footer class="socials-credentials">
      <div>
        <span>Hexsculpts</span>
      </div>
      <div class="social-links">
        <a
          href="https://github.com/late0024"
          target="_blank"
          aria-label="Github"
        >
          <svg
            xmlns="http://www.w3.org/2000/svg"
            x="0px"
            y="0px"
            width="25"
            height="25"
            viewBox="0 0 30 30"
          >
            <path
              d="M15,3C8.373,3,3,8.373,3,15c0,5.623,3.872,10.328,9.092,11.63C12.036,26.468,12,26.28,12,26.047v-2.051 c-0.487,0-1.303,0-1.508,0c-0.821,0-1.551-0.353-1.905-1.009c-0.393-0.729-0.461-1.844-1.435-2.526 c-0.289-0.227-0.069-0.486,0.264-0.451c0.615,0.174,1.125,0.596,1.605,1.222c0.478,0.627,0.703,0.769,1.596,0.769 c0.433,0,1.081-0.025,1.691-0.121c0.328-0.833,0.895-1.6,1.588-1.962c-3.996-0.411-5.903-2.399-5.903-5.098 c0-1.162,0.495-2.286,1.336-3.233C9.053,10.647,8.706,8.73,9.435,8c1.798,0,2.885,1.166,3.146,1.481C13.477,9.174,14.461,9,15.495,9 c1.036,0,2.024,0.174,2.922,0.483C18.675,9.17,19.763,8,21.565,8c0.732,0.731,0.381,2.656,0.102,3.594 c0.836,0.945,1.328,2.066,1.328,3.226c0,2.697-1.904,4.684-5.894,5.097C18.199,20.49,19,22.1,19,23.313v2.734 c0,0.104-0.023,0.179-0.035,0.268C23.641,24.676,27,20.236,27,15C27,8.373,21.627,3,15,3z"
            ></path>
          </svg>
        </a>

        <a
          href="https://www.linkedin.com/in/mohammed-lateef-a576b5164"
          target="_blank"
          aria-label="LinkedIn"
        >
          <svg
            xmlns="http://www.w3.org/2000/svg"
            x="0px"
            y="0px"
            width="25"
            height="25"
            viewBox="0 0 30 30"
          >
            <path
              d="M24,4H6C4.895,4,4,4.895,4,6v18c0,1.105,0.895,2,2,2h18c1.105,0,2-0.895,2-2V6C26,4.895,25.105,4,24,4z M10.954,22h-2.95 v-9.492h2.95V22z M9.449,11.151c-0.951,0-1.72-0.771-1.72-1.72c0-0.949,0.77-1.719,1.72-1.719c0.948,0,1.719,0.771,1.719,1.719 C11.168,10.38,10.397,11.151,9.449,11.151z M22.004,22h-2.948v-4.616c0-1.101-0.02-2.517-1.533-2.517 c-1.535,0-1.771,1.199-1.771,2.437V22h-2.948v-9.492h2.83v1.297h0.04c0.394-0.746,1.356-1.533,2.791-1.533 c2.987,0,3.539,1.966,3.539,4.522V22z"
            ></path>
          </svg>
        </a>

        <a
          href="https://www.artstation.com/mohammedkhalil"
          target="_blank"
          aria-label="Artstation"
        >
          <svg
            xmlns="http://www.w3.org/2000/svg"
            x="0px"
            y="0px"
            width="25"
            height="25"
            viewBox="0 0 50 50"
          >
            <path
              d="M47.819 32.652L33.02 6.535C32.133 4.972 30.466 4 28.669 4H20c-.357 0-.687.19-.865.499-.179.31-.18.69-.002.999l23 40C42.312 45.81 42.643 46 43 46c.01 0 .02 0 .029 0 .368-.011.7-.224.865-.553l4.047-8.094C48.688 35.861 48.642 34.104 47.819 32.652zM27.84 28.457l-11-17C16.655 11.172 16.339 11 16 11c-.007 0-.014 0-.021 0-.347.008-.665.194-.841.493l-10 17c-.182.309-.184.692-.006 1.003C5.31 29.808 5.642 30 6 30h21c.366 0 .703-.2.879-.522C28.054 29.156 28.039 28.765 27.84 28.457zM36.874 44.515l-5-9C31.698 35.197 31.363 35 31 35H3c-.354 0-.683.188-.862.493-.18.305-.184.683-.012.992l5 9C7.302 45.803 7.637 46 8 46h28c.354 0 .683-.188.862-.493C37.042 45.202 37.046 44.824 36.874 44.515z"
            ></path>
          </svg>
        </a>
      </div>
    </footer>
  </div>
</template>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Barlow:wght@400;600;700&family=Montserrat:wght@600;700&display=swap");

:global(body) {
  margin: 0;
  font-family: "Barlow", "Montserrat", Arial, sans-serif;
  font-size: 18px;
  line-height: 1.6;
  background-color: #ebe5d9;
}
:global(h1),
:global(h2),
:global(h3) {
  font-family: "Montserrat", "Barlow", Arial, sans-serif;
  line-height: 1.2;
}
:global(h1) {
  font-size: 2.4rem;
}
:global(h2) {
  font-size: 1.9rem;
}
:global(h3) {
  font-size: 1.5rem;
}
:global(p),
:global(li) {
  font-family: "Barlow", "Montserrat", Arial, sans-serif;
  font-size: 1.15rem;
}
.page {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}
.header-bar {
  display: grid;
  grid-template-columns: 1fr auto 1fr;
  align-items: center;
  padding: 10px 20px;
  background-color: #d76b3e;
  color: #ffffff;
}
.header-bar > div:first-child {
  justify-self: start;
}
.logo-wrap {
  justify-self: center;
}
.logo-wrap :global(a) {
  display: inline-block;
}
.logo-wrap img {
  width: 70px;
  height: auto;
}
.navigation {
  justify-self: end;
}
.navigation a {
  margin: 0 10px;
  text-decoration: none;
  color: #ffffff;
}
main {
  flex: 1 0 auto;
}
.main-inner {
  width: 80%;
  margin: 0 auto;
}
.socials-credentials {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 10px 20px;
  background-color: #231f20;
  color: #ffffff;
}
.social-links {
  display: flex;
  gap: 15px;
}
.social-links svg path {
  fill: #ffffff;
}
</style>
