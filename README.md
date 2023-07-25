# Create the /add-product route which shows a form

const express = require('express');
const bodyParser = require('body-parser');

const test = express();
test.use(bodyParser.urlendcoded({extended: false}));

test.use('/add-product', (req, res, next) => {
    res.send('2nd Middleware');
    res.send('<form action="/product" method="POST"><input type="text" name="title><button type="submit">Add Product</button>');
});

test.use('/product', (req, res, next) => {
    console.log(req.body);
    res.redirect('/')
});

test.use('/', (req, res, next) => {
    res.send('2nd Middleware');
    res.send('<h1>Namaskaram</>');
});

//const server = http.createServer(test);
//server.listen(3000);
test.listen(3000);
