# what-i-learned-in-week-11


### .map method

.map method is a method used with arrays and objects. it uses another function that once passed through will create new array or object that changes each item in that array or object.

examples:

```
const todos = [
  {
    text: 'Christmas shopping',
    id: 0,
    complete: false,
    priority: 1,
  },
  {
    text: `make doctor's appointment`,
    id: 1,
    complete: true,
    priority: 2,
  }
]

const getTodoName = function(todo) {
  return todo.text
}
const names = function (todos) {
  return todos.map(getTodoName)
}
console.log(names(todos)) will be an array:
['Christmas shopping', 'make doctor\'s appointment']

```

In this example we are using an array 'todos' with objects inside. Using function expression getTodoName helper function with our next function expression in which we are using .map method to return an array of only todos.text from each object inside of todos array.

### .filter method

.filter method is a method that creates new array. it uses another function that once passed through will create new array or object which contains only the elements that that pass the test of a given function.

```
const todos = [
    {
      text: 'Christmas shopping',
      id: 0,
      complete: false,
      priority: 1,
    },
    {
      text: `make doctor's appointment`,
      id: 1,
      complete: true,
      priority: 2,
    }
  ]
  const isComplete = function(todo) {
    return todo.complete
  }
  
  const justComplete = function (todos) {
    return todos.filter(isComplete)
  }
  console.log(justComplete(todos)) will be an array:
      {
      text: `make doctor's appointment`,
      id: 1,
      complete: true,
      priority: 2,
    }

// As you can see only one item from an array which complete returned
```

In this example we are using an array 'todos' with objects inside.
Using function expression IsComplete helper function with our next function expression in which we are using .filter method to return an array with full object that satisfies todo.complete === true condition. cliche as it sounds it filters array without changing its values like aforementioned .map does.

### .sort method