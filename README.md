# Learning Vue

Some notes on Vue and how it compares to React.

### Looks similar
```
Vue               ~    React

ref(0)            ~    useState(0)
watchEffect()     ~    useEffect()
composables       ~    hooks
provide/inject    ~    context
useTemplateRef    ~    useRef
```

### Code reuse
	components = main
	composables = stateful logic
	custom directives = low-level DOM logic
	plugins = global stuff

### Vue Likes
- Vue uses compile-time optimizations
- Vue is more ergonomic
- Vue has great documentation
- Vue has nice ecosystem: vite, pinia, official router, vitest, volar, devtools, nuxt
- Vue source code is very readable

### Types
- Vue types are in the main repo; React's are in DefinitelyTyped

### New Level of Abstraction
- In React people write render functions directly,
	in Vue people write templates that get compiled to render functions
	= +1 level of indirection / abstraction
- Vue uses compile-time macros to define component props
- Options API props are more explicit

### Reactivity
- Vue's reactivity is decupled from components, unlike React's state
- Vue's reactivity makes things more implicit

### Build
- Vue can be used without a build tool
- Vue docs list many justifications for a build step
- components feel like a big deal in Vue docs, why?

### Events
- why does a child communicate with the parent via Events?
- in React people use callback props to communicate child => parent
- is it only the direct parent can react to its child's event in vue? Yes

### Global
- Vue global component registration is wierd
- why does Vue even have an option for global component registration?
- Vue allows many ways for global variables to be declared: maintainability?

This is looks 😐:
```html
<div v-example:foo.bar="baz">
```
custom directive + argument + modifier

### Footer

Anyway, many different decisions with pros and cons. Like both.
