Node JS



* Start the node:

&nbsp;	-> node archive.js



/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/



* Syntax:	 

&nbsp;	-> let http = require('http');

&nbsp;	

&nbsp;	http.createServer(function(req, res) {

&nbsp;		res.writeHead9200, \['CONTENT-type': 'text/plain'});

&nbsp;		res.end9'hello World!');

&nbsp;	}).listen(8080);



&nbsp;	-> const express = require('express');

&nbsp;	const app = express();

&nbsp;	app.get('/', (req, res) => res.send('Hello World!'));

&nbsp;	app.listen(8080);



/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/



* Read a File Asynchronously:

&nbsp;	-> // Load the filesystem module

&nbsp;	const fs = require('fs');



&nbsp;	//Read file asynchronously

&nbsp;	fs.readFile('myfile.txt', 'utf8', (err, data) => {

&nbsp;		if (err) {

&nbsp;			console.error('Error Reading file: ' + err);

&nbsp;			return;

&nbsp;		}

&nbsp;		console.log('File contente: ' + data);

&nbsp;	});

&nbsp;	

&nbsp;	console.log('Reading file... (this runs first!)');



/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/



* Simple Web Server:

&nbsp;	-> const http = require('http');

&nbsp;	http.createServer((req, res) => {

&nbsp;		res.writeHead(200, {'Content-Type': 'text/plain'});

&nbsp;		res.end('Hello Word!');

&nbsp;	}).listen(8080);



/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/



* Variables and Functions:

&nbsp;	-> // Variables (let, const, var)

&nbsp;	let name = 'Node.js';

&nbsp;	const version = 20;



&nbsp;	// Function declaration

&nbsp;	function greet(user) {

&nbsp;		return 'Hello, ${user}!';//Template literal (ES6)

&nbsp;	}

&nbsp;	

&nbsp;	// Arrow function (ES6+)

&nbsp;	const add = (a, b) => a + b;



&nbsp;	console.log(greet('Developer')); // Hello, Developer!

&nbsp;	console.log(add(5, 3)); // 8 



/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/



* Objects and Arrays:

&nbsp;	-> // Object

&nbsp;	const user = {

&nbsp;		name: 'Luigi',

&nbsp;		age: 21,

&nbsp;		greet() {

&nbsp;			console.log('Hi, I'm ${this.name});

&nbsp;		}

&nbsp;	};

&nbsp;	

&nbsp;	// Array

&nbsp;	const colors = \['red', 'green', 'blue'];

&nbsp;	

&nbsp;	// Array methods (ES6+)

&nbsp;	colors.forEach(color => console.log(color));

&nbsp;	const lengths = colors.map(color +> color.length);



/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/



* Asynchronous JavaScript:

&nbsp;	-> // 1. Callbacks (traditional)

&nbsp;	function fetchData(call-back) {

&nbsp;		setTimeout(() => {

&nbsp;			call-back('Data received!');

&nbsp;		}, 1000);

&nbsp;	}



&nbsp;	// 2. Promises (ES6+)

&nbsp;	const fetchDataPromise = () => {

&nbsp;		return new Promise((resolve) => {

&nbsp;			setTimeout(() => resolve('Promise resolved!'), 1000);

&nbsp;		});

&nbsp;	};



&nbsp;	// 3. Async/Await (ES8+)

&nbsp;	async function getData() {

&nbsp;		const result = await fechDataPromise();

&nbsp;		console.log(result);

&nbsp;	}

&nbsp;	

&nbsp;	getData(); // Call the async function



/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/



* Destructuring \& Template Literals (ES6+):

&nbsp;	->const { name } = user;

&nbsp;	console.log(`Hello, ${name}!`);



/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/



* Key Differences:

&nbsp;	-> Node.js and browsers both run JavaScript, but they have different environments and capabilities.



&nbsp;	-> Node.js is designed for server-side development, while browsers are for client-side applications.



&nbsp;	-> APIs: Node.js provides APIs for file system, networking, and OS, which browsers do not.



