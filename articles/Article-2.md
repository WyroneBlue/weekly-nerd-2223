# Modern Modals

## Introduction
During the weekly nerd of Hidde de Vries, I learned about the HTML Dialog element. This element is used to create modals in HTML. In this article, I'll explain what a modal is, how to use the dialog element, and its benefits.

## What is a Modal?
In web development a modal is a term for a box or a popup that appears on top of a webpage. It's used to display additional content or gather user input, by temporarily blocking the rest of the page and focusing the user's attention on the modal.

This can be used for example to show a login form, to show a larger version of an image, show warnings or errors, or to show a confirmation message.

It can sometimes also be annoying, for example when you're browsing a website and suddenly a modal pops up asking you to subscribe to their newsletter. But when used correctly, it can be a great tool to improve the user experience.

## Modals in the past
In the earlier days of web development, creating modals was quite the puzzle for developers. They had to rely on JavaScript and a dash of HTML and CSS magic to achieve the desired effect. It required writing complex code to handle the modal's behavior, animations, and making it responsive across different devices. 

Example of a modal in the past:
**HTML**
```html
<!-- Modal structure -->
<div id="modal" class="modal">
  <div class="modal-content">
      <!-- Modal content goes here -->
  </div>
</div>
```

**CSS**
```css
  /* Styling to get the modal fullscreen */
  display: none;
  position: fixed;
  z-index: 9999;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  overflow: auto;
  background-color: rgba(0, 0, 0, 0.5);
```

**Javascript**
```javascript
// Get the modal element
var modal = document.getElementById("modal");

// Function to open the modal
function openModal() {
  modal.style.display = "block";
}

// Function to close the modal
function closeModal() {
  modal.style.display = "none";
}
```
And this is just the basic structure. If you want to add animations, responsiveness, and other features, you'll need to write even more code.

But then, the HTML Dialog element came to the rescue!

## Introducing the HTML Dialog Element:
The HTML Dialog element is a built-in element in HTML5 that simplifies the creation of modals. Using the dialog element, you can create modals without writing much JavaScript code. It comes with a set of built-in methods that handle the modal's behavior, and it's responsive by default.

Things like close on escape, backdrop and being on the top layer are all handled by the browser. This means that you don't have to worry about these things anymore.

### How to Use the Dialog Element:
To implement dialog element, we need to follow a few simple steps. Let's walk through them step by step:

#### 1. HTML Structure:
We start by creating a button or a link that triggers the modal. We'll assign it a unique ID, like this:

```html
<button id="openModal">Open Modal</button>
```

#### 2. The Modal:
Next, we need to define the dialog element itself. It's recommended to enclose it within the main HTML structure, like this:

```html
<body>
    <main>
        <!-- Main content goes here -->
    </main>

    <dialog id="modal">
        <h2>Welcome to My Modal!</h2>
        <p>This is some cool content inside the modal.</p>
        <button id="closeModal">Close Modal</button>
    </dialog>
</body>
```

!!! note Body
    Make sure the dialog element is placed inside the body element instead of the main liek in the example above.

#### 3. JavaScript Magic:
Now, it's time to add some JavaScript code to handle the modal's behavior. We'll use the `showModal()` and `close()` methods to control its visibility:

```javascript
const openModalBtn = document.getElementById('openModal');
const closeModalBtn = document.getElementById('closeModal');
const myModal = document.getElementById('myModal');

openModalBtn.addEventListener('click', () => {
  myModal.showModal();
});

closeModalBtn.addEventListener('click', () => {
  myModal.close();
});
```

#### Exras

##### Close with form
To open the dialog you **currently** need javascript. But you are able to close the diaog with a form. This is done by adding a submit button to the form and adding the `method="dialog"` attribute to the form.

```html
<dialog open>
  <p>Greetings, one and all!</p>
  <form method="dialog">
    <button>Close dialog</button>
  </form>
</dialog>
```

##### Styling backdrop
The backdrop is the overlay that is shown behind the dialog. This is done by adding the `::backdrop` pseudo-element to the dialog element. This can be styled like any other element.

```css
dialog::backdrop {
  background-color: rgba(0, 0, 0, 0.5);
}
```

And there you go! You've successfully created a modal using the dialog element. Easy, right?

## Conclusion:
The dialog element is a great addition to HTML5. It makes creating modals much easier, and it's responsive by default. It's supported by all major browsers.

The dialog will be my go to starting point for creating modals from now on. It's easy to use, and it saves a lot of time and effort. Especially with the built-in features it comes with.
I hope you'll find it useful too!

## Sources:
- [HTML Dialog Element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dialog)
- [Logrocket](https://blog.logrocket.com/using-the-dialog-element/)