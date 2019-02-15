<template>
  <div id="app">
    <b-container class="title">
      <b-row>
        <b-col cols="3" class="col1"><img class="Logo1" src="./assets/logo.png" height="250" width="200"></b-col>
        <b-col>
          <h1 class="heading">Heritage Animal Hospital</h1>
        </b-col>
      </b-row>
    </b-container>
    <br>
    <div class="NavBar" v-b-scrollspy:nav-scroller>
      <b-container class="NavBarButtons">
        <button id="staff" @click="staff('staff')" class="button">
          Staff
        </button>
        <button id="services" @click="services('services')" class="button">
          Services
        </button>
        <button id="specials" @click="specials('specials')" class="button">
          Specials
        </button>
        <button id="links" @click="links('links')" class="button">
          Links
        </button>
        <button id="contact" @click="contact('contact')" class="button">
          Contact Us
        </button>
      </b-container>
    </div>
    <br>
    <Header />
    <br>
    <b-container ref="staff" class="staffSection">
      <center>
        <h1 class="headers">Staff</h1>
      </center>
      
        <div v-if="employees && employees.length">
      <div v-for="(employee, index)  in employees" v-bind:key='"employee" + index' :employee='employee'>
        <div class="staffContainer">
          <b-container class="staffSection">
            <b-row text-variant="white" class="employee">
              
              <b-col><h1 class="name">{{employee.name}}</h1>
              <img class="photo" v-bind:src="employee.image" height="250px" width="250px"></b-col>

              <b-col><h2 class="Title">{{employee.title}}</h2>
              <h2 class="descBox">{{employee.desc}}</h2></b-col>
              
            </b-row>
          </b-container>
        </div>
      </div>
    </div>
      </b-container>
    <br>
    <br>
    <b-container ref="services" class="servicesContainer">
      <br>
      <center>
        <h1 class="headers">Services</h1>
      </center>
      <b-row>
        <b-col>
          <div>
            <b-button v-b-toggle.collapse1 class="service">Preventative Care</b-button>
            <b-collapse id="collapse1" class="mt-2">
              <b-card class="section">
                <h2>Vaccinations</h2>
                <p class="card-text">Vaccines are an excellent way to keep our pets protected from infectious disease
                  before they strike. Vaccinations can help prevent/prepare our pets for common diseases. By protecting
                  our pets from these illnesses, we can have peace-of-mind when taking our dogs out to the dog park or
                  letting our cats venture outside. Cats also benefit from certain vaccinations, whether they are
                  indoor or outdoor cats.

                  Protecting against diseases like Leptospirosis, Distemper, Bordetella, Parvo virus, and Rabies is
                  imperative in ensuring your dog has a healthy lifestyle and the owner is more confident when out with
                  their pet(s). It is also recommended you keep your cat vaccinated from Feline Leukemia, Rabies,
                  Feline Viral Rhinotracheitis (Feline Herpes Virus), and Feline Parvo.</p>
                <b-button v-b-toggle.collapse1_inner size="sm">See More</b-button>
                <b-collapse id=collapse1_inner class="mt-2">
                  <b-card>If you would like to schedule an appointment to get your pet up-to-date on vaccinations,
                    please give us a call! 720-870-8387</b-card>
                </b-collapse>
                <h2>Wellness Exams</h2>
                <p class="card-text">Regular examinations keep us on top of preexisting conditions and catching
                  possible issues before they become a serious problem. Our comprehensive exams give you a detailed
                  evaluation of your pet’s health. We provide you with the information you need to give your pet a
                  happy, healthy life.

                  Your pet’s health and quality of life are of the utmost important to us. We recommend annual
                  examinations to ensure your pet lives a long, full life. If you are concerned there is a possible
                  issue with your pet or are simply getting a regular checkup, we look forward to providing personal,
                  professional attention.</p>
                <b-button v-b-toggle.collapse2_inner size="sm">See More</b-button>
                <b-collapse id=collapse2_inner class="mt-2">
                  <b-card>Give us a call and schedule a wellness exam today! The first exam for all new patients is 50%
                    off! 720-870-8387</b-card>
                </b-collapse>
                <h2>Parasite Prevention</h2>
                <p class="card-text">Parasites are mostly viewed as a nuisance. Unfortunately they can carry deadly
                  diseases. We believe prevention is key to avoiding side effects or underlying symptoms.

                  Thankfully, it is very easy to be proactive against most parasites, including Heartworm. Through use
                  of an Heartworm Prevention products. Our preferred brands are listed below and typically consist of
                  oral paste, pilsl, or chewables. Pesky fleas and ticks can also be avoided using a topical
                  application. Being proactive is key to to avoiding the dangers of parasites.</p>
                <b-button v-b-toggle.collapse3_inner size="sm">See More</b-button>
                <b-collapse id=collapse3_inner class="mt-2">
                  <b-card>Contact us to get your pet on parasite prevention today! 720-870-8387
                    <b-container>
                      <b-col>
                        <b-row class="supplyers"><img class="supplyer" src="./assets/HeartgardPlus.png" height="50px" width="150px">
                        <img class="supplyer" src="./assets/InterceptorPlus.png" height="100px" width="150px">
                        <img class="supplyer" src="./assets/ParaStar.png" height="50px" width="150px"></b-row>
                      </b-col>
                    </b-container>

                  </b-card>
                </b-collapse>


              </b-card>
            </b-collapse>
          </div>
        </b-col>
      </b-row>
      <b-row>
        <b-col>
          <div>
            <b-button v-b-toggle.collapse2 class="service">Puppy and Kitten Care</b-button>
            <b-collapse id="collapse2" class="mt-2">
              <b-card>
                <p class="card-text">At Heritage Animal Hospital, we offer extensive and affordable puppy/kitten care
                  to ensure your pet starts off on the right foot. Through comprehensive exams and great medical care,
                  we provide a healthy, happy start to your pet’s life.

                  We offer Kitten and Puppy Packages that get the full value out of our services. At an affordable
                  price, our packages cover everything from the spay/neuter to the full series of vaccinations to get
                  them through their first year safely. We pride ourselves in the value and quality of our kitten and
                  puppy care, but mostly enjoy watching them grow!</p>
                <b-button v-b-toggle.collapse2_inner size="sm">See More</b-button>
                <b-collapse id=collapse2_inner class="mt-2">
                  <b-card>If you are interested in our Kitten or Puppy Packages, please contact us for more
                    information! 720-870-8387</b-card>
                </b-collapse>
              </b-card>
            </b-collapse>
          </div>
        </b-col>
      </b-row>
      <b-row>
        <b-col>
          <div>
            <b-button v-b-toggle.collapse3 class="service">Surgery</b-button>
            <b-collapse id="collapse3" class="mt-2">
              <b-card>
                <p class="card-text">We use the latest technology and methods to make our surgical operations as safe
                  and easy as possible. Your pet’s health and comfort are important to us, as we use comprehensive
                  precautions before performing even the most routine procedures.

                  We understand that surgery can be a scary process for our clients as much as our patients. At
                  Heritage Animal Hospital we ensure the safest methods, medicines, and technologies are a part of our
                  surgeries.

                  We also engage Dr. Stubbs of Mile High Veterinary Surgical Specialists. He is an amazing surgeon,
                  specializing in TPLO and Excap procedures. Check out his website by clicking <a href="http://milehighveterinarysurgicalspecialists.com/index.html">HERE</a>.</p>
                <b-button v-b-toggle.collapse3_inner size="sm">See More</b-button>
                <b-collapse id=collapse3_inner class="mt-2">
                  <b-card>If you have any more questions or need a quote on our surgical procedures, please call us at
                    720-870-8387</b-card>
                </b-collapse>
              </b-card>
            </b-collapse>
          </div>
        </b-col>
      </b-row>
      <br>
      <b-row>
        <b-col>
          <div>
            <b-button v-b-toggle.collapse4 class="service">Dental Care</b-button>
            <b-collapse id="collapse4" class="mt-2">
              <b-card>
                <b-row>
                  <b-col><img src="./assets/DentalCare.png" height="450px" width="350px"></b-col>
                <b-col class="dentalcare">
                <h2>Dental Care</h2>
                
                <p class="card-text">
                  Dental hygiene is just as important to our pet’s health as it is to our own. Dental disease can lead
                  to more serious issues, such as pain in the mouth, heart disease, and kidney disease. Sometimes bad
                  breath can be a way of letting you know your pet may have some underlying issues. Let us help you
                  resolve them today!

                  At Heritage Animal Hospital, we prefer to be proactive in dental hygiene. Using thorough visual
                  examinations of the teeth and gums, we can quickly determine the overall health of your pet’s mouth.
                  We hope to catch periodontal disease early, before it becomes an issue. Although regular brushing at
                  home can help keep tartar and gingivitis in check, sometimes a more extensive cleaning is necessary
                  to ensure a healthy mouth and healthy life for your pet.</p>

                <b-button v-b-toggle.collapse4_inner size="sm">See More</b-button></b-col>
                <b-collapse id=collapse4_inner class="mt-2">
                  <b-card class="extraBox">Give us a call to schedule an appointment for a dental cleaning or to examine the health of
                    your pet’s teeth. 720-870-8387</b-card>
                </b-collapse>
                </b-row>
              </b-card>
            </b-collapse>
          </div>
        </b-col>
      </b-row>
      <b-row>
        <b-col>
          <div>
            <b-button v-b-toggle.collapse5 class="service">Diagnostics</b-button>
            <b-collapse id="collapse5" class="mt-2">
              <b-card>
                <h2>Radiology ( X-rays )</h2>
                <p class="card-text">Sometimes it is necessary to take a closer look at your pet through x rays.
                  Radiology help us determine and/or verify any underlying issues. X-Rays are a reliable, safe method
                  for discovering possible issues with your pet. Using the latest in radiography, we can get the
                  clearest view of your pet’s organs and bones.</p>
                <h2>Ultrasound</h2>
                <p class="card-text">Our advances in human medicine have created technology that is beneficial for our
                  pets. Like x-rays, Ultrasound’s are one advancement that allows us to further examine a pet’s
                  condition to diagnose and determine the correct form of action for your pet.

                  Ultrasonography is a diagnostic method that uses ultrasound imaging to safely evaluate the organs of
                  your pet in a non-invasive, comfortable manner. In some cases, ultrasound is the best method to
                  diagnose an issue.</p>
                <h2>Laboratory</h2>
                <p class="card-text">Our advances in human medicine have created technology that is beneficial for our
                  pets. Like x-rays, Ultrasound’s are one advancement that allows us to further examine a pet’s
                  condition to diagnose and determine the correct form of action for your pet.

                  Ultrasonography is a diagnostic method that uses ultrasound imaging to safely evaluate the organs of
                  your pet in a non-invasive, comfortable manner. In some cases, ultrasound is the best method to
                  diagnose an issue.</p>

                <b-button v-b-toggle.collapse5_inner size="sm">See More</b-button>
                <b-collapse id=collapse5_inner class="mt-2">
                  <b-card>Whether routine procedures or medical treatments of chronically painful conditions, we are
                    dedicated to providing safe and effective pain management. We also help you recognize signs of pain
                    in your pet and help establish a pain management plan.</b-card>
                </b-collapse>
              </b-card>
            </b-collapse>
          </div>
        </b-col>
      </b-row>
      <b-row>
        <b-col>
          <div>
            <b-button v-b-toggle.collapse6 class="service">Grooming</b-button>
            <b-collapse id="collapse6" class="mt-2">
              <b-card>
                <h2>Grooming</h2>
                <p class="card-text">
                  Keeping your dog’s body/coat clean/untangled can seem like a monumental task. Our grooming services
                  are here to help! Ashley is amazing at giving your family member (pet) a positive experience and also
                  shines at addressing their owners specific needs. Keeping your dog clean and groomed can not only
                  help maintain a beautiful coat, but also helps prevent matting and possible health issues.

                  Heritage Animal Hospital offers a full grooming service. Because our groomers operate within our
                  facility, we provide convenience and peace-of-mind should your dog have pre-existing medical issues
                  or you would need to follow up the groom with a comprehensive exam.</p>
                <b-button v-b-toggle.collapse6_inner size="sm">See More</b-button>
                <b-collapse id=collapse6_inner class="mt-2">
                  <b-card>Kales is available for appointments! Contact us today!
                  </b-card>
                </b-collapse>
              </b-card>
            </b-collapse>
          </div>
        </b-col>
      </b-row>
      <br>
      <b-row>
        <b-col>
          <div>
            <b-button v-b-toggle.collapse7 class="service">Pain Management</b-button>
            <b-collapse id="collapse7" class="mt-2">
              <b-card>
                <p class="card-text">At Heritage Animal Hospital, we focus on the whole picture, from medical issues
                  that affect the patient’s physical health, to the psychological issues that affect the quality of
                  life your pet is experiencing. Pain can affect proper function of the body and have a detrimental
                  effects on a patient’s quality of life. Pain Management is a primary consideration when treating a
                  pet for certain medical conditions.

                  Whether routine procedures or medical treatments of chronically painful conditions, we are dedicated
                  to providing safe and effective pain management. We also help you recognize signs of pain in your pet
                  and help establish a pain management plan.</p>
                <b-button v-b-toggle.collapse7_inner size="sm">See More</b-button>
                <b-collapse id=collapse7_inner class="mt-2">
                  <b-card>Call us if you have concerns over your pet’s behavior that may be associated with discomfort
                    or pain. 720-870-8387</b-card>
                </b-collapse>
              </b-card>
            </b-collapse>
          </div>
        </b-col>
      </b-row>
      <b-row>
        <b-col>
          <div>
            <b-button v-b-toggle.collapse8 class="service">Boarding</b-button>
            <b-collapse id="collapse8" class="mt-2">
              <b-card>
                <p class="card-text">Sometimes it is necessary to take a closer look at your pet through x rays.
                  Radiology help us determine and/or verify any underlying issues.</p>
                <b-button v-b-toggle.collapse8_inner size="sm">See More</b-button>
                <b-collapse id=collapse8_inner class="mt-2">
                  <b-card>X-Rays are a reliable, safe method for discovering possible issues with your pet. Using the
                    latest in radiography, we can get the clearest view of your pet’s organs and bones.</b-card>
                </b-collapse>
              </b-card>
            </b-collapse>
          </div>
        </b-col>
      </b-row>
      <br>
    </b-container>
    <br>
    <b-container class="linksPage" ref="links">
      <center>
        <h1 class="headers">Links</h1>
      </center>
      <b-row>
        <b-col class="link">
          <h1 class="linkTitle">The American Society for the Prevention of Cruelty to Animals</h1>
          <img class="aspcaPhoto" src="./assets/ASPCA.png">
          <h3 class="aspcaDesc">The first humane organization to be granted legal authority to investigate and make arrests for crimes
            against animals.</h3>
            <a href="https://www.aspca.org/" target="_blank">
          <b-button>Visit Site</b-button></a>
        </b-col>
        <b-col class="link">
          <h1 class="linkTitle">Animal Emergency & Specialty Center</h1>
          <img class="aescPhoto" src="./assets/AnimalEmergencyCenter.png">
          <h3 class="aescDesc">For after hours emergencies, please contact AESC at 720-842-5050.</h3>
          <h3 class="aescDesc">Located at 17701 Cottonwood Drive in Parker.</h3>
          <a href="http://aescparker.com/wp-content/" target="_blank">
          <b-button>Visit Site</b-button></a>
        </b-col>
      </b-row>
      <b-row>
        <b-col class="link">
          <h1 class="linkTitle">American Veterinary Medical Association</h1>
          <img class="avmaPhoto" src="./assets/AVMA-Logo.png">
          <br>
          <a href="https://www.avma.org/Pages/home.aspx" target="_blank">
            <b-button>Visit Site</b-button></a>
        </b-col>
        <b-col class="link">
          <h1 class="linkTitle">Mile HighVeterinary Surgical Specialists</h1>
          <img class="mhssPhoto" src="./assets/mhss.png">
          <br>
          <a href="http://milehighveterinarysurgicalspecialists.com/bio.html" target="_blank">
            <b-button>Visit Site</b-button></a>
        </b-col>
      </b-row>
    </b-container>
    <br>
    <b-container ref="specials" class="specialsSection">
      <center>
        <h1 class="headers">Specials</h1>
      </center>
      <b-row>
        <b-col>
          <img class="coupon" src="./assets/coupon.png">
          <a href="https://s3.us-east-2.amazonaws.com/coupon-firstexam/coupon.png" target="_blank">
          <b-button >Print</b-button>
          </a>
        </b-col>
        <br>
        <b-col> 
          <img class="coupon" src="./assets/coupon-2.png">
          <a href="https://s3.us-east-2.amazonaws.com/coupon-firstexam/coupon-2.png" target="_blank">
          <b-button >Print</b-button>
          </a>
        </b-col>
        <br>
        <b-col>
          <img class="coupon" src="./assets/coupon-3.png">
          <a href="https://s3.us-east-2.amazonaws.com/coupon-firstexam/coupon-3.png" target="_blank">
          <b-button>Print</b-button>
          </a>
        </b-col>
        <br>
        <b-col> 
          <img class="coupon" src="./assets/coupon-1.png">
          <a href="https://s3.us-east-2.amazonaws.com/coupon-firstexam/coupon-1.png" target="_blank">
          <b-button>Print</b-button>
          </a>
        </b-col>
      </b-row>
    </b-container>
    <br>
    <b-container ref="contact" class="contact">
      <br>
      <center>
        <h1 class="headers">Contact Us</h1>
      </center>
      <b-row>
        <b-col class="contactPart">
          <h4><b>Email Us</b></h4>
          <h4>hahparker@gmail.com</h4>
          <br>
          <h4><b>Contact Us</b></h4>
          <h4>720-870-8387</h4>
        </b-col>
      </b-row>
      <br>
      <b-col>
        <b-button href="https://goo.gl/maps/eXUfAuAYnD72" class="locationButton">
          <h4 class="locationText">22651 E Aurora Parkway, Ste A-1</h4>
        </b-button>
      </b-col>
      <b-row>
        <b-col>
          <img class="locationImage" src="./assets/location.png">
        </b-col>
      </b-row>
      <br>
      <h4><b>Hours</b></h4>
      <center>
        <b-row class="day">
          <b-col class="time">
            <h5 class="day">Monday</h5>
            8 am - 6 pm
          </b-col>
          <b-col class="time">
            <h5 class="day">Tuesday</h5>
            8 am - 6 pm
          </b-col>
          <b-col class="time">
            <h5 class="day">Wednesday</h5>
            8 am - 6 pm
          </b-col>
          <b-col class="time">
            <h5 class="day">Thursday</h5>
            8 am - 6 pm
          </b-col>
          <b-col class="time">
            <h5 class="day">Friday</h5>
            8 am - 6 pm
          </b-col>
          <b-col class="time">
            <h5 class="day">Saturday</h5>
            8 am - 12 pm
          </b-col>
          <b-col class="time">
            <h5 class="day">Sunday</h5>
            Closed
          </b-col>
        </b-row>
      </center>
      <br>
    </b-container>
    <br>



    <center>
      <v-footer dark height="auto">

        <div class="footer">
          <v-card-text>
            <v-card-text class="white--text pt-0">
              Follow Us On
            </v-card-text>
            <b-container>
              <b-row>
                <b-col>
                  <b-button href="https://twitter.com/heritageah/" class="twitter"><i class="fab fa-twitter fa-3x"></i></b-button>
                </b-col>
                <b-col>
                  <b-button href="https://www.facebook.com/hahpetvets/" class="facebook"><i class="fab fa-facebook fa-3x"></i></b-button>
                </b-col>
                <b-col>
                  <b-button href="https://plus.google.com/111520823811354306725" class="googleplus"><i class="fab fa-google-plus fa-3x"></i></b-button>
                </b-col>
                <b-col>
                  <b-button href="https://www.instagram.com/explore/locations/473812699/heritage-animal-hospital/"
                    class="instagram"><i class="fab fa-instagram fa-3x"></i></b-button>
                </b-col>
              </b-row>
            </b-container>
          </v-card-text>
        </div>


        <v-divider></v-divider>

        <v-card-text class="ender">
          &copy;2019 — <strong>Created & Developed by Jared Candelaria</strong>
        </v-card-text>

      </v-footer>
    </center>


  </div>
