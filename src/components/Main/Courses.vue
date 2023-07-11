<template>
  <div :class="changeBgColor">
    <div class="large-container">
      <h1>{{ info.title }}</h1>
      <!-- Categories -->
      <div v-if="info.title === 'Recent courses'" class="categories">
        <span v-for="(category, index) in categories" :key="index" :class="index === 0 ? 'active' : ''">{{ category
        }}</span>
      </div>
      <div v-else>
        <p class="desc">Discover our most popular courses for self learning.</p>
      </div>
      <!-- Courses Grid -->
      <div v-if="info.title === 'Recent courses'" class="grid">
        <SingleCourse v-for="(course, index) in courses" :key="index" :course="course" />
      </div>
      <div v-else class="grid">
        <SingleCourse v-for="(course, index) in filteredCourses" :key="index" :course="course" />
      </div>
      <a v-if="info.title === 'Recent courses'" class="btn btn-primary p-3">Show All</a>
      <div v-else class="slider">
        <div>
          <i class="fa-solid fa-chevron-left"></i>
        </div>
        <div>
          <i class="fa-solid fa-chevron-right"></i>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import SingleCourse from "./Courses/SingleCourse.vue";

export default {
  name: "CoursesDiv",
  components: {
    SingleCourse,
  },
  props: ["info"],
  data() {
    return {
      categories: [
        "All Categories",
        "Art",
        "Exercise",
        "Material Design",
        "Music",
        "Photography",
        "Software Development",
      ],
      courses: [
        {
          category: "Apache",
          title: "Web Coding and Apache",
          hours: "6",
          free: true,
          img: '../../assets/img/photo-1461749280684-dccba630e2f6-544x322.jpeg'
        },
        {

          category: "Art",
          title: "Real Things Art Painting",
          hours: "6",
          price_discount: "60",
          price_final: "45",
        },
        {

          category: "Software Development",
          title: "Basics of Masterstudy",
          stars: 5,
          free: true,
        },
        {

          category: "Electronic",
          title: "How to be a DJ?",
          stars: 5,
          price_discount: "59",
          price_final: "49",
        },
        {

          category: "Communication",
          title: "Design Instruments",
          hours: "6",
        },
        {

          category: "Art",
          title: "Make your Concept Right",
          hours: "6",
          price_final: "70",
        },
        {

          category: "Bicycling",
          title: "Road Bike Manual",
          hours: "6",
          price_final: "20",
        },
        {

          category: "Documentary",
          title: "How to Make Photos?",
          hours: "6",
          price_final: "60",
        },
        {

          category: "Art",
          title: "Van Gogh's Starry Night",
          hours: "6",
          price_final: "79",
        },
        {

          category: "Nvidia",
          title: "Nvidia and UE4",
          stars: 5,
          free: true,
        },
        {

          category: "Art",
          title: "Legendary RED Camera",
          hours: 6,
          free: true,
        },
        {

          category: "Software Development",
          title: "MasterStudy Mobile",
          hours: 2,
          free: true,
        },
      ],
    };
  },
  computed: {
    changeBgColor() {
      return this.info.title === "Popular courses" ? "bg-blue" : "";
    },
    filteredCourses() {
      return this.courses.slice(0, 6);
    },
  },
};
</script>

<style scoped lang="scss">
@import "../../assets/sass/style.scss";

.bg-blue {
  background-color: $backgroundlightblue;
}

.large-container {
  padding: 6rem 0;
  text-align: center;
}

h1 {
  margin-bottom: 1rem;
}

.desc {
  margin-bottom: 3rem;
}

.btn {
  margin: 0 auto;
  width: 8rem;
}

.categories {
  @include flex(row, center, center);
  column-gap: 3rem;
  row-gap: 1rem;
  padding: 0 10rem;
  color: $denim;
  margin: 3rem;
  flex-wrap: wrap;
  cursor: pointer;

  .active {
    padding: 0.7rem 1rem;
    border-radius: 3rem;
    color: $william;
    background-color: $lightblue;
  }
}

.grid {
  @include grid(6);
  gap: 2rem;
  margin-bottom: 3rem;
  padding: 0 2rem;
}

.slider {
  text-align: center;
  @include flex(row, center, center);

  div {
    @include flex(row, center, center);
    padding: 1rem 1.2rem;
    background-color: white;
    border: 1px solid $anthensgray;

    &:hover {
      background-color: $william;
      color: white;
      cursor: pointer;
    }

    &:hover i {
      opacity: 1;
    }

    i {
      opacity: 0.5;
    }
  }
}

@include xxl {
  .grid {
    @include grid(3);
  }
}

@include xl {
  .categories {
    padding: 0 2rem;
    gap: 1rem;
  }
}

@include md {
  .grid {
    @include grid(1);
  }

  .categories {
    padding: 0;
    gap: 1rem;
  }
}
</style>
