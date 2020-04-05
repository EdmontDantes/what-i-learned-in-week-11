# what-i-learned-in-week-11


## .map method

.map method is a method used with arrays and objects and **creates** new array. it uses another function that once passed through will create new array or object that changes each item in that array or object.(will not modify original array)

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

In this example we are using an array 'todos' with objects inside. Using function expression getTodoName helper function with our next function expression in which we are using .map method to return an array of only todos.text from each object inside of todos array.(will not modify original array).

## .filter method

.filter method is a method that **creates** new array. it uses another function that once passed through will create new array or object which contains only the elements that that pass the test of a given function.

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

## .sort method
.sort method is a method that **changes** original array or object. it uses another function (sorting algorith) that once passed through will change the original array into **"sorted"** array. This method can **"sort"** either numbers or strings(based on their unicode numbers).

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
    },
    {
    text: 'binge watch The Office',
    id: 2,
    complete: false,
    priority: 2,
    },
  ]
  const helperCompleteLast = function (todo1, todo2) {
  todo1 = todo1.complete;
  todo2 = todo2.complete;
  return todo1 - todo2;
}
const completeLast = function (todos) {
  return [...todos].sort(helperCompleteLast);
}

console.log(completeLast(todos)): will change the original todos array to ordered by complete === true Last
[ { text: 'Christmas shopping', 
    id: 0, 
    complete: false, 
    priority: 1 }, 
  { text: 'binge watch The Office', 
    id: 2, 
    complete: false, 
    priority: 2 }, 
  { text: 'make doctor\'s appointment', 
    id: 1, 
    complete: true, 
    priority: 2 } ] 

```

In this example we are using an array 'todos' with objects inside.
Using function expression helperCompleteLast(sorting algorithm) helper function with our next function expression in which we are using .sort method to return an array with full object that is **"sorted"** based on the helper function algorithm for sorting.