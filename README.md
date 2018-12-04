# jQuery

## Dynamic adding to table with ajax request (JSON format)
```js
    $(document).ready(function() {	
        $.ajax({
            url: 'https://jsonplaceholder.typicode.com/todos/',
            dataType: 'json',
            type: 'get',
            cache: false,
            success: function(data) {
                books_id = [];
                titles = [];
                $(data).each(function(index, value) {
                    // if(value.completed)
                        titles[index] = "<td>" + JSON.stringify(value.title) + "</td>";
                        books_id[index] = "<td>" + JSON.stringify(value.id) + "</td>";
                    $( "#waypointsTable" ).append("<tr>" + titles[index] + books_id[index] + "</tr>");
                });
            }
        });
```
### JSON           
```json
[
  {
    "userId": 1,
    "id": 1,
    "title": "delectus aut autem",
    "completed": false
  },
  {
    "userId": 1,
    "id": 2,
    "title": "quis ut nam facilis et officia qui",
    "completed": true
  }
]
```
### HTML
```html
	<table style="width:50%" id="waypointsTable">
	<caption><b>Sort from JSON to table with jQuery</b></caption>
		<tr>
			<th>Title</th>
			<th>ID</th>
		</tr>
    </table>
```
### CSS
```css
    table, th, td {
        border: 1px solid black;
        border-collapse: collapse;
    }
    th, td {
        padding: 5px;
        text-align: left;
    }
    th {
        padding: 5px;
        text-align: center;
    }
    tr:hover { background-color:yellow; }   /* row hover only with CSS*/
```