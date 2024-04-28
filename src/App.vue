<script setup lang="ts">
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
import TheFooter from './components/TheFooter.vue'
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

    <div>
      <h2>A modern publishing platform</h2>
      <p>Grow your audience and build your online brand</p>
      <div>
        <button>Start for Free</button>
        <button>Learn More</button>
      </div>
    </div>

    <section>
      <h2>Designed for the future</h2>

      <div>
        <img
          alt="Editor"
          src="./assets/images/illustration-editor-mobile.svg"
          width="326"
          height="326"
        />
      </div>

      <div>
        <h3>Introducing an extensible editor</h3>
        <p>
          Blogr features an exceedingly intuitive interface which lets you focus on one thing:
          creating content. The editor supports management of multiple blogs and allows easy
          manipulation of embeds such as images, videos, and Markdown. Extensibility with plugins
          and themes provide easy ways to add functionality or change the looks of a blog.
        </p>
      </div>

      <div>
        <h3>Robust content management</h3>
        <p>
          Flexible content management enables users to easily move through posts. Increase the
          usability of your blog by adding customized categories, sections, format, or flow. With
          this functionality, you're in full control.
        </p>
      </div>
    </section>

    <section>
      <img alt="Editor" src="./assets/images/illustration-phones.svg" width="328" height="347" />
      <h2>State of the Art Infrastructure</h2>
      <p>
        With reliability and speed in mind, worldwide data centers provide the backbone for
        ultra-fast connectivity. This ensures your site will load instantly, no matter where your
        readers are, keeping your site competitive.
      </p>
    </section>

    <section>
      <img alt="Editor" src="./assets/images/illustration-phones.svg" width="328" height="347" />
      <div>
        <h2>Free, open, simple</h2>
        <p>
          Blogr is a free and open source application backed by a large community of helpful
          developers. It supports features such as code syntax highlighting, RSS feeds, social media
          integration, third-party commenting tools, and works seamlessly with Google Analytics. The
          architecture is clean and is relatively easy to learn.
        </p>
      </div>
      <div>
        <h2>Powerful tooling</h2>
        <p>
          Batteries included. We built a simple and straightforward CLI tool that makes
          customization and deployment a breeze, but capable of producing even the most complicated
          sites.
        </p>
      </div>
    </section>
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
</style>
