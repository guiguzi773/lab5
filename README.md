<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>个人简历表单 - 盒子模型版</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Noto+Sans+SC:wght@400;500;700&display=swap');
        
        :root {
            --primary-color: #3498db;
            --primary-dark: #2980b9;
            --secondary-color: #2c3e50;
            --light-gray: #f5f5f5;
            --white: #ffffff;
            --border-color: #ddd;
            --shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            --transition: all 0.3s ease;
        }
        
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }
        
        body {
            font-family: 'Noto Sans SC', 'Microsoft YaHei', sans-serif;
            line-height: 1.6;
            background-color: var(--light-gray);
            color: #333;
            padding: 20px;
        }
        
        .container {
            max-width: 800px;
            margin: 0 auto;
            background-color: var(--white);
            border-radius: 10px;
            box-shadow: var(--shadow);
            overflow: hidden;
        }
        
        .form-title {
            text-align: center;
            font-size: 28px;
            padding: 25px 0;
            color: var(--secondary-color);
            font-weight: 700;
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
            position: relative;
            transition: var(--transition);
        }
        
        .form-title:hover {
            transform: translateY(-3px);
            text-shadow: 0 5px 10px rgba(0, 0, 0, 0.1);
        }
        
        .form-title::after {
            content: "";
            display: block;
            width: 100px;
            height: 4px;
            background: var(--primary-color);
            margin: 10px auto;
            border-radius: 2px;
        }
        
        .form-group {
            padding: 25px;
            border-bottom: 1px solid var(--border-color);
        }
        
        .section {
            margin-bottom: 30px;
            border: 2px solid var(--primary-color);
            border-radius: 8px;
            padding: 20px;
            background-color: var(--white);
            transition: var(--transition);
        }
        
        .section:hover {
            box-shadow: 0 6px 12px rgba(52, 152, 219, 0.2);
            transform: translateY(-2px);
        }
        
        .section-title {
            font-size: 20px;
            color: var(--primary-color);
            margin-bottom: 20px;
            padding-bottom: 10px;
            border-bottom: 2px solid var(--primary-color);
            display: flex;
            align-items: center;
            transition: var(--transition);
        }
        
        .section-title:hover {
            transform: translateX(5px);
        }
        
        .section-title i {
            margin-right: 10px;
            font-size: 24px;
            transition: var(--transition);
        }
        
        .section-title:hover i {
            transform: rotate(15deg);
        }
        
        .row {
            display: flex;
            flex-wrap: wrap;
            margin-bottom: 15px;
            gap: 15px;
        }
        
        .col {
            flex: 1;
            min-width: 200px;
        }
        
        .photo-container {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            padding: 15px;
            border: 2px dashed var(--border-color);
            border-radius: 8px;
            background-color: #f9f9f9;
            transition: var(--transition);
        }
        
        .photo-container:hover {
            border-color: var(--primary-color);
            background-color: #f0f8ff;
        }
        
        .photo-preview {
            width: 100px;
            height: 130px;
            object-fit: cover;
            border: 1px solid var(--border-color);
            margin-bottom: 10px;
            background-color: #eee;
            display: flex;
            align-items: center;
            justify-content: center;
            color: #999;
            font-size: 12px;
        }
        
        label {
            display: block;
            margin-bottom: 8px;
            font-weight: 500;
            color: var(--secondary-color);
        }
        
        input[type="text"],
        input[type="tel"],
        input[type="email"],
        input[type="number"],
        select,
        textarea {
            width: 100%;
            padding: 10px 12px;
            border: 1px solid var(--border-color);
            border-radius: 6px;
            font-family: inherit;
            font-size: 15px;
            transition: var(--transition);
        }
        
        input[type="text"]:focus,
        input[type="tel"]:focus,
        input[type="email"]:focus,
        input[type="number"]:focus,
        select:focus,
        textarea:focus {
            border-color: var(--primary-color);
            box-shadow: 0 0 0 3px rgba(52, 152, 219, 0.2);
            outline: none;
        }
        
        textarea {
            height: 100px;
            resize: vertical;
        }
        
        .radio-group, .checkbox-group {
            display: flex;
            align-items: center;
            gap: 15px;
            padding: 8px 0;
        }
        
        .radio-group label, .checkbox-group label {
            display: flex;
            align-items: center;
            gap: 5px;
            cursor: pointer;
            transition: var(--transition);
            margin-bottom: 0;
        }
        
        .radio-group label:hover, .checkbox-group label:hover {
            color: var(--primary-color);
        }
        
        input[type="radio"], input[type="checkbox"] {
            width: 16px;
            height: 16px;
            cursor: pointer;
        }
        
        input[type="file"] {
            width: 100%;
            padding: 8px;
            border: 1px solid var(--border-color);
            border-radius: 6px;
            background-color: var(--white);
        }
        
        button {
            background-color: var(--primary-color);
            color: white;
            padding: 12px 30px;
            border: none;
            border-radius: 6px;
            cursor: pointer;
            font-size: 16px;
            font-weight: 500;
            display: block;
            margin: 30px auto;
            transition: var(--transition);
            box-shadow: var(--shadow);
            position: relative;
            overflow: hidden;
        }
        
        button:hover {
            background-color: var(--primary-dark);
            transform: translateY(-3px);
            box-shadow: 0 6px 12px rgba(52, 152, 219, 0.3);
        }
        
        button:active {
            transform: translateY(1px);
        }
        
        button::after {
            content: "";
            position: absolute;
            top: 50%;
            left: 50%;
            width: 5px;
            height: 5px;
            background: rgba(255, 255, 255, 0.5);
            opacity: 0;
            border-radius: 100%;
            transform: scale(1, 1) translate(-50%);
            transform-origin: 50% 50%;
        }
        
        button:focus:not(:active)::after {
            animation: ripple 1s ease-out;
        }
        
        @keyframes ripple {
            0% {
                transform: scale(0, 0);
                opacity: 0.5;
            }
            100% {
                transform: scale(20, 20);
                opacity: 0;
            }
        }
        
        .required::after {
            content: " *";
            color: red;
        }
        
        /* 图标动画 */
        .icon-animate {
            display: inline-block;
            transition: var(--transition);
        }
        
        .icon-animate:hover {
            transform: scale(1.1) rotate(10deg);
        }
        
        /* 响应式调整 */
        @media (max-width: 768px) {
            .col {
                flex: 100%;
            }
            
            .row {
                flex-direction: column;
                gap: 15px;
            }
            
            .photo-container {
                margin-top: 15px;
            }
        }
        
        /* 添加的图标样式 */
        .icon-section {
            margin-right: 10px;
            color: var(--primary-color);
        }
    </style>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
