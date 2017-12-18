```jsx
// Bad
<ul>
  <li>A</li>
  <li>B</li>
  <li>C</li>
  <li>D</li>
<ul>

// Good
<ul>
  {
    ['A', 'B', 'C', 'D'].map((alphabet)=>
      <li key={alphabet}>{alphabet}</li>
    )
  }
<ul>
```
