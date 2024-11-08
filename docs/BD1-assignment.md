BD1 - Assignment
Introduction

FlipDeal is an eCommerce company that has recently started dealing with multiple fitness products. Currently, they are starting small with 3 items in their cart:

    Shoes

    Bag

    Jacket

They have also launched a “Prime Membership” program where if you are the member at their platform, you get good discounts on the products.

Now, they already have built the frontend of the application showing the cart page with product details, images, and other options. But now they want a backend developer who can create the APIs for various cart actions and work with frontend.
Objective

FlipDeal has given you the project to create the APIs on the backend for their “Cart Page”.

Before declaring the API Endpoints, make sure you declare the following variables and also import cors to the code.


Endpoint 1: Calculate the total price of items in the cart

Create an endpoint that takes a newItemPrice and cartTotal as a query parameter and returns total cart value.

Write an Express code snippet.

    Declare an endpoint cart-total using the get keyword.

    Declare two variables newItemPrice and cartTotalto take the input.

    Parse the input as a float to calculate the total cart price.

    Return the result as a string.

API Call: <http://localhost:3000/cart-total?newItemPrice=1200&cartTotal=0>

Expected Output: 1200


Endpoint 2 : Apply a discount based on membership status

Create an endpoint that takes a cartTotal and isMember as a query parameter and returns final price after applying the discount.

Write an Express code snippet.

    Declare an endpoint /membership-discount using the get keyword.

    Declare two variables cartTotal and isMember to take the input.

    Parse the cartTotal as a float to calculate the total cart value.

    Return the result as a string.

If the Membership status = true, then the discount percentage is applied

If the Membership status = false, no discount is applied

API Call: <http://localhost:3000/membership-discount?cartTotal=3600&isMember=true>

Expected Output: 3240


Endpoint 3 : Calculate tax on the cart total

Create an endpoint that takes a cartTotal as a query parameter and returns the tax applied on the Cart Total.

Write an Express code snippet.

    Declare an endpoint /calculate-tax using the get keyword.

    Declare a variable cartTotal as input.

    Parse the cartTotal input as float to calculate the cart amount after applying the tax rate.

    Return the result as a string.

API Call: <http://localhost:3000/calculate-tax?cartTotal=3600>

Expected Output: 180


Endpoint 4 : Estimate delivery time based on shipping method

Create an endpoint that takes a shippingMethod and distance as a query parameter and returns the number of days for delivering the package.

Write an Express code snippet.

    Declare an endpoint /estimate-delivery using the get keyword.

    Declare 2 variables shippingMethod and distance as inputs.

    Parse the distance input as float to calculate the delivery time based on the distance.

    Return the result as a string.

If the shippingMethod = Standard, the delivery days will be 1 day per 50 kms.

If the shippingMethod = Express, the delivery days will be 1 day per 100 kms.

API Call: <http://localhost:3000/estimate-delivery?shippingMethod=express&distance=600>

Expected Output: 6


Endpoint 5 : Calculate the shipping cost based on weight and distance

Create an endpoint that takes weight and distance as query parameters and returns the shipping cost of the packages.

Write an Express code snippet.

    Declare an endpoint /shipping-cost using the get keyword.

    Declare 2 variables weight and distance as inputs.

    Parse the weight and distance input as float to calculate the price based on the distance.

    Return the result as a string.

Note: The formula to calculate shipping cost would be:

weight * distance * 0.1 where weight is 2 kgs.

API Call: <http://localhost:3000/shipping-cost?weight=2&distance=600>

Expected Output: 120


Endpoint 6 : Calculate loyalty points earned from a purchase

Create an endpoint that takes purchaseAmount as query parameters and returns the loyalty points.

Write an Express code snippet.

    Declare an endpoint /loyalty-points using the get keyword.

    Declare a variable purchaseAmount as an input.

    Parse the purchaseAmount input as float to calculate the loyalty points based on the purchase amount.

    Return the result as a string.

API Call: <http://localhost:3000/loyalty-points?purchaseAmount=3600>

Expected Output: 7200


Amazing!

FlipDeal is content with the APIs that you have built.


Integrating it with Frontend

As the next step, you need to integrate your APIs with their front end. Make sure, you keep checking the logger (On the bottom right of your frontend screen) to ensure that your APIs are working fine at every action.

This is how FlipDeal’s Cart page works:


What are the various actions a user has to take?

    Add all the 3 Products to the Cart.

    Once the products are added, check for the membership status.

    If the membership status is “Standard”: No Discount is Added. If the membership status is “Prime”: 10% discount is added to the total cart amount.

    Once done, select the location where you want your package to be delivered. We have 4 cities:

    Mumbai

    Delhi

    Chennai

    Kolkata

    Based on the distance for the selected city, it calculates the “Shipping Cost”.

    Now, select the type of “Shipping Method”. If the Shipping method is “Standard”, it calculates the time in which the package will be delivered in which is 1 day per 50 kms. If the Shipping method is “Express”, it calculates the time in which the package will be delivered which is 1 day per 100 kms

    The Estimated Delivery time is visible.

    Based on all the factors, the total payable amount is calculated.

        Total Cart Amount

        Membership Discount (if any)

        Shipping Cost (Based on the Location)

        Estimated Delivery Time (in days)

        Tax Rate

        Loyalty Points

Note: If you wish to test it with other factors, click “Reset form” button and try again.


How to integrate the Backend APIs with FlipDeal’s Frontend UI?

    You need to deploy your StackBlitz project to Vercel by following the given video: https://drive.google.com/file/d/18OCtAhMJtplpC1Hi5msUxyGSLy849K8d/view?usp=sharing

    Once done, go to this link: https://bd1-1.vercel.app/

    Copy your Vercel URL to the Server URL text box.


    Once you click “Save Changes”, it will show the Cart Page section with 3 items.

    Add all the 3 items by clicking “Add to Cart” Note: To enable the “Select Membership” button, you need to add all the 3 items. If you have already added 1 item, you can’t add the same item again.

    When you take any user action, you can see the response of your APIs on the bottom right of the screen also known as the “Logger”.


API Endpoints

    Calculate Cart Total: When a user adds a new item to the cart, the frontend makes a GET request to /cart-total with the price of the new item and the current cart total to update the total price.

    Apply Membership Discount: If the user is a member, the frontend makes a GET request to /membership-discount to apply any applicable discounts to the cart total.

    CalculateTax: For the total cart amount, the frontend makes a GET request to /calculate-tax to apply 5% tax rate on the total cart amount.

    Estimate Delivery Time: The user can see the estimated delivery time by making a GET request to /estimate-delivery with the chosen shipping method and delivery distance.

    Calculate Shipping Cost: The shipping cost based on the weight of the items and the delivery distance is calculated by making a GET request to /shipping-cost.

    Calculate Loyalty Points: To calculate the loyalty points, front end is making a GET request to /loyalty-points to add 2 points per $1.

Conclusion

You are all set! FlipDeal is all set to launch their cart page now because you helped them set up the Backend APIs. Everything is running smoothly.