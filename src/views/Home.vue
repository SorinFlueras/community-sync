<template>
  <v-app>
    <v-main>
      <v-container class="fill-height" fluid>
        <v-row align="center" justify="center">
          <v-col cols="12" sm="8" md="8">
            <v-card class="elevation-12">
              <v-window v-model="step">
                <v-window-item :value="1">
                  <v-row>
                    <v-col cols="12" md="8">
                      <v-card-text class="mt-12">
                        <h1 class="text-center display-2 light-blue--text text--accent-3">
                          Sign in to
                        </h1>
                        <v-img :src="logo" alt="Community Sync Logo" contain aspect-ratio="2"></v-img>
                        <div class="text-center mt-4">
                          <v-btn class="mx-2" fab color="black" outlined>
                            <v-icon>fab fa-facebook-f</v-icon>
                          </v-btn>
                          <v-btn class="mx-2" fab color="black" outlined>
                            <v-icon>fab fa-google-plus-g</v-icon>
                          </v-btn>
                          <v-btn class="mx-2" fab color="black" outlined>
                            <v-icon>fab fa-linkedin-in</v-icon>
                          </v-btn>
                        </div>
                        <h4 class="text-center mlt-4">
                          Provide your email for registration
                        </h4>
                        <v-form>
                          <v-text-field
                            label="Email"
                            name="Email"
                            prepend-icon="email"
                            type="text"
                            color="light-blue accent-3"
                          />
                          <v-text-field
                            id="password"
                            label="Password"
                            name="Password"
                            prepend-icon="lock"
                            type="password"
                            color="light-blue accent-3"
                          />
                        </v-form>
                        <h3 class="text-center mt-3">Forget your password?</h3>
                      </v-card-text>
                      <div class="text-center mt-3">
                        <v-btn rounded color="light-blue accent-3" dark @click="redirectToAbout();"
                          >SIGN IN</v-btn
                        >
                      </div>
                    </v-col>
                    <v-col cols="12" md="4" class="light-blue accent-3">
                      <v-card-text class="white--text mt-12">
                        <h1 class="text-center display-1">Hello, neighbour!</h1>
                        <h5 class="text-center">
                          Enter your personal details and join your community.
                        </h5>
                      </v-card-text>
                      <div class="text-center">
                        <v-btn rounded outlined="" dark @click="step++"
                          >SIGN UP</v-btn
                        >
                      </div>
                    </v-col>
                  </v-row>
                </v-window-item>
                <v-window-item :value="2">
                  <v-row class="fill-height">
                    <v-col cols="12" md="4" class="light-blue accent-3">
                      <v-card-text class="white--text mt-12">
                        <h1 class="text-center display-1">Welcome back!</h1>
                        <h5 class="text-center">
                          To get back into your account, please login with your
                          personal info.
                        </h5>
                      </v-card-text>
                      <div class="text-center">
                        <v-btn rounded outlined dark @click="step--"
                          >SIGN IN</v-btn
                        >
                      </div>
                    </v-col>
                    <v-col cols="12" md="8">
                      <v-card-text class="mt-12">
                        <h1
                          class="text-center display-2 light-blue--text text--accent-3"
                        >
                          Create Account
                        </h1>
                        <v-img :src="logo" alt="Community Sync Logo" contain aspect-ratio="2"></v-img>
                        <div class="text-center mt-4">
                          <v-btn class="mx-2" fab color="black" outlined>
                            <v-icon>fab fa-facebook-f</v-icon>
                          </v-btn>
                          <v-btn class="mx-2" fab color="black" outlined>
                            <v-icon>fab fa-google-plus-g</v-icon>
                          </v-btn>
                          <v-btn class="mx-2" fab color="black" outlined>
                            <v-icon>fab fa-linkedin-in</v-icon>
                          </v-btn>
                        </div>
                        <h4 class="text-center mt-4">
                          Provide your email for registration.
                        </h4>
                        <v-form>
                          <v-text-field
                            label="Name"
                            name="Name"
                            prepend-icon="person"
                            type="text"
                            color="light-blue accent-3"
                          />
                          <v-text-field
                            label="Email"
                            name="Email"
                            prepend-icon="email"
                            type="text"
                            color="light-blue accent-3"
                          />
                          <v-text-field
                            label="Password"
                            name="Password"
                            prepend-icon="lock"
                            type="password"
                            color="light-blue accent-3"
                          />
                        </v-form>
                      </v-card-text>
                      <div class="text-center mt-5">
                        <v-btn rounded color="light-blue accent-3" dark
                          >SIGN UP</v-btn
                        >
                      </div>
                    </v-col>
                  </v-row>
                </v-window-item>
              </v-window>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
export default {
  data: () => ({
    step: 1,
    logo: require('../assets/CommunitySyncLogoFinal.png')
  }),
  props: {
    source: String,
  },
  methods: {
    redirectToAbout() {
      this.$router.push({path: '/about'})
    }
  }
};
</script>
