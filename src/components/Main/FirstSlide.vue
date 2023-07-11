<template>
  <div class="slide">
    <div class="container">
      <div class="text">
        <h1>
          Limitless learning,<br />
          more possibilities
        </h1>
        <p>
          Online courses open the opportunity for learning to almost anyone,
          regardless of their scheduling commitments.
        </p>
        <button type="button" class="btn btn-primary p-3">Learn More</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "FirstSlide",
};
</script>

<style scoped lang="scss">
@import "../../assets/sass/style.scss";

.slide {
  background-image: url("../../assets/img/Untitled-1-1-1-1-1.png");
  background-color: $backgroundlightblue;
  background-position: center;
  padding: 6rem 0;

  .text {
    width: 40%;
    @include flex(column, center, flex-start);
    gap: 1rem;

    p {
      opacity: 0.7;
    }
  }
}

@include md {
  .slide {
    background-image: none;

    .text {
      width: 100%;
    }
  }
}
</style>
