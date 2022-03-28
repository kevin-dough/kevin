{% include navigation.html %}

# Tech Talks
> Tech Talk notes all in one place.

## Table of Contents
<table>
    <tr>
        <td><a href="#tt0">TT0</a></td>
        <td><a href="#tt1">TT1</a></td>
        <td><a href="#tt2">TT2</a></td>
        <td><a href="#tt3">TT3</a></td>
        <td><a href="#tt4">TT4</a></td>
        <td><a href="#tt5">TT5</a></td>
        <td><a href="#tt6">TT6</a></td>
        <td><a href="#tt7">TT7</a></td>
        <td><a href="#tt8">TT8</a></td>
        <td><a href="#tt9">TT9</a></td>
        <td><a href="#tt10">TT10</a></td>
    </tr>
</table>

## TT0

### Imperative vs. Object Oriented Paradigms
Imperative Paradigms are more step-by-step than Object Oriented Paradigms. OOP relies on classes and objects, although the methods have Imperative Paradigms.


### Java Arrays
```java
public static Animal[] animalData() {
	return new Animal[]{
	        new Animal("Lion", 8, "Gold"),
	        new Animal("Pig", 3, "Pink"),
		new Animal("Robin", 7, "Red"),
		new Animal("Cat", 10, "Black"),
		new Animal("Kitty", 1, "Calico"),
		new Animal("Dog", 14, "Brown")
	};
}
```

### Java Dictionaries
```java
private final Map<String, Integer> OPERATORS = new HashMap<>();
    {
        // Map<"token", precedence>
        OPERATORS.put("*", 3);
        OPERATORS.put("/", 3);
        OPERATORS.put("%", 3);
        OPERATORS.put("+", 4);
        OPERATORS.put("-", 4);
    }
```

## TT1

### Java Generic `T` and Java Iterable
> `T` is the iterator variable. Iterators are used to retrieve elements one by one. Every class that implements Iterable interface appropriately, can be used in the enhanced For loop (for-each loop). The need to implement the Iterator interface arises while designing custom data structures.

### Queue
> Add to the end of the queue but remove from the beginning. Has head and tail.

```java
public void add(T data) {
    // add new object to end of Queue
    LinkedList<T> tail = new LinkedList<>(data, null);
    if (head == null)  // initial condition
      this.head = this.tail = tail;
    else {  // nodes in queue
      this.tail.setNextNode(tail); // current tail points to new tail
      this.tail = tail;  // update tail
    }
  }

public void delete(){
    head = head.getNext();
}
```

### Stack
> Only needs a head.

## TT2

### Calculator
1. Tokenize
2. Put Numbers into List and if Operator, compare for precedence. (RPN)
3. Pop entries: numbers go into a list and if operator, do calculations.
4. Kill numbers and operator becomes result.
5. Put result back into list and repeat until there is nothing left.

```java
// Takes RPN and produces a final result
private void rpnToResult()
{
    // Stack used to hold calculation while process RPN
    Stack calculation = new Stack();

    // for loop to process RPN
    for(int i = 0; i < this.reverse_polish.size(); i++)
    {
        // If the token is a number
        if (isNumeric(this.reverse_polish.get(i))){
          // Push number to stack
          calculation.push(this.reverse_polish.get(i));
        }
        // else
        else{
          // Pop the two top entries
          // Based off of Token operator calculate result
          // Push result back onto the stack
          if(this.reverse_polish.get(i) == "sqrt") {
            Double num = Double.parseDouble(calculation.pop().toString());
            calculation.push(Math.pow(num, 0.5));
          }
          else {
            Double num2 = Double.parseDouble(calculation.pop().toString());
            Double num1 = Double.parseDouble(calculation.pop().toString());
            switch(this.reverse_polish.get(i)){
                case "+":
                    calculation.push(num1 + num2);
                    break;
                case "-":
                    calculation.push(num1 - num2);
                    break;
                case "*":
                    calculation.push(num1 * num2);
                    break;
                case "/":
                    calculation.push(num1 / num2);
                    break;
                case "%":
                    calculation.push(num1 % num2);
                    break;
                case "^" :
                    calculation.push(Math.pow(num1, num2));
          }
        }
      }
    }
    // Pop final result and set as final result for expression
    result = (Double) calculation.pop();
}
```

## TT3

## TT4

## TT5

## TT6

## TT7

## TT8

## TT9

## TT10