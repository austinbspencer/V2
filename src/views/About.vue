<template>
  <div class="about">
    <b-container>
      <b-row align-v="center">
        <b-col md="5">
          <b-card
            text-variant="white"
            no-body
            img-top
            img-src="https://scontent.fphx1-1.fna.fbcdn.net/v/t1.0-9/83322175_2958884524156199_6029303686017056768_n.jpg?_nc_cat=111&_nc_sid=8bfeb9&_nc_ohc=fnfapXEthZMAX_avawZ&_nc_oc=AQlPmAdGcaj7aAR2YRr3Omt2C-MlqWsYSVQM6zG-rM1fDbjo_hKqeAjsHMFJ4CGU-_x3ASTBzSSLN9VL6PNGpfGZ&_nc_ht=scontent.fphx1-1.fna&oh=6281bba06014fd36955b4b3d1e86536b&oe=5F8CE9F3"
            img-alt="Card Image"
            style="min-width: 20rem;"
            footer-tag="footer"
          >
            <!-- <b-card-text>Check out my resume!</b-card-text> -->
            <template v-slot:footer>
              <div id="pdf" class="float-center">
                <b-button
                  id="danger"
                  size="md"
                  v-b-modal="'resume'"
                  @click="show = true"
                  variant="outline-danger"
                  >Resume</b-button
                >
                <!-- <b-button size="md" variant="danger">
                  <a id="pdf" href="public/Austin_Resume.pdf" download
                    ><i class="fas fa-download"></i>
                  </a>
                </b-button> -->
                <b-modal
                  id="resume"
                  centered
                  title="Resume"
                  size="xl"
                  header-bg-variant="dark"
                  header-text-variant="light"
                  body-bg-variant="light"
                  footer-bg-variant="dark"
                  backdrop
                >
                  <b-row>
                    <b-col cols="12">
                      <iframe
                        height="800"
                        width="100%"
                        src="https://austinspencer.works/resume/Austin_Resume.pdf"
                      ></iframe>
                    </b-col>
                  </b-row>
                  <template v-slot:modal-footer="{ close }">
                    <!-- Button with custom close trigger value -->
                    <div class="w-100">
                      <b-button
                        size="sm"
                        class="float-left"
                        variant="light"
                        href="https://austinspencer.works/resume/Austin_Resume.pdf"
                        target="_blank"
                      >
                        Full Page
                      </b-button>
                      <!-- Emulate built in modal footer ok and cancel button actions -->
                      <b-button
                        size="sm"
                        variant="danger"
                        class="float-right"
                        @click="close()"
                      >
                        Close
                      </b-button>
                    </div>
                  </template>
                </b-modal>
              </div>
            </template>
          </b-card>
          <br />
          <br />
        </b-col>
        <br />
        <br />
        <b-col md="5">
          <b-card
            text-variant="dark"
            title="A little about me.."
            footer-tag="footer"
          >
            <b-card-text
              >Hi, I'm Austin Spencer. Thank you for visiting my website! I am
              an undergraduate student at Arizona State University. My major is
              computer science and I plan to graduate in May of 2022. I enjoy
              staying active and being outdoors! Let's get in touch, click the
              'Contact' button to be redirected to a page where you can email me
              directly!
            </b-card-text>
            <!-- Footer template -->
            <template v-slot:footer>
              <!-- Button with custom close trigger value -->
              <div class="w-100">
                <b-button
                  id="dark"
                  size="md"
                  variant="outline-dark"
                  class="float-left"
                  href="https://github.com/abspen1"
                >
                  GitHub
                </b-button>
                <b-button
                  id="success"
                  size="md"
                  variant="outline-success"
                  class="float-right"
                  href="https://austinspencer.works/about/contact/"
                >
                  Contact
                </b-button>
              </div>
            </template>
            <br />
            <br />
          </b-card>
        </b-col>
      </b-row>
      <b-row align-v="center">
        <b-col cols="2"></b-col>
        <b-col cols="3" md="3">
          <b-card
            img-top
            img-src="https://pbs.twimg.com/profile_images/1283165293473419267/5TKLbwkL_400x400.jpg"
            img-alt="Card Image"
            text-variant="dark"
            title="My Current Project"
            style="min-width: 20rem;"
            footer-tag="footer"
          >
            <template v-slot:footer>
              <div class="w-100">
                <b-button
                  id="dark"
                  size="md"
                  variant="outline-dark"
                  class="float-left"
                  href="https://github.com/abspen1/Fantasy-Twitter"
                >
                  GitHub
                </b-button>
                <b-button
                  id="info"
                  size="md"
                  variant="outline-info"
                  class="float-right"
                  href="https://austinspencer.works/Fantasy-Twitter/"
                >
                  Webpage
                </b-button>
              </div>
            </template>
          </b-card>
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
export default {};
</script>
<style lang="scss" scoped></style>
