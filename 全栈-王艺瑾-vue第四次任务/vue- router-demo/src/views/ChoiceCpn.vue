<template>
    <div>
        <h1>你的选择是: {{ selectedItem }}</h1>
    </div>
</template>

<script>
export default {
    data() {
        return {
            selectedItem: this.$route.params.item
        }
    },
    created() {
        this.selectedItem = this.$route.params.item
    }
}
</script>