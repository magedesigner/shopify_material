# SHOPIFY Brands logo

A set of Shopify files used to implement a brands logo section on a Shopify store using (S)CSS and Liquid. 

NOTE: These files relay on jQuery being included in you theme.liduid before the close of **```</head>```**
```
{{ '//code.jquery.com/jquery-1.11.3.min.js' | script_tag }}
{{ '//cdnjs.cloudflare.com/ajax/libs/slick-carousel/1.9.0/slick.min.js' | script_tag }}
{{ 'slick.min.css' | asset_url | stylesheet_tag }}
```

## Features

* Let users add brands section on home page show different brands with logo.


## Usage

To begin using the Shopify brand logo section copy the following files into your project directory:
* assets/logo-bar.css
* assets/slick.min.css
* Sections/logo-bar-section-full.liquid


You must initalize the **slider** module at the (debut theme) theme.js line-number:7458 add below code.
If any another theme active in your store you can use this code at theme.liquid before **```</body>```** end.

```
<!-- Add code in theme.js files  ================================ -->
<script>
  $(document).ready(function() 
{
	// add this code
	$('.brand-slider').not('.slick-initialized').slick({
	  slidesToShow: 3,
	  slidesToScroll: 1,
	  arrows: true,
	  responsive: [
	  	{
          breakpoint: 1200,
	      settings: {
	        slidesToShow: 2,
            slidesToScroll: 1,
	        arrows: true,
	      }
	    },
        {
	      breakpoint: 480,
	      settings: {
	        slidesToShow: 1,
            slidesToScroll: 1,
	        arrows: true,
	      }
	    }
	  ]
	});
	// slider code end 
});
</script>
```
## Optional

* If you have use debut theme (slick.min.css) this files optional 
* if you have issue with slider is initialized but not display use below css for troubleshooting

```
<style type="text/css">
	.brand-slider .slick-slide div{ display: inline; }
</style>
```