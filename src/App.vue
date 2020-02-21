<template>
<div id="app">
    <div id="nav">
        <router-link to="/">Home</router-link> |
        <span @click="sliderShow" class="slide">Slide Page</span>
    </div>
    <slider ref="slider" :closeBtn="true">
        <div class="test" @click="sliderHide">关闭</div>
    </slider>
    <router-view/>
</div>
</template>
<script>
import Slider from '@/components/Slider'

export default {
    components: { Slider },

    methods: {
        sliderShow() {
            this.$refs.slider.show()
        },

        sliderHide() {
            this.$refs.slider.hide()
        }
    }
}
</script>
<style lang="stylus">
#app
    font-family Avenir, Helvetica, Arial, sans-serif
    -webkit-font-smoothing antialiased
    -moz-osx-font-smoothing grayscale
    text-align center
    color #2c3e50
    margin-top 60px

.slide
    text-decoration underline
</style>
