<template>
    <div class="btn">
        <SvgIcon :name="icon" />
        <slot />
    </div>
</template>

<script>
    import SvgIcon from './SvgIcon.vue';

    export default {
        props:['icon'],
        components: {
            SvgIcon
        }
    }
</script>

<style lang="less" scoped>
.btn.hang {
    svg {transform: rotate(135deg);}
}
</style>