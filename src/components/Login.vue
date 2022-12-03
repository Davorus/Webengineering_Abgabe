<template>
    <div class="Loginbereich">
        <label for="username_input">Username:</label>
        <input type="text" id="username_input">
        <br>
        <label for="password">Password:(nur pedantisch, Standard-Passwort: passwort)</label>
        <input type="password" id="password_input">
        <button @click="submit_login()">Login</button>
    </div>
    <div class="Registrierungsbereich">
        <h2>Noch kein Account?</h2>
        <p>
            Dann registrieren Sie sich jetzt und seien Sie ein weiteres glückliches Mitglied
            des Zeitschriftabos (nur in digitaler Form)!
        </p>
        <label for="username_input">Username:</label>
        <input type="text" id="username_register_input">
        <br>
        <button @click="submit_register()">Register</button>
    </div>
</template>
  
<script>
export default {
    name: "LoginSeite",
    data() {
        return {
            users: [],
            password: "passwort",
        }
    },
    created() {
        this.users.push("lokal");
        console.log(this.users[0]);
        console.log("Check_cookies");
        let name = document.cookie;
        for(let i = 0; i < this.users.length; i++) {
            if(name === this.users[i]) {
                console.log("Cookie Login s");
                console.log("Logged in successfully through set cookie");
            } else {
                console.log("Cookie Login u");
                console.log("Noch kein Account mit diesem Nutzernamen");
            }
        }
    },
    methods: {
        submit_login() {
            console.log("Submit_Login");
            let name = document.getElementById('username_input').value;
            console.log(this.users.length);
            for(let i = 0; i < this.users.length; i++) {
                if(name === this.users[i]) {
                    document.cookie = name;
                    console.log("Logged in successfully");
                } else {
                    console.log("Noch kein Account mit diesem Nutzernamen");
                }
            }
        },
        submit_register() {
            console.log("Submit_Register");
            let name = document.getElementById('username_register_input').value;
            for(let i = 0; i < this.users.length; i++) {
                if(name === this.users[i]) {
                    console.log("Nutzername schon vergeben!")
                } else {
                    this.users.push(name);
                }
            }
        }
    }
}
</script>
  
<style lang="scss">

.Loginbereich {
    display: flex;
    flex-direction: column;
    width: 90%;
    margin: auto;
    justify-content: center;
    align-items: center;
    padding-top: 5em;
    
    label, input {
        text-align: center;
    }

    button {
        width: fit-content;
        margin: auto;
    }
}

.Registrierungsbereich {
    display: flex;
    flex-direction: column;
    width: 90%;
    margin: auto;
    margin-top: 2em;
    justify-content: center;
    align-items: center;

    h2, p {
        text-align: center;
    }
}

</style>  