<template>
  <div>
    <md-table v-model="users" :table-header-color="tableHeaderColor">
      <md-table-row slot="md-table-row" slot-scope="{ item }">
        <md-table-cell md-label="Nama Produk">{{ item.name }}</md-table-cell>
        <md-table-cell md-label="Harga">{{ item.salary }}</md-table-cell>
        <md-table-cell md-label="Jumlah Produk">{{ item.jml }}</md-table-cell>
        <md-table-cell md-label="Brands">{{ item.Brands }}</md-table-cell>
        
      </md-table-row>
    </md-table>
  </div>
</template>

<script>
export default {
  name: "simple-table",
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
          name: "Asus VivoBook Ultra A412DA",
          salary: "Rp.6.499.000",
          jml: "154",
          Brands: "ASUS"
        },
        {
          name: "Asus ROG GL503GE HERO i7 8750H -16Gb",
          salary: "Rp.17.990.000",
          jml: "201",
          Brands: "ASUS"
        },
        {
          name: "Lenovo IdeaPad 130-14AST",
          salary: "Rp.3.799.000",
          jml: "232",
          Brands: "LENOVO"
        },
        {
          name: "Lenovo Server ThinkSystem SR 530",
          salary: "Rp.73.488.600",
          jml: "81",
          Brands: "LENOVO"
        },
        {
          name: "Apple Macbook Air 13 MQD32",
          salary: "Rp.13.049.000",
          jml: "201",
          Brands: "APPLE"
        },
        {
          name: "Macbook Pro MPXQ2",
          salary: "Rp.17.450.000",
          jml: "132",
          Brands: "APPLE"
        },
        {
          name: "Dell Wireless Mouse WM-126",
          salary: "Rp.185.000",
          jml: "421",
          Brands: "DELL"
        },
        {
          name: "Alienware Advanced Gaming Mouse - AW 558",
          salary: "Rp.699.000",
          jml: "46",
          Brands: "DELL"
        }
      ]
    };
  }
};
</script>
