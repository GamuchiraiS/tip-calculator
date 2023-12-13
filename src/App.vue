<script setup>
//Imports
import ButtonWithNumber from './components/ButtonWithNumber.vue'
import InputFieldLabel from './components/InputFieldLabel.vue'
import ResultsTile from './components/ResultsTile.vue'
import ButtonWithText from './components/ButtonWithText.vue'
import {ref} from 'vue'

//Variables
const initialBillAmount = ref('')
const initialTipPercentage = ref('')
const initialNumberOfPeople = ref('')
const initialTipAmountPerPerson = ref('')
const initialTotalPerPerson = ref('')

//Functions
function getBillAmount(event) {
  const billAmount = event.target.value
}

function getCustomTipPercentage(event) {
  const customTipPercentage = event.target.value
}

function getNumberOfPeople(event) {
  const numberOfPeople = event.target.value
}

function getTipAmountPerPerson(){
  const tipPercentage = initialTipPercentage.value
  const numberOfPeople = initialNumberOfPeople.value
  const billTotal = initialBillAmount.value

  let tipAmountPerPerson = null
  tipAmountPerPerson = (billTotal * (tipPercentage/100)) / numberOfPeople
  initialTipAmountPerPerson.value = parseInt(tipAmountPerPerson)

}

function getTotalAmountPerPerson(){
  const billAmount = initialBillAmount.value
}
</script>

<template>

  <main>

    <div class="calculations">

      <div class="bill">
        <InputFieldLabel text="Bill"/>
        <input
            name="bill"
            v-model="initialBillAmount"
            type="number"
            placeholder="0"
            @change="getBillAmount"
        />
      </div>

      <div class="tip">
        <p>Select tip %</p>
        <div class="buttons">
          <ButtonWithNumber number="5"/>
          <ButtonWithNumber number="10"/>
          <ButtonWithNumber number="15"/>
          <ButtonWithNumber number="25"/>
          <ButtonWithNumber number="50"/>
          <input
              name="custom"
              v-model="initialTipPercentage"
              type="number"
              placeholder="Custom"
              @change="getCustomTipPercentage"
          />
        </div>
      </div>

      <div class="people">
        <InputFieldLabel text="Number of people"/>
        <input
            name="people"
            v-model="initialNumberOfPeople"
            type="number"
            placeholder="0"
            @change="getNumberOfPeople"
        />
      </div>
    </div>

    <div class="results">
      <ResultsTile
          heading="Tip amount"
          subtext="/ person"
          :number="initialTipAmountPerPerson"
      />
      <ResultsTile
          heading="Total"
          subtext="/ person"
          :number="initialTotalPerPerson"
      />

      <ButtonWithText
          text="Reset"
          @click="getTipAmountPerPerson"
      />
    </div>

  </main>
</template>

<style scoped>
  main{
    display: grid;
    grid-template-columns: 50% 50%; /*TODO: Change to use fr*/
    grid-column-gap: 1.8rem;
    justify-content: center;
    background-color: hsl(0, 0%, 100%);
    //max-width: 50vw;
    padding: 1.5em 2.5em;
    border-radius: 15px;
  }

  .results{
    background-color: hsl(183, 100%, 15%);
    border-radius: 10px;
  }
</style>
