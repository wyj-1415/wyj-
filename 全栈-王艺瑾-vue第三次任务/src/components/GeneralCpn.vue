<template>
    <h1>{{ header }}</h1>
    <div>
        <slot name="firstline"></slot>
    </div>
    <!-- <div>
        <slot name="secondline">这是第二个插槽的默认内容</slot>
    </div> -->
</template>
<script>
export default {
    name: 'GeneralCpn',
    props: {
        header: {
            type: String,
            default: '这里是该组件的标题props'
        }
    }
}
</script>