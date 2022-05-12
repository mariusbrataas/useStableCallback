# useStableCallback

A substitute for [`useCallback`](https://reactjs.org/docs/hooks-reference.html#usecallback) that returns a memoized version of whatever callback that it is given.

The returned function maintains a stable reference, but **it will always have accesss to the most recent scope of the component in which it is used.**

```tsx
function MyComponent({ url }: { url: string }) {
  const refreshData = useStableCallback(() =>
    fetch(url, { method: 'GET' }).then(r => r.json())
  );

  return <SomeChildComponent refresh={refreshData} />;
}
```
