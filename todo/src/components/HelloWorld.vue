<template>
  <div class="w3-container">
    <input type="text" v-bind:placeholder="vmessage" id="inputvalue" v-model="ipvalue" />
    <button v-on:click="value" v-bind:title="ipvalue">Add</button>
    <button v-on:click="deltelast">Delete Last</button>
    <button v-on:click="deltefirst">Delete Fast</button>
    <button v-on:click="DeleteString">Delete</button>

    <ul class="w3-ul w3-card-4">
      <li class="w3-bar" v-for:="list in lists">
        <span
          onclick="this.parentElement.style.display='none'"
          class="w3-bar-item w3-button w3-xlarge w3-right"
          >&times;</span
        >
        <img
          src="https://www.w3schools.com/w3css/img_avatar2.png"
          class="w3-bar-item w3-circle"
          style="width: 85px"
        />
        <div class="w3-bar-item">
          <span class="w3-large">{{ list }}</span
          ><br />
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  // props: {
  //   msg: String
  // }
  data() {
    return {
      ipvalue: "",
      lists: [],
      vmessage: ""
    };
  },
  methods: {
    value() {
      if (!this.ipvalue=="") {
         this.lists.push(this.ipvalue);
      this.ipvalue = "";
      } this.vmessage="Enter Something Here to add"
     
    },
    deltelast() {
      this.lists.pop();
    },
    deltefirst() {
      this.lists.shift();
    },

    DeleteString() {
      for (let index = 0; index < this.lists.length; index++) {
        if (this.lists[index] == this.ipvalue) {
          this.lists.splice(index, 1);
        }
      }
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
