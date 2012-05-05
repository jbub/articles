## python coding style guide

### whitespace

* 4 spaces per indentation level
* no hard tabs
* never mix tabs and spaces
* one blank line between functions
* two blank lines between classes
* add space after "," in dicts, lists, tuples, argument lists, and after ":" in dicts, but no before
* put spaces around assignments and comparisons (except in argument lists)
* no spaces just inside parentheses or just before argument lists 
* no spaces just inside docstrings	
 
This is how it should be done:

	def do_something(arg1, arg2, kwarg1='sup', kwarg2='abc'):
		"""This is a docstring."""
		my_dict = {"key": "value"}
		my_list = [1, 2, 3]
		return False

### naming convections

* **joined_lower** for functions, methods, attributes
* **joined_lower** or **ALL_CAPITALS** for constants
* **StudlyCaps** for classes
* **attr** for public and **_attr** for private attributes

### long lines

* keep lines below 80 characters in length
* use backslashes as a last resort


