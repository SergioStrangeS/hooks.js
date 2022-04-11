<template>
  <nav class="navbar navbar-expand-lg border-bottom"
       :class="localdata.darkTheme ? 'navbar-dark bg-dark border-secondary' : 'navbar-light bg-light'">
    <div class="container">
      <router-link class="navbar-brand" to="/">HOOKS.js</router-link>
      <button class="navbar-toggler" type="button" data-bs-toggle="collapse"
              data-bs-target="#navbarNavDropdown" aria-controls="navbarNavDropdown" aria-expanded="false"
              aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNavDropdown">
        <div class="form-check form-switch me-auto mb-2 mb-lg-0">
          <label>
            <input class="form-check-input" type="checkbox" @input="changeTheme($event)">
          </label>
        </div>
        <ul class="navbar-nav me-auto mb-2 mb-lg-0">
          <li class="nav-item">
            <router-link class="nav-link" aria-current="page" to="/">Главная</router-link>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#" data-bs-toggle="modal" data-bs-target="#config">Конфигуратор</a>
          </li>
          <li class="nav-item dropdown">
            <a class="nav-link dropdown-toggle" id="navbarDropdownMenuLink" role="button"
               data-bs-toggle="dropdown" aria-expanded="false">
              Предыдущие версии
            </a>
            <ul class="dropdown-menu" aria-labelledby="navbarDropdownMenuLink">
              <li><a class="dropdown-item" target="_blank"
                     href="https://github.com/SergioStrangeS/hooks.ds">hooks.ds</a></li>
              <li><a class="dropdown-item" target="_blank"
                     href="https://github.com/SergioStrangeS/DiscordWebhooks">DiscordWebhooks</a>
              </li>
            </ul>
          </li>
        </ul>
        <form class="d-flex">
          <input class="form-control me-2" type="search" placeholder="Кинопоиск URL" aria-label="Search"
                 v-model="url" id="search-input">
          <button class="btn btn-success" type="submit"
                  :disabled="localdata.Kinopoisk.item == null || localdata.Kinopoisk.item === ''"
                  @click.prevent="getFilm(url)">Поиск
          </button>
        </form>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'NavbarMenu',
  props: [
    'localdata',
    'url'
  ],
  methods: {
    changeTheme (event) {
      this.$emit('isDarkTheme', event.target.checked)
    }
  }
}
</script>

<style scoped>

</style>
