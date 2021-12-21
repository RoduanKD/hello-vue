<template>
  <div class="about">
    <v-container>
      <h1>test</h1>
      <v-row>
        <v-col class="primary--text">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Possimus odio cum vero quo nemo nihil, dolorem harum, accusamus porro inventore voluptas nulla dolor. Inventore alias enim suscipit, esse dolorum voluptatibus!
        </v-col>
        <v-col cols="12">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Possimus odio cum vero quo nemo nihil, dolorem harum, accusamus porro inventore voluptas nulla dolor. Inventore alias enim suscipit, esse dolorum voluptatibus!
        </v-col>
        <v-col>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Possimus odio cum vero quo nemo nihil, dolorem harum, accusamus porro inventore voluptas nulla dolor. Inventore alias enim suscipit, esse dolorum voluptatibus!
        </v-col>
        <v-col cols="12">
          <v-btn @click="show = !show">
            hide
          </v-btn>
          <v-slide-y-transition>
            <v-btn v-if="show" color="success" @click="$vuetify.rtl = !$vuetify.rtl">Toggle Direction</v-btn>
          </v-slide-y-transition>
            <v-btn v-if="show" color="success" @click="$vuetify.theme.dark = !$vuetify.theme.dark">Toggle</v-btn>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
export default {
  data () {
    return {
      show: true
    }
  },
  mounted () {
    this.$vuetify.rtl = true
  }
}
</script>
