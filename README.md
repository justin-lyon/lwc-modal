# lwc-modal

A drop-in Lightning Web Component modal.

## Slots

 1. header
 1. default
 1. footer

## Demo

## Usage

myComponent.html
```html
<template>
  <button onclick={toggleModal}>toggle modal</button>

  <c-modal is-shown={isShown}
    onclose={handleClosed}>

    <div slot="header">my header</div>

    <!-- content here goes to the default (body) slot -->
    body

    <div slot="footer">my footer</div>
  </c-modal>
</template>
```

myComponent.js
```javascript
import { LightningElement, track } from 'lwc'

export default class MyComponent extends LightningElement {
  @track isShown = false

  toggleModal () {
    this.isShown = !this.isShown
  }

  handleClosed () {
    this.isShown = false
  }
}
```