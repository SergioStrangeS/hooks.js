<template>
  <div class="modal fade" id="config" data-bs-backdrop="static" data-bs-keyboard="false" tabindex="-1" aria-labelledby="configLabel" aria-hidden="true">
    <div class="modal-dialog modal-lg">
      <div class="modal-content" :class="localdata.darkTheme ? 'bg-dark': ''">
        <div class="modal-header">
          <h5 class="modal-title" id="configLabel">Конфигуратор</h5>
          <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
        </div>
        <div class="modal-body">
          <div class="mb-3">
            <label class="form-label">Kinopoisk Api Unofficial</label>
            <input :type="localdata.Kinopoisk.show ? 'text' : 'password'" v-model="localdata.Kinopoisk.item"
                   class="form-control" aria-describedby="ApiHelp">
            <div id="ApiHelp" class="form-text">Неофициальное API для доступа к актуальной информации
              кинопоиска.</div>
            <div class="form-check">
              <input class="form-check-input" type="checkbox" value="true" id="KinopoiskApi"
                     v-model="localdata.Kinopoisk.show">
              <label class="form-check-label" for="KinopoiskApi">
                Показать токен
              </label>
            </div>
          </div>
          <div class="mb-3">
            <label for="discordToken" class="form-label">Discord Server Webhooks</label>
            <input id="discordToken" :type="localdata.Discord.show ? 'text' : 'password'" v-model="localdata.Discord.item"
                   class="form-control">
            <div class="form-check">
              <input class="form-check-input" type="checkbox" value="true" id="Discord"
                     v-model="localdata.Discord.show">
              <label class="form-check-label" for="Discord">
                Показать hook
              </label>
            </div>
          </div>
        </div>
        <div class="modal-footer d-flex justify-content-between">
          <button type="button" class="btn btn-success" data-bs-toggle="modal" data-bs-target="#secondConfigPage">Дополнительные настройки</button>
          <button type="button" class="btn btn-primary" data-bs-dismiss="modal">Сохранить и выйти</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'MainConfig',
  props: {
    localdata: Object
  }
}
</script>

<style scoped>

</style>
