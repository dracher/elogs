title: AngularJS Notes 02
thumbnail: /img/blog.png
categories: Technical
date: 2015-12-30 13:19:18
tags: [angular, javascript]
---

# 5. Dependency Injection

## Dependency Annotation

- Inline Array Annotation

	```javascript
	someModule.controller('MyController', ['$scope', 'greeter', function($scope, greeter) {
  	// ...
	}]);
	```

- `$inject` Property Annotation

	```javascript
	var MyController = function($scope, greeter) {
  	// ...
	}
	MyController.$inject = ['$scope', 'greeter'];
	someModule.controller('MyController', MyController);
	```
- Implicit Annotation

	**Careful: If you plan to minify your code, your service names will get renamed and break your app**

	```javascript
	someModule.controller('MyController', function($scope, greeter) {
  	// ...
	});
	```

## Using Strict Dependency Injection

- You can add an `ng-strict-di` directive on the same element as `ng-app` to opt into strict DI mode

	```html
	<!doctype html>
	<html ng-app="myApp" ng-strict-di>
	<body>
	  I can add: {{ 1 + 2 }}.
	  <script src="angular.js"></script>
	</body>
	</html>
	```

- If you're using manual bootstrapping, you can also use strict DI by providing `strictDi: true` in the optional config argument

	```javascript
	angular.bootstrap(document, ['myApp'], {
	  strictDi: true
	});
	```