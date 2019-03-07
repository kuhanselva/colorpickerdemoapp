<script>
import appConfig from '@src/app.config'
import Layout from '@layouts/main'
import ColorPicker from '@radial-color-picker/vue-color-picker'

export default {
  page: {
    title: 'Home',
    meta: [{ name: 'description', content: appConfig.description }],
  },
  components: { Layout, ColorPicker },
  data() {
    return {
      color: {
        hue: 50,
        saturation: 100,
        luminosity: 50,
        alpha: 1,
      },
    }
  },
  methods: {
    onInput(hue) {
      this.color.hue = hue
      console.log('selected color is: ', hue)
    },
  },
}
</script>

<template>
  <Layout>
    <h1>Home Page</h1>
    <!-- <img src="@assets/images/logo.png" alt="Logo" /> -->

    <ColorPicker v-bind="color" @input="onInput"></ColorPicker>
    <br />
    <br />
    <br />
    <p>Selected hexa color is : {{ color.hue }}</p>
  </Layout>
</template>

<style>
@import '~@radial-color-picker/vue-color-picker/dist/vue-color-picker.min.css';
</style>
