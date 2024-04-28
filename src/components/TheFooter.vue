<template>
  <footer class="footer-container">
    <div class="content-container">
      <img alt="Blogr logo" class="logo" src="../assets/images/logo.svg" width="101" height="40" />

      <div class="content">
        <div class="content-section">
          <h4>Product</h4>
          <ul>
            <li><a href="#" class="link">Overview</a></li>
            <li><a href="#" class="link">Pricing</a></li>
            <li><a href="#" class="link">Marketplace</a></li>
            <li><a href="#" class="link">Features</a></li>
            <li><a href="#" class="link">Integrations</a></li>
          </ul>
        </div>

        <div class="content-section">
          <h4>Company</h4>
          <ul>
            <li><a href="#" class="link">About</a></li>
            <li><a href="#" class="link">Team</a></li>
            <li><a href="#" class="link">Blog</a></li>
            <li><a href="#" class="link">Careers</a></li>
          </ul>
        </div>

        <div class="content-section">
          <h4>Connect</h4>
          <ul>
            <li><a href="#" class="link">Contact</a></li>
            <li><a href="#" class="link">Newsletter</a></li>
            <li><a href="#" class="link">LinkedIn</a></li>
          </ul>
        </div>
      </div>
    </div>
  </footer>
</template>

<style scoped>
.footer-container {
  padding: 75px 24px;
  background-color: #24242c;
  border-top-right-radius: 100px;

  font-family: 'Ubuntu';
  font-size: 18px;
  color: white;
}

.footer-container .content-container {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.footer-container .content-container .logo {
  margin-bottom: 72px;
}

.footer-container .content-container .content {
  display: flex;
  flex-direction: column;
  gap: 40px;
}

.footer-container .content-container .content .content-section {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 21px;
}

.footer-container .content-container .content .content-section h4 {
  font-weight: 500;
}

ul {
  padding: 0;
  list-style-type: none;
}

li {
  text-align: center;
}

li + li {
  margin-top: 12px;
}

a.link {
  text-decoration: none;
  color: white;
  opacity: 0.75;
}

a.link:hover {
  text-decoration: underline;
}

@media (min-width: 768px) {
  .footer-container .content-container {
    margin-left: auto;
    margin-right: auto;
    max-width: 1110px;
    flex-direction: row;
    align-items: start;
    justify-content: space-between;
    gap: calc(184 / 1440 * 100%);
  }

  .footer-container .content-container .content {
    flex: 1 1 auto;
    flex-direction: row;
    align-items: start;
    gap: 30px;
  }

  .footer-container .content-container .content .content-section {
    width: calc(255 / 1440 * 100%);
    flex: 1 1 auto;
    align-items: start;
  }

  .footer-container .content-container .content .content-section li {
    text-align: left;
  }
}
</style>