</template>

<script>


import Vue from 'vue'
import BootstrapVue from 'bootstrap-vue'
import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap-vue/dist/bootstrap-vue.css'
import Header from "./components/Header.vue"
import Vuetify from 'vuetify'
import axios from "axios";

Vue.use(Vuetify)

Vue.use(BootstrapVue);


export default {
  name: 'app',
    data() {
    return {
      employees: [],
      apiURL: "https://hahparker.herokuapp.com/api/employee/"
    };
  },
  mounted() {
    axios.get(this.apiURL).then(response => {
      console.log(response.data);
      this.employees = response.data;
    });
  },
  components: {
   Header
  },
  
  methods:{
    staff(refName){
      var element = this.$refs[refName];
      console.log(element);
      var top = element.offsetTop;
      window.scrollTo(0, top)
    },
     services(refName){
      var element = this.$refs[refName];
      console.log(element);
      var top = element.offsetTop;
      window.scrollTo(0, top)
    },
    contact(refName){
      var element = this.$refs[refName];
      console.log(element);
      var top = element.offsetTop;
      window.scrollTo(0, top)
    },
    links(refName){
      var element = this.$refs[refName];
      console.log(element);
      var top = element.offsetTop;
      window.scrollTo(0, top)
    },
    specials(refName){
      var element = this.$refs[refName];
      console.log(element);
      var top = element.offsetTop;
      window.scrollTo(0, top)
    },
  }
}

