<template>
  <v-app dark class="indigo darken-4">

    <v-toolbar app flat class="indigo darken-3">
      <v-spacer></v-spacer>
        <v-toolbar-title v-text="title"></v-toolbar-title>
      <v-spacer></v-spacer>
    </v-toolbar>

    <v-content>
      <v-container>

        <v-layout row wrap>

          <v-flex xs6 class="text-xs-center">
            <v-carousel :cycle="true" hide-controls="true" class="elevation-0" interval="2000" left-control-icon="false" right-control-icon="false">
              <v-carousel-item v-for="(item,i) in pics" :key="i" :src="item" transition="fade"></v-carousel-item>
            </v-carousel>
          </v-flex>

          <v-flex xs6 class="text-xs-left pt-4 pl-4 pr-4">
            <h1 class="mt-5">Focus on your food.</h1>
            <!-- <h5 class="mt-4">Adaptab.ly connects your business to your customers more intimately, more completely. And you can adapt it to your needs.</h5> -->
          </v-flex>

        </v-layout>

        <v-layout row wrap>
          <v-flex class="text-xs-center py-4">
            <h5>Adaptab.ly connects your business to your customers more intimately, more completely. And you can adapt it to your needs.</h5>
          </v-flex>
        </v-layout>

        <v-layout row>
          <v-flex>
            <v-card light class="text-xs-center pa-4 elevation-10">
              <h3>Your new point of sale is in your customer's pocket</h3>
              <p>Meet your entirely adaptable system for connecting with your customers. Adaptab.ly allows for ordering from anywhere. Take control of your menu and put it directly into the hands of your customers without the need for additional staff or third party menu systems. Enable ordering on the go or in-store without the need of a cashier.</p>
              <v-btn flat light class="mt-4 amber darken-2">Request a Demo</v-btn>
            </v-card>
          </v-flex>
        </v-layout>

        <h3 class="mt-5 text-xs-center pa-1">Adaptab.ly has been crafted for...</h3>

        <!-- <v-layout row wrap>

          <v-flex xs4 class="text-xs-center pa-2">
            <v-card>
              <v-card-media src="/public/mobileordering.jpg" height="100px">
              </v-card-media>
            </v-card>
            <h6 class="mt-4">Mobile Ordering</h6>
            <p>No need for the lines – have customers submit their orders from their phones. Take orders and payment while you focus on serving your customers. Use location to promote your truck, even ETA for orders.</p>
            <v-btn light class="mb-3 amber darken-2">View the example</v-btn>
          </v-flex>

          <v-flex xs4 class="text-xs-center pa-2">
            <v-card>
              <v-card-media src="/public/kiosk.jpg" height="100px">
              </v-card-media>
            </v-card>
            <h6 class="mt-4">In-store Kiosk</h6>
            <p>Concerned for customers without phones? No problem. Take orders with a tablet optimised version that allows for taking anonymous payment via credit card. Get back to providing your amazing food.</p>
            <v-btn light class="mb-3 amber darken-2">View the example</v-btn>
          </v-flex>

          <v-flex xs4 class="text-xs-center pa-2">
            <v-card>
              <v-card-media src="/public/notification.png" height="100px">
              </v-card-media>
            </v-card>
            <h6 class="mt-4">Notification alerts</h6>
            <p>Have customers alerted to their completed order with a notification on their phone. Provide updates and offers to loyal repeat customers. Use location to show distance and time to your food truck.</p>
            <v-btn light class="mb-3 amber darken-2">View the example</v-btn>
          </v-flex>

          <v-flex xs4 class="text-xs-center pa-2">
            <v-card>
              <v-card-media class="mt-4" src="/public/counter.jpg" height="100px">
              </v-card-media>
            </v-card>
            <h6 class="mt-4">Front-counter orders</h6>
            <p>You might still want to support customers and accept orders from your front counter. Use a user-friendly tablet optimised interface to input your customer orders into Adaptab.ly, and get your orders out.</p>
            <v-btn light class="mb-3 amber darken-2">View the example</v-btn>
          </v-flex>

          <v-flex xs4 class="text-xs-center pa-2">
            <v-card>
              <v-card-media class="mt-4" src="/public/readyorder.jpg" height="100px">
              </v-card-media>
            </v-card>
            <h6 class="mt-4">Ready orders</h6>
            <p>Don't just shout for customers to pick up their orders, show what their orders are ready. Present ready orders on via a large tablet or TV screen either as numbers or names and save the shouting.</p>
            <v-btn light class="mb-3 amber darken-2">View the example</v-btn>
          </v-flex>

          <v-flex xs4 class="text-xs-center pa-2">
            <v-card>
              <v-card-media class="mt-4" src="/public/reporting.png" height="100px">
              </v-card-media>
            </v-card>
            <h6 class="mt-4">System reporting</h6>
            <p>Taking orders is a great start but Adaptab.ly provides you with real-time reporting visualising orders, products, customers and more. Build a smarter better business through a more intelligent system.</p>
            <v-btn light class="mb-3 amber darken-2">View the example</v-btn>
          </v-flex>

        </v-layout> -->
      </v-container>

			<div class="form grey darken-4 pb-4">
	      <v-container>
	        <v-layout row wrap>

	          <v-flex xs12 sm10 md8 offset-sm1 offset-md2>
		          <h3 class="mt-5 text-xs-center">Like to know more? Get in touch.</h3>

		          <v-form class="mt-5">

			          <!-- <v-text-field
			            label="Your Name"
			            v-model="name"
			            :error-messages="nameErrors"
			            :counter="10"
			            @input="$v.name.$touch()"
			            @blur="$v.name.$touch()"
			            required
			          ></v-text-field>

			          <v-text-field
			            label="E-mail address"
			            v-model="email"
			            :error-messages="emailErrors"
			            @input="$v.email.$touch()"
			            @blur="$v.email.$touch()"
			            required
			          ></v-text-field>

			          <v-select
			            label="I'm a..."
			            v-model="select"
			            :items="items"
			            :error-messages="selectErrors"
			            @change="$v.select.$touch()"
			            @blur="$v.select.$touch()"
			            required
			          ></v-select>

			          <v-checkbox
			            label="I'd like to hear more from you crazy kids!"
			            v-model="checkbox"
			            :error-messages="checkboxErrors"
			            @change="$v.checkbox.$touch()"
			            @blur="$v.checkbox.$touch()"
			          ></v-checkbox>

			          <v-btn light class="amber darken-2" @click="submit">submit</v-btn>
			          <v-btn light class="amber darken-2" @click="clear">clear</v-btn> -->

			        </v-form>

		        </v-flex>

	        </v-layout>
	      </v-container>
			</div>

    </v-content>

    <v-footer :fixed="fixed" app>
      <v-flex class="text-xs-center py-4 mt-2">
        <span>&copy; 2017 Adaptab.ly – Customer-powered Point of Sale for Food Trucks</span>
      </v-flex>
    </v-footer>

  </v-app>
