# Underscore.js global template helpers

This [underscore.js](https://github.com/documentcloud/underscore) mixin allows you to define global template helpers that will be available in all your underscore templates. For example, you can define aa "if and only if" function that will only output text if its first argument evaluates to `true`:

	_.addTemplateHelpers( {
		iff : function( condition, outputString ) {
			return condition ? outputString : "";
		}
	} );

Now in an underscore template, you can use the `iff` function:

	<script type="text/template">
		<div class="button <%= iff( isHightlighted, "highlighted" ) %>">
			My button
		</div>
	</script>

### Using with Backbone.Subviews

Helpers also come handy when used with [Backbone.Subviews](https://github.com/rotundasoftware/backbone.subviews), a mixin for easily creating subviews in your [Backbone.js](http://backbonejs.org/) applications from your view templates.

```javascript
_.addTemplateHelpers( {
	subview : function( subviewName ) {
		return "<div data-subview='" + subviewName + "'></div>";
	}
} );
```

Now to create a subview from your template, you just need:

	<script type='text/template' id="MyItemViewTemplate">
		<h1>This is my item view template</h1>

		<%= subview( "mySubview" ) %>
	</script>
