# jQuery

## Dynamic data to table with ajax request
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
