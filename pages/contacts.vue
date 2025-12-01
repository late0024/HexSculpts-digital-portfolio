<script setup lang="ts">
const resumeUrl = new URL(
  "~/assets/Mohammed-Lateef-Resume.pdf",
  import.meta.url
).href;
</script>

<template>
  <section class="container py-5">
    <div class="row g-4">
      <div class="col-lg-5">
        <div class="p-4 contact-card rounded-4 shadow-sm h-100">
          <p class="text-uppercase medium mb-1">Get in touch</p>
          <h1 class="h3 mb-2">Contact</h1>
          <p class="lead mb-0">
            Let’s talk about projects, collaborations, or commissions.
          </p>
          <br></br>
          <p class="mb-2">
            <strong>Email: </strong>
            <a class="fw-semibold" href="mailto:khalilmo13@gmail.com">khalilmo13@gmail.com</a>
          </p>
          <p class="mb-2">
            <strong>Phone:</strong> +1 (613) 355-2171
          </p>
          <div class="mt-3">
            <a
              class="btn contact-btn px-4"
              :href="resumeUrl"
              target="_blank"
              rel="noopener noreferrer"
            >
              View Resume
            </a>
          </div>
        </div>
      </div>

      <div class="col-lg-7">
        <div class="p-4 contact-card rounded-4 shadow-sm">
          <h2 class="h4 mb-3">Send a Message</h2>
          <form class="row g-3">
            <div class="col-12">
              <label class="form-label">Name</label>
              <input
                type="text"
                name="name"
                class="form-control"
                placeholder="Your name"
              />
            </div>
            <div class="col-12">
              <label class="form-label">Email</label>
              <input
                type="email"
                name="email"
                class="form-control"
                placeholder="you@example.com"
              />
            </div>
            <div class="col-12">
              <label class="form-label">Message</label>
              <textarea
                name="message"
                rows="4"
                class="form-control"
                placeholder="Tell me about your project"
              ></textarea>
            </div>
            <div class="col-12">
              <button type="button" class="btn contact-btn px-4">Send</button>
            </div>
          </form>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.contact-card {
  background: #198754;
  border: 1px solid #146c43;
  color: #ffffff;
}
.contact-card a {
  color: #e6f4ea;
}
.contact-btn {
  background: #292a2a;
  border-color: #292a2a;
  color: #ffffff;
}
.contact-btn:hover,
.contact-btn:focus {
  background: #1f2020;
  border-color: #1f2020;
  color: #ffffff;
}
</style>
