<template>
    <div id="show-blogs" v-theme:column="'wide'">
        <h1>All Blog Articles</h1>
        <input type="text" v-model="search" placeholder="search blogs" />
        <div
            v-for="(blog, i) in filteredBlogs"
            v-bind:key="i"
            class="single-blog"
        >
            <h2 v-rainbow>{{ blog.title | toUpperCase }}</h2>
            <article>{{ blog.body | snippet }}</article>
        </div>
    </div>
</template>

<script>
import axios from "axios";
export default {
    components: {},
    data() {
        return {
            blogs: [],
            search: "",
        };
    },
    methods: {},
    computed: {
        filteredBlogs: function() {
            return this.blogs.filter((blog) => {
                return blog.title.match(this.search);
            });
        },
    },
    created() {
        axios.get("https://jsonplaceholder.typicode.com/posts").then((data) => {
            this.blogs = data.data.slice(0, 10);
        });
    },
    filters: {
        toUpperCase: function(value) {
            return value.toUpperCase();
        },
    },
};
</script>

<style>
#show-blogs {
    max-width: 800px;
    margin: 0 auto;
}
.single-blog {
    padding: 20px;
    margin: 20px 0;
    box-sizing: border-box;
    background: #eee;
}

input[type="text"] {
    padding: 10px;
    line-height: 28px;
    font-size: 2rem;
}
</style>
