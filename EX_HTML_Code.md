## Modal Bootstrap
```html
<link href="//maxcdn.bootstrapcdn.com/bootstrap/3.3.2/css/bootstrap.min.css" rel="stylesheet"/>
<div id="modalUserViewEdits" class="modal-block modal-block-lg mfp-hide">
<section class="panel">
    <header class="panel-heading">
        <h2 class="panel-title">User</h2>
    </header>

    <div class="alert alert-message hide">
        <!--User message alert popup-->
    </div>
    <div class="form-data">
        <form id="form_UserEdits" class="form-horizontal form-userEditsDetails">
            <div class="panel-body">
                <div class="form-group">
                    <label class="control-label col-sm-3">
                        Username
                        <span class="required">*</span>
                    </label>
                    <div class="col-sm-9">
                        <input class="form-control" id="userId_modalUserViewEdits" type="hidden" name="id" value="0" />
                        <input class="form-control" id="userAction_modalUserViewEdits" type="hidden" name="action" value="active"/>
                        <input class="form-control" id="userOperation_modalUserViewEdits" type="hidden" name="operation" />
                        <input class="form-control" id="userName_modalUserViewEdits" type="text" placeholder="Username" name="userName" disabled />
                    </div>
                </div>
            </div>
        </form>
        <div id="divDynamicTable" class="form-data table-responsive">
		<div class=container-fluid>
            <table class="table table-bordered table-striped mb-none" id="table_viewUserChanges" data-swf-path="lookandfeel/assets/vendor/jquery-datatables/extras/TableTools/swf/copy_csv_xls_pdf.swf">
                <thead>
                    <tr>
                        <th>Field</th>
                        <th>Old Value</th>
                        <th>New Value</th>
                    </tr>
                </thead>
                <tbody>
                </tbody>
            </table>
			</div>
        </div>
        <footer class="panel-footer">
            <div class="row">
                <div class="col-md-12 text-right">
                    <button type="button" id="btnApproveUserEdit" class="btn btn-success" data-name='approve'>Approve</button>
                    <button type="button" id="btnDeclineUserEdit" class="btn btn-danger" data-name='decline'>Decline</button>
                    <button type="button" class="btn btn-default modal-dismiss">Cancel</button>
                </div>
            </div>
        </footer>
    </div>
</section>
```


## Data Table

```
$('#example').dataTable( {
  "columnDefs": [
    { "width": "20%", "targets": 0 }
  ]
} );

$('#example').dataTable( {
  "columns": [
    { "width": "20%" },
    null,
    null,
    null,
    null
  ]
} );
```
