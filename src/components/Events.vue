<template>
  <div class="entirePage">
    <div>

      <b-container class="bv-example-row m-3">
        <b-row>
          <b-col sm="4">State Association: <select v-model="selected" @change="getStateAssociation()">
      <option v-for="option in options" v-bind:value="option.value">
        {{ option.text }}
      </option>
    </select></b-col>

          <b-col sm="4">Start Date: <input v-model="startDate" v-on:blur="getStateAssociation" v-on:keyup.enter="$event.target.blur()" ></b-col>
          <b-col sm="4">End Date: <input v-model="endDate" v-on:blur="getStateAssociation"
            v-on:keyup.enter="$event.target.blur()" ></b-col>
        </b-row>


      </b-container>







<div v-if="noDate==false" class="container">
       <div class="row">
           <div class="col-lg-5 col-md-12 col-sm-12 col-xs-12" v-for="(n, index) in headline" :key="index">


  <b-card
overlay
    :title="n.headline"
    :img-src="n.background_image"
    text-variant="white"
    style= "max-width: 90em; max-height: 90em; "
    border-variant="light"
    class="mt-3"

  >

    <b-card-text style="color: white;font-weight: 700; filter: drop-shadow(.15em .15em black);">
      {{n.subheadline}}
    </b-card-text>

<b-card-text style="margin-top: auto">
  key: {{n.key}}
  <div>
    <b-card-text style="color: white;font-weight: 700;">
      date: {{getDate(n.date)}}
    </b-card-text>
  </div>
</b-card-text>


  </b-card>


</div>
</div>
</div>


<div v-else>
  <h1 style="color:white;">
    The date range you enter doesn't have any event. Please retry again.
  </h1>

</div>







    </div>



  </div>
</template>

<script>
import moment from "moment"
export default {
  name: 'Events',

  data() {
    return {
      selected:null,
      startDate: null,
      endDate: null,
      options: [
        { text: 'Please select...', value: null },
      { text: 'GHSA', value: '18bad24aaa' },
      { text: 'UIL', value: '542bc38f95' }
    ],
    headline: [],

    noDate:false,
    someResult: '',


    }
  },
  methods: {

    getStateAssociation (){
      if(this.selected==null){
        alert('Please choose a State Association')
      }
      this.noDate = false,
      this.headline=[];
      var userInputFrom;
      var userInputTo;

      if(  this.startDate != null&&this.startDate.includes(':') ==true){
          var userInputFrom = moment(this.startDate).format('YYYY-MM-DDTHH:mm:ss.SSS') + 'Z';
          if(this.startDate.includes('Invalid') == true){
            alert('Please re-enter the date')
          }

      }else if( this.startDate != null){
        var userInputFrom = moment(this.startDate).format('YYYY-MM-DD');
      }else{
        var userInputFrom = '';
      }


      if( this.endDate != null &&this.endDate.includes(':') ==true){
          var userInputTo = moment(this.endDate).format('YYYY-MM-DDTHH:mm:ss.SSS') + 'Z';
          if(this.endDate.includes('Invalid') == true){
            alert('Please re-enter the date')
          }
      }else if( this.endDate != null){
        var userInputTo = moment(this.endDate).format('YYYY-MM-DD');
      }else{
        var userInputTo = '';
      }




      function getStateAsso(userDefine,userFrom,userTo){
          return new Promise((resolve, reject)=>{
            fetch("https://challenge.nfhsnetwork.com/v2/search/events/upcoming?from="+userFrom+"&to="+userTo+"&card=true&size=50&start=0&state_association_key="+userDefine,{
              methods: "GET",
              redirect: 'follow'
            }).then(response=>{return response.json()}).then(data=>{resolve(data)}).catch(err=>{reject(err)})
          })
        }
  getStateAsso(this.selected, userInputFrom, userInputTo).then(data=>{
for(var i=0;i<data.items.length;i++)
{

  var headline = data.items[i];
   this.headline.push(headline);

}

if(this.headline.length ==0){
  this.noDate = true
}




  }).catch(err=>{console.log(err)})


},
getDate(datetime){
  let date = moment(datetime).utc().format('MMMM DD YYYY, h:mm:ss a')

    return date


}
}}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.entirePage{
  min-height: 100vh;
 overflow-x: hidden;
  background: #09121A;
  color:white;
  padding-top: 40px;
  padding-bottom: 30px;
}
.card-columns {
  display: flex;
}


</style>
