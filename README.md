# react-testing-components-enzyme
Sample repo for a blog post on testing react components with enzyme

# PreRequired
## quik (auto run tool)
	npm install -g quik
## chai sinon enzyme jsdom (test tools)
	npm install chai sinon enzyme jsdom
## React enviroment
	npm install react react-dom react-addons-test-utils
## Mocha (Test Runer)
	npm install -g mocha
## Babel
	npm install babel-core babel-preset-es2015 babel-preset-react
## .babelrc file
	{
		"presets": ["es2015", "react"]
	}
## testHelper (browser.js -- ./test/helpers/browser.js) 
	require('babel-register')();
	 
	var jsdom = require('jsdom').jsdom;
	 
	var exposedProperties = ['window', 'navigator', 'document'];
	 
	global.document = jsdom('');
	global.window = document.defaultView;
	Object.keys(document.defaultView).forEach((property) => {
		if (typeof global[property] === 'undefined') {
			exposedProperties.push(property);
			global[property] = document.defaultView[property];
		}
	});
 
	global.navigator = {
		userAgent: 'node.js'
	};

# Usage
## Components.js Test Execute
mocha --watch --require test/helpers/browser.js *.spec.js
