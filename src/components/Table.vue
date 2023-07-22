<template>
  <div class="container">
    <table class="table">
      <!-- 在這裡放入你的表格標頭（thead）-->
      <thead>
        <tr>
          <th>列名1</th>
          <th>列名2</th>
          <!-- 其他列名... -->
        </tr>
      </thead>
      <tbody>
        <!-- 使用 v-for 顯示表格資料 -->
        <tr v-for="row in displayedData" :key="row.id">
          <td>{{ row.column1 }}</td>
          <td>{{ row.column2 }}</td>
          <!-- 其他列資料... -->
        </tr>
      </tbody>
    </table>

    <!-- 分頁組件 -->
    <nav aria-label="Page navigation">
      <ul class="pagination">
        <li class="page-item" v-for="page in pagination" :key="page">
          <a class="page-link" href="#" @click="changePage(page)">{{ page }}</a>
        </li>
      </ul>
    </nav>
  </div>
</template>

<script>
import { ref, onMounted } from 'vue';

export default {
  setup() {
    // 假設每頁要顯示的項目數量為10
    const itemsPerPage = 10;

    // 假設總共有50條數據
    const totalItems = 50;

    // 計算總共有多少頁
    const totalPages = Math.ceil(totalItems / itemsPerPage);

    // 使用 ref 創建一個響應式的變數來保存當前頁數
    const currentPage = ref(1);

    // 定義所有表格資料的陣列
    const tableData = [
      // 表格資料...
      // 這裡假設每條資料有 column1 和 column2 兩個屬性，你可以根據實際情況修改
    ];

    // 動態生成分頁按鈕
    const pagination = [];
    for (let i = 1; i <= totalPages; i++) {
      pagination.push(i);
    }

    // 計算當前頁數的起始索引和結束索引
    const startIndex = (currentPage.value - 1) * itemsPerPage;
    const endIndex = startIndex + itemsPerPage;

    // 根據索引範圍提取需要顯示的資料
    const displayedData = ref(tableData.slice(startIndex, endIndex));

    // 點擊事件處理程序
    const changePage = (page) => {
      // 更新當前頁數
      currentPage.value = page;

      // 計算新的索引範圍
      const startIndex = (page - 1) * itemsPerPage;
      const endIndex = startIndex + itemsPerPage;

      // 更新顯示資料
      displayedData.value = tableData.slice(startIndex, endIndex);
    };

    // 使用 onMounted 鉤子來生成分頁按鈕
    onMounted(() => {
      // 不需要額外的邏輯，因為在模板中使用了 v-for 指令來顯示分頁按鈕
    });

    return {
      pagination,
      currentPage,
      displayedData,
      changePage,
    };
  },
};
</script>
