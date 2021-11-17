Vue3 Form with Slots
---

### [DEMO](https://vue3-form-slots.vercel.app)

-----

## [Slots](https://v3.ru.vuejs.org/ru/guide/component-slots.html)

Add ability to use data from a parent App component.

No need to pass it down like a prop (alternative).

## [Dynamic components](https://v3.ru.vuejs.org/ru/guide/component-dynamic-async.html)

Components that can be swapped with another components.

## [Animations](https://v3.ru.vuejs.org/ru/guide/transitions-enterleave.html)

```html

<transition name="fade">
    <p v-if="show">fade in</p>
</transition>
```

> The v-enter transition class has been renamed to v-enter-from and the v-leave transition class has been renamed to v-leave-from. [link](https://v3.vuejs.org/guide/migration/transition.html#overview)

```css
.v-enter-from,
.v-leave-to {
    opacity: 0;
}

.v-leave-from,
.v-enter-to {
    opacity: 1;
}
```

Animation Hooks:

* before-enter
* enter
* after-enter
* before-leave
* leave
* after-leave

## [Web Animations API](https://developer.mozilla.org/ru/docs/Web/API/Web_Animations_API)

* [Using the Web Animations API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Animations_API/Using_the_Web_Animations_API)

## [Animate.css](https://animate.style)

* [public/index.html](public/index.html)
* `<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css" referrerpolicy="no-referrer" />`
* [https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css](https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css)

----- 

## Project setup

```
yarn install
```

### Compiles and hot-reloads for development

```
yarn serve
```

[Localhost](http://localhost:8080)

### Compiles and minifies for production

```
yarn build
```

### Lints and fixes files

```
yarn lint
```

### Customize configuration

See [Configuration Reference](https://cli.vuejs.org/config/).
