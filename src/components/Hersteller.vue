<template>
    <div v-if="(this.manufacturer === -1)" class="ManufacturerList">
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

    <div v-if="(this.manufacturer === 0)" class="Audi Manufacturer">
        <img src="../assets/audi-sport-quattro-s1.jpg">
        <div class="Manufacturer_introduction">
            <p>
                1899 gründete August Horch als Absolvent des Technikums im sächsischen Mittweida
                sein eigenes Automobilwerk. 1904 wurde die Firma in eine Aktiengesellschaft umgewandelt.
                Am 16. Juli 1909 durfte August Horch seine neu gegründete Firma nicht mehr unter seinem Namen tragen und
                taufte sie deshalb in die lateinische Version seines Nachmane "Audi" um.
                Die vier Ringe sind ein Symbol der Vereinigung von vier Marken: Audi, DKW, Horch und Wanderer.
            </p>
        </div>
        <hr style="width: 100%; margin-top: 1em; margin-bottom: 1em;">
        <div class="Manufacturer_story">
            <p>
                Seit dem 16. November 2020 gehört Audi der Volkswagen AG zu 100%.
                Damit haben sie sich unter anderem auch die Tochtergesellschaften von Audi eingekauft,
                darunter sind "Audi Sport", "Lamborghini", "Bentley", der Motorradhersteller "Ducati" und das Designstudio
                "Italdesign".<br>
                Wenn man mit Fahrzeugenthusiasten spricht und Audi zum Thema werden sollte, dann findet man schnell
                gespaltene Meinungen. Sei es, dass die einen diese Marke zu ihrer Nummer eins gewählt haben, da sie
                ihre Jugend damit verbinden, die Innovationen die von dieser Marke auf die deutschen Straßen kamen,
                oder das unglaublich beliebte Fahrgefühl ihrer stark motorisierten Kombis. Oder die anderen die der Meinung
                vertreten sind, dass diese Marke an jeglicher Authenitizität verloren hätte und einfach nicht mehr das ist was 
                es mal war und nicht ist was es sein sollte. Sind alle doch einer Meinung. Diese Marke vertritt starke Emotionen.
                Die Historie mit vielen Erfolgen ist eine spannende und alle lieben den Audi Quattro S1, denn dieser gewann viele 
                Rallyrennen und erzeugte viel Aufmerksamkeit für diese Marke. Heute verbindet man mit Audi einen luxuriösen Stand,
                damit einhergehend ein komfortables Fahrgefühl und Zuverlässigkeit. Doch wenn man es sportlich mag, dann kann man
                zu ihren Modellen mit der Bezeichnung "S" oder "RS" greifen. Mit diesen Modellen versprechen sie ein sportliches
                Erlebnis und doch soll man auf nichts verzichten.
            </p>
        </div>
        <button @click="resetValue()">Liste</button>
    </div>

    <div v-if="(this.manufacturer === 1)" class="BMW Manufacturer">
        <img src="../assets/bmw-635csi.jpg">
        <div class="Manufacturer_introduction">
            <p>
                BMW("Bayrische Motorenwerke") entstand durch Rapps eigenes Unternehmen, Rapp Motorenwerke GmbH und die zugekaufte Firma Schneeweis,
                diese Firma verfügte über großes Vorwissen von Flugmotoren. Im April 1917 änderte sich der Name von Rapp Motorenwerke
                in BMW GmbH und nur ein Jahr in die BMW AG um.
            </p>
        </div>
        <hr style="width: 100%; margin-top: 1em; margin-bottom: 1em;">
        <div class="Manufacturer_story">
            <p>
                1928 kaufte BMW die Fahrzeugfabrik Eisenach A.G., den Hersteller des Kleinwagens Dixi und wurde so zum Automobilhersteller. 1929
                produzierte BMW dann auch sein erstes Serienautomobil mit der Bezeichnung 3/15 PS bzw. DA 2 und war nur eine Weiterentwicklung 
                des Modells Dixi 3/15 DA. 1932 folgte dann der erste "echte" BMW der BMW AM-Baureihe mit der Bezeichnung AM1. Diese Bezeichnung steht
                für "Automobilkonstruktion München Nr. 1" und besiegelt damit die erste BMW-eigene Automobilkonstruktion. Und ab diesem Zeitpunkt
                entwickelte BMW dann eine Reihe von Fahrzeugen, welche bei vielen Menschen noch schöne Gefühle hervorbringen.
                Bekannt ist der Konkurrent der S-Klasse, der 7er BMW, welcher auch mit einer Reihe von Luxus geschmückt wurde und ein sehr angenehmes
                Fahrgefühl gibt.
            </p>
        </div>
        <button @click="resetValue()">Liste</button>
    </div>

    <div v-if="(this.manufacturer === 2)" class="Mercedes-Amg Manufacturer">
        <img src="../assets/amg-one.jpg">
        <div class="Manufacturer_introduction">
            <p>
                AMG selbst ist eine Tochtergesellschaft der Mercedes-Benz AG und zuständig für die Hochleistungsfahrzeuge
                dieses Konzerns. Gegründet wurde dieses Unternehmen am 1. Juni 1967. Diese entwickeln mit Mercedes
                zusammen Gesamtfahrzeugkonzepte im Hochleistungsbereich und ist ein Mercedes-Benz-Original-Equipment-Manufacturer.
            </p>
        </div>
        <hr style="width: 100%; margin-top: 1em; margin-bottom: 1em;">
        <div class="Manufacturer_story">
            <p>
                Gegründet wurde AMG von Hans Werner Aufrecht und Erhard Melcher, im Jahre 1967. Ihr erster großer Erfolg war das 24-Stunden-Rennen von
                Spa-Francorchamps mit dem Klassensieg und zweitem Platz ihres AMG Mercedes 300 SEL 6.8, einer Rennversion des Mercedes-Benz 300 SEL 6.3.
                1990 schlossen Mercedes und AMG einen Kooperationsvertrag ab und 1993 entwickelten sie ihr erstes Projekt, den C36 AMG. 1998 übernahm
                Daimler dann 51% der Anteile von Hans Werner Aufrecht und dadurch wurde das Unternehmen dann in Mercedes-AMG GmbH umbenannt.
                Heutzutage entwickelt Mercedes-AMG selber Fahrzeugkonzepte im Hochleistungsbereich, aber blieb ein Original-Equipment-Manufacturer. 
            </p>
        </div>
        <button @click="resetValue()">Liste</button>
    </div>

    <div v-if="(this.manufacturer === 3)" class="Mercedes-Benz Manufacturer">
        <img src="../assets/560sec.jpg">
        <div class="Manufacturer_introduction">
            <p>
                Mercedes ist eine Weltweit bekannte Luxusmarke, aus deutscher Hand und noch immer einer der ersten Hersteller der genannt wird
                wenn es um Luxus, technischen Fortschritt und Qualität geht. Am 5. November  1921 beantragte die Daimler-Motoren-Gesellschaft
                beim Patentamt den Gebrauchsmusterschutz für diese sowie andere Varianten des Markenzeichens. Die Eintragung als Warenzeichen erfolgte 
                dann im August 1923.
            </p>
        </div>
        <hr style="width: 100%; margin-top: 1em; margin-bottom: 1em;">
        <div class="Manufacturer_story">
            <p>
                Die Geschichte von Mercedes geht aber noch weiter zurück. Bereits 1899 nutzt der in Baden bei Wien, sowie in Nizza lebende Österreicher
                Emil Jellinek diesen Namen. Er nutzte beim Einsatz von Fahrzeugen der Daimler-Motoren-Gesellschaft den Namen Mercédès als Pseudonym
                für Team und Fahrer.
                Das wohl bekannteste Modell von Mercedes ist die allseitsbeliebte S-Klasse. Diese ist das Zeichen deutschen Luxusgutes. Aber viele 
                verbinden auch die Historie mit diesem Modell, denn an ihr kann sich die Geschichte von Mercedes gut ableiten, da in dieses Modell
                das meiste Geld und die meiste Mühe gesteckt wurde. Und das mit Erfolg: die technischen Fortschritte die dadurch entstanden sind, 
                sind ausschlaggebend dafür dass der heutige Fahrkomfort von Autos so hoch ist.
            </p>
        </div>
        <button @click="resetValue()">Liste</button>
    </div>

    <div v-if="(this.manufacturer === 4)" class="Mercedes-Maybach Manufacturer">
        <img src="../assets/Maybach-sklasse.jpg">
        <div class="Manufacturer_introduction">
            <p>
                Maybach ist seit Ende 2014 eine Ergänzungsmarke von Mercedes-Benz. Sie folgt auf die bis dahin bestehende Maybach-Manufaktur,
                einer Sparte der Mercedes-Benz Group, welche Limousinen der Marke Maybach produzierte und verkaufte.
            </p>
        </div>
        <hr style="width: 100%; margin-top: 1em; margin-bottom: 1em;">
        <div class="Manufacturer_story">
            <p>
                Unter Maybach verkaufte bereits die Maybach-Motorenbau GmbH von 1921 bis 1941 luxuriöse Automobile. Daimler-Benz übernahm 1960 die
                GmbH und damit die Markenrechte. 1969 wurde die Maybach-Motorenbau GmbH zu MTU Friedrichshafen umfirmiert.
                Ab 2002 wurden wieder Fahrzeuge unter der Marke Maybach verkauft und die ersten Fahrzeuge der Maybach-Manufaktur ausgeliefert.
                Zu Gunsten der S-Klasse wurde die Marke Maybach eingestellt. Heutzutage definiert Mercedes ihre Maybach sparte als das was Luxus 
                zu unserer Zeit bedeuten soll: Größter Anmut und höchster Komfort, Liebe zum Detail und Aura der Erhabenheit.
            </p>
        </div>
        <button @click="resetValue()">Liste</button>
    </div>

    <div v-if="(this.manufacturer === 5)" class="Opel Manufacturer">
        <img src="../assets/opel-insignia.jpg">
        <div class="Manufacturer_introduction">
            <p>
                Opel Automobile GmbH ist ein deutscher Kraftfahrzeughersteller. Nachdem PSA und FCA fusioniert sind, ist Opel eine Marke
                im 2021 gegründeten Konzern Stellantis.
            </p>
        </div>
        <hr style="width: 100%; margin-top: 1em; margin-bottom: 1em;">
        <div class="Manufacturer_story">
            <p>
                Angefangen hat Opel 1862 unter Adam Opel mit der Nähmaschinenherstellung. 1886 bis 1940 entwickelte Opel dann Fahrräder und nachdem
                der Vater und der damit ursprüngliche Besitzer von Opel verstorben war, begann seine Tochter mit dem Automobilbau. Von Anfang an
                produzierte Opel verschiedene Karosserien und Motorvarianten, darunter auch einen Lieferwagen. 
                1931 übernahm General Motors Opel komplett, aber der Name und die Modellpolitik blieben erhalten und die Opel-Brüder konnten durchsetzen
                dass sie im Vorstand bleiben.
                Nach dem zweiten Weltkrieg begann Opel in Rüsselsheim neu. Dieser Neustart tat dem Unternehmen auch sehr gut, da die 1960er und 70er Jahre
                für Opel die Blütezeit waren und unter den größten Automobilherstellern rangierte.
                Aber nach dem Höhenflüg kam in der Zeit von 1980 bis 2008 doch ein Tiefflug. Opel hatte mit Qualitätsproblemen zu kämpfen. Dabei geriet
                einiges ins negative, darunter waren Fehler im Marketing, bei der Modellentwicklung und die Produktions- und Qualitätssicherung ging auch
                daneben.
                2008 bis 2010 trennte sich Opel dann wieder von General Motors.
                2011 bis 2016 fing bei Opel dann die Umwandlung zu einer Aktiengesellschaft an und bekam auch einen neuen Vorstandsvorsitzenden.
                2017 wurde das Unternehmen dann von der Groupe PSA übernommen und auch im Frühjahr 2017 wieder in eine GmbH umgewandelt. 
            </p>
        </div>
        <button @click="resetValue()">Liste</button>
    </div>

    <div v-if="(this.manufacturer === 6)" class="Porsche Manufacturer">
        <img src="../assets/918spyder.jpg">
        <div class="Manufacturer_introduction">
            <p>
                Porsche wurde mit Sitz in Stuttgart-Zuffenhausen, 1931 als Konstruktionsbüro von Ferdinand Porsche gegründet, welches nach
                1945 in einer Automobilfabrik aufging, welches vor allem Sportwagen produzierte.
            </p>
        </div>
        <hr style="width: 100%; margin-top: 1em; margin-bottom: 1em;">
        <div class="Manufacturer_story">
            <p>
                Anfangs hatte er in seinem Konstruktionsbüro das Ziel Fahrzeugkonzepte für andere herzustellen und Unternehmen zu Beraten. Er hatte ein
                kleines Team aus Mitarbeitern. Entwickelt wurden in ihrem Büro der Porsche Typ 32, welcher viele Ähnlichkeiten mit dem VW Käfer aufwies.
                Doch die Produktionskosten dieses Fahrzeugs waren so hoch, dass es niemals in die Serienfertigung kam. Das gleiche Schicksal erlitt dann
                der Tourenwagen für Wanderer-Werke. Jedoch hatte das Büro in der Entwicklung des Grand-Prix-Rennwagens des Auto-Union-Rennwagens sehr viel Erfolg.
            </p>
        </div>
        <button @click="resetValue()">Liste</button>
    </div>
    
    <div v-if="(this.manufacturer === 7)" class="Smart Manufacturer">
        <img src="../assets/SmartForTwo.jpg">
        <div class="Manufacturer_introduction">
            <p>
                Smart ist eine von der Mercedes-Benz AG gegründete Automobilmarke. Hauptsächlich wurden Kleinwagen mit Verbrennungsmotoren, 
                welche für die Stadt konzipiert sind produziert, inzwischen aber auch elektrisch betriebene und Hybridfahrzeuge produzieren.
            </p>
        </div>
        <hr style="width: 100%; margin-top: 1em; margin-bottom: 1em;">
        <div class="Manufacturer_story">
            <p>
                Die Idee hinter dem Smart ist der, dass kleinere Fahrzeuge als die der VW-Polo-Klasse auf den Straßen unterwegs sein sollen, Smarts
                sinds reine Stadtfahrzeuge. <br>
                Nicolas Hayek, hatte eine Vision eines kleinen und vor allem günstigen Autos. Als erstes ging er mit seiner Idee zu VW, zuerst war 
                das Konzept so gestalten, dass das Fahrzeug eine auswechselbare Karosserie vor. Aber VW stieg aus dem Projekt aus und da sprang
                Mercedes dann ein.
            </p>
        </div>
        <button @click="resetValue()">Liste</button>
    </div>

    <div v-if="(this.manufacturer === 8)" class="Volkswagen Manufacturer">
        <img src="../assets/vw-scirocco.jpg">
        <div class="Manufacturer_introduction">
            <p>
                Volkswagen ist ein deutscher Automobilhersteller mit Sitz im niedersächsischen Wolfsburg. Nach generiertem Umsatz und 2016 verkauften Fahrzeugen ist VW
                der größte Automobilhersteller der Welt. Die VW AG ist die Muttergesellschaft der Fahrzeugmarke Volkswagen, sowie einiger Tochtergesellschaften. Darunter Seat, Škoda, Audi, Bentley,
                Ducati, Lamborghini und Porsche.
            </p>
        </div>
        <hr style="width: 100%; margin-top: 1em; margin-bottom: 1em;">
        <div class="Manufacturer_story">
            <p>
                Der Ursprung vom heutigen Konzern VW, ist durch die Entwicklung von Ferdinand Porsche eines Volkswagens. Dazu kam es durch einen Auftrag von Adolf Hitler
                bei der 24. Internationalen Automobil- und Motorrad-Ausstellung in Berlin, da forderte er den Bau eines Wagens für die breite Schicht der Bevölkerung.
                Damit beauftragte Hitler auch die Deutsche Arbeitsfront mit dem Bau der größten Automobilfabrik Europas. <br>
                Der Volkswagen sollte imstande sein, auf der Autobahn längere Strecken zurücklegen zu können, sollte Familienfreundlich und sparsam sein. Nach dem zweiten
                Weltkrieg wurde der Kultwagen schlechthin produziert: Der Käfer. 
            </p>
        </div>
        <button @click="resetValue()">Liste</button>
    </div>

    <div v-if="(this.manufacturer === 9)" class="Wiesmann Manufacturer">
        <img src="../assets/wiesmann-roadster.jpg">
        <div class="Manufacturer_introduction">
            <p>
                Wiesmann ist ein 1988 gegründetes Unternehmen der Automobilfertigung, welches für Cabrios Hardtops und 1993 bis 2013 eigene Cabrios entwickelte.
            </p>
        </div>
        <hr style="width: 100%; margin-top: 1em; margin-bottom: 1em;">
        <div class="Manufacturer_story">
            <p>
                Das Unternehmen entstand von den Brüdern Friedhelm und Martin Wiesmann. Ihre Eltern besaßen ein Autohaus, was die Brüder dazu verleitete eigene, 
                klassische Roadster mit deutscher Qualitätsarbeit herzustellen. Anfangs waren es nur Hardtops für Cabrios, aber im Jahr 1993 wurde ihr erstes
                Serienmodell, der Roadster MF30, als offener Zweisitzer mit Faltdach gefertigt. <br>
                Leider ging Wiesmann 2013 ins Insolvenzverfahren und stellte erstmal die Produktion von Fahrzeugen ein, auch die Brüder trennten sich vom 
                Unternehmen und gingen ihrer eigenen Wege. Jedoch wurde 2015 eine Übernahme für 5,7 Millionen € veranlasst und 2016 wurde diese auch vollendet.
                Der neue Geschäftsführer ist der ehemalige Marketing und Vertriebs Chef von Mercedes-AMG gewesen.<br>
                Heute orientiert sich Wiesmann neu und bringt ein vollelektrisch betriebenes Coupé auf die Straßen, welches sich vom Designelement an den ehemaligen
                Fahrzeugen orientiert und heutige moderne miteinbezieht.
            </p>
        </div>
        <button @click="resetValue()">Liste</button>
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
            } else {
                this.manufacturer = -1;
            }
        },
        resetValue() {
            this.manufacturer = -1;
        }
    }
}
</script>
  
<style lang="scss">

    .ManufacturerList {
        padding-top: 3.2em;
        display: flex;
        align-content: center;
        justify-content: center;
        margin: auto;
        font-size: 1.4em;
        width: 80%;

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

    .Manufacturer {
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
        align-items: center;
        
        button {
            margin-top: 1.5em;
            margin-left: 1em;
            margin-bottom: 2.5em;
            width: 10%;
            font-size: auto;
        }

        p {
            margin: auto;
            margin-top: 1.5em;
            margin-left: 2.5em;
            margin-right: 2.5em;
            width: 66%;
            text-align: center;
        }

        img {
            width: 80%;
            margin: auto;
            margin-top: 5.5em;
        }

        .Manufacturer_introduction {
            display: flex;
            justify-content: center;
        }

        .Manufacturer_story {
            display: flex;
            justify-content: center;
        }
    }
</style>  