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
                    </div>
                    <div class="navigation_manual" style="padding-bottom: 15px;">
                        <label for="radio1" class="manual_button"></label>
                        <label for="radio2" class="manual_button"></label>
                        <label for="radio3" class="manual_button"></label>
                    </div>
                </div>

                <div class="home_text">
                    <p>
                        Deutschland ist das Land der Autos und die Heimat der Automobilindustrie. Das macht sich darin
                        bemerkbar, dass
                        oftmals die deutschen Hersteller in den Sinn kommen wenn man über Fahrzeuge zu sprechen kommt.
                        Entsprechend sind auch einige Marken weltweit bekannt und dominant. BMW wird für seine
                        Sportlichkeit geliebt,
                        Mercedes für seinen Luxus und hohe Qualität und Volkswagen ist als das deutsche Auto schlechthin
                        bekannt.
                    </p>
                </div>

                <div class="home_history_text" style="padding-top: 25px">
                    <h2>Geschichte</h2>
                    <p>
                        Die Entwicklung der deutschen Automobilindustrie kann auf 1886 zurückgelegt werden.
                        In diesem Jahr patentierten zwei deutsche Ingenieure gleichzeitig und völlig unabhängig
                        voneinander
                        das Auto mit einem Benzin-Verbrennunsmotor. Die Ingenieure waren Karl Benz und Gottlieb Daimler.
                        Beide gründeten ihre eigenen Unternehmen welche 1926 zu Mercedes-Benz zusammengeschlossen
                        wurden.
                        Doch das war erst der Anfang, denn die deutsche Automobilindustrie entwickelte sich sehr
                        schnell.
                        Fast zeitgleich erschienen mehrere Firmen, deren Namen noch heute hörbar sind.
                        Diese bilden immernoch die Spitze der besten Automobilhersteller der Welt. Deutschen Marken wird
                        zugerufen,
                        dass diese zuverlässig, hochwertig, qualitativ und komfortabel sein sollen.
                    </p>
                </div>

                <div class="drawACar" style="margin-top: 1.5em; border: 1px solid #000">
                    <b>Male ein Auto</b>
                    <canvas ref="draw"></canvas>
                    <button @click="resetCanvas()">Reset</button>
                </div>

                <div class="spotify-podcast" style="padding-top: 20px" @click="startPainting(MouseDown)">
                    <iframe style="border-radius:12px"
                        src="https://open.spotify.com/embed/episode/5kKJFE5B3qPLYSCxZRX6Gm?utm_source=generator"
                        width="auto" height="352" frameBorder="0" allowfullscreen=""
                        allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture"
                        loading="lazy"></iframe>
                </div>

            </div>
        </section>
    </div>
</template>
  
<script>
// @ is an alias to /src
export default {
    name: "MyHome",
    data: () => {
        return {
            canvas: null,
            context: null,
            isDrawing: false,
            startX: 0,
            startY: 0,
            points: [],
        }
    },
    mounted() {
        var vm = this
        vm.canvas = vm.$refs.draw
        vm.context = vm.canvas.getContext("2d");
        vm.canvas.addEventListener('mousedown', vm.mousedown);
        vm.canvas.addEventListener('mousemove', vm.mousemove);
        document.addEventListener('mouseup', vm.mouseup);
        vm.canvas.addEventListener('touchstart', vm.touchstart);
        vm.canvas.addEventListener('touchemove', vm.touchemove);
        document.addEventListener('touchcancel', vm.touchend);
        vm.canvas.addEventListener('Reset', vm.clearCanvas);
    },
    methods: {
        mousedown(e) {
            var vm = this
            var rect = vm.canvas.getBoundingClientRect();
            var x = e.clientX - rect.left;
            var y = e.clientY - rect.top;

            vm.isDrawing = true;
            vm.startX = x;
            vm.startY = y;
            vm.points.push({
                x: x,
                y: y
            });
        },
        mousemove(e) {
            var vm = this
            var rect = vm.canvas.getBoundingClientRect();
            var x = e.clientX - rect.left;
            var y = e.clientY - rect.top;

            if (vm.isDrawing) {
                vm.context.beginPath();
                vm.context.moveTo(vm.startX, vm.startY);
                vm.context.lineTo(x, y);
                vm.context.lineWidth = 1;
                vm.context.strokeStyle = "rgba(0,0,0,1)";
                vm.context.stroke();

                vm.startX = x;
                vm.startY = y;

                vm.points_push({
                    x: x,
                    y: y
                });
            }
        },
        mouseup() {
            var vm = this
            vm.isDrawing = false;
            if (vm.points.length > 0) {
                localStorage['points'] = JSON.stringify(vm.points);
            }
        },
        replay() {
            var vm = this
            vm.canvas.width = vm.clientWidth();

            if (vm.points === 0) {
                if (localStorage["points"] !== undefined) {
                    vm.points = JSON.parse(localStorage["points"]);
                }
            }

            var point = 1;
            setInterval(function () {
                drawNextPoint(point);
                point += 1;
            }, 10);

            function drawNextPoint(index) {
                if (index >= vm.points.length) {
                    return;
                }
                var startX = vm.points[index - 1].x;
                var startY = vm.points[index - 1].y;

                var x = vm.points[index].x;
                var y = vm.points[index].y;

                vm.context.beginPath();
                vm.context.moveTo(startX, startY);
                vm.context.lineTo(x, y);
                vm.context.lineWidth = 1;
                vm.context.lineCap = 'round';
                vm.context.strokeStyle = "rgba(0,0,0,1)";
                vm.context.stroke();
            }
        },
        touchstart(e) {
            var vm = this
            var rect = vm.canvas.getBoundingClientRect();
            var x = e.clientX - rect.left;
            var y = e.clientY - rect.top;

            vm.isDrawing = true;
            vm.startX = x;
            vm.startY = y;
            vm.points.push({
                x: x,
                y: y
            });
        },
        touchemove(e) {
            var vm = this
            var rect = vm.canvas.getBoundingClientRect();
            var x = e.clientX - rect.left;
            var y = e.clientY - rect.top;

            if (vm.isDrawing) {
                vm.context.beginPath();
                vm.context.moveTo(vm.startX, vm.startY);
                vm.context.lineTo(x, y);
                vm.context.lineWidth = 1;
                vm.context.strokeStyle = "rgba(0,0,0,1)";
                vm.context.stroke();

                vm.startX = x;
                vm.startY = y;

                vm.points_push({
                    x: x,
                    y: y
                });
            }
        },
        touchcancel() {
            var vm = this
            vm.isDrawing = false;
            if (vm.points.length > 0) {
                localStorage['points'] = JSON.stringify(vm.points);
            }
        },
        clearCanvas() {
            var vm = this
            vm.canvas.clearRect(0, 0, vm.canvas.width, vm.canvas.height);
        }
    }
}
</script>
  
<style lang="scss" scoped>
.introduction {
    padding-top: 15px;
    display: flex;
    align-items: center;

    p,
    h2 {
        text-align: center;
    }
}

.slider {
    max-width: 800px;
    min-height: 140px;
    border-radius: 10px;
    overflow: hidden;
    margin: auto;

    .slides {
        display: flex;
        width: 500%;
        max-height: 500px;
        min-height: 140px;

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

        #radio1:checked~.first {
            margin-left: 0;
        }

        #radio2:checked~.first {
            margin-left: -20%;
        }

        #radio3:checked~.first {
            margin-left: -40%;
        }
    }

    .navigation_manual {
        position: relative;
        max-width: 800px;
        padding-top: 50px;
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
  