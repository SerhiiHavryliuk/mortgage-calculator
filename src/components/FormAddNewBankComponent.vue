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
