<template>
  <div>
    <h1>{{ header }}</h1>
    <ul class="list-group">
      <!--            Oefening 3.6, click voor listitem afvangen -->
      <li class="list-group-item"

          @click="showCountry(country)"
          v-for="(country) in countryData.countries"
          v-bind:key="country.id">
                <span v-bind:id="country.id"
                      v-bind:title="country.details">

                {{ country.id }} -
                {{country.name}}
                </span>
      </li>
    </ul>
    <hr>
    <h3>Teller: {{ counter }}</h3>
    <!-- Rechtstreeks ophogen -->
    <button v-on:click="counter++" class="btn btn-success">+</button>
    <button v-on:click="counter--" class="btn btn-danger">-</button>
    <!--   Ophogen via methode van de component -->
    <h3>Ophogen via methode op de component:</h3>
    <button @click="increment()" class="btn btn-success">+</button>
    <button @click="decrement()" class="btn btn-danger">-</button>
    <hr>
    <!--        Oefening 3.5-->
    <!--        <h3><label for="list1">Kies een getal</label></h3>-->
    <!--        <select name="list1" id="list1">-->
    <!--            <option v-for="(num, index) in numbers"-->
    <!--                    :value="num"-->
    <!--                    :key="index">{{num}}-->
    <!--            </option>-->
    <!--        </select>-->
  </div>
</template>

<script>
import countryData from '../data/CountryData'

export default {
  name: "VacationPicker",
  data() {
    return {
      countryData,
      header: 'Vue Vacation Picker',
      counter: 0,
      numbers: [10, 20, 30, 40, 50] // oefening 3.6
    }
  }, methods: {
    increment() {
      this.counter++;
    },
    decrement() {
      this.counter--;
    },
    showCountry(country) {
      alert('You selected: ' + country.name);
    }
  }
}
</script>