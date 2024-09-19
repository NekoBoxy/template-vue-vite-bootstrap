<script setup>
import { ref, onMounted } from "vue";

// 法 1 - 只引入需要的功能
import { Modal } from 'bootstrap';
const myModal = ref(null);

onMounted(() => {
  const test = new Modal(myModal.value);
  test.show();
})

// 法 2 - 全引入，但 vite 的 treeshaking 會濾掉無用檔案
// import * as bootstrap from 'bootstrap';
// const myModal = ref(null);

// 法 2 .1 - 多了 {} (設定用?)
// onMounted(() => {
//   const test = new bootstrap.Modal(myModal.value, {});
//   test.show();
// });

// 法 2 .2 - 無 {}
// onMounted(() => {
//   const test = new bootstrap.Modal(myModal.value);
//   test.show();
// });

// 法 3 - 極不建議使用。若官方換檔名/結構就全滅
// import Modal from 'bootstrap/js/dist/modal';
// const myModal = ref(null);

// onMounted(() => {
//   const test = new Modal(myModal.value);
//   test.show();
// });
</script>

<template>
  <main>
    <!-- Button trigger modal -->
    <!-- <button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#exampleModal">
      Launch demo modal
    </button> -->

    <div>嗨</div>


    <!-- Modal -->
    <div class="modal fade" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true"
      ref="myModal">
      <div class="modal-dialog">
        <div class="modal-content">
          <div class="modal-header">
            <!-- <h1 class="modal-title fs-5" id="exampleModalLabel">Modal title</h1> -->
            <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
          </div>
          <div class="modal-body">
            ...
          </div>
          <div class="modal-footer">
            <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
            <button type="button" class="btn btn-primary">Save changes</button>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>
