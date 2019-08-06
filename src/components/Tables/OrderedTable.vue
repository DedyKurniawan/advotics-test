<template>
  <div>
    <md-table v-model="users" :table-header-color="tableHeaderColor">
      <md-table-row slot="md-table-row" slot-scope="{ item }">
        <md-table-cell md-label="ID">{{ item.id }}</md-table-cell>
        <md-table-cell md-label="Name Product">{{ item.name }}</md-table-cell>
        <md-table-cell md-label="Harga">{{ item.salary }}</md-table-cell>
        <md-table-cell md-label="Jumlah Terjual">{{ item.jml }}</md-table-cell>
     
      </md-table-row>
    </md-table>
  </div>
</template>

<script>
export default {
  name: "ordered-table",
  props: {
    tableHeaderColor: {
      type: String,
      default: ""
    }
  },
  data() {
    return {
      selected: [],
      users: [
        {
          id: 1,
          name: "Macbook Pro MPXQ2",
          salary: "Rp.17.450.000",
          jml: "132"
        },
        {
          id: 2,
          name: "Lenovo IdeaPad 130-14AST",
          salary: "Rp.3.799.000",
          jml: "232"
        },
        {
          id: 3,
          name: "Lenovo HDMI to VGA adapter",
          salary: "Rp.350.000",
          jml: "33"
        },
        {
          id: 4,
          name: "Apple Macbook Air 13 MQD32",
          salary: "Rp.13.049.000",
          jml: "201"
        },
          {
          id: 5,
          name: "Asus VivoBook Ultra A412DA",
          salary: "Rp.6.499.000",
          jml: "154"
        },
          {
          id: 6,
          name: "Asus ROG GL503GE HERO i7 8750H -16Gb",
          salary: "Rp.17.990.000",
          jml: "201"
        },
          {
          id: 7,
          name: "Dell Wireless Mouse WM-126",
          salary: "Rp.185.000",
          jml: "421"
        },
          {
          id: 8,
          name: "Alienware Advanced Gaming Mouse - AW 558",
          salary: "Rp.699.000",
          jml: "46"
        },
          {
          id: 9,
          name: "Lenovo Server ThinkSystem SR 530",
          salary: "Rp.73.488.600",
          jml: "83"
        }

      ]
    };
  }
};
</script>
