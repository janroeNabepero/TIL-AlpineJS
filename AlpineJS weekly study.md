# TIL

Jan 20, 2022
`$dispatch` alpine magic to dispatch browser events 
```js
<div @alertPopUp="alert($event.detail.message)">
    <button @click="$dispatch('alertPopup', { message: 'insert message to show' })">
        Show Pop-up Message
    </button>
</div>
```
due to event bubbling, use `eventName.window` if elements are siblings
```js
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




