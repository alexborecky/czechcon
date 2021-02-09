<template>
  <div class="hero" id="home">
    <div class="container flex column">
      <div class="hero value-proposition flex center">
        <img src="@/assets/images/graphic-one.svg" alt="">
        <div class="value">
          <h1>{{home.value}}</h1>
          <p class="sub-value">{{home.subValue}}</p>
        </div>
      </div>
      <div class="hero flex center-column-left" id="projects">
        <h2>Na čem děláme?</h2>
        <div class="project-list flex full-width">
            <ProjectPreview 
              title="https://ik.imagekit.io/alexborecky/CzechCon/vygruntujeme-light_1__QbmZRYCyWnqC.svg"
              :description="home.vygruntujeme"
              :link="home.vygLink"
            />
            <ProjectPreview 
              title="https://ik.imagekit.io/alexborecky/CzechCon/e-shop_XrI7YXeFM.svg"
              :description="home.eshop"
              :link="home.sLink"
            />
            <ProjectPreview class="ready"
              title="https://ik.imagekit.io/alexborecky/CzechCon/ready_0t-gZmFgT.svg"
              :description="home.doprava"
              :link="home.dLink"
            />
        </div>
      </div>
      <div class="hero flex column" id="about">
        <img class="desktop" src="@/assets/images/timeline.svg" alt="">
        <img class="phone" src="@/assets/images/timeline-phone.svg" alt="">
        <div class="about-content">
          <h2>O nás</h2>
          <p>{{home.about}}</p>
        </div>
      </div>
      <!-- <div class="hero">
        <h2>Historie</h2>
      </div> -->
      <div class="hero flex column center" id="contact">
        <div class="contact-content">
          <h2>Kontaktujte nás</h2>
          <div class="contacts flex column center">
            <a href="mailto:info@czechcon.cz">{{home.email}}</a>
            <!-- <a href="tel:+420123456789">+420123456789</a> -->
          </div>
          <div class="legal flex column middle">
            <ul class="flex column center">
              <li><p>{{home.comp}}</p></li>
              <li><p>{{home.address}}</p></li>
              <li><p>{{home.country}}</p></li>
              <li><p>{{home.ic}}</p></li>
              <li><p>{{home.dic}}</p></li>
              <li><p>Datová schránka: {{home.dataMail}}</p></li>
            </ul>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  async asyncData({$content}) {
        const home = await $content('home').fetch();
        return {home}
  },
  data () {
    return {

    }
  }
}
</script>

<style lang="scss" scoped>

.value-proposition {
  margin-top: -10vh;
  height: 100vh;
  img {
    position: absolute;
    top: 0;
    right: 0;
    max-width: 100%;
    z-index: 0;
    @media only screen and (max-width: 1500px) {
        width: 180%;
    }
  }
  .value {
    z-index: 1;
    // margin-top: -5vh;
  }
  .sub-value {
    font-size: 24px;
    opacity: .56;
    line-height: 32px;
  }
  @media only screen and (max-width: 1060px) {
      margin-top: 0;
  }
}

#projects {
  width: 100%;
  min-height: 50vh;
  @media only screen and (max-width: 960px) {
      align-items: center;
      height: auto;
  }
  @media only screen and (max-width: 450px) {
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
      margin-left: 40px;
    }
    @media only screen and (max-width: 450px) {
      align-items: center;
      margin-left: 0px;
    }
  }
}

#about {
  min-height: 140vh;
  max-height: 160vh;
  position: relative;
  @media only screen and (max-width: 960px) {
    align-items: center;
  }
  img {
    position: absolute;
    top: 100px;
    left: 0;
    z-index: 0;
    height: 100%;
    max-width: 100%;
    @media only screen and (max-width: 960px) {
      position: relative;
      order: 2;
      top: 0;
      margin-top: 40px;
    }
    @media only screen and (max-width: 650px) {
      max-height: 100%;
      width: 72%;
    }
  }
  .about-content {
    z-index: 1;
    align-self: flex-end;
    margin: 100px 40px 0 0;
    max-width: 560px;
    @media only screen and (max-width: 1440px) {
      margin: 100px 0 0 0;
      max-width: 480px;
    }
    @media only screen and (max-width: 960px) {
      align-self: flex-start;
    }
    @media only screen and (max-width: 450px) {
      align-self: center;
      text-align: center;
    }
  }
}

#contact {
  // height: 40vh !important;
  .contacts {
    a {
      font-size: 24px;
      margin: 8px 0;
    }
  }
  .legal {
    margin-top: 40px;
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
