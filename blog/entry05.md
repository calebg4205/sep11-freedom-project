# Entry 5
##### 04/30/25

### Context

As I began to work on my freedom project I was terrified. I didn't know if I knew enough react aand logic for the job. Still I knew I had to beign protoytping. So I got to work. I wanted to desoign a sleak, So I began working. I made the easy things first. Things I could copy and paste from my testing. The first thign you have to do with react is organize yyour file structure. So I created my `src` file and then a `componenets` file. Insdie the compenents file I made some buttons and the narbar. So I was set up with the basic setup. I created a hero compnenet and then I had the basic deign. 


![image](https://github.com/user-attachments/assets/2978fca9-ffb3-4bad-83e9-d4742d68fe12)



 Now came the hard part. I had to make the translation work.

 ### Challenge 1: Translating the page

 So to create my MVP I had to translate one quote. The simple "We are and always will be a nation of immigrants. We were strangers once, too." - Barack Obama. To code this I needed to think thorugh the process logically.

1. I had to get the quote so I had to make it some sort of varible
2. Then I had to pass it rhough my partners API to translarte
3. I have to print the translated version on the page

So I decided to split it into parts

#### Part 1: Getting the quote

So in react I couldn't simply create a varible with the quote name. I had to use an i18next built in function.

```js

{t("quote")} - Barack Obama
```

In this peice of cide 2 things are happening. The quote is being stored and the i18next now knows to translate the quote. All it needs next is the lanaguge to translate. So in the `locales` folder I added the langauges. I had to use something called a `.json` file. This is like a set of rules for the computer to use. It can look in the json file for instructions and data, So adding the translation in the `.json` made  it so these rules were folled by the computer:

```js

{
  "hello": "Hola!",
  "quote": "Somos y siempre seremos una nación de inmigrantes. También éramos extraños.",
  "picklang": "Por favor seleccione un idioma"
}


```

Here in the "quote" you can see the object that is quote. So the quote is in the lanaguge we want to tranlsate it to. Then when the button is clicked we call the `t` will tell the compyter ti translate the page. So we have it stored in a varible. But next we need to pass it though tranlsation to make sure it works.

#### Part 2: Making sure the translation works

So first we need to go to the `backend` folder to check how the API works, Depending on where the user's IP is the langage should translate. Now we need to makre sure that the API is reconized using API endpoints and fetch. So we connect the `initI18n.js ` to the `VITE_BACKEND`. Then we have to write out some logic to make this code work. So first we call the API then we write the logic.

```js


 try {
    const response = await fetch(`${VITE_BACKEND_API_URL}/fetchlanguage`);
    const data = await response.json();
    const lang = data.region;

```

So the first thing we want the computer to do is try and fetch the langauge. Then we pause the code for a minute as we wait fot the API to send a repsonse. That should get the region which we can then return. So we have to wait for the region which is the important part. This is follwed up by error handling in case we can't get the region. Then we can print 404. We also get the language ready to send out based on the region. How I imagine it is before someone goes down a water slide you have to wait for the person ahaed of you to go first. So we got the info we need which is going into the water slide line. But on line we have to wait for the lifeguard to day go. Which is the await. Then when the lifegaurd makes sure the guy is at the bottom you can go. Sending the langauge to the frontened. The lifeguard at the bottom catches you can he helps you out. Which is our frontend.

### Part 3: Printing the language

So now our API check the region. But we also want the user to be able to switch the langauge manually. That was the first part. All that's left is testing to make sure the langauge gets switched. SO we go onto our website and we click the button component.

![image](https://github.com/user-attachments/assets/cb3da948-687d-4f0d-9d89-aa4c8bbf32d9)


Sure enough the drop down manu comes uo and we can switch the langauge. But at first we had a big problem. For some reason this manual switiching would only work on [tor](https://www.torproject.org/download/). So for a week I loooked through the logic, looking for any error. Me and my partner couldn't find the bug untill we asked [Phizy](https://github.com/phizyts) for help. He was able to look trhough out logic and saw that we had an override in the code. 

```js

if (lang === "us") {
       return;
     }
   
```

This simple line we had used for testing was at the top of our file. So the code was being overrun by tring to return English. Which went Manual switiching only wanted to return English. No matter what, I deleted this line and the code worked. Leading to our MVP being finished.


Link to project: [Immigration app](https://ip-immigration-website-frontend.vercel.app/)

### Engineering deisgn process

At this stage in the EDP I am reeady to countiure prototyping. Now that we can tranlsate I want to add more content to the app. This app was incerdiobly difficult to make translate but now that it works we can begin with content. I want to reuse my componenets and use React to the fullest.


### Skills

1. Don't be afarid to ask for help- Help is a nessary part of coding. At first I was embaressed to have to ask a third party for help. Phizy (our real life friend) was able to debug our code. I felt ashamed to have to ask him but it was nessary. Using the resources around you and the people around you can be a big help. Especailly in big projects like our freedom project!
2. Always have a plan- Planning before hand saved me on this project. I knew what I wnated to make and was able to do reserch on the logic I needed. Also it is very helpful to put code in psudeo-code to understand what I want to do. Talking like that to myself got me out of many tough spots. I was able to use "rubber duck" debugging to save myself. Whenever I got lost I could always rememebr my plan!




[Previous](entry04.md) | [Next](entry06.md)

[Home](../README.md)
