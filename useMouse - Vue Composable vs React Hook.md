# `useMouse` - Vue Composable vs React Hook

Vue:
```js
export function useMouse() {
  const x = ref(0)
  const y = ref(0)

  function update(event) {
    x.value = event.pageX
    y.value = event.pageY
  }

  onMounted(() => window.addEventListener('mousemove', update))
  onUnmounted(() => window.removeEventListener('mousemove', update))

  return { x, y }
}
```

React:
```js
export function useMouse() {
  const [position, setPosition] = useState({ x: 0, y: 0 });

  useEffect(() => {
    function update(event) {
      setPosition({
	    x: event.pageX,
	    y: event.pageY
	  });
    }
	
    window.addEventListener('mousemove', update);
    return () => {
      window.removeEventListener('mousemove', update);
    };
  }, []);
  
  return position;
}
```
