<script>
export default {
    name: "TopHeader",
    data() {
        return {
            topHeaderLinks: [
                {
                    name: "Courses",
                    url: "#",
                },
                {
                    name: "Zoom",
                    url: "#",
                },
                {
                    name: "Pages",
                    url: "#",
                },
                {
                    name: "Bundles",
                    url: "#",
                },
                {
                    name: "Course Formats",
                    url: "#",
                },
                {
                    name: "Add Course",
                    url: "#",
                },
                {
                    name: "Demos",
                    url: "#",
                },
            ],
            topHeaderIcons: [
                "fa-twitter",
                "fa-instagram",
                "fa-behance",
                "fa-dribbble",
                "fa-git",
                "fa-linkedin",
                "fa-pinterest",
            ],
        };
    },
};
</script>

<template>
    <div class="mb">
        <div class="large-container">
            <div class="top-header">
                <!-- Left -->
                <div>
                    <select class="form-select form-select-sm" aria-label=".form-select-sm example">
                        <option selected>English</option>
                        <option value="1">Italian</option>
                        <option value="2">Deutch</option>
                        <option value="3">Francais</option>
                    </select>
                </div>
                <!-- Right -->
                <div class="right">
                    <!-- Link -->
                    <div>
                        <ul>
                            <li v-for="(link, index) in topHeaderLinks" :key="index" class="mt-3">
                                <a :href="link.url">{{ link.name }}</a>
                                <div v-if="index === 2 || index === 4">New</div>
                            </li>
                        </ul>
                    </div>
                    <!-- Icons -->
                    <div class="icons">
                        <i v-for="(icon, index) in topHeaderIcons" class="fa-brands" :class="icon" :key="index"></i>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<style scoped lang="scss">
@import "../../assets/sass/style.scss";

.mb {
    border-bottom: 1px solid $anthensgray;
}

.top-header {
    @include flex(row, space-between, center);
    padding: 1rem 0;

    a,
    span,
    i {
        opacity: 0.6;
        font-size: 0.9rem;
        text-decoration: none
    }

    ul {
        @include flex(row, flex-end, center);
        gap: 2rem;
    }

    li {
        list-style: none;
        position: relative;

        div {
            position: absolute;
            color: white;
            background-color: $red;
            padding: 0.2rem;
            text-transform: uppercase;
            font-size: 0.6rem;
            top: -1rem;
            right: -0.5rem;
        }

        a {
            color: black;
        }
    }

    .lang {
        margin-right: 0.7rem;
    }

    .right {
        @include flex(row, flex-end, center);
        gap: 3rem;

        .icons {
            display: flex;
            gap: 1rem;
        }
    }
}

@include xl {
    .top-header {
        ul {
            display: none;
        }
    }
}
</style>  