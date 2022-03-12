# redesigned-octo-eureka

basically some component examples and [7guis](https://eugenkiss.github.io/7guis/) tasks in Angular, Next (React), Nuxt (Vue) and SvelteKit (Svelte).

Character counts done with VSCode with code formatted by Prettier (using tabs) and with as few empty lines as Prettier allows.

## Hello World

This is the most minimal component you can make, which lets us closely inspect how the technology deals with components.

|                      |                           Angular |                   Next |                  Nuxt |       SvelteKit |
| -------------------- | --------------------------------: | ---------------------: | --------------------: | --------------: |
| character count      |                               150 |                     67 |                    33 |              12 |
| declared as          | Class with `@Component` Decorator | Function returning JSX |          SFC (`.vue`) | SFC (`.svelte`) |
| imported (in)        |  Class with `@NgModule` Decorator |              Component |         Automatically |       Component |
| self closing allowed |                                ❌ |                     ✅ |                    ✅ |              ✅ |
| renders wrapper      |                                ❌ |                     ✅ |                    ✅ |              ✅ |
| Notes                |                                   |      Requires Fragment | Requires `<template>` |                 |

## [Counter](https://eugenkiss.github.io/7guis/tasks#counter)

Binding of count state in a `<span>` inside the template and handling of click event from button.

|                       |                                 Angular |                                          Next |                       Nuxt |                      SvelteKit |
| --------------------- | --------------------------------------: | --------------------------------------------: | -------------------------: | -----------------------------: |
| character count       |                                     150 |                                            67 |                         33 |                             12 |
| declaring state       |                declaring class property | calling and destructuring `useState` function |     calling `ref` function |             declaring variable |
| setting state         | mutation of `this.count` class property |                   calling `setCount` function | assigning to `count.value` | assignment to `count` variable |
| binding state to view |                           `{{ count }}` |                                     `{count}` |              `{{ count }}` |                      `{count}` |
| adding event listener |                 `(click)="increment()"` |                         `onClick={increment}` |       `@click="increment"` |         `on:click={increment}` |
