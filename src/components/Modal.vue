<template>
  <transition name="modal-slide" mode="out-in">
    <div class="modal-container" v-if="showModal">
        <div class="head df">
            <div class="col-callinfo df alit-cn gap8">
                <SvgIcon name="PhoneOut" />
                <div class="col-number">
                    <strong>+7-321-654-56-56</strong> дом.
                    <div class="small">20 окт 2023, 12:25</div>
                </div>
            </div>

            <div class="col-close" @click="closeModal"><SvgIcon name="Plus" /></div>
        </div>
        <div class="comment">
          <textarea rows="10" placeholder="Комментарий"></textarea>
        </div>
        <div class="foot">
            <div class="call-time df alit-cn">
                <div class="col-time">00:32</div>
                <div class="col-rec">
                    <div class="col-mic"><SvgIcon name="Mic" /></div>
                    <div class="col-rec-text">Запись</div>
                    <div class="col-switch">
                        <div class="switch">
                            <div class="switch-btn">ON</div>
                        </div>
                    </div>
                </div>
            </div>

            <AppBtn icon="Phone" class="w100p hang just-cn btn-red">Завершить звонок...</AppBtn>
        </div>
      </div>
  </transition>
</template>

<script>
import AppBtn from './AppBtn.vue';
import SvgIcon from './SvgIcon.vue';

export default {
    props: {
        showModal: {
            type: Boolean,
            required: true,
        },
    },
    methods: {
        closeModal() {
            this.$emit('close');
        },
    },
    components: { SvgIcon, AppBtn }
};
</script>

<style lang="less" scoped>
.switch {
    border-radius: 8px;
    border: 1px solid #4C505E;
    background: rgba(14, 14, 19, 0.69);
    width: 14px;
    height: 10px;
    position: relative;
    margin: 0 10px;
    .switch-btn {
        position: absolute;
        width: 25px;
        border-radius: 8px;
        background: linear-gradient(0deg, #5167F1 0%, #5167F1 100%), linear-gradient(180deg, #6764ED 0%, #5756ED 100%);
        padding: 2px 4px;
        color: #FFF;
        text-align: center;
        font-size: 9px;
        font-weight: 600;
        top: 50%;
        transform: translateY(-50%) translateX(5px);
    }
}
.col-mic {
    position: relative;
    margin-right: 6px;
    svg {
        width: 16px;
        height: 16px;
    }
    &::before {
        content: '';
        position: absolute;
        width: 30px;
        height: 30px;
        background-color: #5167F1;
        opacity: .2;
        border-radius: 50%;
        left: 50%;
        top: 50%;
        transform: translate(-50%, -50%);
    }
    &::after {
        content: '';
        position: absolute;
        width: 40px;
        height: 40px;
        background-color: #5167F1;
        opacity: .15;
        border-radius: 50%;
        left: 50%;
        top: 50%;
        transform: translate(-50%, -50%);
    }
}
.col-rec {
    display: flex;
    align-items: center;
}
.head {
    padding: 20px 24px;
    cursor: grab;
}
.comment {
    background-color: #292A2B;
    textarea {
        border: 0;
        width: 100%;
        display: block;
        background: none;
        resize: none;
        font-family: 'Raleway', sans-serif;
        font-variant-numeric: lining-nums;
        padding: 8px 24px;
    }
}
.call-time {
    justify-content: space-between;
    margin-bottom: 16px;
}
.foot {
    padding: 20px 24px;
}
.col-close {
    cursor: pointer;
    margin-left: auto;
    svg {transform: rotate(45deg);}
}
.modal-container {
  width: 362px;
  position: fixed;
  z-index: 999;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  background-color: #191A1B;
  border-radius: 16px;
  display: flex;
  flex-direction: column;
  color: #fff;
}

.modal-content {
  padding: 20px;
}

button {
  margin-top: 10px;
}
.modal-slide-enter-active, .modal-slide-leave-active {
    transition: all 0.35s;
}
.modal-slide-enter, .modal-slide-leave-to {
    opacity: 0;
    transform: translate(-50%, 50vw);
}
</style>
