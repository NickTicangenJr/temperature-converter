<template>
  <v-container>
    <v-card elevation="0">
      <v-card-title><h4>Temperature Converter</h4></v-card-title>
      <v-card-text>
        <v-form ref="form">
          <v-row>
          <v-col cols="6"> 
            <v-text-field label="Degrees" v-model="txtDegrees"
              :rules="[ v => !!v || '*Required' ]"></v-text-field>
          </v-col>
          <v-col cols="6">
            <v-select label="Type" :items="type" v-model="txtType"
              :rules="[ v => !!v || '*Required' ]"></v-select>
          </v-col>
        </v-row>
        <v-row>
          <v-text-field label="Result" outlined readonly v-model="txtResult"></v-text-field>
        </v-row>
        </v-form>
      </v-card-text>
      <v-card-actions>
          <v-btn class="primary" block large @click="convert">Convert</v-btn>
      </v-card-actions>
    </v-card>
  </v-container>
</template>

<script>
  export default {
    name: 'HelloWorld',

    data: () => ({
      type: [ "Celcius", "Fahranheit" ],
      txtDegrees: "",
      txtResult: "",
      txtType: "",
      valid: true

    }),
    methods: {
      convert(){

        this.$refs.form.validate()

        if(this.type[0] == this.txtType){
          let computed = (parseInt(this.txtDegrees) - 32) / 1.8
          this.txtResult = parseFloat(computed).toFixed(2)+" °C"
        }else if(this.type[1] == this.txtType){
          let computed = (parseInt(this.txtDegrees)*1.8) + 32
          this.txtResult = parseFloat(computed).toFixed(1) + " °F"
        }
      },
    }
  }
</script>
