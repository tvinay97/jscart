There are several ways to implement the shopping cart into your webpages, here is the essential code to display your cart and products.

**Contents**
  * Add the javascript
  * Adding Products
  * Mini Cart Display
  * Cart Overview
  * Checkout

## Add the javascript ##
Add this javascript code to the **head** of your document.

```
<script type="text/javascript" src="http://jscart.googlecode.com/svn/jscart.js">

Unknown end tag for &lt;/script&gt;



<script type="text/javascript">```
```
   simpleCart.email = "email@address.com";
   simpleCart.checkoutTo = PayPal;
// simpleCart.merchantId = "118575326044237";
// simpleCart.checkoutTo = GoogleCheckout;
   simpleCart.currency = USD;
// simpleCart.currency = GBP;
// simpleCart.currency = EUR;
   simpleCart.taxRate  = 0.078;
// simpleCart.shippingFlatRate = 5.25;
   simpleCart.shippingQuantityRate = 1.00;

/* 
   CartItem.prototype.shipping = function(){
	if( this.size ){
		switch( this.size.toLowerCase() ){
			case 'small':
				return this.quantity * 10.00;
			case 'medium':
				return this.quantity * 12.00;
			case 'large':
				return this.quantity * 15.00;
			case 'bull':
				return 45.00;
			default:
				return this.quantity * 5.00;
		}
	}
};
*/

simpleCart.cartHeaders = ["Thumb_image_noHeader", "Name" , "Size_input_div_div", "Price" , "decrement_noHeader" , "Quantity", "increment_noHeader", "remove_noHeader", "Total" ];
```
```


Unknown end tag for &lt;/script&gt;

```

## Add Products ##

How to add a product with a link

```
<h2>ProductX</h2>
<span>$14.12</span>
<p>This product would make a great gift for anybody.
<a href="javascript:;" onclick="simpleCart.add('name=Baby Lion', 'price=34.95','size=Default','quantity=1','thumb=images/e.png');" >Add to cart</a></p>
```

How to add a product with options, make sure to add "simpleCart\_shelfItem" class

```
<ul>
   <li class="simpleCart_shelfItem">
      <h1 class="item_name">Evolution T-Shirt</h1>
      <p>Sale Price: <span class="item_price">$28.00</span></p>
      <img src="http://www.websitex.com/pictures/tshirt.jpg" />
      <p>Select Size: 
      <select class="item_Size">
         <option value="Small">Small</option>
         <option value="Medium">Medium</option>
         <option value="Large">Large</option>
      </select></p>
      <p>Quantity: <input type="text" class="item_quantity" value="1" style="width:20px;" /></p>
      <p><input type="button" class="item_add" value="Add to cart" /></p>
   </li>
   <li class="simpleCart_shelfItem">
      <h1 class="item_name">Baseball Hat</h1>
      <p>Sale Price: <span class="item_price">$12.00</span></p>
      <img src="http://www.websitex.com/pictures/black_hat.jpg" />
      <p>Select Size: 
      <select class="item_Size">
         <option value="Black">Black</option>
         <option value="White">White</option>
      </select></p>
      <p>Quantity: <input type="text" class="item_quantity" value="1" style="width:20px;" /></p>
      <p><input type="button" class="item_add" value="Add to cart" /></p>
   </li>
</ul>
```
## Mini Cart Display ##

Show how many products in cart and total

```
 Cart: <span class="simpleCart_total"></span> (<span class="simpleCart_quantity"></span> items) <br />
    <a href="javascript:;" class="simpleCart_empty">Empty Cart</a> <a href="#" class="viewcart">Viewcart</a>
```

## Cart Overview ##

Displays all the products in a cart, update qty, remove products, coupon code, and checkout options.

```
<div class="simpleCart_items" ></div>
<div style="clear:left"></div>
<div class="couponcode">Coupon Code<br />
<input type="text" id="ccv" value="" onchange="simpleCart.applydiscount()" /></div>

SubTotal: <span class="simpleCart_total"></span> <br />
Tax: <span class="simpleCart_taxCost"></span><br />
Shipping: <span class="simpleCart_shippingCost"></span><br />

<span id="couponcode"></span><br />
Final Total: <span class="simpleCart_finalTotal"></span><br />
<a href="#" class="simpleCart_checkout">checkout</a>
```