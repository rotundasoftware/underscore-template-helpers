Define global template helpers in underscore. Example:

	_.addTemplateHelpers( {
		iff : function( condition, outputString ) {
			return condition ? outputString : "";
		}
	} );

Now in an underscore template:

	<script type="text/template">
		<div class="button <%= iff( isHightlighted, "highlighted" ) %>">
			My button
		</div>
	</script>

### Use with Backbone.Subviews

This mixin comes in handy in conjunction with the Backbone.Subviews view mixin, for a simple syntax to insert subviews into a view template:

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