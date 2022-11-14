# Quform 2 Generate Dropdown Options Dynamically

The code below will allow you to generate custom options for dropdown field using PHP using quform 2.

```php
add_action( 'quform_pre_display_1', function ( Quform_Form $form ) {
	$element = $form->getElement( 'quform_1_2' );

	if ( $element instanceof Quform_Element_Multi ) {
      $options = array(); 
			$options[] = array( 'label' => 'Test', 'value' => 'test', 'id' => '1' );
			$options[] = array( 'label' => 'Test 2', 'value' => 'test-2', 'id' => '2' );
		  $element->setOptions( $options );
	}
} );
```

## Notes
- Please see https://support.themecatcher.net/quform-wordpress-v2/guides/hooks/quform_pre_display for reference about using quform_pre_display_1 hook
- Please make sure to disable "Validate submitted value" in the field options or add your custom validation.
