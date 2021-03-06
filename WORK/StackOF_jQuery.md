# Data table

[jQuery DataTables: How to add a checkbox column](http://www.gyrocode.com/articles/jquery-datatables-how-to-add-a-checkbox-column/)

```js
$(document).ready(function (){
   var table = $('#example').DataTable({
      'ajax': {
         'url': '/lab/articles/jquery-datatables-how-to-add-a-checkbox-column/ids-arrays.txt'
      },
      'columnDefs': [{
         'targets': 0,
         'searchable': false,
         'orderable': false,
         'className': 'dt-body-center',
         'render': function (data, type, full, meta){
             return '<input type="checkbox" name="id[]" value="' + $('<div/>').text(data).html() + '">';
         }
      }],
      'order': [[1, 'asc']]
   });

   // Handle click on "Select all" control
   $('#example-select-all').on('click', function(){
      // Get all rows with search applied
      var rows = table.rows({ 'search': 'applied' }).nodes();
      // Check/uncheck checkboxes for all rows in the table
      $('input[type="checkbox"]', rows).prop('checked', this.checked);
   });

   // Handle click on checkbox to set state of "Select all" control
   $('#example tbody').on('change', 'input[type="checkbox"]', function(){
      // If checkbox is not checked
      if(!this.checked){
         var el = $('#example-select-all').get(0);
         // If "Select all" control is checked and has 'indeterminate' property
         if(el && el.checked && ('indeterminate' in el)){
            // Set visual state of "Select all" control
            // as 'indeterminate'
            el.indeterminate = true;
         }
      }
   });

   // Handle form submission event
   $('#frm-example').on('submit', function(e){
      var form = this;

      // Iterate over all checkboxes in the table
      table.$('input[type="checkbox"]').each(function(){
         // If checkbox doesn't exist in DOM
         if(!$.contains(document, this)){
            // If checkbox is checked
            if(this.checked){
               // Create a hidden element
               $(form).append(
                  $('<input>')
                     .attr('type', 'hidden')
                     .attr('name', this.name)
                     .val(this.value)
               );
            }
         }
      });
   });

});
```
```html
<table id="example" class="display select" cellspacing="0" width="100%">
   <thead>
      <tr>
         <th><input type="checkbox" name="select_all" value="1" id="example-select-all"></th>
         <th>Name</th>
         <th>Position</th>
         <th>Office</th>
         <th>Extn.</th>
         <th>Start date</th>
         <th>Salary</th>
      </tr>
   </thead>
   <tfoot>
      <tr>
         <th></th>
         <th>Name</th>
         <th>Position</th>
         <th>Office</th>
         <th>Extn.</th>
         <th>Start date</th>
         <th>Salary</th>
      </tr>
   </tfoot>
</table>
```

-----------------

## Excel

### Jquery Export

[Exclude Specific Columns when exporting data from HTML table to excel](http://stackoverflow.com/questions/19983822/exclude-specific-columns-when-exporting-data-from-html-table-to-excel
)


```
var $table =  $('#testTable').clone();

$table = filterNthColumn($table, 9); //remove Action column

function filterNthColumn($table, n){
    return $table.find('td:nth-child('+n+'), th:nth-child('+n+')').remove();
}
```
