# React Components
* Access properties of a component with: ```{this.props.author}``` or ```{this.props.children}```. 
  * Ex: ```<Comment author="Jordan Walke">This is *another* comment</Comment>```
  * In this case, author is just a property, but the comment itself is regarded as a child. 
* Components need a render() function to create the necessary HTML on the page. 
* getInitialState only runs once during the life cycle of the component. 
* ```componentDidMount()``` is a method called automatically by React when a component is rendered.
