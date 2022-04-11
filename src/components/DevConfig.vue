<template>
  <div class="modal fade" id="secondConfigPage" data-bs-backdrop="static" data-bs-keyboard="false" tabindex="-1"
       aria-labelledby="secondConfigPageLabel" aria-hidden="true">
    <div class="modal-dialog modal-lg">
      <div class="modal-content bg-dark">
        <div class="modal-header">
          <h5 class="modal-title" id="secondConfigPageLabel">Конфигуратор - дополнительные настройки</h5>
          <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
        </div>
        <div class="modal-body">
          <div class="gap-2 d-sm-flex justify-content-sm-center">
            <button type="submit" class="btn btn-outline-danger my-2 w-100" @click.prevent="cleanHistory()">Очистить
              историю поиска
            </button>
            <button type="submit" class="btn btn-outline-danger my-2 w-100" @click.prevent="resetToDefault()">Сбросить
              до настроек по умолчанию
            </button>
          </div>
          <button type="submit" class="btn btn-outline-danger my-2 w-100" @click.prevent="devTool()">Загрузить историю
            поиска по умолчанию
          </button>
        </div>
        <div class="modal-footer">
          <button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#config">Назад</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DevConfig',
  props: {
    localdata: Object
  }
}
</script>

<style scoped>

</style>
