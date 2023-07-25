# Routers and Filters
#Test code

const express = require('express');
const bodyParser = require('body-parser');
const test = express();
const adminRoutes = require('./routes/admin'),
const shopRoutes = require('./routes/shop');
test.use(bodyParser.urlendcoded({extended: false}));
test.use('/admin', adminRoutes);
test.use(shopRoutes);

test.use((req, res, next) => {
    res.status(404).send('<h1>Page not found</h1>');
});
test.listen(3000);

#admin code

const express = require('express');
const router = express.Router();

router.get('/add-product', (req, res, next) => {
    res.send('<form action="/product" method="POST"><input type="text" name="title><button type="submit">Add Product</button></form>');
});
router.post('/add-product', (req, res, next) => {
    console.log(req.body);
    res.redirect('/');
});
module.exports = router;
