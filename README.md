# Assignment1-Mern

A dashboard for the assignment using Html, Css and Boothstrap

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Admin Dashboard</title>
    
    <!-- Bootstrap 5 CSS -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
    
    <!-- Font Awesome for Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        body {
            font-family: Arial, sans-serif;
        }
        .sidebar {
            height: 100vh;
            position: fixed;
            width: 250px;
            background: #343a40;
            padding-top: 20px;
        }
        .sidebar a {
            color: white;
            padding: 10px;
            display: block;
            text-decoration: none;
        }
        .sidebar a:hover {
            background: #495057;
        }
        .content {
            margin-left: 250px;
            padding: 20px;
        }
        @media (max-width: 768px) {
            .sidebar {
                width: 100px;
            }
            .content {
                margin-left: 100px;
            }
        }
    </style>
</head>
<body>
    <!-- Sidebar -->
    <nav class="sidebar">
        <a href="#" class="text-center fs-4"><i class="fas fa-tachometer-alt"></i> Dashboard</a>
        <a href="#"><i class="fas fa-users"></i> Users</a>
        <a href="#"><i class="fas fa-chart-bar"></i> Reports</a>
        <a href="#"><i class="fas fa-cogs"></i> Settings</a>
    </nav>
    
    <!-- Main Content -->
    <div class="content">
        <!-- Navbar -->
        <nav class="navbar navbar-expand-lg navbar-light bg-light">
            <div class="container-fluid">
                <button class="btn btn-dark" data-bs-toggle="collapse" data-bs-target="#sidebarMenu">☰</button>
                <h3 class="ms-3">Admin Dashboard</h3>
            </div>
        </nav>
        
        <!-- Dashboard Cards with Popups -->
        <div class="row mt-4">
            <div class="col-md-4">
                <div class="card text-white bg-primary mb-3" onclick="showPopup('Total Users: 1,200')">
                    <div class="card-body">
                        <h5 class="card-title">Total Users</h5>
                        <p class="card-text fs-3">1,200</p>
                    </div>
                </div>
            </div>
            <div class="col-md-4">
                <div class="card text-white bg-success mb-3" onclick="showPopup('Revenue: $50,000')">
                    <div class="card-body">
                        <h5 class="card-title">Revenue</h5>
                        <p class="card-text fs-3">$50,000</p>
                    </div>
                </div>
            </div>
            <div class="col-md-4">
                <div class="card text-white bg-warning mb-3" onclick="showPopup('Orders: 350')">
                    <div class="card-body">
                        <h5 class="card-title">Orders</h5>
                        <p class="card-text fs-3">350</p>
                    </div>
                </div>
            </div>
        </div>
        
        <!-- Chart Section -->
        <div class="row">
            <div class="col-md-6">
                <div class="card">
                    <div class="card-body">
                        <h5 class="card-title">Sales Overview</h5>
                        <canvas id="salesChart"></canvas>
                    </div>
                </div>
            </div>
        </div>
        
        <!-- Table Section -->
        <div class="row mt-4">
            <div class="col-md-12">
                <div class="card">
                    <div class="card-body">
                        <h5 class="card-title">User Data</h5>
                        <div class="table-responsive">
                            <table class="table table-bordered">
                                <thead class="table-dark">
                                    <tr>
                                        <th>ID</th>
                                        <th>Name</th>
                                        <th>Email</th>
                                        <th>Role</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr onclick="showPopup('User: John Doe, Email: john@example.com, Role: Admin')">
                                        <td>1</td>
                                        <td>John Doe</td>
                                        <td>john@example.com</td>
                                        <td>Admin</td>
                                    </tr>
                                    <tr onclick="showPopup('User: Jane Smith, Email: jane@example.com, Role: User')">
                                        <td>2</td>
                                        <td>Jane Smith</td>
                                        <td>jane@example.com</td>
                                        <td>User</td>
                                    </tr>
                                    <tr onclick="showPopup('User: Michael Brown, Email: michael@example.com, Role: Editor')">
                                        <td>3</td>
                                        <td>Michael Brown</td>
                                        <td>michael@example.com</td>
                                        <td>Editor</td>
                                    </tr>
                                </tbody>
                            </table>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
    
    <!-- Scripts -->
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/js/bootstrap.bundle.min.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <script>
        // Chart.js Sales Overview Chart
        const ctx = document.getElementById('salesChart').getContext('2d');
        new Chart(ctx, {
            type: 'bar',
            data: {
                labels: ['Jan', 'Feb', 'Mar', 'Apr', 'May'],
                datasets: [{
                    label: 'Sales ($)',
                    data: [1200, 1500, 1800, 2000, 2200],
                    backgroundColor: 'rgba(54, 162, 235, 0.6)'
                }]
            }
        });

        // Function to show popups
        function showPopup(message) {
            alert(message);
        }
    </script>
</body>
</html>
