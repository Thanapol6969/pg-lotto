<template>
  <v-app dark>
    <v-main class="centered">
      <v-card>
        <v-card-title> </v-card-title>
        <v-card-text>
          <v-text-field
            v-model="Username"
            :error-messages="nameErrors"
            label="Name"
            required
          ></v-text-field>
          <v-text-field
            v-model="Password"
            :error-messages="passwordErrors"
            label="Password"
            required
          ></v-text-field>
        </v-card-text>
        <v-card-actions>
          <!-- <v-btn class="mr-4" color="success" nuxt to="/"> submit </v-btn> -->
          <v-btn
            :loading="loading5"
            :disabled="loading5"
            color="success"
            class="ma-2 white--text"
            
            @click="loader = 'loading5'"
          >
            submit
          </v-btn>
          <v-btn @click="clear"> clear </v-btn>
          <v-btn @click="clear"> clear </v-btn>

          
        </v-card-actions>
      </v-card>
    </v-main>
  </v-app>
</template>

<script>
export default {
  layout: "full",
  data() {
    return {
        loader: null,
      loading5: false,
    };
  },
  watch: {
    loader() {
      const l = this.loader;
      this[l] = !this[l];

      setTimeout(() => 
        //   this[l] = false
            this.$router.push("/")
          , 1000);

      this.loader = null;
    },
  },
};
</script>
<style lang="css">
.centered {
  position: fixed;
  top: 50%;
  left: 50%;
  /* bring your own prefixes */
  transform: translate(-50%, -50%);
}
.custom-loader {
    animation: loader 1s infinite;
    display: flex;
  }
  @-moz-keyframes loader {
    from {
      transform: rotate(0);
    }
    to {
      transform: rotate(360deg);
    }
  }
  @-webkit-keyframes loader {
    from {
      transform: rotate(0);
    }
    to {
      transform: rotate(360deg);
    }
  }
  @-o-keyframes loader {
    from {
      transform: rotate(0);
    }
    to {
      transform: rotate(360deg);
    }
  }
  @keyframes loader {
    from {
      transform: rotate(0);
    }
    to {
      transform: rotate(360deg);
    }
  }
</style>