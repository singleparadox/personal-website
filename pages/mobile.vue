<template>
  <v-container fluid class="ma-0 pa-0">
    <v-card class="main-card" flat>
      <v-container class="ma-0 pa-0 avatar-cover"></v-container>
      <v-list-item three-line>
        <v-list-item-content>
          <v-container fluid class="ma-0 pa-0 mb-1 d-flex flex-column align-center">
            <v-avatar size="80" color="grey" class="avatar-picture">
              <img :src="links.avatar" alt="Glenn's Avatar" />
            </v-avatar>
          </v-container>
          <div class="text-overline text-center mb-4" aria-label="Glenn Perez">Glenn Perez</div>
          <v-list-item-subtitle class="text-center">I'm a Software Developer</v-list-item-subtitle>
          <v-list-item-subtitle
            class="text-center"
          >I am proficient in JavaScript (ES6), Python 3, and PHP 7</v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>

      <v-card-actions class="pt-5 d-flex flex-row align-center justify-center">
        <v-btn icon large :color="buttonsColor" aria-label="Email Address" @click="getEmail">
          <v-icon large>mdi-email</v-icon>
        </v-btn>
        <v-btn
          icon
          large
          target="_blank"
          :color="buttonsColor"
          aria-label="LinkedIn Profile"
          :href="links.linkedIn"
        >
          <v-icon large>mdi-linkedin</v-icon>
        </v-btn>
        <v-btn
          icon
          large
          target="_blank"
          :color="buttonsColor"
          aria-label="Resume"
          :href="links.resume"
        >
          <v-icon large>mdi-book</v-icon>
        </v-btn>
        <v-btn
          icon
          large
          target="_blank"
          :color="buttonsColor"
          aria-label="GitHub Profile"
          :href="links.gitHub"
        >
          <v-icon large>mdi-github</v-icon>
        </v-btn>
      </v-card-actions>
    </v-card>
    <v-container fluid class="ma-0 pa-0 text-center footer">
      <span>Created using Nuxt.js and Vuetify</span>
      <br />
      <span>Hosted on GitHub Pages</span>
    </v-container>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      buttonsColor: '#9fc1ff',
      links: {
        avatar: "https://i.imgur.com/mTY19OP.png",
        linkedIn: "https://www.linkedin.com/in/glenn-p-perez/",
        resume: "https://drive.google.com/file/d/1uhZ40S4Zn2uMLoEMUaEeos5nnojKk_J8/view?usp=sharing",
        gitHub: "https://github.com/singleparadox/"
      }

    }
  },
  methods: {
    getEmail() {
      const encryptedEmail = "ingppocvvjgyargtg|Bjqvockn0eqo";
      const decryptedEmail = encryptedEmail
                            .split("")
                            .map(v => String.fromCharCode(v.charCodeAt(0) - 2))
                            .join("");

      window.open("mailto:" + decryptedEmail, '_blank');
    }
  }
}
</script>

<style lang="scss" scoped>
.main-container {
  height: 100%;
}

.main-card {
  background-repeat: no-repeat;
  background-position: center center;
  transition: box-shadow 0.3s;
}

// Avatar cover
.avatar-cover {
  bottom: 210px;
  position: absolute;
  height: 80px;
  background: rgb(159, 193, 255);

  //   ?To gradiant or not to gradient? Hard choice :-(
  //   background: linear-gradient(
  //     180deg,
  //     rgba(159, 193, 255, 1) 87%,
  //     rgba(60, 31, 255, 0) 100%
  //   );
}

.avatar-picture {
  margin-top: 25px;
  border: 0.5px solid black;
  z-index: 3;
}

.footer {
  //   top: 340px;
  bottom: 15vh;
  position: absolute;
  height: 60px;
  color: rgba(0, 0, 0, 0.6);
  font-size: 10pt;
  // background: linear-gradient(
  //   180deg,
  //   rgba(63, 94, 251, 1) 0%,
  //   rgba(252, 70, 107, 0) 0%,
  //   rgba(182, 100, 224, 0.6530987394957983) 56%
  // );
}

.button-container {
  width: 150px;
}

.v-card > *:last-child:not(.v-btn):not(.v-chip):not(.v-avatar) {
  border-bottom-left-radius: 0;
  border-bottom-right-radius: 0;
  border-top-left-radius: 20px;
  border-top-right-radius: 20px;
}
</style>