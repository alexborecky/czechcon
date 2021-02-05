<template>
  <div class="hero" id="home">
    <div class="container flex column">
      <div class="hero value-proposition flex center">
        <img src="@/assets/images/graphic-one.svg" alt="">
        <div class="value">
          <h1>{{home.value}}</h1>
          <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Metus semper ultrices ut volutpat, erat tortor. Donec cursus pellentesque ornare aliquam faucibus amet.</p>
        </div>
      </div>
      <div class="hero flex center-column-left" id="projects">
        <h2>Na čem děláme?</h2>
        <div class="project-list flex full-width">
            <ProjectPreview 
              title="https://ik.imagekit.io/alexborecky/CzechCon/vygruntujeme_ghqeaO3ehUpR.png"
              :description="home.vygruntujeme"
              :link="home.vygLink"
            />
            <ProjectPreview 
              title="https://ik.imagekit.io/alexborecky/CzechCon/vygruntujeme-eshop_6mI2vadGU6qO.png"
              :description="home.eshop"
              :link="home.sLink"
            />
            <ProjectPreview 
              title="https://ik.imagekit.io/alexborecky/CzechCon/vygruntujeme_ghqeaO3ehUpR.png"
              :description="home.vygruntujeme"
              :link="home.vygLink"
            />
        </div>
      </div>
      <div class="hero flex center-column-right" id="about">
        <img src="@/assets/images/graphic-two.svg" alt="">
        <div class="about-content">
          <h2>O nás</h2>
          <p>{{home.about}}</p>
        </div>
      </div>
      <!-- <div class="hero">
        <h2>Historie</h2>
      </div> -->
      <div class="hero flex column center" id="contact">
        <h2>Kontaktujte nás</h2>
        <div class="contacts flex column center">
          <a href="mailto:info@czechcon.cz">info@czechcon.cz</a>
          <a href="tel:+420123456789">+420123456789</a>
        </div>
        <div class="legal">
          <ul class="flex column center">
            <li><p>CzechCon s.r.o.</p></li>
            <li><p>Kaprova 42/14, 110 00 Praha 1</p></li>
            <li><p>Česká republika</p></li>
            <li><p>IČ: 25260651</p></li>
            <li><p>DIČ: CZ25260651</p></li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Logo from '~/components/Logo.vue'

export default {
  async asyncData({$content}) {
        const home = await $content('home').fetch();
        return {home}
  },
}
</script>

<style lang="scss" scoped>

.value-proposition {
  margin-top: -120px;
  height: 100vh;
  img {
    position: absolute;
    top: 0;
    right: 0;
    max-width: 100%;
    z-index: 0;
  }
  .value {
    z-index: 1;
  }
  @media only screen and (max-width: 1060px) {
      margin-top: 0;
  }
}

#projects {
  width: 100%;
  min-height: 40vh;
  @media only screen and (max-width: 960px) {
      align-items: center;
      height: auto;
  }
  .project-list {
    justify-content: space-between;
    flex-wrap: wrap;
    margin-top: 40px;
    @media only screen and (max-width: 960px) {
      flex-flow: column;
      align-items: center;
    }
  }
}

#about {
  height: 100vh;
  img {
    height: 90%;
    position: absolute;
    left: 0;
    z-index: 0;
    @media only screen and (max-width: 650px) {
      width: 80%;
    }
  }
  .about-content {
    z-index: 1;
  }
}

#contact {
  height: 60vh;
  .contacts {
    a {
      font-size: 24px;
      margin: 8px 0;
    }
  }
  .legal {
    margin: 40px 0;
    ul {
      padding-left: 0;
      list-style: none;
      p {
        font-size: 12px;
        line-height: 16px;
      }
    }
  }
}

</style>