</head>
<body>
    <div class="container">
        <h1 class="form-title">
            <i class="fas fa-user-tie icon-animate"></i> 个人简历表单
        </h1>
        
        <form action="#" method="post" enctype="multipart/form-data">
            <div class="form-group">
                <div class="section">
                    <h2 class="section-title">
                        <i class="fas fa-id-card icon-section"></i> 基本信息
                    </h2>
                    
                    <div class="row">
                        <div class="col">
                            <label for="fullname" class="required">姓名</label>
                            <input type="text" id="fullname" name="fullname" required maxlength="20" placeholder="请输入您的姓名">
                        </div>
                        
                        <div class="col">
                            <label class="required">性别</label>
                            <div class="radio-group">
                                <label><input type="radio" name="gender" value="male" checked> <i class="fas fa-mars"></i> 男</label>
                                <label><input type="radio" name="gender" value="female"> <i class="fas fa-venus"></i> 女</label>
                            </div>
                        </div>
                        
                        <div class="col photo-container">
                            <div class="photo-preview">
                                <i class="fas fa-camera"></i> 照片预览
                            </div>
                            <input type="file" id="photo" name="photo" accept="image/*" required>
                        </div>
                    </div>
                    
                    <div class="row">
                        <div class="col">
                            <label for="age" class="required">年龄</label>
                            <input type="number" id="age" name="age" min="18" max="60" required placeholder="18-60岁">
                        </div>
                        
                        <div class="col">
                            <label for="hometown" class="required">籍贯</label>
                            <input type="text" id="hometown" name="hometown" required maxlength="20" placeholder="请输入您的籍贯">
                        </div>
                    </div>
                    
                    <div class="row">
                        <div class="col">
                            <label for="phone" class="required">联系电话</label>
                            <input type="tel" id="phone" name="phone" required maxlength="11" pattern="\d{11}" placeholder="11位手机号码">
                        </div>
                        
                        <div class="col">
                            <label for="email" class="required">电子邮箱</label>
                            <input type="email" id="email" name="email" required maxlength="50" placeholder="example@email.com">
                        </div>
                    </div>
                    
                    <div class="row">
                        <div class="col">
                            <label for="education" class="required">学历</label>
                            <select id="education" name="education" required>
                                <option value="">请选择</option>
                                <option value="highschool">高中及以下</option>
                                <option value="college">大专</option>
                                <option value="bachelor">本科</option>
                                <option value="master">硕士</option>
                                <option value="phd">博士</option>
                            </select>
                        </div>
                        
                        <div class="col">
                            <label for="marital" class="required">婚姻状况</label>
                            <select id="marital" name="marital" required>
                                <option value="">请选择</option>
                                <option value="single">未婚</option>
                                <option value="married">已婚</option>
                                <option value="divorced">离异</option>
                            </select>
                        </div>
                    </div>
                    
                    <div class="row">
                        <div class="col">
                            <label for="health" class="required">健康状况</label>
                            <select id="health" name="health" required>
                                <option value="">请选择</option>
                                <option value="excellent">优秀</option>
                                <option value="good">良好</option>
                                <option value="fair">一般</option>
                            </select>
                        </div>
                        
                        <div class="col">
                            <label for="job_target" class="required">求职意向</label>
                            <input type="text" id="job_target" name="job_target" required maxlength="50" placeholder="请输入您的求职意向">
                        </div>
                    </div>
                    
                    <div class="row">
                        <div class="col">
                            <label for="major" class="required">专业</label>
                            <input type="text" id="major" name="major" required maxlength="30" placeholder="请输入您的专业">
                        </div>
                        
                        <div class="col">
                            <label for="school" class="required">毕业院校</label>
                            <input type="text" id="school" name="school" required maxlength="50" placeholder="请输入您的毕业院校">
                        </div>
                    </div>
                </div>
            </div>
            
            <div class="form-group">
                <div class="section">
                    <h2 class="section-title">
                        <i class="fas fa-info-circle icon-section"></i> 详细信息
                    </h2>
                    
                    <div class="content-block">
                        <h3 class="section-title">
                            <i class="fas fa-certificate icon-animate"></i> 技能证书
                        </h3>
                        <textarea id="certificates" name="certificates" placeholder="请输入您的技能证书信息，每项用逗号或分号分隔" maxlength="500"></textarea>
                    </div>
                    
                    <div class="content-block">
                        <h3 class="section-title">
                            <i class="fas fa-heart icon-animate"></i> 个人特长与爱好
                        </h3>
                        <textarea id="hobbies" name="hobbies" placeholder="请输入您的特长与爱好，每项用逗号或分号分隔" maxlength="300"></textarea>
                    </div>
                    
                    <div class="content-block">
                        <h3 class="section-title">
                            <i class="fas fa-briefcase icon-animate"></i> 项目经历
                        </h3>
                        <textarea id="projects" name="projects" placeholder="请按以下格式填写项目经历：&#10;项目名称(时间): 项目描述&#10;• 职责1&#10;• 职责2" maxlength="1000"></textarea>
                    </div>
                    
                    <div class="content-block">
                        <h3 class="section-title">
                            <i class="fas fa-comment-dots icon-animate"></i> 自我评价
                        </h3>
                        <textarea id="self_evaluation" name="self_evaluation" placeholder="请简要描述您的自我评价" maxlength="800"></textarea>
                    </div>
                    
                    <div class="content-block">
                        <h3 class="section-title">
                            <i class="fas fa-check-circle icon-animate"></i> 其他信息
                        </h3>
                        <div class="checkbox-group">
                            <label><input type="checkbox" name="agree" required> <i class="fas fa-handshake"></i> 我确认以上信息真实有效</label>
                        </div>
                    </div>
                </div>
            </div>
            
            <button type="submit">
                <i class="fas fa-paper-plane"></i> 提交简历
            </button>
        </form>
    </div>

    <script>
        // 照片预览功能
        document.getElementById('photo').addEventListener('change', function(e) {
            const file = e.target.files[0];
            if (file) {
                const reader = new FileReader();
                reader.onload = function(event) {
                    const preview = document.querySelector('.photo-preview');
                    preview.innerHTML = '';
                    const img = document.createElement('img');
                    img.src = event.target.result;
                    img.style.width = '100%';
                    img.style.height = '100%';
                    img.style.objectFit = 'cover';
                    preview.appendChild(img);
                };
                reader.readAsDataURL(file);
            }
        });
        
        // 为所有输入元素添加悬停效果
        const inputs = document.querySelectorAll('input, select, textarea');
        inputs.forEach(input => {
            input.addEventListener('mouseenter', function() {
                this.style.boxShadow = '0 0 0 2px rgba(52, 152, 219, 0.3)';
            });
            
            input.addEventListener('mouseleave', function() {
                this.style.boxShadow = 'none';
            });
        });
    </script>
</body>
</html>
