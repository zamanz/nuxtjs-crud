<template>
<div class="container">
    <div class="row">
        <div>
            <Logo />
            <h1 class="title">
                NuxtCRUD
            </h1>
            <div class="links">
                <a href="https://nuxtjs.org/" target="_blank" rel="noopener noreferrer" class="button--green">
                    Documentation
                </a>
                <a href="https://github.com/nuxt/nuxt.js" target="_blank" rel="noopener noreferrer" class="button--grey">
                    GitHub
                </a>
            </div>
            {{ posts }}
        </div>
    </div>
</div>
</template>

<script>
export default {
    data() {
        return {
            posts: []
        }
    },
    async fetch() {
        this.posts = await this.$axios.$get(
            'https://jsonplaceholder.typicode.com/posts'
        )
    },
    fetchOnServer: false
}
</script>

<style>

</style>
