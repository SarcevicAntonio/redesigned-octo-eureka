# as-guis

basically some component examples and [7guis](https://eugenkiss.github.io/7guis/) tasks in [Angular](https://angular.io/), [Next](https://nextjs.org/) ([React](https://reactjs.org/)), [Nuxt](https://v3.nuxtjs.org/) ([Vue](https://vuejs.org/)) and [SvelteKit](https://kit.svelte.dev/) ([Svelte](https://svelte.dev/)).

View live versions for [Angular](https://as-guis-angular.netlify.app/), [Next](https://as-guis-next.vercel.app/), [Nuxt](https://as-guis-nuxt.netlify.app/) and [SvelteKit](https://as-guis-sveltekit.netlify.app/).

View source code for [Angular](/angular), [Next](/next), [Nuxt](/nuxt) and [SvelteKit](/sveltekit).

---

Below I compare component syntax for these technologies.

Character counts done with VSCode with code formatted by Prettier (using tabs) and with as few empty lines as Prettier allows.

Click the name of the technology in the tables to view source of each component.

## Hello World

This is the most minimal component you can make, which lets us closely inspect how the technology deals with components.

|                             | [Angular](/angular/src/app/components/hello-world.component.ts) | [Next](/next/lib/HelloWorld.tsx) | [Nuxt](/nuxt/components/HelloWorld.vue) | [SvelteKit](/sveltekit/src/lib/HelloWorld.svelte) |
| --------------------------- | --------------------------------------------------------------- | -------------------------------- | --------------------------------------- | ------------------------------------------------- |
| character count             | 150                                                             | 57                               | 33                                      | 12                                                |
| component declared as       | Class with `@Component` Decorator                               | Function returning JSX           | SFC (`.vue`)                            | SFC (`.svelte`)                                   |
| component imported [inside] | Class with `@NgModule` Decorator                                | Parent Component                 | Automatically                           | Parent Component                                  |
| self closing tag allowed    | ❌                                                              | ✅                               | ✅                                      | ✅                                                |
| renders wrapper element     | ❌                                                              | ✅                               | ✅                                      | ✅                                                |
| notes                       |                                                                 | Requires Fragment                | Requires `<template>`                   |                                                   |

## [Counter](https://eugenkiss.github.io/7guis/tasks#counter)

Binding of count state in a `<span>` inside the template and handling of click event from button.

|                       | [Angular](/angular/src/app/components/counter.component.ts) | [Next](/next/lib/Counter.tsx)                 | [Nuxt](/nuxt/components/Counter.vue) | [SvelteKit](/sveltekit/src/lib/Counter.svelte) |
| --------------------- | ----------------------------------------------------------- | --------------------------------------------- | ------------------------------------ | ---------------------------------------------- |
| character count       | 266                                                         | 258                                           | 228                                  | 162                                            |
| declaring state       | declaring class property                                    | calling and destructuring `useState` function | calling `ref` function               | declaring variable                             |
| setting state         | mutation of `this.count` class property                     | calling `setCount` function                   | assigning to `count.value`           | assignment to `count` variable                 |
| binding state to view | `{{ count }}`                                               | `{count}`                                     | `{{ count }}`                        | `{count}`                                      |
| adding event listener | `(click)="increment()"`                                     | `onClick={increment}`                         | `@click="increment"`                 | `on:click={increment}`                         |

## [Temperature Converter](https://eugenkiss.github.io/7guis/tasks/#temp)

Bidirectional data flow.

|                 | [Angular](/angular/src/app/components/temperature-converter.component.ts) | [Next](/next/lib/TemperatureConverter.tsx)                                                      | [Nuxt](/nuxt/components/TemperatureConverter.vue) | [SvelteKit](/sveltekit/src/lib/TemperatureConverter.svelte) |
| --------------- | ------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- | ------------------------------------------------- | ----------------------------------------------------------- |
| character count | 547                                                                       | 734                                                                                             | 505                                               | 387                                                         |
| two way binding | `[(ngModel)]="c"`                                                         | none (manually set value on event)                                                              | `v-model="c"`                                     | `bind:value={c}`                                            |
| notes           |                                                                           | can't have undefined initial value<br>ts requires unary plus (`HTMLInputElement.value: string`) |                                                   |                                                             |
