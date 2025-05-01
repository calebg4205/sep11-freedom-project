# Entry 5

#### 04/30/25

### Context

As I began to work on my freedom project I was terrified. I didn't know if I knew enough React and logic for the job. Still, I knew I had to begin prototyping. So I got to work. I wanted to design a sleek app, so I began working. I made the easy things first things I could copy and paste from my testing. The first thing you have to do with React is organize your file structure. So I created my `src` file and then a `components` file. Inside the components file I made some buttons and the navbar. So I was set up with the basic setup. I created a hero component and then I had the basic design.

![image](https://github.com/user-attachments/assets/2978fca9-ffb3-4bad-83e9-d4742d68fe12)

Now came the hard part. I had to make the translation work.

### Challenge 1: Translating the page

So to create my MVP I had to translate one quote. The simple:"We are and always will be a nation of immigrants. We were strangers once, too." — Barack ObamaTo code this I needed to think through the process logically.

1. I had to get the quote so I had to make it some sort of variable
2. Then I had to pass it through my partner’s API to translate
3. I had to print the translated version on the page

So I decided to split it into parts.

#### Part 1: Getting the quote

So in React I couldn't simply create a variable with the quote name. I had to use an i18next built-in function:
```js
{t("quote")} - Barack Obama
```
In this piece of code, two things are happening. The quote is being stored, and i18next now knows to translate the quote. All it needs next is the language to translate to. So in the `locales` folder I added the languages. I had to use something called a `.json` file. This is like a set of rules for the computer to use. It can look in the JSON file for instructions and data. So adding the translation in the `.json` made it so these rules were followed by the computer:
```js
{
  "hello": "¡Hola!",
  "quote": "Somos y siempre seremos una nación de inmigrantes. También éramos extraños.",
  "picklang": "Por favor seleccione un idioma"
}
```
Here in the "quote" you can see the object that is the quote. So the quote is in the language we want to translate it to. Then when the button is clicked, the t will tell the computer to translate the page. So we have it stored in a variable. But next we need to pass it through translation to make sure it works.

#### Part 2: Making sure the translation works

So first we need to go to the backend folder to check how the API works. Depending on where the user's IP is, the language should translate. Now we need to make sure that the API is recognized using API endpoints and fetch. So we connect the `initI18n.js` to the VITE_BACKEND. Then we have to write out some logic to make this code work. First we call the API, then we write the logic:
``` ja
try {
  const response = await fetch(`${VITE_BACKEND_API_URL}/fetchlanguage`);
  const data = await response.json();
  const lang = data.region;
```
So the first thing we want the computer to do is try and fetch the language. Then we pause the code for a minute as we wait for the API to send a response. That should get the region, which we can then return. So we have to wait for the region, which is the important part. This is followed up by error handling in case we can't get the region. Then we can print 404. We also get the language ready to send out based on the region.

How I imagine it is: before someone goes down a water slide, you have to wait for the person ahead of you to go first. So we got the info we need—which is like getting into the water slide line. But on the line we have to wait for the lifeguard to say go, which is the await. Then when the lifeguard makes sure the guy is at the bottom, you can go. Sending the language to the frontend. The lifeguard at the bottom catches you and helps you out. Which is our frontend.

#### Part 3: Printing the language

So now our API checks the region. But we also want the user to be able to switch the language manually. That was the first part. All that's left is testing to make sure the language gets switched. So we go onto our website and we click the button component.

![image](https://github.com/user-attachments/assets/cb3da948-687d-4f0d-9d89-aa4c8bbf32d9)

Sure enough, the dropdown menu comes up and we can switch the language. But at first, we had a big problem. For some reason, this manual switching would only work on [Tor](https://www.torproject.org/download/). So for a week I looked through the logic, looking for any error. Me and my partner couldn't find the bug until we asked [Phizy](https://github.com/phizyts) for help. He was able to look through our logic and saw that we had an override in the code:

```js
if (lang === "us") {
  return;
}
```
This simple line we had used for testing was at the top of our file. So the code was being overrun by trying to return English. Which meant manual switching only wanted to return English. No matter what. I deleted this line and the code worked. Leading to our MVP being finished.

Link to project: [Immigration app](https://ip-immigration-website-frontend.vercel.app/)

### Engineering Design Process

At this stage in the EDP I am ready to continue prototyping. Now that we can translate, I want to add more content to the app. This app was incredibly difficult to make translate, but now that it works, we can begin with content. I want to reuse my components and use React to the fullest.

### Skills

***Don't be afraid to ask for help*** – Help is a necessary part of coding. At first I was embarrassed to have to ask a third party for help. Phizy (our real-life friend) was able to debug our code. I felt ashamed to have to ask him, but it was necessary. Using the resources around you and the people around you can be a big help—especially in big projects like our freedom project!

***Always have a plan*** – Planning beforehand saved me on this project. I knew what I wanted to make and was able to do research on the logic I needed. Also, it is very helpful to put code in pseudo-code to understand what I want to do. Talking like that to myself got me out of many tough spots. I was able to use “rubber duck” debugging to save myself. Whenever I got lost, I could always remember my plan!


[Previous](entry04.md) | [Next](entry06.md)

[Home](../README.md)
