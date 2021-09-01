# React: Props - Contact Cards
Created with [CodeSandbox](https://codesandbox.io/)      
Notes from: React module    
[The Complete 2021 Web Development Bootcamp](https://www.udemy.com/course/the-complete-web-development-bootcamp/)  
Instructor: Dr. Angela Yu      

## Description
This app renders a heading "My contacts"        
and 2 cards with information of two humans: their name, a picture, their (fake) telephone and their (fake) email

This app was helpful to get some practice about converting the hard coded cards into reusable React Components        
and understand how to create React Properties (props).

## Notes:
HTML Elements have Attributes. We can NOT define our custom Attributes.       
But React Components are almost custom HTML elements so we can define these attributes.       
In the React Component world, those attributes are called properties (usually referred to as "props").

React Components: we can pass properties using very similar syntax to HTML Elements.      
When this Card Component gets created, it will have a property called name that's set to equal to "Cristian":
```
<Card name="Cristian" />
```

We can get hold of it by adding a name to the inputs to access those things that are sent over.       
And it's customary to call it props. Basic eg:
```
function Card(props) {
  console.log(props);}  //to access properties
```
This means that we can actually completely remove all of these hard coded parts of our React Components            
and instead, rely on inserting the values of these props.

### HTML Attributes
We have the HTML tag and we get to use these predetermined fixed name Attributes .       
The attributes depends on the Element we are using.        
eg: [`<input>`: The Input (Form Input) element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) >> Attributes (in this case, attributes such as id or place holder or value.)
```
<input id="email"  placeholder="Enter your email"  value="Cristian@Villalba.com" />
```
When we use these attributes, we can pass in some custom data.      
And that data can then be accessed on the element by tapping into the .id   or  .placeholder   or  .value  properties.    
eg: document.getElementByID(" email  ")

### React Props
We have our custom Component and we can create as many Props as we want.        
We are the ones that are creating this custom Card element and we get to specify which attributes or properties they should have.     
But these values for each of these properties then get passed along when this card component is created.        
And when we output this HTML element we can incorporate those properties into the creation of that element.        
And it's usually via an input called props.
```
function Card(props) {
  return (
    <div className="my-style">
      <h2>{props.name}</h2>
      <img src={props.img} alt="avatar_img" />
      <p>{props.tel}</p>
      <p>{props.email}</p>
    </div>
  );
}
```
So the easiest way to imagine it is just simply that you're creating a new Javascript object with these key and value pairs      
and then that whole object gets sent over as the props object and then you can tap into it using .name, .telephone,        
as long as they match up with the names in your component element.       
eg:  name , img , tel , email >> props.name , props.img , props.tel , props.email
```
<Card
  name="Chuck Norris"
  img="https://i.pinimg.com/originals/e3/94/47/e39447de921955826b1e498ccf9a39af.png"
  tel="+1800-RoundKick"
  email="BillGates.com - My secretary"
/>
```

## What I have learned with this project: 
* Differences between HTML Attributes and React Props
* How to create React Props
* How to pass values to our React Props