&nbsp;	-> Browsers provide DOM, fetch, and UI APIs not available in Node.js.



&nbsp;	-> Global Objects: Node.js uses global; browsers use window or self.



&nbsp;	-> Modules: Node.js uses CommonJS (require) and ES modules (import); browsers use ES modules or plain <script> tags.

&nbsp;	

&nbsp;	-> Security: Browsers run in a sandbox with limited access; Node.js has full access to the file system and network.



&nbsp;	-> Event Loop: Both environments use an event loop, but Node.js has additional APIs for timers, process, etc.



&nbsp;	-> Environment Variables: Node.js can access environment variables (process.env); browsers cannot.



&nbsp;	-> Package Management: Node.js uses npm/yarn; browsers use CDNs or bundlers.



/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/





* Global Objects:

&nbsp;	-> // Node.js

&nbsp;	global.mylet = 42;

&nbsp;	console.log(global.mylet); // 42



 	-> // Browser

 	window.mylet = 42;

 	console.log(window.mylet); // 42



/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/



* File Access:

&nbsp;	-> // Node.js

&nbsp;	const fs = require('fs');

&nbsp;	fs.readFile('myfile.txt', 'utf8', (err, data) => {

&nbsp;		if (err) throw err;

&nbsp;		console.log(data);

&nbsp;	});



&nbsp;	-> // Browser

&nbsp;	// Not allowed for security reasons



/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/



* HTTP Requests:

&nbsp;	-> // Node.js

&nbsp;	const https = require('https');

&nbsp;	https.get('https://example.com', res => {

&nbsp;		let data = '';

&nbsp;		res.on('data', chunk => data += chhunk);

&nbsp;		res.on('end', () => console.log(data));

&nbsp;	});



&nbsp;	-> // Browser

&nbsp;	fetch('https://example.com')

&nbsp;		.then(response => response.txt())

&nbsp;		.then(console.log);



/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/



* Modules:

&nbsp;	-> // Node.js (CommonJS)

&nbsp;	const fs = require('fs');



&nbsp;	-> // Node.js \& Browser (ES Modules)

&nbsp;	// import fs from 'fs'; // Node.js only, not browser

&nbsp;	// import \_ from 'https://cdn.jsdelivr.net/npm/lodash-es/lodash.js'; // Browser



/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/



* Run a JavaScript file:

&nbsp;	-> # Run a JavaScript file

&nbsp;	node app.js



&nbsp;	-> # Run with additional arguments

&nbsp;	node app.js arg1 arg2



&nbsp;	-> # Run in watch mode (restarts on file changes)

&nbsp;	node --watch app.js



/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/



* Using the REPL:

&nbsp;	-> The Node.js REPL (Read-Eval-Print Loop) is an interactive shell for executing JavaScript code.

&nbsp;	The REPL is started by running node in the terminal:



&nbsp;	-> >const name = 'Node.js';

&nbsp;	>console.log('Hello, ${name}!');

&nbsp;	>.help // Show avaliable commands

&nbsp;	>.exit // Exit REPL



/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/



* Command Line Arguments:

&nbsp;	-> // args.js

&nbsp;	console.log('All arguments:', process.argv);

 	console.log('First argument:', process.argv\[2]);

 	console.log('Second argument:', process.argv\[3]);



&nbsp;	-> // Example usage:

&nbsp;	// node args.js hello world

&nbsp;	// Output:

&nbsp;	// All arguments: \['/path/to/node', '/path/to/args.js', 'hello', 'world']

&nbsp;	// First argument: hello

&nbsp;	// Second argument: world



/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/-/



* Environment Variables:

&nbsp;	-> // env.js

&nbsp;	console.log('Environment:', process.env.NODE\_ENV || 'development');

&nbsp;	console.log('Custom variable:', process.env.MY\_VARIABLE);

&nbsp;	console.log('Database URL:', process.env.DATABASE\_URL || 'Not set');



&nbsp;	-> // Example usage with environment variables:

&nbsp;	// NODE\_ENV=production MY\_VARIABLE=test node env.js





