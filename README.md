# ssMasonryGallery
Create interesting masonry layout/collage effect with super simple html and barely any javascript. Gallery option is also available to open images in a lightbox.

[Demo](https://veek727.github.io/ssMasonryGallery/)

### Features
* Simple HTML
* No javascript/css knowledge required
* Row or Column wise layout
* Responsive
* Lightbox gallery
* Optional thumbnails for fast loading

### Installation
1. Add files
```
<link rel="stylesheet" type="text/css" href="dist/ssMasonryGallery.min.css">

<script src="src/jquery-3.3.1.min.js"></script>
<script src="dist/ssMasonryGallery.min.js"></script>
```

2. Create HTML
```
<div id="ss-masonry">
		  <img src="src/img/1c99.jpg" />
		  <img src="src/img/6e1d.jpg" />
      ...
</div>
```

3. Initialize
```
<script>
// This code comes after including the files
$(window).on('load', function(){ //use window.load to wait till the images are loaded
	$('#ss-masonry').ssMasonryGallery();
});
</script>
```

### Options
| Option  | Type  | Default | Description |
|---------|-------|---------|-------------|
| mode  | string  | row  | In "rows" mode images are neatly organized in rows, width of images vary while heights are constant. In "columns" mode, the images are organized in columns similar to pinterest. The widths remain constant while height varies |
| margin  | int | 5 | Gaps between images in pixels |
| gallery | boolean | true  | images can be clicked on to open them in lightbox |
| responsive  | array of objects  | see below | An array to define breakpoints, row height and number of columns. More info below |

`responsive` is an array of objects with following format
```
responsive: [
	{
		breakpoint: 0, //first breakpoint must be defined and zero in case you are overiding defaults
		rowHeight: 400, // needed in case of rows mode, can be skipped if using column mode. This is the maximum height of row
		columns: 1 // needed in case of columns mode, can be skipped if using row mode. How many columns should be created in the container
	},
	{
		breakpoint: 480,
		rowHeight: 250,
		columns: 2
	},
	{
		breakpoint: 720,
		rowHeight: 250,
		columns: 3
	}
  ...
]
```
Some options are defined in the HTML as `data-` attributes.
1. To use thumbnail
```
<img src="img/thumbnail.jpg" data-highres="img/fullresolution.jpg">
```
Masonry layout will use thumbnail while lightbox will use high res image
2. To add captions in lightbox
```
<img src="img/myimage.jpg" data-caption="I define this image">
```

### Events
| Name | Description |
|------|-------------|
| onLoad | Executed when layout is drawn and execution is completed |

---
Follow me on Twitter if you like [@MrVipulKapoor](https://twitter.com/MrVipulKapoor)

