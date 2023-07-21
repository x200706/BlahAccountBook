<!--之後還想做上鎖功能-->
<script setup>
  import CompleteSaveBtn from './CompleteSaveBtn.vue'
</script>

<template>
<nav class="navbar navbar-dark bg-dark">
    <div class="container-fluid">
      <a class="navbar-brand" href="#">BlahAccountBook</a>
    </div>
</nav>

<div class="container">
  <div class="row">
    <div class="col">
<!--我是左邊-->
      每月支出<br>
      每月支出細節
    </div>
    <div class="col-6">
      <!-- Button trigger modal -->
      總資產
      總收入
<div class="account-btn"><button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#exampleModal" align="left">
  記帳
</button>
  </div>

<!-- Modal -->
<div class="modal fade" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
  <div class="modal-dialog">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title" id="exampleModalLabel">記帳</h5>
        <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
      </div>
      <div class="modal-body">
        表單預留位
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">取消</button>
        <CompleteSaveBtn/>
      </div>
    </div>
  </div>
</div>
<table class="table">
  <thead class=table-dark>
    <tr>
      <th scope="col">項目</th>
      <th scope="col">日期</th>
      <th scope="col">收/支</th>
      <th scope="col">分類</th>
      <th scope="col">金額</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>洗碗精</td><!--希望飄上去有memo欸-->
      <td>2023/07/19</td>
      <td>支出</td>
      <td>日用品</td>
      <td>70</td>
    </tr>
  </tbody>
</table>
    </div>
    <div class="col">
<!--我是右邊-->
      總支出分布<br>
      開銷Top10
    </div>
  </div>
</div>
</template>
<style scoped>
.account-btn{
  text-align: right;
  margin-bottom: 10px;
  margin-top: 10px;
}
</style>
