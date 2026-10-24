Assignment 8.4 — Dashboard with Grid and Flexbox1. Project structure
Create these two files in your project:


text
Assignment-8.4/
├── index.html
└── style.css
2. HTML code — index.html

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dashboard - Assignment 8.4</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <div class="dashboard">

        <!-- Header -->
        <header class="header">
            <h2>My Dashboard</h2>
            <div class="profile">
                <span>Welcome, Admin</span>
                <div class="avatar">A</div>
            </div>
        </header>

        <!-- Sidebar -->
        <aside class="sidebar">
            <h2>MyPanel</h2>
            <nav>
                <a href="#" class="active">🏠 Dashboard</a>
                <a href="#">📊 Analytics</a>
                <a href="#">📦 Products</a>
                <a href="#">👥 Customers</a>
                <a href="#">⚙️ Settings</a>
            </nav>
        </aside>

        <!-- Main Content -->
        <main class="main-content">
            <h1>Dashboard Overview</h1>
            <p class="subtitle">
                Welcome back! Here is your business summary.
            </p>

            <!-- Statistics Cards -->
            <section class="stats">

                <div class="card">
                    <div class="card-icon blue">👥</div>
                    <div class="card-info">
                        <h3>Total Users</h3>
                        <p>2,450</p>
                        <span class="positive">+12.5% this month</span>
                    </div>
                </div>

                <div class="card">
                    <div class="card-icon green">💰</div>
                    <div class="card-info">
                        <h3>Total Revenue</h3>
                        <p>₹85,600</p>
                        <span class="positive">+8.2% this month</span>
                    </div>
                </div>

                <div class="card">
                    <div class="card-icon orange">📦</div>
                    <div class="card-info">
                        <h3>Total Orders</h3>
                        <p>1,280</p>
                        <span class="positive">+5.4% this month</span>
                    </div>
                </div>

                <div class="card">
                    <div class="card-icon purple">📈</div>
                    <div class="card-info">
                        <h3>Growth Rate</h3>
                        <p>18.6%</p>
                        <span class="positive">+3.1% this month</span>
                    </div>
                </div>

            </section>

            <!-- Recent Activity Table -->
            <section class="activity">
                <h2>Recent Activity</h2>

                <div class="table-wrapper">
                    <table>
                        <thead>
                            <tr>
                                <th>Customer</th>
                                <th>Activity</th>
                                <th>Date</th>
                                <th>Status</th>
                            </tr>
                        </thead>

                        <tbody>
                            <tr>
                                <td>Rahul Sharma</td>
                                <td>Purchased Product A</td>
                                <td>24 Oct 2026</td>
                                <td><span class="status completed">Completed</span></td>
                            </tr>

                            <tr>
                                <td>Priya Singh</td>
                                <td>Placed a new order</td>
                                <td>23 Oct 2026</td>
                                <td><span class="status pending">Pending</span></td>
                            </tr>

                            <tr>
                                <td>Amit Kumar</td>
                                <td>Updated profile</td>
                                <td>22 Oct 2026</td>
                                <td><span class="status completed">Completed</span></td>
                            </tr>

                            <tr>
                                <td>Neha Verma</td>
                                <td>Cancelled an order</td>
                                <td>21 Oct 2026</td>
                                <td><span class="status cancelled">Cancelled</span></td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </section>

            <footer>
                © 2026 My Dashboard | Assignment 8.4
            </footer>
        </main>

    </div>

</body>
</html>
3. CSS code — style.css

css

/* General Reset */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: Arial, sans-serif;
    background-color: #f4f7fc;
    color: #1f2937;
}

/* OUTER LAYOUT: CSS GRID */
.dashboard {
    display: grid;
    grid-template-columns: 240px 1fr;
    grid-template-rows: 70px 1fr;
    grid-template-areas:
        "sidebar header"
        "sidebar main";
    min-height: 100vh;
}

/* Header */
.header {
    grid-area: header;
    background-color: #ffffff;
    padding: 0 30px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
}

.header h2 {
    font-size: 22px;
}

.profile {
    display: flex;
    align-items: center;
    gap: 12px;
}

.avatar {
    width: 38px;
    height: 38px;
    background-color: #2563eb;
    color: white;
    border-radius: 50%;
    display: flex;
    justify-content: center;
    align-items: center;
    font-weight: bold;
}

/* Sidebar */
.sidebar {
    grid-area: sidebar;
    background-color: #172554;
    color: white;
    padding: 28px 18px;
}

