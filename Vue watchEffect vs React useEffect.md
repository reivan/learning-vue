# Vue `watchEffect` vs React `useEffect`

Vue's [`watchEffect`](https://vuejs.org/guide/essentials/watchers#watcheffect) is probably the closest thing to [`useEffect`](https://react.dev/reference/react/useEffect):
```js
watchEffect(async () => {
  const response = await fetch(
    `https://jsonplaceholder.typicode.com/todos/${todoId.value}`
  )
  data.value = await response.json()
})
```

In React:
```js
useEffect(() => {
  async function fetchTodo() {
    const response = await fetch(
      `https://jsonplaceholder.typicode.com/todos/${todoId}`
    )
    const data = await response.json()
	
	setData(data)
  }
  
  fetchTodo()
}, [todoId])
```

Notes:

- in Vue deps are tracked by reactivity
