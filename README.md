# Bootstrap DataTable Example

This is an example of a Bootstrap 5 DataTable integrated with jQuery.

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Agent List</title>

  <!-- Bootstrap 5 CSS -->
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet">

  <!-- DataTables CSS -->
  <link rel="stylesheet" href="https://cdn.datatables.net/1.13.8/css/dataTables.bootstrap5.min.css">

  <!-- Font Awesome -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.2/css/all.min.css">

  <!-- jQuery -->
  <script src="https://code.jquery.com/jquery-3.7.1.min.js"></script>

  <!-- Bootstrap 5 JS -->
  <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js"></script>

  <!-- DataTables JS -->
  <script src="https://cdn.datatables.net/1.13.8/js/jquery.dataTables.min.js"></script>
  <script src="https://cdn.datatables.net/1.13.8/js/dataTables.bootstrap5.min.js"></script>

   <style>
    table.dataTable thead {
      background: #e5e7eb;
      color: #374151;
      font-weight: 600;
    }

    .dataTables_wrapper .dataTables_filter {
      float: right;
      text-align: right;
      margin-bottom: 1rem;
      position: relative;
      width: 100%;
      max-width: 280px;
    }

    .dataTables_wrapper .dataTables_filter input {
      width: 100%;
      padding: 6px 12px 6px 28px;
      /* reduce left padding */
      border-radius: 50px;
      border: 1px solid #d1d5db;
      transition: 0.3s;
    }

    .dataTables_wrapper .dataTables_filter input:focus {
      outline: none;
      border-color: #3b82f6;
      box-shadow: 0 0 5px rgba(59, 130, 246, 0.5);
    }

    /* Search icon closer */
    .dataTables_wrapper .dataTables_filter::before {
      content: "\f002";
      font-family: "Font Awesome 6 Free";
      font-weight: 900;
      position: absolute;
      left: 8px;
      /* closer to input */
      top: 50%;
      transform: translateY(-50%);
      color: #9ca3af;
      pointer-events: none;
      font-size: 14px;
    }


    .dataTables_wrapper .dataTables_paginate {
      margin-top: 20px;
      gap: 6px;
    }


    @media (max-width: 576px) {
      .dataTables_wrapper .dataTables_filter {
        float: none;
        text-align: center;
        margin-bottom: 10px;
        max-width: 100%;
      }

      .dataTables_wrapper .dataTables_filter input {
        width: 100%;
      }
    }
  </style>
</head>
<body>

<div class="container mt-4">
  <!-- Header -->
  <div class="page-header">
    <h4>Agent List</h4>
    <button class="btn btn-add">
      <i class="fas fa-user-plus"></i> Add Agent
    </button>
  </div>

  <!-- Table -->
  <div class="card shadow-sm border-0">
    <div class="card-body">
      <table id="myTable" class="table table-hover align-middle" style="width:100%">
        <thead>
          <tr>
            <th>ID</th>
            <th>Agent Name</th>
            <th>Email Address</th>
            <th>Total Bookings</th>
            <th>Status</th>
            <th>Actions</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>101</td>
            <td>Rahim Uddin</td>
            <td><a href="mailto:rahim.uddin@mail.com" class="text-primary">rahim.uddin@mail.com</a></td>
            <td>120</td>
            <td>
              <div class="form-check form-switch">
                <input class="form-check-input" type="checkbox" checked>
              </div>
            </td>
            <td>
              <div class="d-flex gap-2 action-btns">
                <button class="btn btn-sm btn-outline-primary"><i class="fas fa-eye"></i></button>
                <button class="btn btn-sm btn-outline-secondary"><i class="fas fa-edit"></i></button>
                <button class="btn btn-sm btn-outline-danger"><i class="fas fa-trash"></i></button>
              </div>
            </td>
          </tr>
          <tr>
            <td>102</td>
            <td>Ayesha Akter</td>
            <td><a href="mailto:ayesha.akter@mail.com" class="text-primary">ayesha.akter@mail.com</a></td>
            <td>78</td>
            <td>
              <div class="form-check form-switch">
                <input class="form-check-input" type="checkbox">
              </div>
            </td>
            <td>
              <div class="d-flex gap-2 action-btns">
                <button class="btn btn-sm btn-outline-primary"><i class="fas fa-eye"></i></button>
                <button class="btn btn-sm btn-outline-secondary"><i class="fas fa-edit"></i></button>
                <button class="btn btn-sm btn-outline-danger"><i class="fas fa-trash"></i></button>
              </div>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</div>

<script>
 $(document).ready(function () {
      $('#myTable').DataTable({
        paging: true,
        lengthChange: true,
        searching: true,
        ordering: true,
        info: true,
        autoWidth: false,
        responsive: true,
        language: {
          search: "_INPUT_",
          searchPlaceholder: "Search agents...",
          lengthMenu: "Show _MENU_ agents",
          info: "Showing _START_ to _END_ of _TOTAL_ agents",

        }

      });
    });
</script>

</body>
</html>

