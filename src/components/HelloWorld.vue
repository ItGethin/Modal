<template>
<div>
    <div class='aft-box'>
            <div class='aft-flex aft-pd'>
                <div class='aft-btn' @click='alerts'>alert</div>
            </div>
            <div class='aft-flex aft-pd'>
                <div class='aft-btn aft-blue' @click='confirms'>confirm</div>
            </div>
    </div>
    <Modal  type='alert' @took='okfall' :showstate='showa'>
            <span slot='tlt'>提示</span>
            <div slot='text'>我是一个alert提示弹窗</div>
    </Modal>
    <Modal  type='confirm' @took='okfall2' @tocancel='cancelfall' :showstate='showc'>
            <span slot='tlt'>确认</span>
            <div slot='text'>{{msg}}</div>
    </Modal>
</div>
</template>
<script>
import Modal from "./Pop";
export default {
  name: "container",
  components: {
    Modal
  },
  data() {
    return {
      showa: false,
      showc: false,
      msg: "我有两个按钮，是confirm确认弹窗"
    };
  },
  methods: {
    alerts() {
      this.showa = true;
    },
    confirms() {
      this.showc = true;
      this.msg = "我有两个按钮，是confirm确认弹窗";
    },
    okfall() {
      this.showa = false;
    },
    okfall2() {
      this.msg = "点击了确认按钮，2秒后弹窗关闭";
      setTimeout(() => {
        this.showc = false;
      }, 2000);
    },
    cancelfall() {
      this.showc = false;
    }
  }
};
</script>
<style>
.aft-box {
  display: flex;
  line-height: 0.65rem;
  font-size: 0.26rem;
  color: #333;
  padding: 0.5rem 0;
}
.aft-flex {
  flex: 1;
}
.aft-pd {
  padding: 0.5rem 0.1rem;
}
.aft-btn {
  display: block;
  line-height: 0.88rem;
  text-align: Center;
  color: #fff;
  border-radius: 0.12rem;
  background: #ffb63b;
}
.aft-blue {
  background: #488bf1;
}
</style>