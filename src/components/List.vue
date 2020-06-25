<template>
  <div>
    <ul class="list">
      <li class="list-item" v-for="(item, index) in list_items" :key="item">
        <span class="check">
          <input v-on:change="changed(index)" type="checkbox" /> </span
        >{{ item }}
      </li>

      <input type="text" v-model="entered" class="newitem" />
      <button v-on:click="addItem" class="btn">Add New To-do</button>
      <button v-on:click="deleteAll" class="btn">Clear List</button>
    </ul>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      entered: "",
      list_items: ["Hello", "World"]
    };
  },

  methods: {
    addItem: function() {
      this.list_items.push(this.entered);
      this.entered = "";
    },

    changed: function(index) {
      this.list_items = this.list_items.filter(
        item => item !== this.list_items[index]
      );
      console.log(this.list_items);
    },

    deleteAll: function() {
      this.list_items = [];
    }
  }
};
</script>

<style scoped>
.list {
  width: 50%;
  margin-top: 1rem;
  padding: 1rem;
  display: grid;
  align-items: left;
}

.list-item {
  list-style-type: none;
  padding: 0.2rem;
}

.newitem {
  margin-top: 3rem;
  margin-bottom: 0.2rem;
  padding: 0.5rem;
  font-size: 1rem;
}

.btn {
  display: inline-block;
  background: lightblue;
  color: #ccc 1px solid;
  padding: 0.4rem 1.3rem;
  border: none;
  cursor: pointer;
  font-size: 1rem;
  margin-right: 0.5rem;
  outline: none;
  margin: 0.5rem;
}

.check {
  padding: 1rem;
}
</style>