</script>

<style>
html{
 background-color: #3E69B1;
  width: 100%;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: white;
  margin-top: 60px;
  width: 100%;
 background-color: #3E69B1;
 
}
.title{
  background-image: url(./assets/background.png);
  width: 100%;
  height: 250px;
}
.contact{
  background-color: white;
  border: 3px solid black;
  border-radius: 15px;
}
h1{
  color: white;
  text-shadow: .5px .5px black;
  font-family: 'Lato', sans-serif;
  font-size: 35px;
}
h2{
  color: black;
  font-family: 'Lato', sans-serif;
}
h3{
  font-family: 'Lato', sans-serif;
}
h4{
  font-family: 'Lato', sans-serif;
  color: black;
}
h5{
  font-family: 'Lato', sans-serif;
  color: black;
  text-shadow: .5px .5px white;
}
.button{
  background-color: #1e1472;
  border: 3px solid black;
  text-shadow: 1px 1px black;
  border-radius: 15px;
  display: space-around;
  color: white;
  font-size: 24px;
}
.Logo1{
  display: flex;
}
#services{
  margin-right: 5px;
}
#specials{
  margin-right: 5px;
}
#links{
  margin-right: 5px;
}
.servicesContainer{
  background-color: white;
  border: 3px solid black;
  border-radius: 15px;
}
.service{
  background-color: #49A35B;
  border: 3px solid black;
  font-family: 'Lato', sans-serif;
  color: white;
  font-size:24px;
  height: 75px;
  width: 275px;
}
.staffSection{
  background-color: #49A35B;
  padding-top:20px;
  width: 100%;
  border: 3px solid black;
  border-radius: 15px;
}
.headers{
  background-color: #1e1472;
  border-radius: 20px;
  width: 250px;
margin-top: 5px;
}
#staff{
  margin-right: 5px;
}

