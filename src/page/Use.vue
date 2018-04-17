<template>
    <div class="use">
        <button type="button" class="btn" @click="showModal">打开Modal</button> 
        <modal v-show="isModalVisible" @close="closeModal" >
            <h2 slot="header">我是新的标题</h2>
        </modal>
    </div>
</template>
<script>
import Modal from "../components/Pops";
export default {
  name: "container",
  components: {
    Modal
  },
  data() {
    return {
      isModalVisible: false
    };
  },
  methods: {
    showModal() {
      this.isModalVisible = true;
    },
    closeModal() {
      this.isModalVisible = false;
    }
  }
};
</script>
<style>

</style>