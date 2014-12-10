## Example
![Example Image](/img/example.jpg "Example Image")

# Summary
I needed to extend the Bootstrap progress bar to handle a timeline of deadlines. I felt that telling people how many days were left until an event promoted procrastination, so I decided I'd make the entire thing visual in the hopes it'd combat the issue of last minute ticket purchasing and maybe even create a sense of urgency with the "burn down" bar.

So, if you provide a series of deadlines with the expected data as seen in the .js file's default data (you can remove or replace this if you choose to pass in that data from your page), the library will populate your progress bar with color coded bars of appropriate widths relative to the start and end dates of your timeline. The current deadline phase like "earlybird" will get an active class that turns on the fancy candycane animated stripes and adds a special gray "burn bar" to expand as you get further into that period. That period's own little countdown if you will. And any period that's completely over turns gray.

Right now it's only on pageload and I'm sure there are other things I could improve, but I included the basic jQuery plugin and additional styling needed for the injected markup. You can change it as you see fit.

Anyway, enjoy. Comment or extend as you'd like.

## Usage
### Include

```html
https://maxcdn.bootstrapcdn.com/bootstrap/3.3.0/css/bootstrap.min.css

https://code.jquery.com/jquery-1.11.1.min.js
https://maxcdn.bootstrapcdn.com/bootstrap/3.3.0/js/bootstrap.min.js
path/to/timeline.js```

### Markup

```html
<div id="progress-bar-wrapper" class="progress"></div>```

### Script

```javascript
// The usefulness of this example will almost immediately expire, 
// so update the dates as necessary

// colors are the normal bootstrap colors:
// info, success, warning, danger

$(document).ready(function(){
	$('#progress-bar-wrapper').timeline({
		start: "November 16 2014",
		end: "February 13 2015",
		deadlines: [
			{
				"name": "Earlybird",
				"price": 300,
				"startDate": "November 16 2014",
				"color": "success"
			},
			{
				"name": "Normal",
				"price": 400,
				"startDate": "December 16 2014",
				"color": "warning",
			},
			{
				"name": "Latebird",
				"price": 450,
				"startDate": "January 30 2015",
				"color": "danger",
			}
		]
	});
});
```