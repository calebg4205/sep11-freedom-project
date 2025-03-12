# Entry 3
##### 03/12/25

### Context

Over the last month i have been working on my understanding of react and Node.js. I completd my book keeping project with relativly eaily. Creating objects and keys made me better at undetstanding how to reuse code. Sadly the computer I hosted the project on got curropted and I had to recycle it. Now I am working with how to reintergrate code so it is usable. In order to do this I began with [Bro Codes react video](https://www.youtube.com/watch?v=CgkZ7MvWUAA) for a solif fondation. I worked on trying to understand how both on them work together. I know that Node.js works to create a backend server which can handle requests. React seems to work on the frontend and making it easier to write less code. Working on this for the last month has persented me with a lot of challenges.

### Challenge 1: understanding and processing requests between the frontend and backened

When trying to build a framework for me and Jacob's project I wanted to create reusable compnents we will defenitley use. While making simple things like buttons, and boxes, I ran into the problem our processing requests. I want the buttons to do something but when the frontend button is clicked it needs to travel to the backend. This confused me. After spending some time on the React doccumentation I came across [UseState](https://react.dev/reference/react/useEffect). Usestate allows the button to be update dynamically without having to refresh the whole page. I decided to try it,


```js

import { useState } from 'react'

function NumberGoesUp() {
  const [plus, counting] = useState(0)

  return (
    <div>
      <p>Count: {plus}</p>
      <button onClick={() => counting(plus + 1)}>Increment</button>
    </div>
  )
}

export default NumberGoesUp

```

What this does is it creates a reusbalbe component that adds 1 to a button on click. When I wrote this I sturggled at first with the `onClick` but when I learned DOM it became a much easier process. When I set `useState(0)` that means the hook will always start at 0. Next time I reuse the function it will have the same effect even on diffrent pages. Learning [hooks](https://react.dev/reference/react/hooks) really opened up react for me. I could offically make a bunch of compenents with less code and have more time to make m webpage better.


### Challenge 2: Understaning component re-rendering and and updating states



[Previous](entry02.md) | [Next](entry04.md)

[Home](../README.md)
