<template>
  <div class="col px-0">
    <div class="row justify-content-center align-items-center">
      <!-- <img
              src="img/brand/white.png"
              style="width: 200px;"
                class="img-fluid">-->
      <b-container :class="[blur ?'blur' :'blur active']">
        <b-col>
          <div class="main-block shadow justify-content-between">
            <div class="quaver" />
            <div
              class="content flex-grow-1 d-flex justify-content-center align-items-center"
            >
              <h1
                class="text-white"
                v-html="$t('landing.title')"
              />
              <p
                class="lead text-white mt-4 mb-5"
                v-html="$t('landing.subtitle')"
              />
              <div class="buttons">
                <base-button
                  tag="a"
                  href="#"
                  class="mb-3 mb-sm-0"
                  type="info"
                  icon="ni ni-world"
                  @click.prevent="$router.push({name:'top'})"
                >
                  <!-- <template v-slot:icon><font-awesome-icon icon="fa-chess-queen" /></template> -->
                  {{ $t("landing.topCollectionsButton") }}
                </base-button>

                <base-button
                  tag="a"
                  href="#"
                  class="mb-3 mb-sm-0"
                  type="white"
                  icon="ni ni-cloud-download-95"
                  @click.prevent="$router.push({name:'recent'})"
                >
                  {{ $t("landing.recentCollectionsButton") }}
                </base-button>
                <!-- <a href="/u/40455" class="home-btn btn-key">view profile</a>
                  <a
                    href="/leaderboard"
                    class="home-btn btn-how"
                    style="margin-left: 6px;"
                  >view leaderboards</a> -->
              </div>
            </div>
          </div>
        </b-col>
      </b-container>
    </div>
    <!-- <div class="col-lg-7 text-center pt-lg">
        123123
      </div> -->
    <b-collapse v-model="show">
      <div class="row align-items-center pt-lg justify-content-around">
        <!-- <div class="btn-wrapper" /> -->
      </div>
      <div class="row align-items-center pt-lg justify-content-around">
        <div class="col mt-4">
          <span class="text-white alpha-7 ml-3">{{ $t('landing.title') }}</span>
          <!-- <a
                            href="https://github.com/creativetimofficial/argon-design-system"
                            target="_blank"
                            title="Support us on Github"
                        >
                            <img
                                src="img/brand/github-white-slim.png"
                                style="height: 22px; margin-top: -3px"
                            />
                        </a>-->
        </div>
        <div class="col mt-4 mt-sm-0 text-right">
          <span class="text-white alpha-7">{{ $t("statements.testTitle") }}</span>
          <!-- <a
              href="https://www.creative-tim.com"
              target="_blank"
              title="Creative Tim - Premium Bootstrap Themes and Templates"
            >
              <img
                src="img/brand/creativetim-white-slim.png"
                class="ml-3"
                style="height: 30px;"
              >
            </a> -->
        </div>
      </div>
    </b-collapse>
  </div>
</template>
<script>

export default {
  layout: 'hero',

  data: () => ({
    blur: true,
    loading: true
  }),
  computed: {
    show: {
      get () {
        return !this.loading
      },
      set () {}
    }
  },
  mounted () {
    setTimeout(() => (this.blur = false), 0)
    setTimeout(() => (this.loading = false), 500)
  }
}
</script>
<style scoped>
.blur {
    filter: blur(8px);
    transition: all 0.3s ease;
}
.active {
    filter: none;
}
.main-block {
    border-radius: 4px;
    display: flex;
    justify-content: center;
    margin-top: 110px;
    height: 260px;
    /* padding-right: 34px; */
    background: linear-gradient(87deg, #8c98dd53 0, #af9edd66 100%) !important;
    backdrop-filter: blur(15px);
}
.quaver {
    background-image: url(https://Akatsuki.pw/static/characters/quaver.png);
    background-repeat: no-repeat;
    height: 363px;
    width: 427px;
    align-self: flex-end;
}
.content {
    display: flex;
    flex-direction: column;
    color: #fff;
    height: 100%;
    justify-content: center;
}
@media (max-width: 990px) {
    .quaver {
        display: none;
    }
}
</style>
