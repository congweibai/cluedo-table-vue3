<template>
  <div>
    <div class="table-container">
      <table style="text-align: left">
        <tr>
          <th>Who?</th>
          <th></th>
          <th></th>
        </tr>
        <tr v-for="(item, index) in whoList" :key="index">
          <td
            :class="{ 'is-confirm': item.isConfirm }"
            @click="whoList[index].isConfirm = !whoList[index].isConfirm"
          >
            {{ item.name }}
          </td>
          <td @click="whoList[index].status = (whoList[index].status + 1) % 3">
            <span v-if="item.status === 0"> [ ] </span>
            <span v-if="item.status === 1"> [?] </span>
            <span v-if="item.status === 2"> [X] </span>
          </td>
        </tr>
      </table>
      <table style="text-align: left">
        <tr>
          <th>What?</th>
          <th></th>
          <th></th>
        </tr>
        <tr v-for="(item, index) in whatList" :key="index">
          <td
            :class="{ 'is-confirm': item.isConfirm }"
            @click="whatList[index].isConfirm = !whatList[index].isConfirm"
          >
            {{ item.name }}
          </td>
          <td
            @click="whatList[index].status = (whatList[index].status + 1) % 3"
          >
            <span v-if="item.status === 0"> [ ] </span>
            <span v-if="item.status === 1"> [?] </span>
            <span v-if="item.status === 2"> [X] </span>
          </td>
        </tr>
      </table>
      <table style="text-align: left">
        <tr>
          <th>Where?</th>
          <th></th>
          <th></th>
        </tr>
        <tr v-for="(item, index) in whereList" :key="index">
          <td
            :class="{ 'is-confirm': item.isConfirm }"
            @click="whereList[index].isConfirm = !whereList[index].isConfirm"
          >
            {{ item.name }}
          </td>
          <td
            @click="whereList[index].status = (whereList[index].status + 1) % 3"
          >
            <span v-if="item.status === 0"> [ ] </span>
            <span v-if="item.status === 1"> [?] </span>
            <span v-if="item.status === 2"> [X] </span>
          </td>
        </tr>
      </table>
    </div>
    <button @click="resetTable">RESET</button>
  </div>
</template>

<script>
export default {
  name: "CluedoTable",
  data() {
    return {
      whoList: [],
      whatList: [],
      whereList: [],
    };
  },
  methods: {
    resetTable() {
      this.whoList = [
        { name: "Green", status: 0, isConfirm: false },
        { name: "Mustard", status: 0, isConfirm: false },
        { name: "Orchid", status: 0, isConfirm: false },
        { name: "Peacock", status: 0, isConfirm: false },
        { name: "Plum", status: 0, isConfirm: false },
        { name: "Scarlett", status: 0, isConfirm: false },
      ];
      this.whatList = [
        { name: "Candllestick", status: 0, isConfirm: false },
        { name: "Dagger", status: 0, isConfirm: false },
        { name: "Lead Pipe", status: 0, isConfirm: false },
        { name: "Revolver", status: 0, isConfirm: false },
        { name: "Rope", status: 0, isConfirm: false },
        { name: "Wrench", status: 0, isConfirm: false },
      ];
      this.whereList = [
        { name: "Ballroom", status: 0, isConfirm: false },
        { name: "Billiard Room", status: 0, isConfirm: false },
        { name: "Conservatory", status: 0, isConfirm: false },
        { name: "Dining Room", status: 0, isConfirm: false },
        { name: "Hall", status: 0, isConfirm: false },
        { name: "Kitchen", status: 0, isConfirm: false },
        { name: "Library", status: 0, isConfirm: false },
        { name: "Lounge", status: 0, isConfirm: false },
        { name: "Study", status: 0, isConfirm: false },
      ];
    },
  },
  mounted() {
    this.resetTable();
    console.log("hello");
  },
};
</script>

<style>
.table-container {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
}
.is-confirm {
  border: 1px solid red;
  border-radius: 5px;
}
</style>
