# Slideup

## Setup
```sh
npm i slideup
```

Usage
```vue
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
import Slider from 'slideup'

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
```

