# DataCamp Light

This library allows for interactive coding exercises to be inserted directly into a webpage using a lightweight version of the DataCamp interface.

## Usage
The first step is to include the JavaScript library into your webpage. For this we recommend using the latest release on the DataCamp CDN (https://cdn.datacamp.com/datacamp-light-1.0.0.min.js) like this:

```
<script src="https://cdn.datacamp.com/datacamp-light-1.0.0.min.js"></script>
```

Next we can start creating exercises using simple HTML tags. We will look into how to do this using the following simple example :

```
<div data-datacamp-exercise data-lang="r">
	<code data-type="pre-exercise-code">
		# This will get executed each time the exercise gets initialized
		b = 6
	</code>
	<code data-type="sample-code">
		# Create a variable a, equal to 5


		# Print out a


	</code>
	<code data-type="solution">
		# Create a variable a, equal to 5
		a <- 5

		# Print out a
		print(a)
	</code>
	<code data-type="sct">
		test_object("a")
		test_function("print")
		success_msg("Great job!")
	</code>
	<p data-type="hint">Use the assignment operator (<code><-</code>) to create the variable <code>a</code>.</p>
</div>
```

As we can see in the example, the whole exercise is contained in a single `<div>` element with two data attributes `data-datacamp-exercise` and `data-lang`. The first attribute `data-datacamp-exercise` indicates that the `<div>` should be treated as a DataCamp Light exercise, while the other attribute `data-lang` specifies which programming language should be used.

### Pre Exercise Code

Pre Exercise Code is code that initializes the workspace such that users can start coding the essence of the exercise instead of worrying about loading in data and packages. The way to do this is by specifying a `<code>` tag containing your initialization code and set the `data-type` attribute to `pre-exercise-code` like this:

```
<code data-type="pre-exercise-code">
	# This will get executed each time the exercise gets initialized
	b = 6
</code>
```

In our example we initiliaze the (the rather useless) variable `b` with value `6`.

### Sample Code

### Solution

### Submission Correctness Test (SCT)

You can find more information on creating SCTs at http://docs.datacamp.com/teach/sct-design-r.html for R and at http://docs.datacamp.com/teach/sct-design-python.html for python.

### Hint

## Examples

You can find more examples in the `/example` folder in the repository. You can also test out a live example at http://assets.datacamp.com/example/standalone-two-consoles.html.