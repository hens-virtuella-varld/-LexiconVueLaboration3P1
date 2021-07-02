<template>
    <nav class="navbar navbar-expand-lg navbar-light bg-light">
        <div class="container-fluid">
            <router-link class="navbar-brand" to="/"
                ><img src="@/assets/LexiconBig.png" height="30px" />
            </router-link>
            <button
                class="navbar-toggler"
                type="button"
                data-bs-toggle="collapse"
                data-bs-target="#navbarNavAltMarkup"
                aria-controls="navbarNavAltMarkup"
                aria-expanded="false"
                aria-label="Toggle navigation"
            >
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarNavAltMarkup">
                <div class="navbar-nav">
                    <router-link
                        class="nav-link active"
                        aria-current="page"
                        to="/"
                        >Home</router-link
                    >
                    <router-link to="/createPost" class="nav-link"
                        >Create Post</router-link
                    >
                    <router-link to="/about" class="nav-link"
                        >About</router-link
                    >
                </div>
            </div>
        </div>
    </nav>
</template>

<script>
export default {};
</script>

<style></style>
