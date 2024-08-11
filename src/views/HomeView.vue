<script setup>
import { ref, onMounted } from "vue";

// 法 1 - 只引入需要的功能
// import { Modal } from 'bootstrap';
// const myModal = ref(null);

// onMounted(() => {
//   const test = new Modal(myModal.value);
//   test.show();
// })

// 法 2 - 引入全部的 bootstrap
// import * as bootstrap from 'bootstrap';
// const myModal = ref(null);

// onMounted(() => {
//   const test = new bootstrap.Modal(myModal.value, {});
//   test.show();
// });

// 法 3 - 跟法 1 有點像，只是引入檔案的路徑更明確
// import * as bootstrap from 'bootstrap'; // 依需求決定是否引入全部
import Modal from 'bootstrap/js/dist/modal';
const myModal = ref(null);

onMounted(() => {
  const test = new Modal(myModal.value);
  test.show();
});
</script>

<template>
  <main>
    <!-- Button trigger modal -->
    <button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#exampleModal">
      Launch demo modal
    </button>

    <!-- Modal -->
    <div class="modal fade" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true"
      ref="myModal">
      <div class="modal-dialog">
        <div class="modal-content">
          <div class="modal-header">
            <h1 class="modal-title fs-5" id="exampleModalLabel">Modal title</h1>
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
