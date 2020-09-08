<template>
    <header>
    <nav class="navbar navbar-expand navbar-light bg-light sticky-top shadow-sm mb-0" role="navigation">
    <a class="navbar-brand" href="#">TodoList</a>
    <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#collapsibleNavId" aria-controls="collapsibleNavId"
        aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="collapsibleNavId">
        <ul class="navbar-nav mr-auto mt-2 mt-lg-0">
            <li class="nav-item active">
                 <router-link to="/" class="nav-link">Home<span class="sr-only">(current)</span></router-link>
            </li>
            <li class="nav-item">
                 <router-link to="/about" class="nav-link">About</router-link>
            </li>
            <li class="nav-item">
                 <router-link to="/todos" class="nav-link">Todos</router-link>
            </li>
        </ul>
        <!-- <form class="form-inline my-2 my-lg-0">
            <input class="form-control mr-sm-2" type="text" placeholder="Search todo">
        </form> -->
    </div>
</nav>
    </header>
</template>

<script>
export default {
    name:"Header"
}
</script>