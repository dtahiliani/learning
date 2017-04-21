#Vue.js Notes
This directory holds notes for vue.js as well as files for an online tutorial [Vue.js](https://www.youtube.com/watch?v=vzSjlLzGB1A&list=PLwAKR305CRO_1yAao-8aZiQnBqJeyng4O) Fundamentals by [Dev Marketer](https://www.youtube.com/channel/UC6kwT7-jjZHHF1s7vCfg2CA).
###Vue Tutorial
####Part 3: Directives
Text Directives <br>

* **v-text** ="message"<br>
* **v-html** same as text but will insert actual html
* **v-show**<br>
	-if its true it will display the element, if its false it will hide it<br>
	-reminds in the html, just not visible
* **v-if** removes it from the dom when set to false
* **v-else** follows an if statement and displays if "if" returns false
* **v-pre** doesn't render message, displays brackets
* **v-once** only renders once
* **v-cloak** waits to render until the vue has loaded
* **v-bind** take the data from the data object and bind/link it to attributes in the html<br> -can be represented with only a colon <br>
	- **v-bind:title** vs **:title**
* **v-on** all event handlers handled by v-on directive

	
####Part 4: Looping
#####For Loops
```javascript
<ul>
	<ul v-for="<item> in <listName>">{{ <dataObject>.<itemName> }}</li>
</ul>

<!-- example -->
<body>
	<ul>
		<li v-for="todo in todos">{{ todo.text }}</li>
	</ul>
	<ul>
		<li v-for="count in count">Make More ToDos item#{{ count }}</li>
	</ul>
</body>

<script>
	var app = new Vue({
		el: '#app',
		data: {
			message: 'Hello Vue World',
			todos: [
				{ text: 'Learn Vue' },
				{ text: 'Like the Video' },
				{ text: 'Subscribe to DevMarketer' }
			],
			count: 10
		}
	})
	</script>
```
####Part 6: 2-Way Binding
**v-model** creates two way binding between input and message object/model and the object/model can update the input, ie: data updates the vue, and vue updates the data<br>
MVVM - Model View View Model, a loop that allows you to change the data in either place

```javascript
<body>
	<div id="app">
		<h1>{{ message }}</h1>
		<input type="text" v-model="message" />
	</div>
</body>

<script src="https://unpkg.com/vue@2.1.10/dist/vue.js"></script>

<script>
	var app = new Vue({
		el: '#app',
		data: {
			message: 'Hello Vue World'
		}
	})
</script>
```
####Part 7: Events
Header that outputs the message
Input box bound to message model
When input is updated, it updates the message model, which updates the heading<br>

* **v-on** every event in vue happens with v-on
	- can be repleased with **:** 
	- **v-on:click** is the same as **@click**
	- **v-bind:href=** is the same as simply using **:href=**

####Part 9: Computer Getters & Setters
#####Computed Properties vs. Methods
* computed properties are cashed
* Vue.js cashes computed properties, only runs again when depencies change
* don't need to run function again
* save on api calls
* you can only "get" computed values

#####Getters & Setters

