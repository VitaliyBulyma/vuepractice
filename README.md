# Read the documentation!
Follow along with the [official documentation for Vue.js](https://vuejs.org/v2/guide/)

## Asynchronous Activities
Asynchronous activities mean you can complete them at your own pace. More exercises will be added as the course progresses.

## Reflect!
You have a weekly reflection for HTTP5302. If you aren't sure what to talk about, talk about some of these exercises!
# My Progress
[x] Lesson 1
  #### What I learned
    - Need to include vue.js file to work: <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
    - Use this syntax to introduce variable message - {{message}}
    - Craeate a new instance of Vue, and pass options
    el: which is an element selected, and data: which contains the variables
    
````JS
    	var app = new Vue({
		el: '#app',
		data:{
			message: 'Do not go gently into that good night'	
		}
	});
  
````
  
[x] Lesson 2

  #### What I learned
    - v-bind:<name of an HTML attribute>="<name of the variable>"

    
````JS
		<p v-bind:class="loadClass">
			look at me!
		</p>
		<img v-bind:src="imgSrc"
			v-bind:alt="imgAlt"
			v-bind:title="imgTitle">
	</div>

	<script>
		var app = new Vue({
			//Bind Vue object to HTML element through query selector
			el: document.querySelector('#app'),
			data: {
				loadClass : 'container highlight',
				imgSrc:'img/bird-s-eye-view-photography-of-road-in-the-middle-of-desert-1201673.jpg',
				imgAlt: 'bird-s-eye-view-photography-of-road-in-the-middle-of-desert',
				imgTitle: 'bird-s-eye-view-photography-of-road-in-the-middle-of-desert'

			}
		});
	</script>
  
````
  
[] Lesson 3

[] Lesson 4

[] Lesson 5

[] Lesson 6

[] Lesson 7
