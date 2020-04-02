1. Write a program to display current date which updates every second using react

```jsx harmony
class Clock extends React.Component {
  constructor(props) {
    super(props);
    this.state = {date: new Date()};
  }

  componentDidMount() {
    this.timerID = setInterval(
      () => this.tick(),
      1000
    );
  }

  componentWillUnmount() {
    clearInterval(this.timerID);
  }

  tick() {
    this.setState({
      date: new Date()
    });
  }

  render() {
    return (
        <h1>{this.state.date.toLocaleTimeString()}.</h1>
    );
  }
}

ReactDOM.render(
  <Clock />,
  document.getElementById('root')
);
```

Details about how this code works can be found on the [react site](https://reactjs.org/docs/state-and-lifecycle.html#adding-lifecycle-methods-to-a-class)  