<template>
  <q-card-section>
    <template>
      <div class="q-pa-md" style="max-width: 600px; min-width: 260px">

        <q-input class="q-mb-md" outlined v-model="bankName" label="Bank name"></q-input>
        <q-input class="q-mb-md" outlined v-model="interestRate" label="Interest rate" type="number"></q-input>
        <q-input class="q-mb-md" outlined v-model="maximumLoan" label="Maximum loan" type="number"></q-input>
        <q-input class="q-mb-md" outlined v-model="minimumDownPayment" label="Minimum down payment" type="number"></q-input>
        <q-input class="q-mb-md" outlined v-model="loanTerm" label="Loan term" type="number"></q-input>

        <div class="dialog-btn-add-new-bank">
          <q-btn color="primary" label="Add" @click="addNewBank()"></q-btn>
        </div>


      </div>
    </template>
  </q-card-section>
</template>


<script>
  export default {
    name: "Componennt form add new bank",
    data () {
      return {
        bankName: '',
        interestRate: '',
        maximumLoan: '',
        minimumDownPayment: '',
        loanTerm: '',
        columns: [
          {
            Bank_name: 'name',
            required: true,
            label: 'Bank Name',
            align: 'left',
            field: row => row.Bank_name,
            format: val => `${val}`,
            sortable: true
          },
          { name: 'Interest rate', align: 'center', label: 'Interest rate', field: 'Interest_rate', sortable: true },
          { name: 'Maximum loan', align: 'center', label: 'Maximum loan', field: 'Maximum_loan', sortable: true },
          { name: 'Minimum down', align: 'center', label: 'Minimum down', field: 'Minimum_down' },
          { name: 'Loan term', align: 'center', label: 'Loan term', field: 'Loan_term' },
          // { name: 'sodium', label: 'Sodium (mg)', field: 'sodium' },
          // { name: 'calcium', label: 'Calcium (%)', field: 'calcium', sortable: true, sort: (a, b) => parseInt(a, 10) - parseInt(b, 10) },
          // { name: 'iron', label: 'Iron (%)', field: 'iron', sortable: true, sort: (a, b) => parseInt(a, 10) - parseInt(b, 10) }
        ],
        data: [
          {
            Bank_name: 'Frozen Yogurt Bank',
            Interest_rate: 159,
            Maximum_loan: 6.0,
            Minimum_down: 24,
            Loan_term: 4.0,
          },
          {
            Bank_name: 'Ice cream sandwich Bank',
            Interest_rate: 237,
            Maximum_loan: 9.0,
            Minimum_down: 37,
            Loan_term: 4.3,
          },
          {
            Bank_name: 'Eclair Bank',
            Interest_rate: 262,
            Maximum_loan: 16.0,
            Minimum_down: 23,
            Loan_term: 6.0
          },
          {
            Bank_name: 'Cupcake Bank',
            Interest_rate: 305,
            Maximum_loan: 3.7,
            Minimum_down: 67,
            Loan_term: 4.3
          },
          {
            Bank_name: 'Gingerbread Bank',
            Interest_rate: 356,
            Maximum_loan: 16.0,
            Minimum_down: 49,
            Loan_term: 3.9
          },
          {
            Bank_name: 'Jelly bean Bank',
            Interest_rate: 375,
            Maximum_loan: 0.0,
            Minimum_down: 94,
            Loan_term: 0.0
          },
          {
            Bank_name: 'Lollipop Bank',
            Interest_rate: 392,
            Maximum_loan: 0.2,
            Minimum_down: 98,
            Loan_term: 0
          },
          {
            Bank_name: 'Honeycomb Bank',
            Interest_rate: 408,
            Maximum_loan: 3.2,
            Minimum_down: 87,
            Loan_term: 6.5
          },
          {
            Bank_name: 'Donut Bank',
            Interest_rate: 452,
            Maximum_loan: 25.0,
            Minimum_down: 51,
            Loan_term: 4.9
          },
          {
            Bank_name: 'KitKat',
            Interest_rate: 518,
            Maximum_loan: 26.0,
            Minimum_down: 65,
            Loan_term: 7,
            sodium: 54,
            calcium: '12%',
            iron: '6%'
          }
        ],
      }
    },
    methods: {
      addNewBank(){
        this.modalDialogAddNewBank = true;
      }
    }
  }
</script>


<style lang="scss"  scoped>
  .dialog-btn-add-new-bank{
    display: flex;
    justify-content: right;
  }

</style>
