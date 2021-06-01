<script>

    let total = 0;

    let products = [
        {id: 1,quantity:1,name: 'Apple', price: 10, image: 'https://i2.wp.com/ceklog.kindel.com/wp-content/uploads/2013/02/firefox_2018-07-10_07-50-11.png?fit=641%2C618&ssl=1'},
        {id: 2,quantity:1,name: 'Orange', price: 15, image: 'https://i.pinimg.com/736x/05/79/5a/05795a16b647118ffb6629390e995adb.jpg'},
        {id: 3,quantity:1,name: 'Mango', price: 15, image: 'https://thumbs.dreamstime.com/b/single-red-mango-fruit-5986687.jpg'},
    ]

    let purchaseProducts = [];

    $: shipping = total * .1;

    $: grandTotal = total + shipping;

    function AddToCart(product, index){
        total = total + product.price;
        let isExist = purchaseProducts.indexOf(product);
        if(isExist > -1){
            product.quantity += 1;
            purchaseProducts = purchaseProducts
        } else {
            let result = purchaseProducts.push(product);
            purchaseProducts = purchaseProducts
        }
        
    }

    $: if(total > 500){
        shipping = 0;
    }

    function checkout(){
        if(purchaseProducts.length > 0){
            alert('Purchase Done!');
            purchaseProducts = [];
            total = shipping = grandTotal =0;
        } else {
            alert('please add some product in cart')
        }
    }
    
    function remove(index){
        let temp = purchaseProducts.splice(index, 1);
        console.log(temp);
        purchaseProducts = purchaseProducts;
    }

    // $: console.log(purchaseProducts)
</script>

<div class="row">
    <div class="col">
        <h2>All Products</h2>
        {#each products as product, index}
            <div class="product">
                <img src="{product.image}" alt="" width='150'>
                <div>
                    <h4>Name: {product.name}</h4>
                    <h4>Price: {product.price}</h4>
                    <button on:click="{() => AddToCart(product, index)}">Add To Cart</button>
                </div>
            </div>
        {/each}
        </div>
    <div class="col">
        <h2>Purchase Products</h2>
        {#each purchaseProducts as product, index}
        <div class="product">
            <img src="{product.image}" alt="" width='150'>
            <div>
                <h4>Name: {product.name}</h4>
                <h4>Price: {product.price}</h4>
                <h4>Quantity: {product.quantity}</h4>
                <button on:click="{() => remove(index)}">Remove</button>
            </div>
        </div>
        {/each}
        {#if purchaseProducts.length > 0}
        <button on:click="{checkout}">Checkout</button>
        {/if}
    </div>
    
</div>
<hr>
<p>Total: {total}</p>
<p>Shipping: {shipping}</p>
<p>Grand Total: {grandTotal}</p>
<style>
    .row {
        width: 600px;
        display: flex;
        margin: 0 auto;
    }
    .col {
        width: 50%;
    }
    .product {
        display: flex;
        /* flex-direction: column; */
    }
</style>