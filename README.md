# ACF Magento Product Select Field

Base on ACF Field Type Template

##Setup

1. Install [Magento Wordpress integration](http://wordpress.org/support/plugin/magento-wordpress-integration/), make sure it works first.
2. Put this into wp-content/plugins folder
3. Activate this plugin. (Make some products in your magento site).
4. In the template, you could use such code to call out a magento collection 
```
$product_ids = get_field('featured_products');

$_productCollection = Mage::getModel('catalog/product')->getCollection();
$_productCollection
->addAttributeToSelect('*')
->addFieldToFilter( 'entity_id', array('in'=>$product_ids))
->load();

foreach($_productCollection as $_product):
  echo $_product->getName();
endforeach;

```


##Headsup

1. Only support ACF v.5 at the moment.
