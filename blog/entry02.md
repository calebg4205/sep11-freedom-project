### Entry 2  
##### 12/15/24  

### Context  

After setting up Node.js, I focused on understanding how it works. What really helped was realizing that **Express.js** and **Node.js** are not standalone tools; they are usually paired with a frontend framework. So, to expand my knowledge, I also started learning **React Native** for the frontend and **Next.js** as a framework. As for Express.js, I dove into how the backend works—it essentially sends information to the frontend through return statements. The routing is key to delivering the webpage to the user, typically from the server side, which can sometimes take a long time to load. By using libraries, we can speed this up with optimization, allowing the server-side content to load faster. So, I began focusing on understanding how optimization works.  

### Challenge 1: Building with Express.js and Other Frameworks  

After reading the [documentation](https://expressjs.com/), I realized that the best way to learn was through hands-on practice. So, I decided to build a book sorter app—pretty simple, but effective. I started with Express.js for the backend and Next.js for the frontend. Here's the starter code I used:  

```js  
const express = require('express');  
const bodyParser = require('body-parser');  

const app = express();  
const PORT = 3000;  

app.use(bodyParser.json());  
app.use(bodyParser.urlencoded({ extended: true }));  

app.get('/', (req, res) => {  
  res.send(`  
  `);  
});  
```

At first, I struggled with understanding how the frontend gets returned. Initially, I was confused as to why my HTML file wasn’t connecting. But after some reflection on how return functions work, it clicked. I realized that returning the content according to the rules of routing would render it on the webpage. With this understanding, and after watching [this video](https://www.youtube.com/watch?v=0Hu27PoloYw), I was able to build a simple webpage. The constant tinkering and hands-on work with the project was incredibly helpful in reinforcing my learning.

### Challenge 2: Making the Book App  

Building the actual app required a lot of moving parts, starting with the backend. Here’s the process I followed:

1. I needed to create "keys" to store information.  
2. I had to organize the information in a way the computer could understand.  
3. I needed to create a search function so the user could find the books.  
4. Finally, I had to create a frontend to display everything.  

Thinking through the process, I began with creating the keys. I learned about keys from my friend [Phizy](https://phizy.dev/). Then, I created the keys and serial numbers for each book. Here's the code for that:

```js
let books = [  
  { id: 1, title: 'The Great Gatsby', author: 'F. Scott Fitzgerald', year: 1925 },  
  { id: 2, title: 'To Kill a Mockingbird', author: 'Harper Lee', year: 1960 },  
  { id: 3, title: '1984', author: 'George Orwell', year: 1949 },  
];  

// In another function  

// Generate serial number  
Math.floor(Math.random() * 1000000000)  
```

Thinking critically through each part of the process helped me piece everything together. Building the book app really taught me a lot about rendering data and implementing a search function.

### Engineering Design Process  

I’m currently in the second stage of the Engineering Design Process (EDP). I’m doing background research to prepare for building my own translator app. This app could help a lot of people, but I need to understand the mechanics behind it before I can start building. Next, I plan to do more research into APIs and how to integrate them into my app.

### Takeaways  

* **Plan Before Building:** Creating a solid plan made a huge difference in how quickly and effectively I was able to learn and build. Even while learning, having a clear roadmap helped me understand the concepts better. I also learned that I work best through "trial by fire"—building and planning really help me work through bugs and kinks more efficiently.  
* **Drawing Diagrams is Helpful:** When rendering, connecting the frontend to the backend can be a bit tricky. Drawing diagrams of the process helped me visualize how things were connected, and this made everything clearer and easier to understand.

[Previous](entry01.md) | [Next](entry03.md)

[Home](../README.md)
