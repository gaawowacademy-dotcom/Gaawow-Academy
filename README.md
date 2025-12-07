<!DOCTYPE html>
<html lang="so">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>🏫 Gawow Academy - Complete Certificate System</title>
    
    <style>
        /* =========== VARIABLES & RESET =========== */
        :root {
            --primary: #0d47a1;
            --primary-dark: #1a237e;
            --secondary: #ff9800;
            --success: #4CAF50;
            --danger: #f44336;
            --light: #e3f2fd;
            --dark: #212121;
            --gray: #757575;
            --white: #ffffff;
            --shadow: 0 4px 12px rgba(0,0,0,0.1);
            --radius: 10px;
            --transition: all 0.3s ease;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
            min-height: 100vh;
            padding: 20px;
        }
        
        /* =========== HEADER =========== */
        .header {
            background: linear-gradient(135deg, var(--primary), var(--primary-dark));
            color: var(--white);
            padding: 20px;
            border-radius: var(--radius);
            margin-bottom: 30px;
            box-shadow: var(--shadow);
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 20px;
        }
        
        .logo-container {
            display: flex;
            align-items: center;
            gap: 15px;
        }
        
        .logo {
            width: 70px;
            height: 70px;
            background: url('https://i.ibb.co/908KSGf/20251205-143600.png') center/contain no-repeat;
            animation: float 3s ease-in-out infinite;
        }
        
        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }
        
        .logo-text h1 {
            font-size: 28px;
            margin-bottom: 5px;
        }
        
        .logo-text p {
            opacity: 0.9;
            font-size: 14px;
        }
        
        .stats-bar {
            display: flex;
            gap: 15px;
            flex-wrap: wrap;
        }
        
        .stat-item {
            background: rgba(255,255,255,0.1);
            padding: 10px 20px;
            border-radius: var(--radius);
            text-align: center;
            min-width: 120px;
        }
        
        .stat-number {
            font-size: 24px;
            font-weight: bold;
            color: var(--secondary);
        }
        
        .stat-label {
            font-size: 12px;
            opacity: 0.8;
        }
        
        /* =========== MAIN CONTAINER =========== */
        .container {
            display: grid;
            grid-template-columns: 280px 1fr;
            gap: 20px;
            max-width: 1400px;
            margin: 0 auto;
        }
        
        /* =========== SIDEBAR =========== */
        .sidebar {
            background: var(--white);
            border-radius: var(--radius);
            padding: 20px;
            box-shadow: var(--shadow);
            height: fit-content;
            position: sticky;
            top: 20px;
        }
        
        .menu {
            list-style: none;
            margin-bottom: 30px;
        }
        
        .menu li {
            margin-bottom: 10px;
        }
        
        .menu a {
            display: flex;
            align-items: center;
            gap: 12px;
            padding: 12px 15px;
            text-decoration: none;
            color: var(--dark);
            border-radius: var(--radius);
            transition: var(--transition);
            font-weight: 500;
        }
        
        .menu a:hover, .menu a.active {
            background: var(--light);
            color: var(--primary);
            transform: translateX(5px);
        }
        
        .menu a i {
            width: 20px;
            text-align: center;
        }
        
        .storage-info {
            background: var(--light);
            padding: 15px;
            border-radius: var(--radius);
            margin-top: 20px;
        }
        
        .storage-info h4 {
            margin-bottom: 10px;
            color: var(--primary);
            font-size: 14px;
        }
        
        .progress-bar {
            height: 8px;
            background: #e0e0e0;
            border-radius: 4px;
            overflow: hidden;
            margin-bottom: 5px;
        }
        
        .progress-fill {
            height: 100%;
            background: linear-gradient(90deg, var(--success), var(--secondary));
            border-radius: 4px;
            width: 0%;
            transition: width 1s ease;
        }
        
        .storage-stats {
            display: flex;
            justify-content: space-between;
            font-size: 12px;
            color: var(--gray);
        }
        
        /* =========== CONTENT AREA =========== */
        .content {
            background: var(--white);
            border-radius: var(--radius);
            padding: 30px;
            box-shadow: var(--shadow);
            min-height: 600px;
        }
        
        .tab-content {
            display: none;
            animation: fadeIn 0.5s ease;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .tab-content.active {
            display: block;
        }
        
        .page-title {
            color: var(--primary);
            margin-bottom: 25px;
            padding-bottom: 10px;
            border-bottom: 2px solid var(--light);
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .page-title h2 {
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        /* =========== FORMS =========== */
        .form-section {
            background: var(--light);
            padding: 25px;
            border-radius: var(--radius);
            margin-bottom: 30px;
        }
        
        .form-row {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-bottom: 20px;
        }
        
        .form-group {
            margin-bottom: 15px;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 8px;
            color: var(--primary);
            font-weight: 500;
            font-size: 14px;
        }
        
        .form-group label i {
            margin-right: 8px;
            color: var(--secondary);
        }
        
        .form-control {
            width: 100%;
            padding: 12px 15px;
            border: 2px solid #e0e0e0;
            border-radius: var(--radius);
            font-size: 14px;
            transition: var(--transition);
            background: var(--white);
        }
        
        .form-control:focus {
            outline: none;
            border-color: var(--primary);
            box-shadow: 0 0 0 3px rgba(13, 71, 161, 0.1);
        }
        
        .btn {
            padding: 12px 25px;
            border: none;
            border-radius: var(--radius);
            font-size: 14px;
            font-weight: 600;
            cursor: pointer;
            transition: var(--transition);
            display: inline-flex;
            align-items: center;
            gap: 8px;
        }
        
        .btn-primary {
            background: linear-gradient(135deg, var(--secondary), #ff5722);
            color: var(--white);
        }
        
        .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(255, 152, 0, 0.3);
        }
        
        .btn-success {
            background: var(--success);
            color: var(--white);
        }
        
        .btn-block {
            width: 100%;
            justify-content: center;
        }
        
        /* =========== STUDENTS TABLE =========== */
        .table-container {
            overflow-x: auto;
            border-radius: var(--radius);
            border: 1px solid #e0e0e0;
        }
        
        table {
            width: 100%;
            border-collapse: collapse;
            min-width: 1000px;
        }
        
        th {
            background: var(--primary);
            color: var(--white);
            padding: 15px;
            text-align: left;
            font-weight: 500;
        }
        
        td {
            padding: 15px;
            border-bottom: 1px solid #e0e0e0;
        }
        
        tr:hover {
            background: var(--light);
        }
        
        .badge {
            display: inline-block;
            padding: 4px 12px;
            border-radius: 20px;
            font-size: 12px;
            font-weight: 500;
        }
        
        .badge-success {
            background: #d4edda;
            color: #155724;
        }
        
        .badge-warning {
            background: #fff3cd;
            color: #856404;
        }
        
        .badge-primary {
            background: #cce5ff;
            color: #004085;
        }
        
        .actions {
            display: flex;
            gap: 8px;
        }
        
        .btn-icon {
            width: 36px;
            height: 36px;
            border-radius: var(--radius);
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            border: none;
            transition: var(--transition);
        }
        
        .btn-edit {
            background: var(--light);
            color: var(--primary);
        }
        
        .btn-delete {
            background: #fde8e8;
            color: var(--danger);
        }
        
        .btn-cert {
            background: #d4edda;
            color: var(--success);
        }
        
        /* =========== CERTIFICATE DESIGN =========== */
        .certificate-container {
            display: grid;
            grid-template-columns: 300px 1fr;
            gap: 30px;
        }
        
        .certificate-preview {
            background: var(--white);
            padding: 40px;
            border-radius: var(--radius);
            box-shadow: 0 10px 40px rgba(0,0,0,0.1);
            border: 20px solid #f0f0f0;
            position: relative;
            overflow: hidden;
        }
        
        .certificate-preview::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('https://i.ibb.co/908KSGf/20251205-143600.png') center/200px no-repeat;
            opacity: 0.05;
            pointer-events: none;
        }
        
        .watermark {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%) rotate(-45deg);
            font-size: 80px;
            font-weight: 900;
            color: rgba(13, 71, 161, 0.1);
            white-space: nowrap;
        }
        
        .cert-header {
            text-align: center;
            margin-bottom: 30px;
            position: relative;
        }
        
        .cert-header h1 {
            color: var(--primary);
            font-size: 36px;
            margin-bottom: 10px;
        }
        
        .student-name {
            font-size: 42px;
            color: var(--primary);
            text-align: center;
            margin: 40px 0;
            font-weight: 700;
            line-height: 1.2;
        }
        
        .cert-body {
            text-align: center;
            margin: 40px 0;
            font-size: 18px;
            line-height: 1.6;
        }
        
        .details-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 20px;
            margin: 40px 0;
            padding: 20px;
            background: rgba(13, 71, 161, 0.05);
            border-radius: var(--radius);
        }
        
        .detail-item {
            text-align: center;
        }
        
        .detail-label {
            display: block;
            font-size: 12px;
            color: var(--gray);
            margin-bottom: 5px;
        }
        
        .detail-value {
            font-size: 18px;
            color: var(--primary);
            font-weight: 600;
        }
        
        .cert-footer {
            display: flex;
            justify-content: space-between;
            align-items: flex-end;
            margin-top: 60px;
            padding-top: 20px;
            border-top: 2px solid var(--light);
        }
        
        .signature {
            text-align: center;
        }
        
        .signature-line {
            width: 200px;
            height: 1px;
            background: var(--dark);
            margin: 20px auto 10px;
        }
        
        .qr-code {
            width: 120px;
            height: 120px;
            background: var(--white);
            border: 2px solid var(--primary);
            border-radius: var(--radius);
            padding: 10px;
        }
        
        /* =========== TOAST NOTIFICATION =========== */
        .toast-container {
            position: fixed;
            top: 20px;
            right: 20px;
            z-index: 1000;
            display: flex;
            flex-direction: column;
            gap: 10px;
        }
        
        .toast {
            background: var(--white);
            padding: 15px 20px;
            border-radius: var(--radius);
            box-shadow: var(--shadow);
            display: flex;
            align-items: center;
            gap: 15px;
            transform: translateX(100%);
            opacity: 0;
            animation: slideIn 0.5s ease forwards;
            min-width: 300px;
            border-left: 4px solid var(--success);
        }
        
        .toast.error {
            border-left-color: var(--danger);
        }
        
        .toast.warning {
            border-left-color: var(--secondary);
        }
        
        @keyframes slideIn {
            to {
                transform: translateX(0);
                opacity: 1;
            }
        }
        
        .toast-icon {
            width: 30px;
            height: 30px;
            border-radius: 50%;
            background: var(--success);
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        
        .toast.error .toast-icon {
            background: var(--danger);
        }
        
        .toast.warning .toast-icon {
            background: var(--secondary);
        }
        
        /* =========== RESPONSIVE =========== */
        @media (max-width: 1024px) {
            .container {
                grid-template-columns: 1fr;
            }
            
            .sidebar {
                position: static;
            }
            
            .certificate-container {
                grid-template-columns: 1fr;
            }
        }
        
        @media (max-width: 768px) {
            .header {
                flex-direction: column;
                text-align: center;
            }
            
            .logo-container {
                flex-direction: column;
            }
            
            .stats-bar {
                justify-content: center;
            }
            
            .form-row {
                grid-template-columns: 1fr;
            }
            
            .details-grid {
                grid-template-columns: 1fr;
            }
            
            .cert-footer {
                flex-direction: column;
                gap: 30px;
                align-items: center;
            }
        }
    </style>
</head>
<body>
    <!-- Toast Notifications -->
    <div class="toast-container" id="toastContainer"></div>
    
    <!-- Header -->
    <header class="header">
        <div class="logo-container">
            <div class="logo"></div>
            <div class="logo-text">
                <h1>Gawow Academy</h1>
                <p>Ilayska Aqoonta iyo Xirfadda</p>
            </div>
        </div>
        
        <div class="stats-bar">
            <div class="stat-item">
                <div class="stat-number" id="totalStudents">0</div>
                <div class="stat-label">Students</div>
            </div>
            <div class="stat-item">
                <div class="stat-number" id="activeCourses">0</div>
                <div class="stat-label">Courses</div>
            </div>
            <div class="stat-item">
                <div class="stat-number" id="issuedCerts">0</div>
                <div class="stat-label">Certificates</div>
            </div>
        </div>
    </header>
    
    <!-- Main Container -->
    <div class="container">
        <!-- Sidebar -->
        <aside class="sidebar">
            <ul class="menu">
                <li><a href="#" class="active" onclick="showTab('dashboard')"><i>📊</i> Dashboard</a></li>
                <li><a href="#" onclick="showTab('students')"><i>👨‍🎓</i> Students</a></li>
                <li><a href="#" onclick="showTab('addStudent')"><i>➕</i> Add Student</a></li>
                <li><a href="#" onclick="showTab('certificates')"><i>🏆</i> Certificates</a></li>
                <li><a href="#" onclick="showTab('courses')"><i>📚</i> Courses</a></li>
                <li><a href="#" onclick="showTab('reports')"><i>📈</i> Reports</a></li>
            </ul>
            
            <div class="storage-info">
                <h4><i>💾</i> Browser Storage</h4>
                <div class="progress-bar">
                    <div class="progress-fill" id="storageFill"></div>
                </div>
                <div class="storage-stats">
                    <span id="storageUsed">0 KB</span>
                    <span>5 MB Limit</span>
                </div>
            </div>
        </aside>
        
        <!-- Main Content -->
        <main class="content">
            <!-- Dashboard Tab -->
            <div id="dashboard" class="tab-content active">
                <div class="page-title">
                    <h2><i>📊</i> Dashboard</h2>
                </div>
                
                <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 20px; margin-bottom: 30px;">
                    <div style="background: linear-gradient(135deg, var(--primary), var(--primary-dark)); color: white; padding: 25px; border-radius: var(--radius);">
                        <div style="font-size: 32px; font-weight: bold; margin-bottom: 10px;" id="totalRevenue">$0</div>
                        <div style="font-size: 14px; opacity: 0.9;">Total Revenue</div>
                    </div>
                    <div style="background: linear-gradient(135deg, var(--success), #2E7D32); color: white; padding: 25px; border-radius: var(--radius);">
                        <div style="font-size: 32px; font-weight: bold; margin-bottom: 10px;" id="avgScore">0%</div>
                        <div style="font-size: 14px; opacity: 0.9;">Average Score</div>
                    </div>
                    <div style="background: linear-gradient(135deg, var(--secondary), #F57C00); color: white; padding: 25px; border-radius: var(--radius);">
                        <div style="font-size: 32px; font-weight: bold; margin-bottom: 10px;" id="completionRate">0%</div>
                        <div style="font-size: 14px; opacity: 0.9;">Completion Rate</div>
                    </div>
                </div>
                
                <div class="form-section">
                    <h3 style="margin-bottom: 20px; color: var(--primary);"><i>📋</i> Recent Activity</h3>
                    <div class="table-container">
                        <table>
                            <thead>
                                <tr>
                                    <th>Date</th>
                                    <th>Activity</th>
                                    <th>Student</th>
                                    <th>Status</th>
                                </tr>
                            </thead>
                            <tbody id="activityTable">
                                <!-- Activity data will be loaded here -->
                            </tbody>
                        </table>
                    </div>
                </div>
            </div>
            
            <!-- Students Tab -->
            <div id="students" class="tab-content">
                <div class="page-title">
                    <h2><i>👨‍🎓</i> Student Profiles</h2>
                    <input type="text" class="form-control" placeholder="Search students..." style="width: 300px;" onkeyup="searchStudents(this.value)">
                </div>
                
                <div class="table-container">
                    <table>
                        <thead>
                            <tr>
                                <th>ID</th>
                                <th>Name</th>
                                <th>Age</th>
                                <th>Gender</th>
                                <th>Course</th>
                                <th>Type</th>
                                <th>Duration</th>
                                <th>Status</th>
                                <th>Actions</th>
                            </tr>
                        </thead>
                        <tbody id="studentsTable">
                            <!-- Students will be loaded here -->
                        </tbody>
                    </table>
                </div>
            </div>
            
            <!-- Add Student Tab -->
            <div id="addStudent" class="tab-content">
                <div class="page-title">
                    <h2><i>➕</i> Register New Student</h2>
                </div>
                
                <form id="studentForm" class="form-section">
                    <h3 style="margin-bottom: 20px; color: var(--primary);"><i>👤</i> Personal Information</h3>
                    <div class="form-row">
                        <div class="form-group">
                            <label><i>👤</i> Full Name</label>
                            <input type="text" class="form-control" id="fullName" required>
                        </div>
                        <div class="form-group">
                            <label><i>🎂</i> Age</label>
                            <input type="number" class="form-control" id="age" min="15" max="60" required>
                        </div>
                        <div class="form-group">
                            <label><i>⚧</i> Gender</label>
                            <select class="form-control" id="gender" required>
                                <option value="">Select</option>
                                <option value="Male">Male</option>
                                <option value="Female">Female</option>
                                <option value="Other">Other</option>
                            </select>
                        </div>
                    </div>
                    
                    <div class="form-row">
                        <div class="form-group">
                            <label><i>📧</i> Email</label>
                            <input type="email" class="form-control" id="email" required>
                        </div>
                        <div class="form-group">
                            <label><i>📱</i> Phone</label>
                            <input type="tel" class="form-control" id="phone" required>
                        </div>
                    </div>
                    
                    <h3 style="margin-bottom: 20px; color: var(--primary); margin-top: 30px;"><i>📚</i> Course Information</h3>
                    <div class="form-row">
                        <div class="form-group">
                            <label><i>🎓</i> Course Name</label>
                            <select class="form-control" id="course" required onchange="updateCourseDetails()">
                                <option value="">Select Course</option>
                                <option value="Web Development">Web Development</option>
                                <option value="Mobile App Development">Mobile App Development</option>
                                <option value="Data Science">Data Science</option>
                                <option value="Digital Marketing">Digital Marketing</option>
                                <option value="Graphic Design">Graphic Design</option>
                                <option value="Cybersecurity">Cybersecurity</option>
                            </select>
                        </div>
                        <div class="form-group">
                            <label><i>🏷️</i> Course Type</label>
                            <select class="form-control" id="courseType" required>
                                <option value="">Select Type</option>
                                <option value="Diploma">Diploma</option>
                                <option value="Certificate">Certificate</option>
                                <option value="Professional">Professional</option>
                                <option value="Short Course">Short Course</option>
                            </select>
                        </div>
                        <div class="form-group">
                            <label><i>⏱️</i> Duration (Months)</label>
                            <input type="number" class="form-control" id="duration" min="1" max="24" required>
                        </div>
                    </div>
                    
                    <div class="form-row">
                        <div class="form-group">
                            <label><i>📅</i> Start Date</label>
                            <input type="date" class="form-control" id="startDate" required>
                        </div>
                        <div class="form-group">
                            <label><i>📅</i> Issue Date</label>
                            <input type="date" class="form-control" id="issueDate" required>
                        </div>
                        <div class="form-group">
                            <label><i>💰</i> Fee ($)</label>
                            <input type="number" class="form-control" id="fee" min="0" required>
                        </div>
                    </div>
                    
                    <h3 style="margin-bottom: 20px; color: var(--primary); margin-top: 30px;"><i>📊</i> Academic Scores</h3>
                    <div class="form-row">
                        <div class="form-group">
                            <label>Module 1</label>
                            <input type="number" class="form-control" id="score1" min="0" max="100">
                        </div>
                        <div class="form-group">
                            <label>Module 2</label>
                            <input type="number" class="form-control" id="score2" min="0" max="100">
                        </div>
                        <div class="form-group">
                            <label>Module 3</label>
                            <input type="number" class="form-control" id="score3" min="0" max="100">
                        </div>
                        <div class="form-group">
                            <label>Final Project</label>
                            <input type="number" class="form-control" id="project" min="0" max="100">
                        </div>
                    </div>
                    
                    <button type="submit" class="btn btn-primary btn-block" style="margin-top: 30px;">
                        <i>💾</i> Save Student Profile
                    </button>
                </form>
            </div>
            
            <!-- Certificates Tab -->
            <div id="certificates" class="tab-content">
                <div class="page-title">
                    <h2><i>🏆</i> Certificate Generator</h2>
                    <div>
                        <button class="btn btn-success" onclick="downloadCertificate()"><i>📥</i> Download PDF</button>
                        <button class="btn btn-primary" onclick="printCertificate()" style="margin-left: 10px;"><i>🖨️</i> Print</button>
                    </div>
                </div>
                
                <div class="certificate-container">
                    <div class="form-section">
                        <div class="form-group">
                            <label><i>👨‍🎓</i> Select Student</label>
                            <select class="form-control" id="certStudent" onchange="loadCertificateData()">
                                <option value="">Select Student</option>
                            </select>
                        </div>
                        
                        <div class="form-group" style="margin-top: 20px;">
                            <label><i>🎨</i> Certificate Design</label>
                            <select class="form-control" id="certDesign" onchange="updateDesign()">
                                <option value="classic">Classic Design</option>
                                <option value="modern">Modern Design</option>
                                <option value="elegant">Elegant Design</option>
                            </select>
                        </div>
                        
                        <div class="form-group" style="margin-top: 20px;">
                            <label><i>🎨</i> Primary Color</label>
                            <input type="color" class="form-control" id="certColor" value="#0d47a1" onchange="updateColor()">
                        </div>
                        
                        <div class="form-group" style="margin-top: 20px;">
                            <label><i>🏷️</i> Watermark Text</label>
                            <input type="text" class="form-control" id="watermark" value="GAWOW ACADEMY" onkeyup="updateWatermark()">
                        </div>
                        
                        <div class="form-group" style="margin-top: 20px;">
                            <label><i>✍️</i> Signature Name</label>
                            <input type="text" class="form-control" id="signature" value="Director - Gawow Academy" onkeyup="updateSignature()">
                        </div>
                        
                        <button class="btn btn-primary btn-block" onclick="generateCertificate()" style="margin-top: 30px;">
                            <i>✨</i> Generate Certificate
                        </button>
                    </div>
                    
                    <div class="certificate-preview">
                        <div class="watermark" id="watermarkElement">GAWOW ACADEMY</div>
                        
                        <div class="cert-header">
                            <h1 id="certTitle">Certificate of Completion</h1>
                            <p style="color: var(--gray);">This is to certify that</p>
                        </div>
                        
                        <div class="student-name" id="certStudentName">Student Name Here</div>
                        
                        <div class="cert-body">
                            has successfully completed the course requirements and demonstrated proficiency in
                            <strong id="certCourse">Web Development</strong>
                            with distinction and dedication.
                        </div>
                        
                        <div class="details-grid">
                            <div class="detail-item">
                                <span class="detail-label">Duration</span>
                                <span class="detail-value" id="certDuration">3 Months</span>
                            </div>
                            <div class="detail-item">
                                <span class="detail-label">Average Score</span>
                                <span class="detail-value" id="certAverage">85%</span>
                            </div>
                            <div class="detail-item">
                                <span class="detail-label">Grade</span>
                                <span class="detail-value" id="certGrade">A+</span>
                            </div>
                        </div>
                        
                        <div class="cert-footer">
                            <div class="signature">
                                <div class="signature-line"></div>
                                <div style="font-weight: 500;" id="signatureElement">Director - Gawow Academy</div>
                                <div style="font-size: 12px; color: var(--gray); margin-top: 5px;">
                                    Date: <span id="certDate">Dec 05, 2024</span>
                                </div>
                            </div>
                            
                            <div style="text-align: center;">
                                <div class="qr-code" id="qrCode">
                                    <img src="https://api.qrserver.com/v1/create-qr-code/?size=100x100&data=GAWOW-ACADEMY" 
                                         alt="QR Code" style="width: 100%; border-radius: 5px;">
                                </div>
                                <div style="font-size: 10px; color: var(--gray); margin-top: 5px;">Scan to verify</div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </main>
    </div>
    
    <script>
        // =========== GLOBAL VARIABLES ===========
        let students = JSON.parse(localStorage.getItem('gawow_students') || '[]');
        let certificates = JSON.parse(localStorage.getItem('gawow_certificates') || '[]');
        let activities = JSON.parse(localStorage.getItem('gawow_activities') || '[]');
        
        // =========== INITIALIZATION ===========
        document.addEventListener('DOMContentLoaded', function() {
            // Set default dates
            const today = new Date().toISOString().split('T')[0];
            document.getElementById('startDate').value = today;
            document.getElementById('issueDate').value = today;
            
            // Initialize
            updateStats();
            loadStudentsTable();
            loadCertificateStudents();
            updateStorageInfo();
            
            // Form submission
            document.getElementById('studentForm').addEventListener('submit', saveStudent);
            
            // Show welcome
            setTimeout(() => {
                showToast('Welcome to Gawow Academy System!', 'success');
            }, 1000);
        });
        
        // =========== TAB NAVIGATION ===========
        function showTab(tabId) {
            // Hide all tabs
            document.querySelectorAll('.tab-content').forEach(tab => {
                tab.classList.remove('active');
            });
            
            // Remove active from menu
            document.querySelectorAll('.menu a').forEach(link => {
                link.classList.remove('active');
            });
            
            // Show selected tab
            document.getElementById(tabId).classList.add('active');
            
            // Set active menu
            const menuLink = document.querySelector(`[onclick="showTab('${tabId}')"]`);
            if (menuLink) menuLink.classList.add('active');
            
            // Refresh data if needed
            if (tabId === 'students') {
                loadStudentsTable();
            } else if (tabId === 'certificates') {
                loadCertificateStudents();
            } else if (tabId === 'dashboard') {
                updateStats();
            }
        }
        
        // =========== STUDENT MANAGEMENT ===========
        function saveStudent(e) {
            e.preventDefault();
            
            const student = {
                id: 'GAW-' + Date.now().toString(36).toUpperCase(),
                fullName: document.getElementById('fullName').value,
                age: parseInt(document.getElementById('age').value),
                gender: document.getElementById('gender').value,
                email: document.getElementById('email').value,
                phone: document.getElementById('phone').value,
                course: document.getElementById('course').value,
                courseType: document.getElementById('courseType').value,
                duration: parseInt(document.getElementById('duration').value),
                startDate: document.getElementById('startDate').value,
                issueDate: document.getElementById('issueDate').value,
                fee: parseFloat(document.getElementById('fee').value),
                scores: {
                    module1: parseInt(document.getElementById('score1').value) || 0,
                    module2: parseInt(document.getElementById('score2').value) || 0,
                    module3: parseInt(document.getElementById('score3').value) || 0,
                    project: parseInt(document.getElementById('project').value) || 0
                },
                average: calculateAverage(),
                grade: calculateGrade(),
                status: 'active',
                registered: new Date().toISOString()
            };
            
            students.push(student);
            localStorage.setItem('gawow_students', JSON.stringify(students));
            
            // Add activity
            addActivity(`Registered new student: ${student.fullName}`, 'registration');
            
            // Reset form
            document.getElementById('studentForm').reset();
            document.getElementById('startDate').value = new Date().toISOString().split('T')[0];
            document.getElementById('issueDate').value = new Date().toISOString().split('T')[0];
            
            // Show success
            showToast('Student registered successfully!', 'success');
            
            // Update UI
            updateStats();
            loadStudentsTable();
            loadCertificateStudents();
            showTab('students');
        }
        
        function calculateAverage() {
            const s1 = parseInt(document.getElementById('score1').value) || 0;
            const s2 = parseInt(document.getElementById('score2').value) || 0;
            const s3 = parseInt(document.getElementById('score3').value) || 0;
            const proj = parseInt(document.getElementById('project').value) || 0;
            
            const total = s1 + s2 + s3 + proj;
            return total / 4;
        }
        
        function calculateGrade() {
            const avg = calculateAverage();
            if (avg >= 90) return 'A+';
            if (avg >= 85) return 'A';
            if (avg >= 80) return 'B+';
            if (avg >= 75) return 'B';
            if (avg >= 70) return 'C+';
            if (avg >= 65) return 'C';
            if (avg >= 60) return 'D';
            return 'F';
        }
        
        function updateCourseDetails() {
            const course = document.getElementById('course').value;
            const durations = {
                'Web Development': 6,
                'Mobile App Development': 4,
                'Data Science': 8,
                'Digital Marketing': 3,
                'Graphic Design': 4,
                'Cybersecurity': 6
            };
            
            const fees = {
                'Web Development': 800,
                'Mobile App Development': 600,
                'Data Science': 1200,
                'Digital Marketing': 400,
                'Graphic Design': 500,
                'Cybersecurity': 1000
            };
            
            if (course in durations) {
                document.getElementById('duration').value = durations[course];
            }
            
            if (course in fees) {
                document.getElementById('fee').value = fees[course];
            }
        }
        
        function loadStudentsTable() {
            const table = document.getElementById('studentsTable');
            table.innerHTML = '';
            
            students.forEach(student => {
                const row = document.createElement('tr');
                row.innerHTML = `
                    <td>${student.id.substring(0, 8)}...</td>
                    <td>
                        <div style="font-weight: 500;">${student.fullName}</div>
                        <div style="font-size: 12px; color: var(--gray);">${student.email}</div>
                    </td>
                    <td>${student.age}</td>
                    <td>${student.gender}</td>
                    <td>${student.course}</td>
                    <td>${student.courseType}</td>
                    <td>${student.duration} months</td>
                    <td>
                        <span class="badge ${student.status === 'active' ? 'badge-success' : 
                            student.status === 'completed' ? 'badge-primary' : 'badge-warning'}">
                            ${student.status}
                        </span>
                    </td>
                    <td>
                        <div class="actions">
                            <button class="btn-icon btn-edit" onclick="editStudent('${student.id}')" title="Edit">
                                <i>✏️</i>
                            </button>
                            <button class="btn-icon btn-cert" onclick="generateCertForStudent('${student.id}')" title="Generate Certificate">
                                <i>🏆</i>
                            </button>
                            <button class="btn-icon btn-delete" onclick="deleteStudent('${student.id}')" title="Delete">
                                <i>🗑️</i>
                            </button>
                        </div>
                    </td>
                `;
                table.appendChild(row);
            });
        }
        
        function searchStudents(query) {
            const filtered = students.filter(student => 
                student.fullName.toLowerCase().includes(query.toLowerCase()) ||
                student.email.toLowerCase().includes(query.toLowerCase()) ||
                student.course.toLowerCase().includes(query.toLowerCase())
            );
            
            const table = document.getElementById('studentsTable');
            table.innerHTML = '';
            
            filtered.forEach(student => {
                const row = document.createElement('tr');
                row.innerHTML = `
                    <td>${student.id.substring(0, 8)}...</td>
                    <td>${student.fullName}</td>
                    <td>${student.age}</td>
                    <td>${student.gender}</td>
                    <td>${student.course}</td>
                    <td>${student.courseType}</td>
                    <td>${student.duration} months</td>
                    <td>
                        <span class="badge ${student.status === 'active' ? 'badge-success' : 'badge-warning'}">
                            ${student.status}
                        </span>
                    </td>
                    <td>
                        <div class="actions">
                            <button class="btn-icon btn-edit" onclick="editStudent('${student.id}')">
                                <i>✏️</i>
                            </button>
                            <button class="btn-icon btn-cert" onclick="generateCertForStudent('${student.id}')">
                                <i>🏆</i>
                            </button>
                        </div>
                    </td>
                `;
                table.appendChild(row);
            });
        }
        
        function editStudent(id) {
            const student = students.find(s => s.id === id);
            if (student) {
                // Populate form
                Object.keys(student).forEach(key => {
                    if (key !== 'scores') {
                        const element = document.getElementById(key);
                        if (element) element.value = student[key];
                    }
                });
                
                if (student.scores) {
                    document.getElementById('score1').value = student.scores.module1 || 0;
                    document.getElementById('score2').value = student.scores.module2 || 0;
                    document.getElementById('score3').value = student.scores.module3 || 0;
                    document.getElementById('project').value = student.scores.project || 0;
                }
                
                showTab('addStudent');
                showToast(`Editing ${student.fullName}`, 'warning');
            }
        }
        
        function deleteStudent(id) {
            if (confirm('Are you sure you want to delete this student?')) {
                const index = students.findIndex(s => s.id === id);
                if (index > -1) {
                    const studentName = students[index].fullName;
                    students.splice(index, 1);
                    localStorage.setItem('gawow_students', JSON.stringify(students));
                    
                    addActivity(`Deleted student: ${studentName}`, 'deletion');
                    loadStudentsTable();
                    updateStats();
                    loadCertificateStudents();
                    
                    showToast('Student deleted successfully', 'success');
                }
            }
        }
        
        // =========== CERTIFICATE GENERATION ===========
        function loadCertificateStudents() {
            const select = document.getElementById('certStudent');
            select.innerHTML = '<option value="">Select Student</option>';
            
            students.forEach(student => {
                const option = document.createElement('option');
                option.value = student.id;
                option.textContent = `${student.fullName} - ${student.course}`;
                select.appendChild(option);
            });
        }
        
        function loadCertificateData() {
            const studentId = document.getElementById('certStudent').value;
            const student = students.find(s => s.id === studentId);
            
            if (student) {
                // Update certificate preview
                document.getElementById('certStudentName').textContent = student.fullName;
                document.getElementById('certCourse').textContent = student.course;
                document.getElementById('certDuration').textContent = `${student.duration} Months`;
                document.getElementById('certAverage').textContent = `${Math.round(student.average)}%`;
                document.getElementById('certGrade').textContent = student.grade;
                document.getElementById('certDate').textContent = formatDate(student.issueDate);
                
                // Update QR code
                const qrData = `GAWOW-${student.id}-${student.issueDate}`;
                const qrUrl = `https://api.qrserver.com/v1/create-qr-code/?size=100x100&data=${encodeURIComponent(qrData)}`;
                document.getElementById('qrCode').innerHTML = 
                    `<img src="${qrUrl}" alt="QR Code" style="width: 100%; border-radius: 5px;">`;
                
                // Update color
                const color = document.getElementById('certColor').value;
                document.getElementById('certStudentName').style.color = color;
                document.getElementById('certTitle').style.color = color;
                document.querySelectorAll('.detail-value').forEach(el => {
                    el.style.color = color;
                });
            }
        }
        
        function generateCertificate() {
            const studentId = document.getElementById('certStudent').value;
            if (!studentId) {
                showToast('Please select a student first', 'warning');
                return;
            }
            
            const student = students.find(s => s.id === studentId);
            if (student) {
                const certId = 'CERT-' + Date.now().toString(36).toUpperCase();
                
                const certificate = {
                    id: certId,
                    studentId: student.id,
                    studentName: student.fullName,
                    course: student.course,
                    issueDate: new Date().toISOString(),
                    verified: true
                };
                
                certificates.push(certificate);
                localStorage.setItem('gawow_certificates', JSON.stringify(certificates));
                
                addActivity(`Generated certificate for ${student.fullName}`, 'certificate');
                
                showToast('Certificate generated successfully!', 'success');
                updateStats();
                
                // Auto-download after 1 second
                setTimeout(downloadCertificate, 1000);
            }
        }
        
        function generateCertForStudent(studentId) {
            showTab('certificates');
            document.getElementById('certStudent').value = studentId;
            loadCertificateData();
        }
        
        function updateDesign() {
            const design = document.getElementById('certDesign').value;
            const preview = document.querySelector('.certificate-preview');
            
            preview.style.border = '20px solid #f0f0f0';
            preview.style.background = 'white';
            
            if (design === 'modern') {
                preview.style.border = '15px solid var(--primary)';
                preview.style.background = 'linear-gradient(135deg, #ffffff 0%, #f8f9fa 100%)';
            } else if (design === 'elegant') {
                preview.style.border = '1px solid #e0e0e0';
                preview.style.boxShadow = '0 20px 60px rgba(0,0,0,0.15)';
            }
        }
        
        function updateColor() {
            const color = document.getElementById('certColor').value;
            document.getElementById('certStudentName').style.color = color;
            document.getElementById('certTitle').style.color = color;
            document.querySelectorAll('.detail-value').forEach(el => {
                el.style.color = color;
            });
        }
        
        function updateWatermark() {
            const text = document.getElementById('watermark').value;
            document.getElementById('watermarkElement').textContent = text;
        }
        
        function updateSignature() {
            const sig = document.getElementById('signature').value;
            document.getElementById('signatureElement').textContent = sig;
        }
        
        function downloadCertificate() {
            showToast('Preparing PDF download...', 'success');
            // In a real implementation, this would generate a PDF
            setTimeout(() => {
                showToast('Certificate downloaded successfully!', 'success');
            }, 1500);
        }
        
        function printCertificate() {
            window.print();
        }
        
        // =========== DASHBOARD & STATS ===========
        function updateStats() {
            // Update header stats
            document.getElementById('totalStudents').textContent = students.length;
            document.getElementById('activeCourses').textContent = new Set(students.map(s => s.course)).size;
            document.getElementById('issuedCerts').textContent = certificates.length;
            
            // Update dashboard stats
            const totalRevenue = students.reduce((sum, s) => sum + (s.fee || 0), 0);
            document.getElementById('totalRevenue').textContent = `$${totalRevenue}`;
            
            const avgScore = students.length > 0 ? 
                students.reduce((sum, s) => sum + (s.average || 0), 0) / students.length : 0;
            document.getElementById('avgScore').textContent = `${Math.round(avgScore)}%`;
            
            const completed = students.filter(s => s.status === 'completed').length;
            const completionRate = students.length > 0 ? Math.round((completed / students.length) * 100) : 0;
            document.getElementById('completionRate').textContent = `${completionRate}%`;
            
            // Update activity table
            loadActivityTable();
        }
        
        function loadActivityTable() {
            const table = document.getElementById('activityTable');
            table.innerHTML = '';
            
            // Get last 5 activities
            const recentActivities = activities.slice(-5).reverse();
            
            recentActivities.forEach(activity => {
                const row = document.createElement('tr');
                row.innerHTML = `
                    <td>${formatDate(activity.timestamp)}</td>
                    <td>${activity.action}</td>
                    <td>${activity.student || 'System'}</td>
                    <td>
                        <span class="badge ${activity.type === 'registration' ? 'badge-success' : 
                            activity.type === 'certificate' ? 'badge-primary' : 'badge-warning'}">
                            ${activity.type}
                        </span>
                    </td>
                `;
                table.appendChild(row);
            });
        }
        
        function addActivity(action, type, student = '') {
            const activity = {
                timestamp: new Date().toISOString(),
                action: action,
                type: type,
                student: student
            };
            
            activities.push(activity);
            localStorage.setItem('gawow_activities', JSON.stringify(activities));
            
            // Keep only last 50 activities
            if (activities.length > 50) {
                activities = activities.slice(-50);
                localStorage.setItem('gawow_activities', JSON.stringify(activities));
            }
        }
        
        // =========== BROWSER STORAGE ===========
        function updateStorageInfo() {
            const totalStorage = 5 * 1024 * 1024; // 5MB
            let usedStorage = 0;
            
            // Calculate used storage
            ['gawow_students', 'gawow_certificates', 'gawow_activities'].forEach(key => {
                const data = localStorage.getItem(key);
                if (data) usedStorage += new Blob([data]).size;
            });
            
            const usedKB = Math.round(usedStorage / 1024);
            const percentage = Math.round((usedStorage / totalStorage) * 100);
            
            document.getElementById('storageFill').style.width = `${percentage}%`;
            document.getElementById('storageUsed').textContent = `${usedKB} KB`;
        }
        
        // =========== UTILITY FUNCTIONS ===========
        function formatDate(dateString) {
            const date = new Date(dateString);
            return date.toLocaleDateString('en-US', {
                year: 'numeric',
                month: 'short',
                day: 'numeric'
            });
        }
        
        function showToast(message, type = 'success') {
            const toastContainer = document.getElementById('toastContainer');
            const toast = document.createElement('div');
            toast.className = `toast ${type}`;
            toast.innerHTML = `
                <div class="toast-icon">
                    ${type === 'success' ? '✅' : type === 'error' ? '❌' : '⚠️'}
                </div>
                <div>${message}</div>
            `;
            
            toastContainer.appendChild(toast);
            
            // Remove after 5 seconds
            setTimeout(() => {
                toast.style.animation = 'slideIn 0.5s ease reverse';
                setTimeout(() => toast.remove(), 500);
            }, 5000);
        }
        
        // =========== DATA EXPORT/IMPORT ===========
        function exportData() {
            const data = {
                students: students,
                certificates: certificates,
                exportDate: new Date().toISOString()
            };
            
            const blob = new Blob([JSON.stringify(data, null, 2)], { type: 'application/json' });
            const url = URL.createObjectURL(blob);
            const a = document.createElement('a');
            a.href = url;
            a.download = `gawow_backup_${new Date().toISOString().split('T')[0]}.json`;
            document.body.appendChild(a);
            a.click();
            document.body.removeChild(a);
            URL.revokeObjectURL(url);
            
            showToast('Data exported successfully!', 'success');
        }
        
        function importData() {
            const input = document.createElement('input');
            input.type = 'file';
            input.accept = '.json';
            input.onchange = function(e) {
                const file = e.target.files[0];
                const reader = new FileReader();
                reader.onload = function(e) {
                    try {
                        const data = JSON.parse(e.target.result);
                        if (data.students) {
                            students = data.students;
                            localStorage.setItem('gawow_students', JSON.stringify(students));
                        }
                        if (data.certificates) {
                            certificates = data.certificates;
                            localStorage.setItem('gawow_certificates', JSON.stringify(certificates));
                        }
                        
                        updateStats();
                        loadStudentsTable();
                        loadCertificateStudents();
                        showToast('Data imported successfully!', 'success');
                    } catch (err) {
                        showToast('Invalid data file', 'error');
                    }
                };
                reader.readAsText(file);
            };
            input.click();
        }
        
        // =========== AUTO SAVE ===========
        setInterval(() => {
            localStorage.setItem('gawow_students', JSON.stringify(students));
            localStorage.setItem('gawow_certificates', JSON.stringify(certificates));
            localStorage.setItem('gawow_activities', JSON.stringify(activities));
            updateStorageInfo();
        }, 30000); // Auto-save every 30 seconds
    </script>
</body>
</html>