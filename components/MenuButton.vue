<template>
    <button
        class="button-menu"
        :aria-label="open ? 'メニューを閉じる' : 'メニューを開く'"
        :aria-pressed="open"
        @click="toggleMenu"
        type="button">
        <span class="button-menu__icons">
            <span class="button-menu__dots">
                <span class="button-menu__dot"></span>
                <span class="button-menu__dot"></span>
                <span class="button-menu__dot"></span>
            </span>
            <span class="button-menu__bars">
                <span class="button-menu__bar"><span class="button-menu__bar-inner"></span></span>
                <span class="button-menu__bar"><span class="button-menu__bar-inner"></span></span>
            </span>
	    </span>
        <span class="global-header__menu-trigger__label-wrapper" aria-hidden="true">
            <span class="global-header__menu-trigger__label text-en-mobile-label--l text-en-desktop-label--l ">Menu</span>
            <span class="global-header__menu-trigger__label text-en-mobile-label--l text-en-desktop-label--l ">Close</span>
        </span>
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