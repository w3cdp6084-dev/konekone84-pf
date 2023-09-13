<template>
    <button
        class="button-menu"
        :aria-label="open ? 'メニューを閉じる' : 'メニューを開く'"
        :aria-pressed="open"
        @click="toggleMenu"
        type="button">

        <!-- 中略 -->

    </button>
</template>

<script>
export default {
    data() {
        return {
            open: false
        }
    },
    methods: {
        toggleMenu() {
            this.open = !this.open;
        }
    }
}
</script>

<style lang="scss">
    @import '@/assets/css/style/components/Menu.scss';
</style>