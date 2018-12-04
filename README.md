# jQuery

## Dynamic adding to table with ajax request (JSON format)
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

### JSON           
// https://jsonplaceholder.typicode.com/todos/

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
  },
  ...
]