#staff{
  margin-right: 5px;
}
.time{
  color: rgb(255, 255, 255);
  text-shadow: .5px .5px black;
  font-size: 16px;
}
.day{
  border-radius: 15px;
  color: white;
  text-shadow: 1px 1px black;
  width: 100%;
  background-color: #1e1472;
}
.locationButton{
  background-color: #1e1472;
}
.locationImage{
  width: 55%;
}
.locationText{
  color: white;
  text-shadow: 1px 1px black;
  font-family: 'Lato', sans-serif;
}
.employee{
  background-color: white;
  padding-bottom: 10px;
  border: 1px solid black;
  border-radius: 15px;
  height: 100%;
  font-family: 'Lato', sans-serif;
  margin: 15px;
}
.email{
  font-family: 'Lato', sans-serif;
  font-size: 24px;
}
.phoneNumber{
  font-family: 'Lato', sans-serif;
  font-size: 24px;
}
.photo{
  margin-top: 25px;
}
.heading{
  font-size: 58px;
  color:white;
  text-shadow: 1px 1px black;
  width: 100%
}
.white--text{
  color: black;
  font-size: 24px;
}
.ender{
  color:white;
  text-shadow: 1px 1px black;
}
p{
  color: black;
}
div.card-body{
  color: black;
  border: 1px solid black;
}
.mt-2{
  width: 100%;
}