</template>

<script>
  import { validationMixin } from 'vuelidate'
  import { required, maxLength, email } from 'vuelidate/lib/validators'

  export default {
    mixins: [validationMixin],
    validations: {
      name: { required, maxLength: maxLength(10) },
      email: { required, email },
      select: { required }
    },
    data () {
      return {
        pics:[
          '/public/foodtruck01.png',
          '/public/foodtruck02.png',
          '/public/foodtruck03.png',
          '/public/foodtruck04.png',
          '/public/foodtruck05.png',
          '/public/foodtruck06.png',
          '/public/foodtruck07.png',
          '/public/foodtruck08.png',
          '/public/foodtruck09.png',
          '/public/foodtruck10.png'],
        title: 'Adaptab.ly - Customer-powered Point of Sale for Food Trucks',
        name: '',
        email: '',
        select: null,
        items: [
          'A food truck owner',
          'A general busy body',
          'I\'d rather not say'
        ],
        checkbox: false
      }
    },
    methods: {
      submit () {
        this.$v.$touch()
      },
      clear () {
        this.$v.$reset()
        this.name = ''
        this.email = ''
        this.select = null
        this.checkbox = false
      }
    },
    computed: {
      // checkboxErrors () {
      //   const errors = []
      //   if (!this.$v.checkbox.$dirty) return errors
      //   !this.$v.checkbox.required && errors.push('You must agree to continue!')
      //   return errors
      // },
      selectErrors () {
        const errors = []
        if (!this.$v.select.$dirty) return errors
        !this.$v.select.required && errors.push('Item is required')
        return errors
      },
      nameErrors () {
        const errors = []
        if (!this.$v.name.$dirty) return errors
        !this.$v.name.maxLength && errors.push('Name must be at most 10 characters long')
        !this.$v.name.required && errors.push('Name is required.')
        return errors
      },
      emailErrors () {
        const errors = []
        if (!this.$v.email.$dirty) return errors
        !this.$v.email.email && errors.push('Must be valid e-mail')
        !this.$v.email.required && errors.push('E-mail is required')
        return errors
      }
    }
  }
</script>
