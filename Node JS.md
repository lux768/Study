Node JS

* Start the node:
    -> node archive.js

/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/

* Syntax:	 
	let http = require('http');
    http.createServer(function (req, res) {
        res.writeHead(200, {'Content-Type': 'text/plain'});
        res.end('Hello World!');
    }).listen(8080);

	const express = require('express');
	const app = express();
	app.get('/', (req, res) => res.send('Hello World!'));
	app.listen(8080);

/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/

* Read a File Asynchronously:
	//Load the filesystem module
	const fs = require('fs');
	//Read file asynchronously
	fs.readFile('myfile.txt', 'utf8', (err, data) => {
		if (err) {
			console.error('Error Reading file: ' + err);
			return;
		}
		console.log('File contente: ' + data);
	});
	console.log('Reading file... (this runs first!)');

/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/

* Simple Web Server:
	const http = require('http');
	http.createServer((req, res) => {
		res.writeHead(200, {'Content-Type': 'text/plain'});
		res.end('Hello Word!');
	}).listen(8080);

/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/

* Variables and Functions:
	//Variables (let, const, var)
	let name = 'Node.js';
	const version = 20;
	//Function declaration
	function greet(user) {
		return 'Hello, ${user}!';//Template literal (ES6)
	}
	//Arrow function (ES6+)
	const add = (a, b) => a + b;
	console.log(greet('Developer')); //Hello, Developer!
	console.log(add(5, 3)); //8 

/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/

* Objects and Arrays:
	//Object
	const user = {
		name: 'Luigi',
		age: 21,
		greet() {
			console.log('Hi, I'm ${this.name});
		}
	};
    //Array
	const colors = ['red', 'green', 'blue'];
	//Array methods (ES6+)
	colors.forEach(color => console.log(color));
	const lengths = colors.map(color +> color.length);

/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/

* Asynchronous JavaScript:
	//1. Callbacks (traditional)
	function fetchData(call-back) {
		setTimeout(() => {
			call-back('Data received!');
		}, 1000);
	}
	//2. Promises (ES6+)
	const fetchDataPromise = () => {
		return new Promise((resolve) => {
			setTimeout(() => resolve('Promise resolved!'), 1000);
		});
	};
	//3. Async/Await (ES8+)
	async function getData() {
		const result = await fechDataPromise();
		console.log(result);
	}
	getData(); // Call the async function

/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/

* Destructuring \& Template Literals (ES6+):
	const { name } = user;
	console.log(`Hello, ${name}!`);

/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/

* Key Differences:
	Node.js and browsers both run JavaScript, but they have different environments and capabilities.
	Node.js is designed for server-side development, while browsers are for client-side applications.
	APIs: Node.js provides APIs for file system, networking, and OS, which browsers do not.
	Browsers provide DOM, fetch, and UI APIs not available in Node.js.
	Global Objects: Node.js uses global; browsers use window or self.
	Modules: Node.js uses CommonJS (require) and ES modules (import); browsers use ES modules or plain <script> tags.
	Security: Browsers run in a sandbox with limited access; Node.js has full access to the file system and network.
	Event Loop: Both environments use an event loop, but Node.js has additional APIs for timers, process, etc.
	Environment Variables: Node.js can access environment variables (process.env); browsers cannot.
	Package Management: Node.js uses npm/yarn; browsers use CDNs or bundlers.

/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/

* Global Objects:
	//Node.js
	global.mylet = 42;
	console.log(global.mylet); //42
 	//Browser
	window.mylet = 42;
 	console.log(window.mylet); //42

/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/

* File Access:
	//Node.js
	const fs = require('fs');
	fs.readFile('myfile.txt', 'utf8', (err, data) => {
		if (err) throw err;
		console.log(data);
	});
	//Browser
	//Not allowed for security reasons

/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/

* HTTP Requests:
	//Node.js
	const https = require('https');
	https.get('https://example.com', res => {
		let data = '';
		res.on('data', chunk => data += chhunk);
		res.on('end', () => console.log(data));
	});
	//Browser
	fetch('https://example.com')
		.then(response => response.txt())
		.then(console.log);

/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/

* Modules:
	//Node.js (CommonJS)
	const fs = require('fs');
	//Node.js \& Browser (ES Modules)
	//import fs from 'fs'; //Node.js only, not browser
	//import _ from 'https://cdn.jsdelivr.net/npm/lodash-es/lodash.js'; //Browser

/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/

* Run a JavaScript file:
	# Run a JavaScript file
	node app.js
	# Run with additional arguments
	node app.js arg1 arg2
	# Run in watch mode (restarts on file changes)
	node --watch app.js

/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/

* Using the REPL:
	The Node.js REPL (Read-Eval-Print Loop) is an interactive shell for executing JavaScript code.
	The REPL is started by running node in the terminal:
	>const name = 'Node.js';
	>console.log('Hello, ${name}!');
	>.help //Show avaliable commands
	>.exit //Exit REPL

/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/

* Command Line Arguments:
	//args.js
	console.log('All arguments:', process.argv);
 	console.log('First argument:', process.argv[2]);
 	console.log('Second argument:', process.argv[3]);
	//Example usage:
	//node args.js hello world
	//Output:
	//All arguments: ['/path/to/node', '/path/to/args.js', 'hello', 'world']
	//First argument: hello
	//Second argument: world

/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/

* Environment Variables:
	//env.js
	console.log('Environment:', process.env.NODE_ENV || 'development');
	console.log('Custom variable:', process.env.MY_VARIABLE);
	console.log('Database URL:', process.env.DATABASE_URL || 'Not set');
	//Example usage with environment variables:
	//NODE_ENV=production MY_VARIABLE=test node env.js

/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/

* Set Environment Variables
    # Set environment variables when running
    NODE_ENV=production MY_VARIABLE=test node env.js

/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/

* Basic Debugging Commands 
    # Start with inspector (listens on default port 9229)
    node --inspect app.js

    # Break on first line of application
    node --inspect-brk app.js

    # Specify a custom port
    node --inspect=9222 app.js

    # Enable remote debugging (be careful with this in production)
    node --inspect=0.0.0.0:9229 app.js

/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/

* Node Version Manager (nvm)
    # Install and use different Node.js versions
    nvm install 18.16.0 # Install specific version 
    nvm use 18.16.0 # Switch to version 
    nvm ls # List installed versions

/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/

* npm (Node Package Manager)
    # Common npm commands
    npm init # Initialize a new project
    npm install # Install dependencies 
    npm updade # Update packages
    npm audit # Check for vulnerabilities 

/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/

