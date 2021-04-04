#VUE Fundamentals:
https://codepen.io/planetoftheweb/post/links-for-my-vue-js-course-on-linkedin

has all of the code for each of the videos.

Vuejs has commands called directives.
They appear as html attributes
v-bind:src”image” v-bind:alt=“name”
Shortcut syntax for v-bind is :
<img :src”image” :alt=“name” />

For more on v-bind https://vuejs.org/v2/guide/class-and-style.html

{
      "id": "532",
      "name": "",
      "description": " ",
      "price": ,
      "image_title": "slicker-jacket_lynda_29941"
      "image": "https://hplussport.com/wp-content/uploads/2016/12/slicker-jacket_LYNDA_29941.jpg
    },

##LOOPS v-for
v-for=“item in products”

CONDITIONAL DATA	v-if, v-else, v-elseif

##USER INPUT
:value 	just shows the value
v-model=“maximum”	To set the value

API CALLs	mounted app ready to be displayed
mounted: function() {
                fetch('https://hplussport.com/api/products/order/price')
                .then(response => response.json())
                .then(data => {
                    this.products = data;
                })
            }
Can write as: 
mounted() {
fetch('https://hplussport.com/api/products/order/price')
                .then(response => response.json())
                .then(data => {
                    this.products = data;
}

Events	v-on:  | @:
v-on:click="cart.push(item)"


Toggle on|off
<button @click=“sliderStatus = !sliderStatus”></button>

TRANSITIONS & ANIMATIONS

https://v3.vuejs.org/guide/transitions-overview.html#transitions-with-style-bindings

To add animation
1. Place <transition> tags around what you want to animate
2. Add name, if statement
3. Add css .name-enter
.fade-enter, .fade-leave-to {
        opacity: 0;
      }
      .fade-enter-active, .fade-leave-active {
        transition: all 1s ease-in-out;
      }

https://daneden.github.io/animate.css/

##TRANSITION-GROUP use for animating lists

      <transition-group name="fade" tag="div">
        <div
        class="row d-flex mb-3 align-items-center"
        v-for="(item, index) in products" 
        :key="item.id"
        v-if="item.price<=Number(maximum)"
        >
      </transition-group>

#TRANSITION-GROUP w/ animate.css library
https://animate.style/

<transition-group name="fade" tag="div"
      enter-active-class="animated fadeInRight"
      leave-active-class="animated fadeOutRight"
      >
        <div
        class="row d-flex mb-3 align-items-center"
        v-for="(item, index) in products" 
        :key="item.id"
        v-if="item.price<=Number(maximum)"
        >
      </transition-group>

