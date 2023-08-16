<template>
  <nav class="filter-nav">
    <button :class="{ active: current === 'all' }" @click="updateFilter('all')">
      View all
    </button>
    <button
      :class="{ active: current === 'completed' }"
      @click="updateFilter('completed')"
    >
      Completed
    </button>
    <button
      :class="{ active: current === 'ongoing' }"
      @click="updateFilter('ongoing')"
    >
      On going
    </button>
  </nav>
</template>

<script>
export default {
  props: ["current"],
  methods: {
    updateFilter(by) {
      this.$emit("filterChange", by);
    },
  },
};
</script>

<style>
.filter-nav button {
  background: none;
  border: none;
  color: #bbb;
  outline: none;
  font-size: 15px;
  text-transform: uppercase;
  margin-right: 25px;
  letter-spacing: 1px;
  font-weight: bold;
  cursor: pointer;
}
.filter-nav button.active {
  color: #555;
}

@media screen and (max-width: 768px) {
  nav.filter-nav {
    display: flex;
    align-items: center;
    justify-content: space-evenly;
  }
  .filter-nav button {
    margin-right: 0;
  }
}
</style>
