# Xend Payment SDK

This is the test Xend Payment Sdk. Like the live one, it allows a user to make payments via the payment methods made available to them by xend. For now, the sdk supports making payments
via 
* Xend (If the sender is already a xend user)
* Bank account (If the sender or the sendee have reserved an account for this purpose)
* Paystack 
* Monnify

### How to Use
After cloning the repo, type **npm run dev-server** into the command line to generate the sdk and then **npm run minify** to create a minified version. To test, you can host this folder on your express server. move the **payxend.min.js** into the assets folder in your express server.

On the project you want to use your xend payment sdk, provide the script source, include this function in your script file and then, invoke the function. 


### Inline sample
```html
<form >
    <script src="http://localhost:5000/assets/payxend.min.js"></script>
    <button type="button" onclick="openXendSdk()"> Pay </button> 
</form> 
```

``` javascript
<script>
    function openXendSdk(){
    
        Payment.setup(
            {
                amount: 0,
                customerName: '',
                receiverName: '',
                image: '',
                customerEmail: '',
                paymentPurpose: '',
                customerNumber: '',
                invoiceNum: '',
                receiverXendCode: '',
                customerXendCode: '',     
            }
        )
    } 
</script> 
```

### Requirements
 * {Number} amount Amount user wants to pay.
 * {String} customerName Customer's name.
 * {String} receiverName Receiver's name.
 * {String} image Receiver's image.
 * {String} customerEmail Customer's email.
 * {String} paymentPurpose Purpose can be 'Subscription' or 'MerchantBranch' or MerchantCustomer' or 'Invoice'.
 * {String} customerNumber Customer's phone number
 * {String} invoiceNum Customer's invoice number if payment is via invoice, otherwise, return empty string
 * {String} receiverXendCode Receiver's Xend Code
 * {String} customerXendCode Customer's Xend Code