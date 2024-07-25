<template>
  <div>
    <div>
      <v-card to="detail">
        <v-img :aspect-ratio="16 / 9" dark gradient="to top, rgba(25,32,72,.7), rgba(25,32,72,.0)" height="500px"
          src="/src/images/i-miss-yoy.jpg">
          <v-card-text class="fill-height d-flex align-end">
            <v-row class="flex-column">
              <v-col>
                <v-btn color="accent" to="category">VOLTA PARA CASA</v-btn>
              </v-col>
              <v-col cols="12" lg="8" md="10" xl="7">
                <h2 class="text-h3 py-3" style="line-height: 1.2">
                  VOLTA PARA CASA
                </h2>

              </v-col>
              <v-col class="d-flex align-center">
              </v-col>
            </v-row>
          </v-card-text>
        </v-img>
      </v-card>
    </div>

    <v-row>
      <v-col cols="12" lg="12" xl="8">
        <div>
          <div class="pt-16">
            <h2 class="text-h4 font-weight-bold pb-4">Recentes</h2>

            <v-row>
              <v-col v-for="i in 6" :key="i" cols="12" lg="4" md="6">
                <v-hover v-slot:default="{ hover }" close-delay="50" open-delay="50">
                  <div>
                    <v-card :color="hover ? 'white' : 'transparent'" :elevation="hover ? 12 : 0" flat hover
                      to="/detail">
                      <v-img :aspect-ratio="16 / 9" class="elevation-2"
                        gradient="to top, rgba(25,32,72,.4), rgba(25,32,72,.0)" height="400px"
                        src="/src/images/person-1.jpg" style="border-radius: 16px">
                        <v-card-text>
                          <v-btn color="accent" to="category">TIPS</v-btn>
                        </v-card-text>
                      </v-img>

                      <v-card-text>
                        <div class="text-h5 font-weight-bold primary--text">
                          How to write an awesome blog post in 5 steps
                        </div>

                        <div class="text-body-1 py-4">
                          Ultrices sagittis orci a scelerisque. Massa placerat
                          duis ultricies lacus sed turpis
                        </div>

                        <div class="d-flex align-center">
                          <v-avatar color="accent" size="36">
                            <v-icon dark>mdi-feather</v-icon>
                          </v-avatar>

                          <div class="pl-2">Yan Lee · 22 July 2019</div>
                        </div>
                      </v-card-text>
                    </v-card>
                  </div>
                </v-hover>
              </v-col>
            </v-row>
          </div>

          <div class="pt-16">
            <h2 class="text-h4 font-weight-bold pb-4">Encontrados</h2>

            <v-row>
              <v-col v-for="i in 3" :key="i" cols="6" lg="4">
                <v-card dark flat>
                  <v-img :aspect-ratio="16 / 9" class="elevation-2 fill-height"
                    gradient="to top, rgba(25,32,72,.4), rgba(25,32,72,.0)" height="600px"
                    src="https://cdn.pixabay.com/photo/2019/10/29/14/46/landscape-4587079_1280.jpg">
                    <div class="d-flex flex-column justify-space-between fill-height">
                      <v-card-text>
                        <v-btn color="accent">ANIMALS</v-btn>
                      </v-card-text>

                      <v-card-text>
                        <div class="text-h5 py-3 font-weight-bold" style="line-height: 1.2">
                          15 things I have always wondered about birds
                        </div>

                        <div class="d-flex align-center">
                          <v-avatar color="accent" size="36">
                            <v-icon dark>mdi-feather</v-icon>
                          </v-avatar>

                          <div class="pl-2">Yan Lee · 03 Jan 2019</div>
                        </div>
                      </v-card-text>
                    </div>
                  </v-img>
                </v-card>
              </v-col>
            </v-row>
          </div>

        </div>
      </v-col>

      <v-col>
        <div class="pt-16">
          <siderbar />
        </div>
      </v-col>
    </v-row>
  </div>
</template>

<script>
export default {
  name: "Home",
  components: {
    siderbar: () => import("@/components/details/sidebar"),
  },
};
</script>
