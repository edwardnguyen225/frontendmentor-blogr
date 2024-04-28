<script setup lang="ts">
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
import TheFooter from './components/TheFooter.vue'
import ThirdSection from './components/ThirdSection.vue'
import FirstSection from './components/FirstSection.vue'
</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />
    </div>
  </header>

  <main>
    <TheWelcome />

    <nav>
      <ul>
        <li>
          Product
          <ul>
            <li>Overview</li>
            <li>Pricing</li>
            <li>Marketplace</li>
            <li>Features</li>
            <li>Integrations</li>
          </ul>
        </li>
        <li>
          Company
          <ul>
            <li>About</li>
            <li>Team</li>
            <li>Blog</li>
            <li>Careers</li>
          </ul>
        </li>
        <li>
          Connect
          <ul>
            <li>Contact</li>
            <li>Newsletter</li>
            <li>LinkedIn</li>
          </ul>
        </li>
      </ul>
      <button>Login</button>
      <button>Login</button>
    </nav>

    <div style="margin-bottom: 100px">
      <h2>A modern publishing platform</h2>
      <p>Grow your audience and build your online brand</p>
      <div>
        <button>Start for Free</button>
        <button>Learn More</button>
      </div>
    </div>

    <FirstSection />

    <section>
      <img alt="Editor" src="./assets/images/illustration-phones.svg" width="328" height="347" />
      <h2>State of the Art Infrastructure</h2>
      <p>
        With reliability and speed in mind, worldwide data centers provide the backbone for
        ultra-fast connectivity. This ensures your site will load instantly, no matter where your
        readers are, keeping your site competitive.
      </p>
    </section>

    <ThirdSection />
  </main>

  <TheFooter />
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}

footer {
  margin-top: 100px;
}

@media (min-width: 1024px) {
  footer {
    margin-top: 123px;
  }
}
</style>
