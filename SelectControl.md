## CODE

yourBlock.js:

```
import { InspectorControls } from '@wordpress/editor';
// OR: const { InspectorControls } = wp.editor;

import { SelectControl } from '@wordpress/components';
// OR: const { SelectControl } = wp.components;

registerBlockType( ...

  ...
  
  attributes: {
  
    ... 

    selectControlValue: {
			type: 'string',
			default: ''
		}

  },

  edit( props ){

		const { selectControlValue } = props.attributes;
		const { setAttributes } = props;
    
    ...
    
    return (

			<InspectorControls>

				<SelectControl 
					label={ __('SelectControl') }
					value= { selectControlValue }
					instanceId='select-control'
					onChange={ (value)=> {
						props.setAttributes({selectControlValue: value}) } 
					}
					options={ [
						{ label: 'Big', value: '100%' },
						{ label: 'Medium', value: '50%' },
						{ label: 'Small', value: '25%' },
					] }
				/>
        
        ...
        
    )

   },
   
   save( props ){

	return ( <div>SelectControl value: { props.attributes.selectControlValue }</div> );

   }
	
    
```

## REFERENCES

[ Gutenberg Handbook | Components | SelectControl ](https://wordpress.org/gutenberg/handbook/components/select-control/)
