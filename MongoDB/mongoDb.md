<ol>
    <li>Find all the information about each products : <b><em>db.products.find()</em></b></li>
    <li>Find the product price which are between 400 to 800 : <b><em> db.products.find({ product_price : {$gte : 400 , $lte : 800}})</em></b></li>
    <li>Find the product price which are not between 400 to 600 : <b><em>db.products.find({ product_price :{$not: {$gte : 400 , $lte : 600}}})</em></b></li>
    <li>List the four product which are grater than 500 in price : <b>d<em>b.products.find({ product_price :{$gt : 500}}).limit(4)</em></b> </li>
    <li>Find the product name and product material of each products : <b><em>db.products.find({},{ _id : 0, product_name : 1, product_material : 1})</em></b></li>
    <li>Find the product with a row id of 10 : <b> <em>db.products.find({ id : "10"})</em></b></li>
    <li>Find all products which contain the value of soft in product material : <b><em>db.products.find({ product_material : "Soft"})</em></b></li>
    <li>Delete the products which product price value are same : <b> <em>db.products.aggregate([ { $group: { _id: "$product_price", Counter: { $sum: 1 } } }, { $match: { Counter: { $gt: 1 } } }])</em></b><pre> 
    </pre>
    <b><em>db.products.deleteOne({product_price:47})</em></b></li>
</ol>