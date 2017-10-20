Simple function to allow using libs which are loaded at last in footer.

```html
<!DOCTYPE html>
<html>
	<head>
		<script>
			function waitFor(objectName, callback)
			{
				//function body from this repository
			}
		</script>
	</head>
	<body>
		<div class="widget">
			<!-- Sometimes we need to call some js from inside widget which is loaded before js libraries -->
			<script>
				waitFor('SomeClassLoadedInFooter', function () {
					//Our library is loaded, we can call whatever we want
					
					SomeClassLoadedInFooter.myWidgetJustLoaded();
				});
			</script>
		</div>

		<!-- Loading our library with SomeClassLoadedInFooter prototype -->
		<script src="/some-class-loaded-in-footer.js"></script>
	</body>
</html>
```