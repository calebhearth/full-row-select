To use Full Row Select, simply add the following to your html:

    $('#element-id').fullRowSelect();

You may want to do this after the document has loaded:

    $(document).ready(function() {
      $('#element-id').fullRowSelect();
    });

Your table should have two rows allotted to each data row.
The first is constructed like any other table, with cells corresponding to
the header's cells.  The second row should have its colspan attribute set to
the number of columns in the table, and contains a single cell with whatever
content it is that you would like to be shown on click.  This can include
images, links, videos, whatever.
Anything that can be inside a table can be in the one cell.

    <table id='element-id'>
      <tr>
        <th></th>
        <th></th>
        <th></th>
      </tr>
      <tr>
        <td></td>
        <td></td>
        <td></td>
      </tr>
      <tr colspan=3>
        <td>
          [extra content lives here]
        </td>
      </tr>
    </table>

Excluding the header, every even numbered row will be hidden.
Odd rows will have the class 'collapsed' and a click event added.
When the .collapsed rows are clicked, they will toggle the hidden attribute
of the next row, and the class .uncollapsed will be toggled on the row
clicked.

Because of the click event, links do not function properly.  The click on the
link will trigger toggling the hidden attribute of the child row, then the
link will load.  A patch to fix this would be appreciated, as it is not
important enough to me right now to fix this functionality.
