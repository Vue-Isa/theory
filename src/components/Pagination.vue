<template>
  <div class="page__wrapper">
    <div
      class="page"
      v-for="pageNumber in totalPages"
      :key="pageNumber"
      :class="{
        'current-page': page === pageNumber,
      }"
      @click="changePage(pageNumber)"
    >
      {{ pageNumber }}
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      pageNumber: 0,
    };
  },
  props: {
    page: {
      type: Number,
      required: true,
    },
    limit: {
      type: Number,
      required: true,
    },
    totalPages: {
      type: Number,
      required: true,
    },
  },
  methods: {
    changePage(pageNumber) {
      this.$emit("getPageNumber", pageNumber);
    },
  },
};
</script>

<style>
.page__wrapper {
  display: flex;
  justify-content: center;
  margin-top: 15px;
  gap: 5px;
}
.page {
  border: 1px solid teal;
  padding: 10px;
  transition: 0.4s;
}

.current-page {
  background: teal;
  color: #fff;
  transition: 0.4s;
}
</style>
