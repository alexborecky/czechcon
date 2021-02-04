<template>
  <div class="hero" id="home">
    <div class="container">
      <div class="hero value-proposition flex center">
        <img src="@/assets/images/graphic-one.svg" alt="">
        <div class="value">
          <h1>Hello there</h1>
          <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Metus semper ultrices ut volutpat, erat tortor. Donec cursus pellentesque ornare aliquam faucibus amet.</p>
        </div>
      </div>
      <div class="hero flex center-column-left" id="projects">
        <h2>Na čem děláme?</h2>
        <div class="project-list flex full-width">
            <ProjectPreview />
            <ProjectPreview />
            <ProjectPreview />
        </div>
      </div>
      <div class="hero flex center-column-right" id="about">
        <img src="@/assets/images/graphic-two.svg" alt="">
        <div class="about-content">
          <h2>Hello There</h2>
          <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Metus semper ultrices ut volutpat, erat tortor. Donec cursus pellentesque ornare aliquam faucibus amet.</p>
        </div>
      </div>
      <div class="hero" id="contact"></div>
    </div>
  </div>
</template>

<script>
import Logo from '~/components/Logo.vue'

export default {
  components: {
    Logo
  }
}
</script>

<style lang="scss" scoped>

.value-proposition {
  height: 80vh;
  img {
    position: absolute;
    top: 0;
    right: 0;
  }
}

#projects {
  width: 100%;
  .project-list {
    justify-content: space-between;
    flex-wrap: wrap;
    margin-top: 40px;
  }
}

#about {
  height: 100vh;
  img {
    height: 100%;
    position: absolute;
    left: 0;
  }
}

</style>