.name{
  font-family: 'Lato', sans-serif;
  text-shadow: 1px 1px white;
  color: black;
  margin-top: 15px;
}
.footer{
  width: 60%;

}
.Title{
  color: black;
  text-shadow: 1px 1px white;
  margin-top: 5px;
  right: 30px;
}
.descBox{
  margin-top: 10px;
  font-size: 20px;
  color: black;
}
.decBox{
  right: 20px;
}
.sherridescBox{
  font-size: 15px;
}
.emilydescBox{
  font-size: 12px;
}
.sherri{
  height: 300px;
  width: 300px;
  margin-top: 15px;
}
.marvin{
  height: 300px;
  width: 300px;
  margin-top: 15px;
}
.mandy{
  height: 300px;
  width: 300px;
  margin-top: 15px;
}
.sav{
  height: 300px;
  width: 300px;
  margin-top: 15px;
}
.tara{
  height: 300px;
  width: 300px;
  margin-top: 15px;
}
.kales{
   height: 300px;
  width: 300px;
  margin-top: 15px;
}
.alexis{
   height: 300px;
  width: 300px;
  margin-top: 15px;
}
.emily{
   height: 300px;
  width: 300px;
  margin-top: 15px;
}

.twitter{
  background-color: #3E69B1;
  border: 0px solid white;
}
.facebook{
  background-color: #3E69B1;
  border: 0px solid white;
}
.googleplus{
  background-color: #3E69B1;
  border: 0px solid white;
}
.instagram{
  background-color: #3E69B1;
  border: 0px solid white;
}
.service{
  margin: 5px;
}.dentalcare{
right: 25px;
}
.aspcaPhoto{
  height: 75px;
  width: 200px;
}
.aescDesc{
  font-size: 18px;
}
.aspcaDesc{
  font-size: 18px;
}
.mhssPhoto{
height: 60%;
width: 75%;
}
.avmaPhoto{
  height: 60%;
  width: 50%;
}
.linksPage{
background-color: #49A35B;
border: 3px solid black;
border-radius: 15px;
color: black;
}
.link{
  background-color: white;
  border: 3px solid black;
  border-radius: 15px;
  margin: 15px;
}
.linkTitle{
  color: black;
}
.coupon{
  height: 250px;
  width: 350px;
  border: 1px solid black;
  margin: 5px;
  border-radius: 15px;
}
.specialsSection{
  background-color: white; 
  border-radius: 15px;
  border: 3px solid black;
}
.section{
  border: 2px solid black;
}
.supplyers{
  display:flex;
  align-self: center;
  align-items: center;
  align-self: center;
  justify-content: center;
  justify-items: center;
  justify-self: center;
}

</style>
