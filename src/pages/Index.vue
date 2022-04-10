<template>
  <q-page class="q-mx-md">
    <h4 class="bank-title"> Banks </h4>
    <p> Web application where users can create banks and calculate mortgage
      payments using one of these bank’s settings.
    </p>
    <div class="btn-add-new-bank">
      <q-btn class="q-mb-md" color="primary" icon="add_circle" label="add new bank"></q-btn>
    </div>

    <template>
      <div class="">
        <q-table
          title="Bank name"
          :data="data"
          :columns="columns"
          row-key="name"></q-table>
      </div>
    </template>
<!--    <img-->
<!--      alt="Quasar logo"-->
<!--      src="~assets/quasar-logo-vertical.svg"-->
<!--      style="width: 200px; height: 200px"-->
<!--    >-->
  </q-page>
</template>

<!--<script>-->
<!--export default {-->
<!--  name: 'PageIndex'-->
<!--}-->
<!--</script>-->

<script>
  import PageIndex from "./Calc";
  export default {
    components: {PageIndex},
    data () {
      return {
        columns: [
          {
            name: 'name',
            required: true,
            label: 'Dessert (100g serving)',
            align: 'left',
            field: row => row.name,
            format: val => `${val}`,
            sortable: true
          },
          { name: 'Interest rate', align: 'center', label: 'Interest rate', field: 'calories', sortable: true },
          { name: 'Maximum loan', align: 'center', label: 'Maximum loan', field: 'fat', sortable: true },
          { name: 'Minimum down', align: 'center', label: 'Minimum down', field: 'carbs' },
          { name: 'Loan term', align: 'center', label: 'Loan term', field: 'protein' },
          // { name: 'sodium', label: 'Sodium (mg)', field: 'sodium' },
          // { name: 'calcium', label: 'Calcium (%)', field: 'calcium', sortable: true, sort: (a, b) => parseInt(a, 10) - parseInt(b, 10) },
          // { name: 'iron', label: 'Iron (%)', field: 'iron', sortable: true, sort: (a, b) => parseInt(a, 10) - parseInt(b, 10) }
        ],
        data: [
          {
            name: 'Frozen Yogurt Bank',
            calories: 159,
            fat: 6.0,
            carbs: 24,
            protein: 4.0,
          },
          {
            name: 'Ice cream sandwich Bank',
            calories: 237,
            fat: 9.0,
            carbs: 37,
            protein: 4.3,
          },
          {
            name: 'Eclair Bank',
            calories: 262,
            fat: 16.0,
            carbs: 23,
            protein: 6.0
          },
          {
            name: 'Cupcake Bank',
            calories: 305,
            fat: 3.7,
            carbs: 67,
            protein: 4.3
          },
          {
            name: 'Gingerbread Bank',
            calories: 356,
            fat: 16.0,
            carbs: 49,
            protein: 3.9
          },
          {
            name: 'Jelly bean Bank',
            calories: 375,
            fat: 0.0,
            carbs: 94,
            protein: 0.0
          },
          {
            name: 'Lollipop Bank',
            calories: 392,
            fat: 0.2,
            carbs: 98,
            protein: 0
          },
          {
            name: 'Honeycomb Bank',
            calories: 408,
            fat: 3.2,
            carbs: 87,
            protein: 6.5
          },
          {
            name: 'Donut Bank',
            calories: 452,
            fat: 25.0,
            carbs: 51,
            protein: 4.9
          },
          {
            name: 'KitKat',
            calories: 518,
            fat: 26.0,
            carbs: 65,
            protein: 7,
            sodium: 54,
            calcium: '12%',
            iron: '6%'
          }
        ]
      }
    }
  }
</script>

<style lang="scss"  scoped>
  .btn-add-new-bank{
    display: flex;
    justify-content: right;
  }
  .bank-title{
    margin-bottom: 15px;
  }
</style>


