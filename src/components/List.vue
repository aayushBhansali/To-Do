<template>
  <div class="container">
    <ul class="list">
      <li class="list-item" v-for="(item, index) in list_items" :key="item">
        <span class="check">
          <input v-on:change="changed(index)" type="checkbox" />
        </span>
        {{ item }}
      </li>
    </ul>
    <input type="text" v-model="entered" class="newitem" />
    <input v-on:click="addItem" class="btn-primary" type="submit" value="Add new item" />

    <input v-on:click="deleteAll" class="btn-danger" type="submit" value="Clear List" />
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
      if (this.entered !== "") {
        this.list_items.push(this.entered);
        this.entered = "";
      } else {
        alert("List item cannot be empty");
      }
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
.container {
  background: rgba(0, 0, 0, 0.2);
  width: 40%;
  align-content: center;
  display: grid;
  grid-template-columns: 2fr;
  padding: 1rem;
  border-radius: 10px;
}

.list {
  text-align: left;
  width: 50%;
  margin-top: 1rem;
  padding: 1rem;
  margin-left: auto;
  margin-right: auto;
  align-content: center;
  display: grid;
  grid-template-columns: 2fr;
}

.list-item {
  list-style-type: none;
  padding: 0.2rem;
  font-size: 1.5rem;
  align-content: center;
}

.newitem {
  align-content: center;
  margin-top: 3rem;
  margin-bottom: 0.2rem;
  padding: 0.5rem;
  font-size: 1rem;
  width: 30%;
  margin-left: auto;
  margin-right: auto;
}

.btn-primary {
  width: 30%;
  background: rgb(40, 167, 69, 0.6);
  color: #fff;
  padding: 0.4rem 1.3rem;
  border: none;
  cursor: pointer;
  font-size: 1.3rem;
  margin-right: 0.5rem;
  outline: none;
  margin: 0.5rem;
  text-align: center;
  margin-left: auto;
  margin-right: auto;
}

.btn-danger {
  background: rgba(220, 53, 69, 0.6);
  color: #fff;
  padding: 0.4rem 1.3rem;
  border: none;
  cursor: pointer;
  font-size: 1.3rem;
  outline: none;
  margin: 0.5rem;
  text-align: center;
  width: 30%;
  margin-left: auto;
  margin-right: auto;
}

.check {
  padding: 1rem;
}
</style>
