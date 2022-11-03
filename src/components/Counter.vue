<template>
  <h2>{{customTitle}}</h2>
  <p>{{counter}} <sup>2</sup> = {{squareCounter}}</p>

  <div>
    <button v-on:click="increase()">+1</button>
    <button @click="decrease()">-1</button>
    <!-- Listening events shortcut (v-on:) is @-->
  </div>
  
</template>

<script>

export default {
    props: {
        title: String,
        start: {
            type: Number,
            //required: true
            default: 100,
            // Custom validation props
            validator (value) {
                return value >= 100
            }

        }
    },
    /* three ways of defining props
    ['title', 'start'] */

    // name: 'something', // this could be seen on the devtools
    data() {
        return {
            counter: this.start
        }
    },
    methods: {
        getSquareValue() {
            console.log('method squarecounter')
            return this.counter * this.counter
        },
        increase(){
            this.counter++
        },
        decrease(){
            this.counter--
        }
    },

    /* Computed Properties
        Saved on cache, so they can be repeated
        only loads once and  it saves memory
        */
    computed: {
        squareCounter() {
            console.log('computed squarecounter')
            return this.counter * this.counter
        },
        customTitle() {
            return this.title || 'Counter'
            //return this.title ? this.title : 'Counter'

           /*  if(this.title !== undefined) {
                return this.title
            } else {
                return 'Counter'
            } */
            
        }
    }
}
</script>

<style>

button{
    margin: 0 5px;
    background-color: #64BB87;
    color: white;
    border-radius: 5px;
    border: 1px solid white;
    cursor: pointer;
    padding: 5px 15px;
    transition: 0.3s ease-in-out;
}
button:hover {
    background-color:#5aa67b;
    transition: 0.3s ease-in-out;
}
</style>