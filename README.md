[![npm](https://img.shields.io/npm/v/vuejs-image.svg)]() [![npm](https://img.shields.io/npm/dt/vuejs-image.svg)]() [![npm](https://img.shields.io/npm/dw/vuejs-image.svg)]() 
# Vue Image :zap:

+ This is [on GitHub](https://github.com/vinayakkulkarni/vue-image)  so let me know if I've b0rked it somewhere, give me a star :star: if you like it :beers:

+ This uses Semantic-UI classes in some cases, so you might want to use this plugin with Semantic-UI. For a framework independent plugin visit [v-image](https://github.com/vinayakkulkarni/v-image/)

### :white_check_mark: Install :ok_hand:
``` npm i vuejs-image```

### :white_check_mark: Usage :mortar_board:
- Add it to your component  :tada:

```javascript
import vueImage from 'vuejs-image';

export default {
	components : { vueImage },
	data() : {
		return {
			image: ''
		},
	},
	methods: {
		localVariable(imageSentFromComponent) {
			this.image = imageSentFromComponent;
		}
	}
}
```

### :white_check_mark: Example :four_leaf_clover: 

```html
<vue-image 
	alt="Alt Text for the Image" 
	name="name"
	maxWidth="100px"
	maxHeight="100px"
	@loadImage="localVariable">
</vue-image>
```
### :white_check_mark: :book: Props: 
+ `id` (ID attribute for html `input`) [default: "name"]
+ `name` (name attribute for html `input`) [default: "name"]

+ `maxWidth` (Max Width for Image Container)  [default: "200px"]
+ `maxHeight` (Max Height for Image Container)  [default: "200px"]
+ `paddingBottom` (Padding Bottom between Image and Button) [default: "5px"]

### :white_check_mark: :ear: Listener: 
+ `loadImage` (load the base64 to your custom component's variable (see example)) [default: ""]

## NPM :octocat:  

[![NPM](https://nodei.co/npm/vuejs-image.png?downloads=true&downloadRank=true&stars=true)](https://nodei.co/npm/vuejs-image/)
