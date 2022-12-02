<template>
  <div class="home">
    <section class="introduction">
        <div class="container">

            <div class="slider">
                <div class="slides">
                    <input type="radio" name="radio_button" id="radio1">
                    <input type="radio" name="radio_button" id="radio2">
                    <input type="radio" name="radio_button" id="radio3">

                    <div class="slideshow first">
                        <img src="@/assets/pOrsche-Taycan-production-hero.jpeg" alt="Bild1" style="width: 100%;">
                    </div>

                    <div class="slideshow">
                        <img src="@/assets/BMW-M2-production1-1342919936.jpeg" alt="Bild2" style="width: 100%;">
                    </div>
                    
                    <div class="slideshow">
                        <img src="@/assets/Audi_Werk.jpeg" alt="Bild3" style="width: 100%;">
                    </div>

                    <div class="navigation_auto">
                        <div class="auto_btn1"></div>
                        <div class="auto_btn2"></div>
                        <div class="auto_btn3"></div>
                    </div>
                </div>
                <div class="navigation_manual">
                    <label for="radio1" class="manual_button"></label>
                    <label for="radio2" class="manual_button"></label>
                    <label for="radio3" class="manual_button"></label>
                </div>
            </div>

            <div class="home_text">
                <p>
                    Deutschland ist das Land der Autos und die Heimat der Automobilindustrie. Das macht sich darin bemerkbar, dass
                    oftmals die deutschen Hersteller in den Sinn kommen wenn man über Fahrzeuge zu sprechen kommt. 
                    Entsprechend sind auch einige Marken weltweit bekannt und dominant. BMW wird für seine Sportlichkeit geliebt,
                    Mercedes für seinen Luxus und hohe Qualität und Volkswagen ist als das deutsche Auto schlechthin bekannt.
                </p>
            </div>

            <div class="home_history_text" style="padding-top: 20px">
                <h2>Geschichte</h2>
                <p>
                    Die Entwicklung der deutschen Automobilindustrie kann auf 1886 zurückgelegt werden.
                    In diesem Jahr patentierten zwei deutsche Ingenieure gleichzeitig und völlig unabhängig voneinander 
                    das Auto mit einem Benzin-Verbrennunsmotor. Die Ingenieure waren Karl Benz und Gottlieb Daimler. 
                    Beide gründeten ihre eigenen Unternehmen welche 1926 zu Mercedes-Benz zusammengeschlossen wurden.
                    Doch das war erst der Anfang, denn die deutsche Automobilindustrie entwickelte sich sehr schnell.
                    Fast zeitgleich erschienen mehrere Firmen, deren Namen noch heute hörbar sind.
                    Diese bilden immernoch die Spitze der besten Automobilhersteller der Welt. Deutschen Marken wird zugerufen,
                    dass diese zuverlässig, hochwertig, qualitativ und komfortabel sein sollen.
                </p>
            </div>
        </div>
    </section>
  </div>
</template>

<script>
/*Slideshow*/

// @ is an alias to /src
export default {
    name: "MyHome",
    components: {},
    methods: {
    },
    data: () => {
    }
}
</script>

<style lang="scss" scoped>
.introduction {
    padding-top: 25px;
    display: flex;
    align-items: center;
    
    p, h2 {
        text-align: center;
    }
}

.slider {
    width: 800px;
    height: 500px;
    border-radius: 10px;
    overflow: hidden;
    margin: auto;

    .slides {
        display: flex;
        width: 500%;
        height: 500px;

        input {
            display: none;
        }

        .slideshow {
            width: 20%;
            transition: 2s;
        }

        .slideshow img {
            width: 100px;
            height: auto;
        }

        #radio1:checked ~ .first
        {
            margin-left: 0;
        }

        #radio2:checked ~ .first
        {
            margin-left: -20%;
        }

        #radio3:checked ~ .first
        {
            margin-left: -40%;
        }

        .navigation_auto {
            position: absolute;
            display: flex;
            width: 800px;
            justify-content: center;
            margin-top: 460px;
        }

        .navigation_auto div {
            border: 2px solid #1e2022;
            padding: 5px;
            border-radius: 10px;
            transition: 1s;
        }

        .navigation_auto div:not(:last-child)
        {
            margin-right: 40px;
        }

        #radio1:checked ~ .navigation_auto .auto_btn1
        {
            background-color: #1e2022;
        }

        #radio2:checked ~ .navigation_auto .auto_btn2
        {
            background-color: #1e2022;
        }

        #radio3:checked ~ .navigation_auto .auto_btn3
        {
            background-color: #1e2022;
        }
    }

    .navigation_manual {
        position: absolute;
        width: 800px;
        margin-top: -40px;
        display: flex;
        justify-content: center;

        .manual_button {
            border: 2px solid #1e2022;
            padding: 5px;
            border-radius: 10px;
            cursor: pointer;
            transition: 1s;
        }

        .manual_button:not(:last-child) {
            margin-right: 40px;
        }

        .manual_button:hover {
            background-color: #1e2022;
        }
    }
}
</style>
