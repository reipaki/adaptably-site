<template>
  <v-app dark class="purple">
    <v-toolbar app flat class="purple lighten-1">
      <v-spacer></v-spacer>
        <v-toolbar-title v-text="title"></v-toolbar-title>
      <v-spacer></v-spacer>
    </v-toolbar>
    <main>
      <v-content>
        <v-container xs8 offset-xs2>
          <v-layout row wrap>
            <v-flex xs6 class="text-xs-center">
              <img src="/public/foodtruck.png" height="500px" />
            </v-flex>
            <v-flex xs6 class="text-xs-left pa-4">
                <h1>Focus on your food.</h1>
                <p>Adaptab.y helps your business to your customers more intimately, more completely. And you can adapt it to your needs.</p>
            </v-flex>
          </v-layout>
          <v-layout row class="mt-4">
            <v-flex>
              <v-card light class="text-xs-center pa-4 elevation-10">
                  <h3>Your new point of sale is in your customer's pocket</h3>
                  <p>Adaptab.ly allows for ordering from anywhere. Take control of your menu and put it directly into the hands of your customers without the need for additional staff or third party menu systems. Enable ordering on the go or in-store without the need of a cashier. Meet your entirely adaptable system for connecting with your customers.</p>
                  <v-btn class="mt-4 primary">Request a demo</v-btn>
              </v-card>
            </v-flex>
          </v-layout>
            <h5 class="mt-4 text-xs-center pa-1">Adaptab.ly has been crafted for...</h5>
            <v-layout row wrap>
              <v-flex xs4 class="text-xs-center pa-4">
                <v-card>
                  <v-card-media src="/public/mobileordering.jpg" height="100px">
                  </v-card-media>
                </v-card>
                <h6 class="mt-3">Mobile Ordering</h6>
                <p>A little blurby text</p>
              </v-flex>
              <v-flex xs4 class="text-xs-center pa-4">
                <v-card>
                  <v-card-media src="/public/kiosk.jpg" height="100px">
                  </v-card-media>
                </v-card>
                <h6 class="mt-3">In-store Kiosk</h6>
                <p>A little blurby text</p>
              </v-flex>
              <v-flex xs4 class="text-xs-center pa-4">
                <v-card>
                  <v-card-media src="/public/notification.png" height="100px">
                  </v-card-media>
                </v-card>
                <h6 class="mt-3">Notification alerts</h6>
                <p>A little blurby text</p>
              </v-flex>
              <v-flex xs4 class="text-xs-center pa-4">
                <v-card>
                  <v-card-media src="/public/counter.jpg" height="100px">
                  </v-card-media>
                </v-card>
                <h6 class="mt-3">Front-counter orders</h6>
                <p>A little blurby text</p>
              </v-flex>
              <v-flex xs4 class="text-xs-center pa-4">
                <v-card>
                  <v-card-media src="/public/readyorder.jpg" height="100px">
                  </v-card-media>
                </v-card>
                <h6 class="mt-3">Ready orders</h6>
                <p>A little blurby text</p>
              </v-flex>
              <v-flex xs4 class="text-xs-center pa-4">
                <v-card>
                  <v-card-media src="/public/reporting.png" height="100px">
                  </v-card-media>
                </v-card>
                <h6 class="mt-3">System reporting</h6>
                <p>A little blurby text</p>
              </v-flex>
            </v-layout>
          </v-layout>
        </v-container>
        <!-- <v-container dark>
          <v-layout>
            <h5>Like to know more?</h5>
            <form class="mt-5">
            <v-text-field
              label="Name"
              v-model="name"
              :error-messages="nameErrors"
              :counter="10"
              @input="$v.name.$touch()"
              @blur="$v.name.$touch()"
              required
            ></v-text-field>
            <v-text-field
              label="E-mail"
              v-model="email"
              :error-messages="emailErrors"
              @input="$v.email.$touch()"
              @blur="$v.email.$touch()"
              required
            ></v-text-field>
            <v-select
              label="Item"
              v-model="select"
              :items="items"
              :error-messages="selectErrors"
              @change="$v.select.$touch()"
              @blur="$v.select.$touch()"
              required
            ></v-select>
            <v-checkbox
              label="Do you agree?"
              v-model="checkbox"
              :error-messages="checkboxErrors"
              @change="$v.checkbox.$touch()"
              @blur="$v.checkbox.$touch()"
              required
            ></v-checkbox>

            <v-btn @click="submit">submit</v-btn>
            <v-btn @click="clear">clear</v-btn>
          </form>
          </v-layout>
        </v-container> -->

      </v-content>
    </main>
    <v-footer :fixed="fixed" app>
      <span>&copy; 2017</span>
    </v-footer>
  </v-app>
</template>

<script>
  export default {
    data () {
      return {
        title: 'Adaptab.ly'
      }
    }
  }
</script>

<script>
  import { validationMixin } from 'vuelidate'
  import { required, maxLength, email } from 'vuelidate/lib/validators'

  export default {
    mixins: [validationMixin],
    validations: {
      name: { required, maxLength: maxLength(10) },
      email: { required, email },
      select: { required },
      checkbox: { required }
    },
    data () {
      return {
        title: 'Adaptab.ly - customer powered point of sale',
        name: '',
        email: '',
        select: null,
        items: [
          'Item 1',
          'Item 2',
          'Item 3',
          'Item 4'
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
      checkboxErrors () {
        const errors = []
        if (!this.$v.checkbox.$dirty) return errors
        !this.$v.checkbox.required && errors.push('You must agree to continue!')
        return errors
      },
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
