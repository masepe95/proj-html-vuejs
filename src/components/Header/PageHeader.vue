<script>
import TopHeader from "./PageTopHeader.vue";
import BottomHeader from "./PageBottomHeader.vue";

export default {
    name: "HeaderDiv",
    components: {
        TopHeader,
        BottomHeader,
    },
};

</script>

<template>
    <div>
        <TopHeader />
        <BottomHeader />
    </div>
</template>

<style lang="scss">
@import "../../assets/sass/style.scss";
</style>