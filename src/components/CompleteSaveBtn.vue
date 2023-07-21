<!--讓他可以傳入成功或失敗 v-if判斷-->
<template>
  <button ref="liveToastBtn" type="button" class="btn btn-primary" @click="showToast">儲存</button>
  <div class="position-fixed bottom-0 end-0 p-3" style="z-index: 11">
    <div id="liveToast" class="toast" role="alert" aria-live="assertive" aria-atomic="true">
      <div class="toast-header">
        <strong class="me-auto">提示</strong>
        <button type="button" class="btn-close" data-bs-dismiss="toast" aria-label="Close"></button>
      </div>
      <div class="toast-body">
        儲存成功
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from "vue";

const liveToastBtn = ref(null);

const showToast = () => {
  const toastLiveExample = document.getElementById('liveToast');
  const toast = new bootstrap.Toast(toastLiveExample);
  toast.show();
}

onMounted(() => {
  console.log(liveToastBtn.value);
});
</script>
