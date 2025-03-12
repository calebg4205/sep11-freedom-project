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
      <button onClick={() => counting(plus + 1)}>Cheese</button>
    </div>
  )
}

export default NumberGoesUp

```

What this does is it creates a reusbalbe component that adds 1 to a button on click. When I wrote this I sturggled at first with the `onClick` but when I learned DOM it became a much easier process. When I set `useState(0)` that means the hook will always start at 0. Next time I reuse the function it will have the same effect even on diffrent pages. Learning [hooks](https://react.dev/reference/react/hooks) really opened up react for me. I could offically make a bunch of compenents with less code and have more time to make m webpage better.


### Challenge 2: Understaning component re-rendering and and updating states
Compononets are peices of reusable code that can be edidted in the file to match the information. Bascially they are super dynamic and usper useful when coding in Javascript. Instead of manually constantly remaking buttons I can simply call the function. React uses the Virtual DOM (Light weight copy of the real DOM) to render based on states. When I was using states I struggled to make it render correctly. When I make something on the orginal DOM react will change it based on the context. I used ChatGPT to help em understand this concept,

![Febuary 15th Screenshot ](image-2.png)

Now, I wass untill a little bit confused so i started trying to apply it. My earlier example worked because the DOM will constantly re-render. It will make a comparison between the Virtual and real DOM. React is so effiecent becasue it avoids any unnessary rendering making the webpage even faster.

### Engineering design process

At this point in the EDP I am ready to move into making a prototype. I want to start applying my knowlwge not only about Code but also about immigration. This weekend I will begin to work on creating the app and applying my knowlege. I plan to combine my frontend knwoeleg woth my partner who built the translation API.

### Skills

1. **Learning to be stuck**: There were multile times I stuggled with understanding the material. Watching videos and reading articles still didn't help me unserstand. When I was trying to tinker I didn't even know where to start. I tried so hard to force myself to now the answer. After like a week i decided to take a break. I went back to the basics and tried to help myself understand it is ok not know everything. I was beggingng to feel frustarted by the confusing langauge in the docs but I decided to try and look for other sources. I used AI to help break down complex comcepts and went back to the basics or parts of Bro Codes's videos if I was stuck. The idea of not knowing something scared me and beign stuck made me angry. Still when I accpeted I was stuck I was able to backtrack and re learn concepts
2. **Staying Focused**: This not only applied to actually sitting down and doing my work but also while doing my work. The react doccumetation is filled with so muhc cool information. When I didn't understand what it was refrencing I would go down a rabbit hole trying to understand a topic I don't need. I learned that videos often help me learn more becasue they are structred. The docs made me intrigued but I would get side tracked on smaller parts of React I probably didn't need to know.






[Previous](entry02.md) | [Next](entry04.md)

[Home](../README.md)
