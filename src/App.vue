<script>
import HeaderDiv from "./components/Header/PageHeader.vue";
import MainDiv from "./components/Main/PageMain.vue";
import FooterDiv from "./components/Footer/PageFooter.vue";

export default {
    name: "App",
    components: {
        HeaderDiv,
        MainDiv,
        FooterDiv,
    },
};
</script>

<template>
    <div id="app">
        <HeaderDiv />
        <MainDiv />
        <FooterDiv />
    </div>
</template>

<style lang="scss">
@import "./assets/sass/style.scss";

* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

#app {
    font-family: Arial, sans-serif;
    color: black;
    background-color: white;
}

a {
    text-decoration: none;
}

h1,
h2,
h3 {
    font-weight: normal;
}

.btn {
    display: flex;
    justify-content: center;
    align-content: center;
    text-transform: uppercase;
    font-weight: bold;
    color: white;
    background-color: $denim;
    border-radius: 1.3rem;
    padding: 0.7rem 1.2rem;
    transition: background-color 0.5s;

    &:hover {
        background-color: $shamrock;
        cursor: pointer;
    }
}

.large-container {
    max-width: 1600px;
    margin: 0 auto;
    padding: 0 2rem;
}

.container {
    max-width: 1100px;
    margin: 0 auto;
}

@include xl {
    .container {
        padding: 0 2rem;
    }
}
</style>