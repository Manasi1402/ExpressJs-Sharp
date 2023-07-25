# ExpressJs-Sharp

const http = require('http');
const express = require('express');
const test = express();

test.use((req, res, next) => {
    res.send('Middleware');
    next(); // Allows the request to continue to the next  middleware in line
});
test.use((req, res, next) => {
    res.send('2nd Middleware');
    res.send('<h1>Namaskaram</>');
});

//const server = http.createServer(test);
//server.listen(3000);
test.listen(3000);