.sidebar h2 {
    margin-bottom: 35px;
    padding-left: 10px;
}

.sidebar nav {
    display: flex;
    flex-direction: column;
    gap: 10px;
}

.sidebar nav a {
    color: #cbd5e1;
    text-decoration: none;
    padding: 14px 12px;
    border-radius: 8px;
    transition: 0.3s;
}

.sidebar nav a:hover,
.sidebar nav a.active {
    background-color: #2563eb;
    color: white;
}

/* Main Content */
.main-content {
    grid-area: main;
    padding: 30px;
    min-width: 0;
}

.main-content h1 {
    font-size: 28px;
    margin-bottom: 8px;
}

.subtitle {
    color: #64748b;
    margin-bottom: 28px;
}

/* Statistics Grid */
.stats {
    display: grid;
    grid-template-columns: repeat(4, minmax(0, 1fr));
    gap: 20px;
    margin-bottom: 35px;
}

/* INNER LAYOUT: FLEXBOX CARDS */
.card {
    background-color: white;
    padding: 22px 18px;
    border-radius: 12px;
    box-shadow: 0 3px 12px rgba(0, 0, 0, 0.05);
    display: flex;
    align-items: center;
    gap: 15px;
    min-width: 0;
}

.card-icon {
    width: 52px;
    height: 52px;
    flex-shrink: 0;
    border-radius: 10px;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 25px;
}

.blue {
    background-color: #dbeafe;
}

.green {
    background-color: #dcfce7;
}

.orange {
    background-color: #ffedd5;
}

.purple {
    background-color: #f3e8ff;
}

.card-info {
    min-width: 0;
}

.card-info h3 {
    color: #64748b;
    font-size: 13px;
    margin-bottom: 10px;
}

.card-info p {
    font-size: 24px;
    font-weight: bold;
    margin-bottom: 8px;
    overflow-wrap: anywhere;
}

.positive {
    color: #16a34a;
    font-size: 11px;
}

/* Recent Activity */
.activity {
    background-color: white;
    padding: 25px;
    border-radius: 12px;
    box-shadow: 0 3px 12px rgba(0, 0, 0, 0.05);
}

.activity h2 {
    font-size: 21px;
    margin-bottom: 22px;
}

.table-wrapper {
    overflow-x: auto;
}

table {
    width: 100%;
    border-collapse: collapse;
    text-align: left;
}

th,
td {
    padding: 16px 12px;
    border-bottom: 1px solid #e5e7eb;
    white-space: nowrap;
}

th {
    color: #64748b;
    background-color: #f8fafc;
    font-size: 13px;
}

td {
    font-size: 14px;
}

.status {
    display: inline-block;
    padding: 6px 10px;
    border-radius: 20px;
    font-size: 12px;
}

.completed {
    color: #15803d;
    background-color: #dcfce7;
}

.pending {
    color: #a16207;
    background-color: #fef3c7;
}

.cancelled {
    color: #b91c1c;
    background-color: #fee2e2;
}

/* Footer */
footer {
    text-align: center;
    color: #64748b;
    font-size: 13px;
    margin-top: 30px;
}

/* Responsive Layout */
@media (max-width: 1100px) {
    .stats {
        grid-template-columns: repeat(2, minmax(0, 1fr));
    }
}

@media (max-width: 700px) {
    .dashboard {
        grid-template-columns: 1fr;
        grid-template-rows: auto auto 1fr;
        grid-template-areas:
            "header"
            "sidebar"
            "main";
    }

    .header {
        min-height: 70px;
        padding: 15px;
        gap: 10px;
    }

    .header h2 {
        font-size: 18px;
    }

    .profile span {
        font-size: 12px;
    }

    .sidebar {
        padding: 15px;
    }

    .sidebar h2 {
        margin-bottom: 12px;
    }

    .sidebar nav {
        flex-direction: row;
        flex-wrap: wrap;
    }

    .sidebar nav a {
        padding: 10px;
        font-size: 13px;
    }

    .main-content {
        padding: 18px;
    }

    .main-content h1 {
        font-size: 24px;
    }

    .stats {
        grid-template-columns: 1fr;
    }

    .card {
        padding: 20px;
    }

    .activity {
        padding: 16px;
    }
}
4. Expected output
Brilliantly, LLC | The Operating System For Agencies
Your page will have:

A dark-blue sidebar with navigation links.

A white header with the dashboard title and admin profile.

Four statistic cards displaying users, revenue, orders, and growth.

A recent activity table with customer names and status labels.

A responsive layout for desktop, tablet, and mobile screens.