<template>
    <div class="header container-fluid bg-danger">

        <nav class="navbar navbar-expand-lg navbar-dark container">
            <a class="navbar-brand" href="#">
                {{ name }}
            </a>
            <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent"
                aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
            </button>

            <div class="collapse navbar-collapse" id="navbarSupportedContent">
                <ul class="navbar-nav mr-auto" id="nav">
                    <li class="nav-item">
                        <router-link to="/" class="nav-link">Home</router-link>
                    </li>
                    <li class="nav-item">
                        <router-link to="/about" class="nav-link">About</router-link>
                    </li>
                    <li class="nav-item">
                        <router-link to="/service" class="nav-link">Service</router-link>
                    </li>
                    <li class="nav-item">
                        <router-link to="/contact" class="nav-link">Contact</router-link>
                    </li>
                </ul>
                <form class="form-inline my-2 my-lg-0">
                    <input class="form-control mr-sm-2" type="search" placeholder="Search" aria-label="Search">
                    <button class="btn btn-light my-2 my-sm-0" type="submit">Search</button>
                </form>
            </div>
        </nav>

    </div>
</template>

<style scoped>
.router-link-exact-active {
    color: #ffffff !important;
}
.header {
    position: fixed;
    left: 0;
    right: 0;
    top: 0;
    z-index: 1;
}
</style>

<script>
export default {
  name: 'Menu',
  props: {
    name: String
  }
}
</script>