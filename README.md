Define global template helpers in underscore. Example:

	_.addTemplateHelpers( {
		iff : function( condition, outputString ) {
			return condition ? outputString : "";
		}
	} );

Now in an underscore template:

	<script type="text/template">
		<div class="button <% iff( isHightlighted, "highlighted" ) %>">
			My button
		</div>
	</script>