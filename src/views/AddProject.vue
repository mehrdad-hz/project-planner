<template>
  <form @submit.prevent="handleSubmit">
    <label>Title:</label>
    <input type="text" v-model="title" required />
    <label>Details:</label>
    <textarea v-model="details" required></textarea>
    <button>Add Project</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      title: "",
      details: "",
    };
  },
  methods: {
    handleSubmit() {
      let project = {
        title: this.title,
        details: this.details,
        complete: false,
      };
      fetch("http://localhost:3000/projects", {
        method: "POST",
        headers: { "Content-type": "application/json" },
        body: JSON.stringify(project),
      })
        .then(() => {
          this.$router.push("/");
        })
        .catch((err) => console.log(err));
    },
  },
};
</script>

<style>
form {
  background: #112240;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 10px 30px -15px rgba(2, 12, 27, 0.7);
}
label {
  display: block;
  color: #bbb;
  text-transform: uppercase;
  font-size: 14px;
  font-weight: bold;
  letter-spacing: 1px;
  margin: 20px 0 10px 0;
}
input {
  padding: 10px;
  border: 0;
  border-radius: 5px;
  width: 100%;
  outline: none;
  box-sizing: border-box;
  background: #40475e;
  color: #fff;
}
textarea {
  border: none;
  border-radius: 5px;
  padding: 10px;
  width: 100%;
  outline: none;
  box-sizing: border-box;
  height: 100px;
  background: #40475e;
  color: #eee;
}
form button {
  display: block;
  margin: 20px auto 0;
  background: #64ffda;
  color: #333;
  font-weight: 600;
  padding: 10px 15px;
  border: 0;
  border-radius: 6px;
  font-size: 16px;
}
</style>
