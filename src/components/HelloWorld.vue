<!--之後還想做上鎖功能-->
<script setup>
  import IncomeBar from './IncomeBar.vue'
  import CompleteSaveBtn from './CompleteSaveBtn.vue'
  import ExpenditureBar from './ExpenditureBar.vue'
  import CurrentMonthPie from './CurrentMonthPie.vue'
  import TopTenList from './TopTenList.vue'
</script>

<template>
<nav class="navbar navbar-dark bg-dark">
    <div class="container-fluid">
      <a class="navbar-brand" href="#">BlahAccountBook</a>
    </div>
</nav>

<div class="container">
  <div class="row">
    <div class="col-md-8">
      <!-- Button trigger modal -->
      <div style="float:left;width:50%">
        總資產
      <h1>1500000</h1>
      </div>
      <div>總收入
      <IncomeBar />
      </div>
<div class="account-btn"><button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#exampleModal" align="left">
<i class="bi bi-plus-lg"></i>
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
      <th scope="col">操作</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>洗碗精</td><!--希望飄上去有memo欸-->
      <td>2023/07/19</td>
      <td>支出</td>
      <td>日用品</td>
      <td>70</td>
      <td>
        <!--modal-->
<button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#exampleModal1" align="left">
<i class="bi bi-pencil-square"></i>
</button>　
<button type="button" class="btn btn-danger" data-bs-toggle="modal" data-bs-target="#exampleModal1" align="left">
  <i class="bi bi-eraser-fill"></i>
</button>
</td>
    </tr>
        <tr>
      <td>兔子飼料</td><!--希望飄上去有memo欸-->
      <td>2023/07/19</td>
      <td>支出</td>
      <td>日用品</td>
      <td>450</td>
      <td>
        <!--modal-->
<button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#exampleModal1" align="left">
<i class="bi bi-pencil-square"></i>
</button>　
<button type="button" class="btn btn-danger" data-bs-toggle="modal" data-bs-target="#exampleModal1" align="left">
  <i class="bi bi-eraser-fill"></i>
</button>
</td>
    </tr>
        <tr>
      <td>咖啡</td><!--希望飄上去有memo欸-->
      <td>2023/07/19</td>
      <td>支出</td>
      <td>飲食</td>
      <td>90</td>
      <td>
        <!--modal-->
<button type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#exampleModal1" align="left">
<i class="bi bi-pencil-square"></i>
</button>　
<button type="button" class="btn btn-danger" data-bs-toggle="modal" data-bs-target="#exampleModal1" align="left">
  <i class="bi bi-eraser-fill"></i>
</button>
</td>
    </tr>
  </tbody>
</table>
    </div>
    <div class="col-md-4">
<!--我是右邊-->
<details open>
  <summary>每月支出</summary>
  <ExpenditureBar />
</details>
<!--每月支出細節-->
<details open>
  <summary>當月支出分布</summary>
  <CurrentMonthPie />
</details >
<details open>
  <summary>開銷Top10</summary>
  <TopTenList />
</details>
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
