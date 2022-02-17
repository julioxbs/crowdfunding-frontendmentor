<template>
  <header>
      <div class="d-flex justify-content-between p-3 container">
          <a href="#"><img src="/images/logo.svg" alt="logo"></a>

          <nav class="d-none d-md-block">
              <ul class="d-flex gap-3">
                  <li><a class="text-white fw-bold" href="#">About</a></li>
                  <li><a class="text-white fw-bold" href="#">Discover</a></li>
                  <li><a class="text-white fw-bold" href="#">Get Started</a></li>
              </ul>
          </nav>

          <a class="d-block d-md-none" href="#"><img src="/images/icon-hamburger.svg" alt="menu"></a>
      </div>
  </header>
</template>

<style scoped>
    header {
        background-image: url("/images/image-hero-mobile.jpg");
        background-size: cover;
        background-position: center;
        background-repeat: no-repeat;
        position: relative;
        height: 375px;
    }

    @media only screen and (min-width: 800px) {
        header {
            background-image: url("/images/image-hero-desktop.jpg");
        }
    }
</style>