<script>

  export let data;
	
	let products = data.products;
</script>
<style>
	.products-list {
		list-style: none;
		padding: 0;
		display: flex;
    flex-direction: column;
    align-items: center;
	}
	
	.products-list__item {
		margin-bottom: 1rem;
	}
	
	.product {
		display: flex;
    border: 1px solid #e5eaef;
    border-radius: 0.5rem;
    overflow: hidden;
		max-width: 44rem;
	}
	
	.product__image {
		width: 12rem;
		height: auto;
		background-position: center;
    background-size: cover;
	}
	
	.product__content {
		padding: 0.5rem 1rem;
	}
	
	.product__header {
		position: relative;
	}
	
	.product__header h3 {
		margin: 0;
	}
	
	.product__body p {
		display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-line-clamp: 4;
    overflow: hidden;
    width: 30rem;
	}
	
	.product__price {
		position: absolute;
		right: 0;
		top: 50%;
		transform: translate3d(0, -50%, 0);
	}
	
	.add-btn {
		margin-bottom: 0;
	}

  .heading{
    text-align: center;
    font-size: 40px;
  }
  .product-list-count{
    text-align: center;
  }
  .list-test{
    margin-left: 30%;
  }
</style>
<main>

  <h1 class="heading">Storefront</h1>
  <div class="list-test">
    <p class="product-list-count">We currently have {data.products.length} products</p>
  </div>


  {#if products.length}
	<ul class="products-list">
		{#each products as product (product.id)}
			<li class="products-list__item">
				<div class="product">
					<div class="product__image" style="background-image: url('{product.imageUrl}')" />
					<div class="product__content">
						<div class="product__header">
							<h3 class="product__name">{product.name}</h3>
							<strong class="product__price">${product.price}</strong>
						</div>
						<div class="product__body">
							<p class="product__description">{product.description}</p>
						</div>
						<div class="product__footer">
							<a href={product.paymentUrl}>Buy now</a>
						</div>
					</div>
				</div>
			</li>
		{/each}
	</ul>
{/if}

</main>