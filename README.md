# Slideup

## Setup
```sh
npm i slideup
```

### Usage
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

### Event
```html
<slider ref="slider"
    :closeBtn="true"
    :open="open"
    :opened="opened"
    :close="close"
    :closed="closed"
>
    <div class="test" @click="sliderHide">关闭</div>
</slider>
```

### Example  
```sh
git clone https://github.com/gavinning/slideup.git
cd slideup && npm i && npm run dev
```
