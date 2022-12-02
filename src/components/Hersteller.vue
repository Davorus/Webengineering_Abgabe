<template>
    <div v-if="(this.manufacturer === -1)" class="Hersteller">
        <ul>
            <li @click="clicked('Audi')">Audi</li>
            <li @click="clicked('BMW')">BMW</li>
            <li @click="clicked('Mercedes-Amg')">Mercedes-AMG</li>
            <li @click="clicked('Mercedes-Benz')">Mercedes-Benz</li>
            <li @click="clicked('Mercedes-Maybach')">Mercedes-Maybach</li>
            <li @click="clicked('Opel')">Opel</li>
            <li @click="clicked('Porsche')">Porsche</li>
            <li @click="clicked('Smart')">Smart</li>
            <li @click="clicked('Volkswagen')">Volkswagen</li>
            <li @click="clicked('Wiesmann')">Wiesmann</li>
        </ul>
    </div>

    <div class="Audi Manufacturer">
    
    </div>

    <div class="BMW Manufacturer">

    </div>

    <div class="Mercedes-Amg Manufacturer">

    </div>

    <div class="Mercedes-Benz Manufacturer">

    </div>

    <div class="Mercedes-Maybach Manufacturer">
    
    </div>

    <div class="Opel Manufacturer">

    </div>

    <div class="Porsche Manufacturer">
    
    </div>
    
    <div class="Smart Manufacturer">
    
    </div>

    <div class="Volkswagen Manufacturer">
    
    </div>

    <div class="Wiesmann Manufacturer">
    
    </div>

</template>
  
<script>
 export default {
    name: "DieHersteller",
    data() {
        return {
            manufacturer: -1
        }
    },
    methods: {
        clicked(value) {
            if(value === 'Audi') {
                this.manufacturer = 0;
            } else if (value === 'BMW') {
                this.manufacturer = 1;
            } else if (value === 'Mercedes-Amg') {
                this.manufacturer = 2;
            } else if (value === 'Mercedes-Benz') {
                this.manufacturer = 3;
            } else if (value === 'Mercedes-Maybach') {
                this.manufacturer = 4;
            } else if (value === 'Opel') {
                this.manufacturer = 5;
            } else if (value === 'Porsche') {
                this.manufacturer = 6;
            } else if (value === 'Smart') {
                this.manufacturer = 7;
            } else if (value === 'Volkswagen') {
                this.manufacturer = 8;
            } else if (value === 'Wiesmann') {
                this.manufacturer = 9;
            }
        },
    }
 }
</script>
  
<style lang="scss">

    .Hersteller {
        padding-top: 2.3em;
        display: flex;
        align-content: center;
        justify-content: center;
        margin: auto;
        font-size: 2em;

        ul,
        li {
            text-align: center;
            padding: 15px;
            color: #F0F5F9;
            list-style: none;
            border-radius: 10px;
            background-color: #1E2022;
        }

        li:hover {
            cursor: pointer;
            transition: 0.5s;
            color: #B2F9FC;
        }
    }

</style>  