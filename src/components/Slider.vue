<template lang="pug">
.slider-wrapper(
    :class="{ visible, display }"
    @transitionend="animateEnd"
    @webkitTransitionEnd="animateEnd"
)
    .slider-btn-close(v-if="closeBtn" @click="hide")
    slot
</template>
<script>
export default {
    props: {
        closeBtn: {
            type: Boolean,
            default: false
        },
        open: {
            type: Function,
            default: () => {}
        },
        opened: {
            type: Function,
            default: () => {}
        },
        close: {
            type: Function,
            default: () => {}
        },
        closed: {
            type: Function,
            default: () => {}
        }
    },

    data() {
        return {
            display: false,
            visible: false,
        }
    },

    methods: {
        show() {
            this.display = true
            this.visible = true
            this.open()
        },

        hide() {
            this.display = false
            this.close()
        },

        animateEnd() {
            if (this.display === true) {
                this.opened()
            }
            if (this.display === false) {
                this.visible = false
                this.closed()
            }
        }
    }
}
</script>
<style lang="stylus" scoped>
.slider-wrapper
    position fixed
    z-index 900
    left 0
    right 0
    top 0
    bottom 0
    visibility hidden
    background-color #eee
    transform translate3d(0,100vh,0)
    transition transform 260ms ease

    &.visible
        visibility visible

    &.display
        transform translate3d(0,0,0)

.slider-btn-close
    width 40px
    height 40px
    background url(../assets/close.svg) no-repeat center
    background-size 80% auto
    position absolute
    top 6px
    right 6px
    opacity 0.36
</style>
