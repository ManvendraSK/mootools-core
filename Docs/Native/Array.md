[Function:bind]: /Native/#Function:bind


Native: Array {#Array}
======================

A collection of the Array Object methods.

### See Also:

[MDC Array](http://developer.mozilla.org/en/docs/Core_JavaScript_1.5_Reference:Global_Objects:Array)



Array Method: every {#Array:every}
----------------------------------

[Array:every]: http://developer.mozilla.org/en/docs/Core_JavaScript_1.5_Reference:Global_Objects:Array:every

Returns true if every element in the array satisfies the provided testing function.
This method is provided only for browsers without native [Array:every][] support.

### Syntax:

	var allPassed = myArray.every(fn[, bind]);

### Arguments:

	fn   - (function) The function to test for each element.
	bind - (object, optional) The object to use as 'this' in the function. For more information see [Function:bind][].

#### Argument: fn

##### Syntax:

	fn(item, index, array)

##### Arguments:

1. item   - (mixed) The current item in the array.
2. index  - (number) The current item's index in the array.
3. array  - (array) The actual array.

### Returns:

* (boolean) If every element in the array satisfies the provided testing function, returns true. Otherwise, returns false.

### Example:

	var areAllBigEnough = [10, 4, 25, 100].every(function(item, index){
		return item > 20;
	}); //areAllBigEnough = false


### See Also:

[MDC Array:every][Array:every]



Array Method: filter {#Array:filter}
------------------------------------

[Array:filter]: http://developer.mozilla.org/en/docs/Core_JavaScript_1.5_Reference:Global_Objects:Array:filter

Creates a new array with all of the elements of the array for which the provided filtering function returns true.
This method is provided only for browsers without native [Array:filter][] support.

### Syntax:

	var filteredArray = myArray.filter(fn[, bind]);

### Arguments:

1. fn   - (function) The function to test each element of the array. This function is passed the item and its index in the array.
2. bind - (object, optional) The object to use as 'this' in the function. For more information see [Function:bind][].

#### Argument: fn

##### Syntax:

	fn(item, index, array)

##### Arguments:

1. item   - (mixed) The current item in the array.
2. index  - (number) The current item's index in the array.
3. array  - (array) The actual array.

### Returns:

* (array) The new filtered array.

### Example:

	var biggerThanTwenty = [10, 3, 25, 100].filter(function(item, index){
		return item > 20;
	}); //biggerThanTwenty = [25, 100]


### See Also:

[MDC Array:filter][Array:filter]



Array Method: indexOf {#Array:indexOf}
--------------------------------------

[Array:indexOf]: http://developer.mozilla.org/en/docs/Core_JavaScript_1.5_Reference:Global_Objects:Array:indexOf

Returns the index of the first element within the array equal to the specified value, or -1 if the value is not found.
This method is provided only for browsers without native [Array:indexOf][] support.

### Syntax:

	var index = myArray.indexOf(item[, from]);

### Returns:

* (number) The index of the first element within the array equal to the specified value. If not found, returns -1.

### Arguments:

1. item - (object) The item to search for in the array.
2. from - (number, optional: defaults to 0) The index of the array at which to begin the search.

### Example:

	['apple', 'lemon', 'banana'].indexOf('lemon'); //returns 1
	['apple', 'lemon'].indexOf('banana'); //returns -1


### See Also:

[MDC Array:indexOf][Array:indexOf]



Array Method: map {#Array:map}
------------------------------

[Array:map]: http://developer.mozilla.org/en/docs/Core_JavaScript_1.5_Reference:Global_Objects:Array:map

Creates a new array with the results of calling a provided function on every element in the array.
This method is provided only for browsers without native [Array:map][] support.

### Syntax:

	var mappedArray = myArray.map(fn[, bind]);

### Arguments:

1. fn   - (function) The function to produce an element of the new Array from an element of the current one.
2. bind - (object, optional) The object to use as 'this' in the function. For more information see [Function:bind][].

#### Argument: fn

##### Syntax:

	fn(item, index, array)

##### Arguments:

1. item   - (mixed) The current item in the array.
2. index  - (number) The current item's index in the array.
3. array  - (array) The actual array.

### Returns:

* (array) The new mapped array.

### Example:

	var timesTwo = [1, 2, 3].map(function(item, index){
		return item * 2;
	}); //timesTwo = [2, 4, 6];

### See Also:

[MDC Array:map][Array:map]



Array Method: some {#Array:some}
--------------------------------

[Array:some]: http://developer.mozilla.org/en/docs/Core_JavaScript_1.5_Reference:Global_Objects:Array:some

Returns true if at least one element in the array satisfies the provided testing function.
This method is provided only for browsers without native [Array:some][] support.

### Syntax:

	var somePassed = myArray.some(fn[, bind]);

### Returns:

* (boolean) If at least one element in the array satisfies the provided testing function returns true. Otherwise, returns false.

### Arguments:

1. fn   - (function) The function to test for each element. This function is passed the item and its index in the array.
2. bind - (object, optional) The object to use as 'this' in the function. For more information see [Function:bind][].

#### Argument: fn

##### Syntax:

	fn(item, index, array)

##### Arguments:

1. item   - (mixed) The current item in the array.
2. index  - (number) The current item's index in the array.
3. array  - (array) The actual array.

### Example:

	var isAnyBigEnough = [10, 4, 25, 100].some(function(item, index){
		return item > 20;
	}); //isAnyBigEnough = true


### See Also:

[MDC Array:some][Array:some]



Array Method: associate {#Array:associate}
------------------------------------------

Creates an object with key-value pairs based on the array of keywords passed in and the current content of the array.

### Syntax:

	var associated = myArray.associate(obj);

### Arguments:

1. obj - (array) Its items will be used as the keys of the object that will be created.

### Returns:

* (object) The new associated object.

### Example:

	var animals = ['Cow', 'Pig', 'Dog', 'Cat'];
	var sounds = ['Moo', 'Oink', 'Woof', 'Miao'];
	animals.associate(sounds);
	//returns {'Cow': 'Moo', 'Pig': 'Oink', 'Dog': 'Woof', 'Cat': 'Miao'}



Array Method: link {#Array:link}
--------------------------------

Accepts an object of key / function pairs to assign values.

### Syntax:

	var result = Array.link(array, object);

### Arguments:

1. object - (object)  An object containing key / function pairs must be passed to be used as a template for associating values with the different keys.

### Returns:

* (object) The new associated object.

### Example:

	var el = document.createElement('div');
	var arr2 = [100, 'Hello', {foo: 'bar'}, el, false];
	arr2.link({myNumber: Number.type, myElement: Element.type, myObject: Object.type, myString: String.type, myBoolean: $defined});
	//returns {myNumber: 100, myElement: el, myObject: {foo: 'bar'}, myString: 'Hello', myBoolean: false}



Array Method: contains {#Array:contains}
----------------------------------------

Tests an array for the presence of an item.

### Syntax:

	var inArray = myArray.contains(item[, from]);

### Arguments:

1. item - (object) The item to search for in the array.
2. from - (number, optional: defaults to 0) The index of the array at which to begin the search.

### Returns:

* (boolean) If the array contains the item specified, returns true. Otherwise, returns false.

### Example:

	["a","b","c"].contains("a"); //returns true
	["a","b","c"].contains("d"); //returns false

### See Also:

[Array:indexOf](#Array:indexOf)



Array Method: extend {#Array:extend}
------------------------------------

Extends an array with all the items of another.

### Syntax:

	myArray.extend(array);

### Arguments:

1. array - (array) The array whose items should be extended into this array.

### Returns:

* (array) This array, extended.

### Example:

	var animals = ['Cow', 'Pig', 'Dog'];
	animals.extend(['Cat', 'Dog']); //animals = ['Cow', 'Pig', 'Dog', 'Cat', 'Dog'];




Array Method: getLast {#Array:getLast}
--------------------------------------

Returns the last item from the array.

### Syntax:

	myArray.getLast();

### Returns:

* (mixed) The last item in this array.
* (false) If this array is empty, returns null.

### Example:

	['Cow', 'Pig', 'Dog', 'Cat'].getLast(); //returns 'Cat'



Array Method: getRandom {#Array:getRandom}
------------------------------------------

Returns a random item from the array.

### Syntax:

	myArray.getRandom();

### Returns:

* (mixed) A random item from this array. If this array is empty, returns null.

### Example:

	['Cow', 'Pig', 'Dog', 'Cat'].getRandom(); //returns one of the items




Array Method: include {#Array:include}
--------------------------------------

Pushes the passed element into the array if it's not already present (case and type sensitive).

### Syntax:

	myArray.include(item);

### Arguments:

1. item - (object) The item that should be added to this array.

### Returns:

* (array) This array with the new item included.

### Example:

	['Cow', 'Pig', 'Dog'].include('Cat'); //returns ['Cow', 'Pig', 'Dog', 'Cat']
	['Cow', 'Pig', 'Dog'].include('Dog'); //returns ['Cow', 'Pig', 'Dog']




Array Method: merge {#Array:merge}
----------------------------------

Merges an array with all the items of another. Does not allow duplicates and is case and type sensitive.

### Syntax:

	myArray.merge(array);

### Arguments:

1. array - (array) The array whose items should be merged into this array.

### Returns:

* (array) This array merged with the new items.

### Example:

	var animals = ['Cow', 'Pig', 'Dog'];
	animals.merge(['Cat', 'Dog']); //animals = ['Cow', 'Pig', 'Dog', 'Cat'];




Array Method: remove {#Array:remove}
------------------------------------

Removes all occurrences of an item from the array.

### Syntax:

	myArray.remove(item);

### Arguments:

1. item - (object) The item to search for in the array.

### Returns:

* (array) This array with all occurrences of the item removed.

### Example:

	['Cow', 'Pig', 'Dog', 'Cat', 'Dog'].remove('Dog') //returns ['Cow', 'Pig', 'Cat']
	['Cow', 'Pig', 'Dog'].remove('Cat') //returns ['Cow', 'Pig', 'Dog']




Array Method: empty {#Array:empty}
----------------------------------

Empties an array.

### Syntax:

	myArray.empty();

### Returns:

* (array) This array, emptied.

### Example:

	var myArray = ['old', 'data'];
	myArray.empty(); //myArray is now []




Array Method: flatten {#Array:flatten}
--------------------------------------

Flattens a multidimensional array into a single array.

### Syntax:

	myArray.flatten();

### Returns:

* (array) A new flat array.

### Example:

	var myArray = [1,2,3,[4,5, [6,7]], [[[8]]]];
	varnewArray = myArray.flatten(); //newArray is [1,2,3,4,5,6,7,8]