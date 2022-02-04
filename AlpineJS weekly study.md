# TIL

## Jan 20, 2022
`$dispatch` alpine magic to dispatch browser events 
```html
<div @alertPopUp="alert($event.detail.message)">
    <button @click="$dispatch('alertPopup', { message: 'insert message to show' })">
        Show Pop-up Message
    </button>
</div>
```
due to event bubbling, use `eventName.window` if elements are siblings
```html
<div x-data>
	<div @alertPopUp.window="alert($event.detail.message)"></div>
    <button @click="$dispatch('alertPopup', { message: 'insert message to show' })">
        Show Pop-up Message
    </button>
</div>
```

## Jan 21, 2022
Two ways to install alpinejs
(1) from script tag
(2) via npm

## Jan 27, 2022
`x-data` defines an html section as an alpine component
```html

<div x-data="{ open: false }"> <!-- initial state "open"-->
    <button @click="open = ! open">Toggle Content</button> <!-- toggle initial state "open" from true to false and vice-versa -->
 
    <div x-show="open"> <!-- show this div based on the value of "open" if open = true then show; if open = false then hide -->
        This would show or hide depending on the value of open
    </div>
</div>
```

## Jan 28, 2022
methods can be stored inside `x-data`
```html
<div x-data="{ open: false, toggle() { this.open = ! this.open } }"> <!-- toggle method changes "open" state from false to true and vice-versa -->
    <button @click="toggle()">Toggle Content</button> <!-- call toggle method inside x-data initial data -->
 
    <div x-show="open">
        This would show or hide depending on the value of open
    </div>
</div>
```

## Feb 3, 2022
listen for simple events
```html
<button x-on:click="console.log('this will run when this button element is clicked')">Click Me!</button>
or 
<button @click="console.log('this will run when this button element is clicked')">Click Me!</button>

```
listen for specific keys
```html
<input @keyup.enter="console.log('this will run when you are inside this element and press enter')">
```
prevent default
```html
<form @submit.prevent="console.log('when clicking button type submit inside this form element, default behavior which is form submission will be prevented')">...</form>
```

## Feb 4, 2022
`x-init` will execute when element is initializes
```html
<button x-init="alert('button element initialized!')">
```

`$watch` execute code when a state changes. pass the old value and new value
```html
<!-- when "open" state changes, its previous value and new value will be logged in the console -->
<div x-data="{ open: false }" x-init="$watch('open', value => console.log(value))">
```

`x-effect` execute code when a state changes. pass the old value and new value
```html
<!-- console.log() will execute before and everytime "open" state changes, its value will be logged in the console but not the previous value -->
<div x-data="{ open: false }" x-effect="console.log(open)">
```


