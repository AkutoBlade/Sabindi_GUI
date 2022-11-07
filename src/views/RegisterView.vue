<template>
  <v-form>
      <v-container fluid>
          <h1 class="main_title" data-text="SIGN UP">SIGN UP</h1>
          <v-row>
            <v-col class="name" cols="6">
              <v-text-field  :rules="[rules.required]"
                      type="text" name="input-10-1" label="First Name"
                    ></v-text-field>
            </v-col>
            <v-col class="surname"  cols="6">
              <v-text-field  :rules="[rules.required]"
                      type="text" name="input-10-1" label="Surname"
                    ></v-text-field>
            </v-col>
          </v-row>
          <v-row>
                    <v-text-field  :rules="[rules.required, rules.min]"
                        type="email" name="input-10-1" label="Email Address"
                        hint="At least 8 characters" counter></v-text-field>
            </v-row>
          <v-row>
                  <v-text-field :append-icon="show1 ? 'mdi-eye' : 'mdi-eye-off'" :rules="[rules.required, rules.min]"
                      :type="show1 ? 'text' : 'password'" name="input-10-1" label="Password"
                      hint="At least 8 characters" counter @click:append="show1 = !show1"></v-text-field>
          </v-row>
          <v-row>
                  <v-text-field :append-icon="show1 ? 'mdi-eye' : 'mdi-eye-off'" :rules="[rules.required, rules.min]"
                      :type="show1 ? 'text' : 'password'" name="input-10-1" label="Cmfirm Password"
                      hint="At least 8 characters" counter @click:append="show1 = !show1"></v-text-field>
          </v-row>
          <v-row>
            <v-select
          :items="items"
          label="Type of user"
        ></v-select>
          </v-row>
      </v-container>
      <v-checkbox v-model="checkbox">
      <template v-slot:label>
        <div>
          I agree to the
          <v-tooltip bottom>
            <template v-slot:activator="{ on }">
              <a
                target="_blank"
                href=""
                @click.stop
                v-on="on"
              >
                terms and conditions
              </a>
            </template>
            Opens in new window
          </v-tooltip>
        </div>
      </template>
    </v-checkbox>
      <button class="button"> Register
</button>
<p class="register-link">Already have an account? Sign In <router-link to="/">here</router-link></p>
  </v-form>
</template>

<script>
export default {
    data() {

        return { 
          items: ['Client', 'Service Provider'],
            show1: false,
            rules: {
                required: value => !!value || 'Required.',
                min: v => v.length >= 8 || 'Min 8 characters',
                emailMatch: () => (`The email and password you entered don't match`),
            },
        }
    },
}
</script>
<style scoped>

.v-form{
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    position: absolute !important;
    top: 29% !important;
    left: 20% !important;
    width: 60% !important;
}
.name{
  padding-left:0px;
}
.surname{
  padding-right:0px;
}
.main_title{
 text-align: center;
 position: relative;
 left: 0%;
 right: 50%;
 top:0%;
 font-size: 50px;
 /* transform: rotate(90deg); */
  text-shadow: 0px 0px 10px;
  color: orange!important;
  text-decoration: underline;
} 
.main_title::before{
position: absolute;
content: attr(data-text);
text-shadow: 0px 0px 20px white !important;
filter: blur(0px) brightness(1);
animation:  flicker 4s linear 1s infinite;
}
@keyframes flicker{
  0%{filter:blur(1px) brightness(1);}
  3%{filter:blur(1px) brightness(0);}
  6%{filter:blur(1px) brightness(0);}
  7%{filter:blur(1px) brightness(1);}
  8%{filter:blur(1px) brightness(0);}
  9%{filter:blur(1px) brightness(1);}
  10%{filter:blur(1px) brightness(0);}
  20%{filter:blur(1px) brightness(1);}
  50%{filter:blur(1px) brightness(1);}
  99%{filter:blur(1px) brightness(0);}
  100%{filter:blur(1px) brightness(1);}
}


.button {
 display: inline-block;
 padding: 12px 24px;
 border: 1px solid #4f4f4f;
 border-radius: 4px;
 transition: all 0.2s ease-in;
 position: relative;
 overflow: hidden;
 font-size: 19px;
 color: black;
 z-index: 1;
 margin-top: 5%;
}
.register-link{
position:absolute;
top:105%;
}

@media (min-width:1023px){
    .v-form{
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    position: absolute !important;
    top: 15% !important;
    left: 26% !important;
    width: 40% !important;
}
.button {
 display: inline-block;
 padding: 12px 24px;
 border: 1px solid #4f4f4f;
 border-radius: 4px;
 transition: all 0.2s ease-in;
 position: relative;
 overflow: hidden;
 font-size: 19px;
 color: black;
 z-index: 1;
 width:31%;
}


}

@media only screen and (max-width:321px) {
    .main_title{
 font-size: 35px;
 margin-bottom:5%;

}

.button {
padding: 0px 24px;
margin-top: 7%;
}
.register-link{
text-align: center;
margin-top: 7%;
} 

.v-form{
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    position: absolute !important;
    top: 10% !important;
    left: 20% !important;
}
}

.button:before {
 content: "";
 position: absolute;
 left: 50%;
 transform: translateX(-50%) scaleY(1) scaleX(1.25);
 top: 100%;
 width: 140%;
 height: 180%;
 background-color: rgba(0, 0, 0, 0.05);
 border-radius: 50%;
 display: block;
 transition: all 0.5s 0.1s cubic-bezier(0.55, 0, 0.1, 1);
 z-index: -1;
}

.button:after {
 content: "";
 position: absolute;
 left: 55%;
 transform: translateX(-50%) scaleY(1) scaleX(1.45);
 top: 180%;
 width: 160%;
 height: 190%;
 background-color: orange;
 border-radius: 50%;
 display: block;
 transition: all 0.5s 0.1s cubic-bezier(0.55, 0, 0.1, 1);
 z-index: -1;
}

.button:hover {
 color: #ffffff;
 border: 1px solid orange;
}

.button:hover:before {
 top: -35%;
 background-color: orange;
 transform: translateX(-50%) scaleY(1.3) scaleX(0.8);
}

.button:hover:after {
 top: -45%;
 background-color: orange;
 transform: translateX(-50%) scaleY(1.3) scaleX(0.8);
}


</style>
