# vuejs vs react

# react
  - min + gzip : 44kb
  - vitual dom compiler: jsx
  - rerender shouldComponentUpdate, immutable date
  - no custom directive, follow react rule
  - ssr (server side render)
  - native: react-native
  - lead by fb, full of third-party JavaScript libraries
  - write everything in js, support template

# vue
  - min + gzip : 12kb
  - vitual dom compiler : can just do by browser, support jsx, .vue file
  - rerender:  auto, completed handle by yourself
  - have custom directive
  - ssr (server side render)
  - native: weex
  - more official support libraries
  - support html, js, css template

### Iterating

##### react

```sh
// React.js  (.jsx)

const array = [1, 2, 3, 4];
const Iteration = ({ items }) => <div> {items.map(item => <span>{item}</span>)} </div>;
ReactDOM.render(<Iteration items={array}/>, document.getElementById('array'));

<!-- React.js (html) -->

<div id="array"></div>
```


##### Vue
```sh
// Vue.js (js)

var Iteration = new Vue({
  el: '#array',
  data: {
    array: [1,2,3,4]
  }
});

<!-- Vue.js (html) -->

<div id="array">
  <span v-for="value in array">{{value}}</span>
</div>
```

### props

##### react

```sh
// React.js (jsx)

const Component = ({ object }) => <span>{object.title}</span>

// Rendering the Component with the Prop
    // ...
    this.state.array.map( object => <Component key={object.id} object={object} />
    // ...
```
##### vue
```sh
// Vue.js (js)

var Component = Vue.component('component', {
  template: '<span>{{object.title}}</span>',
  props: {
    object: Object
  }
});

<!-- Vue.js (html) -->

<component
  v-for="object in array"
  track-by="id"
  :object="object">
</component>
```

### two-way binding

##### react

```sh
/ React.js (jsx)

var Message = React.createClass({
  getInitialState() {
    return {
      message: ''
    }
  },

  handleMessageChange(e) {
    this.setState({message: e.target.value});
  },

  render() {
    return (
      <div>
        <input type="text" onChange={this.handleMessageChange} />
        <span>{this.state.message}</span>
      </div>
    )
  }
});
```

##### vue

```sh
// Vue.js (js)

var Message = new Vue({
  el: '#message',
  data: {
    message: ''
  }
});

<!-- Vue.js (html) -->

<div id="message">
  <input type="text" v-model="message" />
  <span>{{message}}</span>
</div>

```

### Conditional Rendering

##### react

```sh
// React.js (jsx)

  render() {
    if ( this.state.loggedIn ) {
      return( <Component /> );
    } else {
      return( <LoginForm /> );
    }
  }
```

##### vue

```sh
<!-- Vue.js (html) -->

<component v-if="loggedIn"></component>
<login-form v-else></login-form>
```

### conclusion

react write everythings in js file
vue follow view template, .vue file can contain html, js, css into component
choose the one you like!
