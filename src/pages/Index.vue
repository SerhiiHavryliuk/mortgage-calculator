<template>
  <q-page class="q-mx-md">
    <h4 class="bank-title"> Banks </h4>
    <p> Web application where users can create banks and calculate mortgage
      payments using one of these bank’s settings.
    </p>
    <div class="btn-add-new-bank">
      <q-btn class="q-mb-md" color="primary" icon="add_circle" label="add new bank" @click="openModalDialogAddNewBank()"></q-btn>
    </div>

    <!-- ----------------------------------------------------------------------------------------------------------- -->
    <!--    Таблиця банків    -->
    <!-- ----------------------------------------------------------------------------------------------------------- -->
    <template>
      <div class="">
        <q-table
          title="List of banks"
          :data="data"
          :columns="columns"
          row-key="name"></q-table>
      </div>
    </template>

<!--    <h4> sdfdsf </h4>-->
<!--    <p  id="rrr" class="mytest"> gg</p>-->


    <!-- ----------------------------------------------------------------------------------------------------------- -->
    <!--    Модальне вікно для додавання нового банку    -->
    <!-- ----------------------------------------------------------------------------------------------------------- -->
    <q-dialog v-model="modalDialogAddNewBank">
      <q-card class="spike-materials">
        <q-card-section class="row items-center q-pb-none">

          <div class="text-h6">Add new bank</div>
          <q-space></q-space>
<!--          <q-btn icon="close" flat round dense v-close-popup @click="cancelTeacherMode()"></q-btn>-->
        </q-card-section>

        <!-- ------------------------------------------------------------------------------------------------------------------ -->
        <!--  Компонент материалы учителя -->
        <!-- ------------------------------------------------------------------------------------------------------------------ -->
<!--        <form_add_new_Bank></form_add_new_Bank>-->
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
      </q-card>
    </q-dialog>




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
    components: {
      PageIndex,
      // 'form_add_new_Bank': require('src/components/FormAddNewBankComponent.vue').default,
    },
    data () {
      return {
        modalDialogAddNewBank: false, // за замовчанням закриваємо діалогове вікно

        // значення текстових полів у формі
        bankName: '',
        interestRate: '',
        maximumLoan: '',
        minimumDownPayment: '',
        loanTerm: '',
        // значення текстових полів у формі

        dataLocalStorage: '',

        mydata: [
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
        // data: this.dataLocalStorage
      }
    },
    // Метод виконується перед початком завантаження сторінки
    mounted(){
      // https://stackoverflow.com/questions/2010892/how-to-store-objects-in-html5-localstorage
      console.log("--------------------------");
      console.log("mounted   my data =");
      console.log(typeof this.mydata);
      console.log(this.mydata);

      let testObject = this.mydata;
      // Put the object into storage
      localStorage.setItem('testObject', JSON.stringify(testObject));

      // Retrieve the object from storage
      let dataLocalStorage = localStorage.getItem('testObject');
      this.dataLocalStorage = JSON.parse(dataLocalStorage);

      console.log("--------------------------");
      console.log('dataLocalStorage: ');
      console.log(this.dataLocalStorage);

      console.log(typeof this.dataLocalStorage);

      let test = document.getElementById('rrr');
      let paragraph = document.createElement("p");
      paragraph.appendChild(test);
      paragraph.innerHTML = "this.dataLocalStorage[i]";

      for(let i =0; i<= 5; i++){

        console.log(5555)
      }

    },
    methods: {
      // Метод відкриття модального вікна
      openModalDialogAddNewBank(){
        this.modalDialogAddNewBank = true;

        this.$q.localStorage.set('teacherMode', true)
      },
      // Метод для додавання нового банку
      addNewBank(){
        this.modalDialogAddNewBank = false; // закриваємо модальне вікно
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


