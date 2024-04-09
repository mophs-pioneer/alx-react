React.Component
These docs are old and won’t be updated. Go to react.dev for the new React docs.

These new documentation pages teach modern React:

React.Component
This page contains a detailed API reference for the React component class definition. It assumes you’re familiar with fundamental React concepts, such as Components and Props, as well as State and Lifecycle. If you’re not, read them first.

Overview
React lets you define components as classes or functions. Components defined as classes currently provide more features which are described in detail on this page. To define a React component class, you need to extend React.Component:

class Welcome extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}
The only method you must define in a React.Component subclass is called render(). All the other methods described on this page are optional.

We strongly recommend against creating your own base component classes. In React components, code reuse is primarily achieved through composition rather than inheritance.

Note:

React doesn’t force you to use the ES6 class syntax. If you prefer to avoid it, you may use the create-react-class module or a similar custom abstraction instead. Take a look at Using React without ES6 to learn more.

The Component Lifecycle
Each component has several “lifecycle methods” that you can override to run code at particular times in the process. You can use this lifecycle diagram as a cheat sheet. In the list below, commonly used lifecycle methods are marked as bold. The rest of them exist for relatively rare use cases.

Mounting
These methods are called in the following order when an instance of a component is being created and inserted into the DOM:

constructor()
static getDerivedStateFromProps()
render()
componentDidMount()
Note:

This method is considered legacy and you should avoid it in new code:

UNSAFE_componentWillMount()
Updating
An update can be caused by changes to props or state. These methods are called in the following order when a component is being re-rendered:

static getDerivedStateFromProps()
shouldComponentUpdate()
render()
getSnapshotBeforeUpdate()
componentDidUpdate()
Note:

These methods are considered legacy and you should avoid them in new code:

UNSAFE_componentWillUpdate()
UNSAFE_componentWillReceiveProps()
Unmounting
This method is called when a component is being removed from the DOM:

componentWillUnmount()
Error Handling
These methods are called when there is an error during rendering, in a lifecycle method, or in the constructor of any child component.

static getDerivedStateFromError()
componentDidCatch()
Other APIs
Each component also provides some other APIs:

setState()
forceUpdate()
Class Properties
defaultProps
displayName
Instance Properties
props
state

