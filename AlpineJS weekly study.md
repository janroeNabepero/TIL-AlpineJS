# TIL

Jan 20, 2022
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

Jan 21, 2022
Two ways to install alpinejs
(1) from script tag
(2) via npm

Jan 27, 2022
`x-data` defines an html section as an alpine component
```html

<div x-data="{ open: false }"> <!-- initial data "open"-->
    <button @click="open = ! open">Toggle Content</button> <!-- toggle initial data "open" from true to false and vice-versa -->
 
    <div x-show="open"> <!-- show this div based on the value of "open" if open = true then show; if open = false then hide -->
        This would show or hide depending on the value of open
    </div>
</div>
```


