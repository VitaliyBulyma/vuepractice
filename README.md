# HTTP-5302-0NA Instructor: Christine Bittle

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
  
[x] Lesson 3
  #### What I learned
    - 		A boolean expression evaluates to true or false.
		Examples
		True => True
		False => False
		True && True => True
		True && False => False
		True || False => True
		False || False => False
    - 		Truthy or falsy values
    		Examples
		'Hello' => True
		'' => False
		211 => True
		0 => False
		-192 => True
		null => False

    
````JS
	<div id="app">
		<span v-bind:class="{special:isSpecial, important:isImportant}">
			look at me!
		</span>
	</div>
	
	<script>
	var app = new Vue({
		el: '#app',
		data:{
			isImportant:true,
			isSpecial: false
		}
	});
	</script>
  
````

[x] Lesson 4

#### What I learned

    - If else statements
    		v-if="boolean_expression"
		v-else-if="boolean_expression"
		v-else
    
   
````JavaScript

	<div id="app">
		<span v-if="profile">
			Profile of {{profile.fname}} {{profile.lname}} 
		</span>
		<span v-else>
			No Profile Data found.
		</span>
	</div>
	
	<script>
	var app = new Vue({
		el: '#app',
		
		data:{
			
			profile:{
				fname: "John",
				lname: "Doe"	
			}
			
		}
		
	});
	</script>

````

````JavaScript
	<p class="card-text" v-if="profile.bio">{{profile.bio}}</p>
	<p class="card-text" v-else-if="profile.bio === ''">Author did not write bio</p>
	<p class="card-text" v-else>Profile bio is not available</p>

````

[x] Lesson 5

#### What I learned

    - Loops in Vue.js
    
    - Structure of object with arrays and array of obects inside array
    
````JavaScript

<ul>
	<li v-for="part in scene">
		<span>{{part.character}}</span>
		<p>{{part.dialogue}}</p>
	</li>
</ul>

data:{
//Scene from http://shakespeare.mit.edu/macbeth/macbeth.1.7.html
	scene:[
		{character:'MACBETH', dialogue:"Hath he ask'd for me?"},
		{character:'LADY MACBETH', dialogue:"Know you not he has?"},
		{character:'MACBETH', dialogue:"We will proceed no further in this business:\nHe hath honour'd me of late; and I have bought\nGolden opinions from all sorts of people,\nWhich would be worn now in their newest gloss,\nNot cast aside so soon."},
		{character:'LADY MACBETH', dialogue:"Was the hope drunk\nWherein you dress'd yourself? hath it slept since?\nAnd wakes it now, to look so green and pale\nAt what it did so freely? From this time\nSuch I account thy love. Art thou afeard\nTo be the same in thine own act and valour\nAs thou art in desire? Wouldst thou have that\nWhich thou esteem'st the ornament of life,\nAnd live a coward in thine own esteem,\nLetting 'I dare not' wait upon 'I would,'\nLike the poor cat i' the adage?"}	
	]

}

````
````JavaScript
var temp ={
	character:'MACBETH',
		dialogue:[
			{line:"Prithee, peace:"},
			{line:"I dare do all that may become a man;"},
			{line:"Who dares do more is none."}
			]
	};
app.scene.push(temp);

````
[] Lesson 6

[] Lesson 7
