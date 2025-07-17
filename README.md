$('.workarea').html(`
  <table class="table">
    <thead>
      <tr>
        <th>Name</th>
        <th>Description</th>
        <th>Status</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>Test Doc 1</td>
        <td>This is a hardcoded document</td>
        <td>Active</td>
      </tr>
      <tr>
        <td>Test Doc 2</td>
        <td>This is another hardcoded document</td>
        <td>Inactive</td>
      </tr>
    </tbody>
  </table>
`);
this.highlightTab();
