
# Underscore template helpers

This underscore mixin allows you to define global template helpers in underscore, that will be available in all your underscore templates. For example:

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

This mixin comes in handy when used with the [Backbone.Subviews](https://github.com/dgbeck/backbone.subviews) View mixin to insert subviews into a view template:

```javascript
_.addTemplateHelpers( {
	subview : function( subviewName ) {
		return "<div data-subview='" + subviewName + "'></div>"
	}
} );
```

Now to create a subview from your template, you just need:

	<script type='text/template' id="MyItemViewTemplate">
		<h1>This is my item view template</h1>

		<%= subview( "mySubview" ) %>
	</script>