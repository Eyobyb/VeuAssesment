<template>
  <div id="app">
    <div class="main-container">
      <div class="sub-container">
        <div class="title">Products</div>
        <div class="main-box">
          <custom-filter :actionname="'Search'" :actiontype="'main'" placeholder="Find a Product" />
          <custom-filter
            :actionname="'Add Product'"
            :actiontype="'secondary'"
            placeholder="Product Name"
          />
          <drop-down-wrapper />
          <user-data-holder
            v-for="(userData, index ) of products"
            :key="userData.name + index"
            :userData="userData"
          />
        </div>

        <!-- <pagination @change="change" :limit="limit" :page="page" /> -->
       <div class="paggination-holder">
        <pagination-controller />
       </div>
      </div>
    </div>
  </div>
</template>

<script>
import CustomFilter from "./components/CustomFilter.vue";
import DropDownWrapper from "./components/DropDownWrapper.vue";
import PaginationController from "./components/Pagination-controller.vue";

import UserDataHolder from "./components/UserDataHolder.vue";
export default {
  name: "App",
  components: {
    CustomFilter,
    UserDataHolder,
    DropDownWrapper,
    PaginationController
  },
  data() {
    return {
      limit: 10,
      page: 1,
      filteredData: [],
      products: [
        {
          name: "Americano",
          image: "https://picsum.photos/48",
          status: "green",
          date: null
        },
        {
          name: "Espresso",
          image: "https://picsum.photos/48",
          status: "yellow",
          date: null
        },
        {
          name: "Mocha",
          image: "",
          status: "green",
          date: null
        },
        {
          name: "White Mocha",
          image: "",
          status: "yellow",
          date: 704305433
        },
        {
          name: "Latte",
          image: "https://picsum.photos/48",
          status: "green",
          date: 1666715033
        },
        {
          name: "Cappucino",
          image: "https://picsum.photos/48",
          status: "green",
          date: null
        },
        {
          name: "Walking with Giants",
          image: "https://picsum.photos/48",
          status: "green",
          date: null
        },
        {
          name: "Turbinator 2",
          image: "https://picsum.photos/48",
          status: "red",
          date: null
        },
        {
          name: "Super Cali Fragilistic Expialidocious",
          image: "",
          status: "red",
          date: 704305433
        },
        {
          name: "Baseball Hat",
          image: "https://picsum.photos/48",
          status: "green",
          date: null
        },
        {
          name: "Americano",
          image: "https://picsum.photos/48",
          status: "green",
          date: null
        },
        {
          name: "Espresso",
          image: "https://picsum.photos/48",
          status: "yellow",
          date: null
        },
        {
          name: "Mocha",
          image: "",
          status: "green",
          date: null
        },
        {
          name: "White Mocha",
          image: "",
          status: "yellow",
          date: 704305433
        },
        {
          name: "Latte",
          image: "https://picsum.photos/48",
          status: "green",
          date: 1666715033
        },
        {
          name: "Cappucino",
          image: "https://picsum.photos/48",
          status: "green",
          date: null
        },
        {
          name: "Walking with Giants",
          image: "https://picsum.photos/48",
          status: "green",
          date: null
        },
        {
          name: "Turbinator 2",
          image: "https://picsum.photos/48",
          status: "red",
          date: null
        },
        {
          name: "Super Cali Fragilistic Expialidocious",
          image: "",
          status: "red",
          date: 704305433
        },
        {
          name: "Baseball Hat",
          image: "https://picsum.photos/48",
          status: "green",
          date: null
        }
      ]
    };
  }
};
</script>

<style>
body {
  overflow: hidden;
  padding: 0;
  background: #ececec;
  padding-left: 16px;
  padding-right: 16px;
  margin: 0;
}
.main-container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 100vh;
  width: 100%;
  margin-bottom: 96px;
  overflow: scroll;
}

.sub-container {
  max-width: 1200px;
  width: 100%;
  height: 100vh;
}
.main-box {
  background: white;
  border: 1px solid #e0e2e4;
  border-radius: 8px;
  padding: 16px;
  display: flex;
  flex-direction: column;
  gap: 8px;
}

.data-container {
  display: flex;
  flex-direction: column;
  gap: 8px;
}
.title {
  margin: 16px;
  font-family: "Bitter";
  font-style: normal;
  font-weight: 500;
  font-size: 24px;
  line-height: 32px;
}
* {
  font-family: "Inter";
  font-style: normal;
  font-weight: 400;
  font-size: 14px;
  color: #252526;
}
.line {
  border-top: solid 1px #f0f2f4;
  width: 100%;
}
.highlight {
  font-family: "Inter";
  font-style: normal;
  font-weight: 700;
  font-size: 12px;
  line-height: 15px;
  color: #252526;
}
.paggination-holder{
  display: flex;
  justify-content: center;
}
@import url("https://fonts.googleapis.com/css2?family=Inter:wght@400;700&display=swap");
</style>
