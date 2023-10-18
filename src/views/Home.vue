<template>
  <div class="home">
    <div class="df">
      <div class="col-personal">
        <div class="df gap32">
          <div class="col-photo">
            <img src="@/assets/photo.jpg" alt="">
          </div>
          <div class="col-info">
            <div class="pers-name">Константинопольский Леонид Александрович</div>
            <div class="grid2col">
              <div class="name">Дата рождения:</div>
              <div class="value">18.05.1998 25 лет</div>

              <div class="name">Сумма займа:</div>
              <div class="value">90 000 руб</div>

              <div class="name">Срок возврата:</div>
              <div class="value">60 дней</div>

              <div class="name">Рабочий</div>
            </div>
          </div>
        </div>
        <div class="actions df gap8">
          <AppBtn icon="Phone" @click.native="showModal = true">Вызов</AppBtn>
          <AppBtn class="outline" icon="Sms">SMS</AppBtn>
          <AppBtn class="outline" icon="Mail">Email</AppBtn>
          <AppBtn class="outline" icon="Strategy">Стратегия</AppBtn>
          <AppBtn class="outline" icon="Oper">Оператор</AppBtn>
        </div>
      </div>
      <div class="col-project">
        <div class="grid2col">
          <div class="name">Статус:</div>
          <div class="value">В работе</div>

          <div class="name">Этап:</div>
          <div class="value">Проактивный контакт</div>

          <div class="name">След. этап:</div>
          <div class="value">
            Юридические меры, 19.05.2023
            <div class="small">Шаблон: <a href="Уведомление о судебных действиях">Уведомление о судебных действиях</a></div>
          </div>

          <div class="name">Взыскатель:</div>
          <div class="value">ИП Сидоров</div>

          <div class="name">Цедент:</div>
          <div class="value">ИП Петров</div>

          <div class="name">Договор цессии:</div>
          <div class="value"><a href="#">№987654321</a> 12.02.2023</div>

          <div class="name">Договор займа:</div>
          <div class="value"><a href="#">№548321654</a> 19.05.2022</div>
        </div>
      </div>
    </div>
    <table class="table">
      <tr>
        <th>Дата</th>
        <th>Тип</th>
        <th>Комментарий</th>
        <th>Оператор</th>
        <th></th>
      </tr>
      <tr>
        <td>25.10.2023 10:23</td>
        <td>Звонок</td>
        <td>Позвонил должнику, напомнил о задолженности, договорились о дате погашения.</td>
        <td>Иванов П.А.</td>
        <td><AppBtn class="outline btn-icon" icon="Edit" /></td>
      </tr>
      <tr>
        <td>25.10.2023 10:23</td>
        <td>Звонок</td>
        <td>Долгий разговор с должником, обсуждение личной финансовой ситуации</td>
        <td>Иванов П.А.</td>
        <td><AppBtn class="outline btn-icon" icon="Edit" /></td>
      </tr>
    </table>

    <Modal :show-modal="showModal" @close="showModal = false" />
  </div>
</template>

<script>
import AppBtn from '@/components/AppBtn.vue';
import Modal from '@/components/Modal.vue'

export default {
  data(){
    return {
      showModal: false
    }
  },
  components: {
    AppBtn, Modal
}
}
</script>

<style lang="less" scoped>
  .col-personal {
    padding: 32px;
  }
  .col-project {
    border-left: 1px solid #C7C7C7;
    padding: 32px;
    .small {margin-top: 4px;}
    .grid2col {gap: 16px 0;}
  }
  .pers-name {
    font-size: 24px;
    font-weight: 600;
    max-width: 380px;
    margin-bottom: 16px;
  }
  .col-photo {
    img {border-radius: 32px;}
  }
  .actions {
    margin-top: 16px;
  }
</style>