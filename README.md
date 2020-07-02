# HTTP-5302-0NA Instructor: Christine Bittle

## Game created using Vue.js Framework (index.html)
	> code reference Christine Bittle

![BattleShip Gameboard](/img/battleship.jpeg)
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
[x] Lesson 6

#### What I learned

		v-on:event_handler="method_name(?arg1, ?arg2..)"
		
		You can use v-on to attach events directly to elements, similar to regular HTML and JS
		There must be a matching method name inside the "methods" property, which is a sibling to the "data" property.
		You can pass in extra information with optional parameters if you wish
		"this" will evaluate to the app object when used in the context of a method.
		
		can chain v-on events, order of events does matter

````JavaScript

		<div v-bind:style="{height : y + 'px'}" class="red-box"
			v-on:mouseover="growBox();"
			v-on:click="shrinkBox();"
			v-on:click.right.prevent="rightClick();" >
		</div>

----------------------------		
		<button v-on:click="showhide();">Click</button>	

		methods:{
			showhide : function(){
				console.log(this.boxHidden);
				if(this.boxHidden){
					this.boxHidden=false;
				}else{
					this.boxHidden=true;	
				}
			}


````

[x] Lesson 7

#### What I learned

	reusable components
	Each component can be customized with the use of "props" (properties).
	The Markup scaffolding is included in the template.	
	The components can have methods as well! The prompt function also can change the component properties	
	Components may also have a data property, just like the app.

````JavaScript

<div id="app">
		<orb v-bind:radius="40" v-bind:color="'white'"></orb>
		<orb 
			v-for="orb in orbs"
			v-bind:radius="orb.radius"
			v-bind:color="orb.color"
			v-bind:left="orb.left"
			v-bind:top="orb.top"
			v-bind:key="orb.id">
		</orb>
	</div>
	
	<script>
	Vue.component('orb',{
		props:['radius','color','left', 'top'],	
		template:
		`<span 
			v-bind:class="'circle'" 
			v-bind:style="{'width':radius+'px', 'height':radius+'px', 'background':color, 'left':left+'px','top':top+'px'}"
			v-on:click="prompt();">
		</span>`,
		methods:{
			prompt:function(){
				alert('You clicked the '+this.color+' circle!');
				console.log(this.top);	
				this.color='none';
			}	
		}
	
	});
	
	var app = new Vue({
		el: '#app',
	
		data:{
			
			orbs:
			[
				{id:1, radius:10, color:'green', top:56, left:100},
				{id:2, radius:15, color:'purple', top: 40, left:300},
				{id:3, radius:20, color:'black',top: 140, left:200},
				{id:4, radius:25, color:'blue',top: 340, left:800},
				{id:5, radius:30, color:'orange',top: 220, left:100},
				{id:6, radius:35, color:'yellow',top: 540, left:20},
				{id:7, radius:45, color:'red',top: 75, left:654}
			],

		}
	});
	</script>
````


