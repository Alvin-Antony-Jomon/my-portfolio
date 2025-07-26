# my-portfolio
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Alvin Antony Jomon - Robotics & Automation Engineer</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', 'Segoe UI', sans-serif;
            background: #0a0e1a;
            color: #e2e8f0;
            line-height: 1.7;
            overflow-x: hidden;
        }

        .background-pattern {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: 
                radial-gradient(circle at 25% 25%, rgba(15, 118, 110, 0.1) 0%, transparent 50%),
                radial-gradient(circle at 75% 75%, rgba(99, 102, 241, 0.1) 0%, transparent 50%),
                linear-gradient(135deg, #0a0e1a 0%, #1a202c 100%);
            z-index: -1;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
            position: relative;
            z-index: 1;
        }

        .floating-elements {
            position: absolute;
            width: 100%;
            height: 100%;
            pointer-events: none;
            overflow: hidden;
        }

        .floating-element {
            position: absolute;
            background: linear-gradient(135deg, rgba(15, 118, 110, 0.1), rgba(99, 102, 241, 0.1));
            border-radius: 50%;
            animation: float 6s ease-in-out infinite;
        }

        .floating-element:nth-child(1) {
            width: 80px;
            height: 80px;
            top: 20%;
            left: 10%;
            animation-delay: 0s;
        }

        .floating-element:nth-child(2) {
            width: 120px;
            height: 120px;
            top: 60%;
            right: 15%;
            animation-delay: 2s;
        }

        .floating-element:nth-child(3) {
            width: 60px;
            height: 60px;
            bottom: 20%;
            left: 20%;
            animation-delay: 4s;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); opacity: 0.3; }
            50% { transform: translateY(-20px) rotate(180deg); opacity: 0.6; }
        }

        .header {
            background: linear-gradient(135deg, rgba(15, 118, 110, 0.95), rgba(20, 25, 40, 0.95));
            backdrop-filter: blur(20px);
            border: 1px solid rgba(15, 118, 110, 0.2);
            border-radius: 24px;
            padding: 60px 40px;
            margin-bottom: 40px;
            position: relative;
            overflow: hidden;
            box-shadow: 0 25px 50px rgba(0, 0, 0, 0.3);
        }

        .header::before {
            content: '';
            position: absolute;
            top: -50%;
            right: -50%;
            width: 200%;
            height: 200%;
            background: conic-gradient(from 0deg, transparent 0deg, rgba(15, 118, 110, 0.1) 90deg, transparent 180deg);
            animation: rotate 20s linear infinite;
        }

        @keyframes rotate {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        .header-content {
            position: relative;
            z-index: 2;
        }

        .name {
            font-size: 4em;
            font-weight: 800;
            background: linear-gradient(135deg, #ffffff, #0f766e);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            letter-spacing: -2px;
            margin-bottom: 15px;
            text-shadow: 0 0 30px rgba(15, 118, 110, 0.3);
        }

        .title {
            font-size: 1.6em;
            color: #14b8a6;
            margin-bottom: 25px;
            font-weight: 600;
            position: relative;
        }

        .title::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 100px;
            height: 2px;
            background: linear-gradient(90deg, #14b8a6, transparent);
        }

        .summary {
            font-size: 1.2em;
            line-height: 1.8;
            max-width: 700px;
            opacity: 0.9;
            margin-bottom: 35px;
            color: #cbd5e1;
        }

        .contact-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 25px;
            margin-top: 35px;
        }

        .contact-item {
            display: flex;
            align-items: center;
            gap: 15px;
            background: rgba(255, 255, 255, 0.05);
            padding: 15px 20px;
            border-radius: 12px;
            border: 1px solid rgba(15, 118, 110, 0.2);
            transition: all 0.3s ease;
        }

        .contact-item:hover {
            background: rgba(15, 118, 110, 0.1);
            transform: translateY(-2px);
            box-shadow: 0 10px 25px rgba(15, 118, 110, 0.2);
        }

        .contact-icon {
            background: linear-gradient(135deg, #0f766e, #14b8a6);
            padding: 12px;
            border-radius: 10px;
            width: 48px;
            height: 48px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.2em;
        }

        .section {
            background: rgba(255, 255, 255, 0.03);
            backdrop-filter: blur(20px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 20px;
            padding: 45px;
            margin-bottom: 35px;
            position: relative;
            overflow: hidden;
            transition: all 0.3s ease;
        }

        .section:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.2);
            border-color: rgba(15, 118, 110, 0.3);
        }

        .section::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 2px;
            background: linear-gradient(90deg, #0f766e, #6366f1, transparent);
        }

        .section-title {
            font-size: 2.2em;
            font-weight: 700;
            background: linear-gradient(135deg, #ffffff, #14b8a6);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 35px;
            position: relative;
            display: inline-block;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -8px;
            left: 0;
            width: 60px;
            height: 3px;
            background: linear-gradient(90deg, #0f766e, #6366f1);
            border-radius: 2px;
        }

        .experience-card {
            background: rgba(255, 255, 255, 0.02);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 16px;
            padding: 35px;
            margin-bottom: 30px;
            position: relative;
            transition: all 0.4s ease;
            overflow: hidden;
        }

        .experience-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 4px;
            height: 100%;
            background: linear-gradient(180deg, #0f766e, #6366f1);
        }

        .experience-card:hover {
            background: rgba(15, 118, 110, 0.05);
            transform: translateX(10px);
            box-shadow: -5px 10px 30px rgba(15, 118, 110, 0.2);
        }

        .experience-header {
            display: flex;
            justify-content: space-between;
            align-items: flex-start;
            margin-bottom: 25px;
            flex-wrap: wrap;
            gap: 20px;
        }

        .job-title {
            font-size: 1.5em;
            font-weight: 700;
            color: #ffffff;
            margin-bottom: 8px;
        }

        .company-name {
            font-size: 1.2em;
            color: #14b8a6;
            font-weight: 600;
            margin-bottom: 15px;
        }

        .duration-badge {
            background: linear-gradient(135deg, #0f766e, #6366f1);
            color: white;
            padding: 10px 20px;
            border-radius: 25px;
            font-size: 0.9em;
            font-weight: 600;
            white-space: nowrap;
            box-shadow: 0 4px 15px rgba(15, 118, 110, 0.3);
        }

        .key-achievements {
            background: rgba(15, 118, 110, 0.1);
            border-left: 4px solid #14b8a6;
            border-radius: 0 12px 12px 0;
            padding: 25px;
            margin: 25px 0;
        }

        .achievements-list {
            list-style: none;
            margin: 0;
        }

        .achievement-item {
            position: relative;
            padding-left: 30px;
            margin-bottom: 15px;
            color: #cbd5e1;
            font-size: 1.05em;
            line-height: 1.6;
        }

        .achievement-item::before {
            content: '⚡';
            position: absolute;
            left: 0;
            top: 2px;
            color: #14b8a6;
            font-size: 1.2em;
        }

        .skills-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 30px;
        }

        .skill-group {
            background: rgba(255, 255, 255, 0.02);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 16px;
            padding: 30px;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .skill-group::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 2px;
            background: linear-gradient(90deg, #0f766e, #6366f1);
        }

        .skill-group:hover {
            background: rgba(15, 118, 110, 0.05);
            transform: translateY(-5px);
            box-shadow: 0 15px 35px rgba(15, 118, 110, 0.2);
        }

        .skill-group-title {
            font-size: 1.3em;
            font-weight: 700;
            color: #ffffff;
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            gap: 12px;
        }

        .skill-badges {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
        }

        .skill-badge {
            background: linear-gradient(135deg, #0f766e, #6366f1);
            color: white;
            padding: 10px 18px;
            border-radius: 25px;
            font-size: 0.9em;
            font-weight: 500;
            transition: all 0.3s ease;
            border: 1px solid transparent;
        }

        .skill-badge:hover {
            transform: translateY(-2px) scale(1.05);
            box-shadow: 0 8px 20px rgba(15, 118, 110, 0.4);
            border-color: #14b8a6;
        }

        .expertise-highlight {
            background: linear-gradient(135deg, rgba(15, 118, 110, 0.2), rgba(99, 102, 241, 0.2));
            backdrop-filter: blur(20px);
            border: 1px solid rgba(15, 118, 110, 0.3);
            border-radius: 20px;
            padding: 40px;
            margin: 40px 0;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .expertise-highlight::before {
            content: '';
            position: absolute;
            top: -2px;
            left: -2px;
            right: -2px;
            bottom: -2px;
            background: linear-gradient(45deg, #0f766e, #6366f1, #0f766e);
            border-radius: 20px;
            z-index: -1;
            animation: glow 3s ease-in-out infinite alternate;
        }

        @keyframes glow {
            from { opacity: 0.7; }
            to { opacity: 1; }
        }

        .expertise-title {
            font-size: 1.8em;
            font-weight: 700;
            margin-bottom: 25px;
            color: #ffffff;
        }

        .expertise-keywords {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 15px;
        }

        .keyword-tag {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            color: #ffffff;
            padding: 12px 24px;
            border-radius: 30px;
            font-weight: 600;
            font-size: 0.95em;
            border: 2px solid transparent;
            transition: all 0.4s ease;
        }

        .keyword-tag:hover {
            background: rgba(15, 118, 110, 0.3);
            border-color: #14b8a6;
            transform: translateY(-3px);
            box-shadow: 0 10px 25px rgba(15, 118, 110, 0.3);
        }

        .value-proposition {
            background: rgba(20, 184, 166, 0.1);
            border: 2px solid rgba(20, 184, 166, 0.2);
            border-radius: 16px;
            padding: 30px;
            margin: 35px 0;
            backdrop-filter: blur(10px);
        }

        .value-title {
            font-size: 1.4em;
            font-weight: 700;
            color: #ffffff;
            margin-bottom: 20px;
        }

        .value-points {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 20px;
        }

        .value-point {
            display: flex;
            align-items: center;
            gap: 15px;
            color: #cbd5e1;
        }

        .value-icon {
            background: linear-gradient(135deg, #0f766e, #14b8a6);
            color: white;
            width: 28px;
            height: 28px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 0.9em;
            font-weight: bold;
            flex-shrink: 0;
        }

        .project-card {
            background: rgba(255, 255, 255, 0.02);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 16px;
            padding: 30px;
            margin-bottom: 25px;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .project-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 2px;
            background: linear-gradient(90deg, #6366f1, #0f766e);
        }

        .project-card:hover {
            background: rgba(99, 102, 241, 0.05);
            transform: translateY(-3px);
            box-shadow: 0 15px 30px rgba(99, 102, 241, 0.2);
        }

        .project-title {
            font-size: 1.4em;
            font-weight: 700;
            color: #ffffff;
            margin-bottom: 15px;
        }

        .project-description {
            color: #cbd5e1;
            line-height: 1.7;
            font-size: 1.05em;
        }

        .education-card {
            background: rgba(255, 255, 255, 0.02);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 16px;
            padding: 35px;
            position: relative;
            overflow: hidden;
        }

        .education-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 2px;
            background: linear-gradient(90deg, #10b981, #059669);
        }

        .degree-title {
            font-size: 1.5em;
            font-weight: 700;
            color: #ffffff;
            margin-bottom: 10px;
        }

        .university-name {
            font-size: 1.2em;
            color: #10b981;
            font-weight: 600;
            margin-bottom: 15px;
        }

        .coursework {
            color: #cbd5e1;
            line-height: 1.7;
            font-size: 1.05em;
        }

        .cta-section {
            background: linear-gradient(135deg, rgba(15, 118, 110, 0.2), rgba(99, 102, 241, 0.2));
            backdrop-filter: blur(20px);
            border: 2px solid rgba(15, 118, 110, 0.3);
            border-radius: 24px;
            padding: 60px 40px;
            text-align: center;
            margin-top: 50px;
            position: relative;
            overflow: hidden;
        }

        .cta-section::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0%;
            width: 100%;
            height: 100%;
            background: linear-gradient(45deg, transparent, rgba(15, 118, 110, 0.1), transparent);
            animation: shimmer 3s ease-in-out infinite;
        }

        @keyframes shimmer {
            0% { transform: translateX(-100%); }
            100% { transform: translateX(100%); }
        }

        .cta-title {
            font-size: 2.5em;
            font-weight: 700;
            margin-bottom: 20px;
            background: linear-gradient(135deg, #ffffff, #14b8a6);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            position: relative;
            z-index: 2;
        }

        .cta-subtitle {
            font-size: 1.2em;
            color: #cbd5e1;
            margin-bottom: 35px;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
            line-height: 1.6;
            position: relative;
            z-index: 2;
        }

        .cta-buttons {
            display: flex;
            justify-content: center;
            gap: 25px;
            flex-wrap: wrap;
            position: relative;
            z-index: 2;
        }

        .cta-button {
            background: linear-gradient(135deg, #0f766e, #6366f1);
            color: white;
            padding: 18px 36px;
            border: none;
            border-radius: 50px;
            font-size: 1.1em;
            font-weight: 600;
            text-decoration: none;
            display: inline-block;
            transition: all 0.4s ease;
            position: relative;
            overflow: hidden;
        }

        .cta-button::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.2), transparent);
            transition: left 0.5s;
        }

        .cta-button:hover::before {
            left: 100%;
        }

        .cta-button:hover {
            transform: translateY(-5px) scale(1.05);
            box-shadow: 0 15px 35px rgba(15, 118, 110, 0.4);
        }

        @media (max-width: 768px) {
            .name {
                font-size: 2.8em;
            }
            
            .header {
                padding: 40px 25px;
            }
            
            .section {
                padding: 30px 20px;
            }
            
            .experience-header {
                flex-direction: column;
                align-items: flex-start;
            }
            
            .contact-grid {
                grid-template-columns: 1fr;
            }

            .floating-element {
                display: none;
            }
        }
    </style>
</head>
<body>
    <div class="background-pattern"></div>
    
    <div class="floating-elements">
        <div class="floating-element"></div>
        <div class="floating-element"></div>
        <div class="floating-element"></div>
    </div>

    <div class="container">
        <!-- Professional Header -->
        <header class="header">
            <div class="header-content">
                <h1 class="name">ALVIN ANTONY JOMON</h1>
                <div class="title">Robotics & Automation Engineer</div>
                <p class="summary">
                    Innovative engineering professional with 8+ months of specialized experience in industrial robotics, 
                    simulation technologies, and automation systems. Proven expertise in optimizing manufacturing processes 
                    and implementing cutting-edge robotic solutions that drive operational excellence and cost efficiency.
                </p>
                
                <div class="contact-grid">
                    <div class="contact-item">
                        <div class="contact-icon">📧</div>
                        <span>alvjom@gmail.com</span>
                    </div>
                    <div class="contact-item">
                        <div class="contact-icon">📱</div>
                        <span>+91 9633391298</span>
                    </div>
                    <div class="contact-item">
                        <div class="contact-icon">📍</div>
                        <span>Thrissur, Kerala, India</span>
                    </div>
                </div>
            </div>
        </header>

        <!-- Value Proposition -->
        <div class="value-proposition">
            <h3 class="value-title">Why Choose Me as Your Robotics Engineer</h3>
            <div class="value-points">
                <div class="value-point">
                    <div class="value-icon">✓</div>
                    <span>Hands-on experience with FANUC & KUKA industrial robots</span>
                </div>
                <div class="value-point">
                    <div class="value-icon">✓</div>
                    <span>Proven expertise in process optimization & cycle time reduction</span>
                </div>
                <div class="value-point">
                    <div class="value-icon">✓</div>
                    <span>Strong foundation in C++ programming for robotic control</span>
                </div>
                <div class="value-point">
                    <div class="value-icon">✓</div>
                    <span>Advanced simulation capabilities with RoboGuide & Gazebo</span>
                </div>
            </div>
        </div>

        <!-- Core Expertise -->
        <div class="expertise-highlight">
            <div class="expertise-title">Core Technical Expertise</div>
            <div class="expertise-keywords">
                <span class="keyword-tag">Industrial Automation</span>
                <span class="keyword-tag">FANUC Programming</span>
                <span class="keyword-tag">KUKA Robotics</span>
                <span class="keyword-tag">RoboGuide Simulation</span>
                <span class="keyword-tag">Process Optimization</span>
                <span class="keyword-tag">C++ Development</span>
                <span class="keyword-tag">Manufacturing Systems</span>
                <span class="keyword-tag">Quality Control</span>
                <span class="keyword-tag">CAD Design</span>
                <span class="keyword-tag">Control Systems</span>
            </div>
        </div>

        <!-- Professional Experience -->
        <section class="section">
            <h2 class="section-title">Professional Experience</h2>
            
            <div class="experience-card">
                <div class="experience-header">
                    <div style="flex: 1;">
                        <div class="job-title">Robotics & Simulation Engineer</div>
                        <div class="company-name">Putumai Innovative Engineering Automation Private Limited</div>
                    </div>
                    <div class="duration-badge">June 2024 - January 2025</div>
                </div>
                
                <div class="key-achievements">
                    <ul class="achievements-list">
                        <li class="achievement-item">
                            <strong>Spearheaded robotic automation projects</strong> utilizing Process Simulator software for KUKA and FANUC industrial robot systems, resulting in measurable improvements in production efficiency
                        </li>
                        <li class="achievement-item">
                            <strong>Developed and implemented C++ programming solutions</strong> for advanced robotic control systems, enhancing automation workflows and system reliability
                        </li>
                        <li class="achievement-item">
                            <strong>Collaborated with multidisciplinary engineering teams</strong> on complex automation projects, ensuring seamless integration and timely project delivery
                        </li>
                        <li class="achievement-item">
                            <strong>Maintained strict adherence to quality and safety standards</strong> in robotic system design, development, and implementation processes
                        </li>
                        <li class="achievement-item">
                            <strong>Achieved significant cycle time reductions</strong> through systematic process analysis and optimization of robotic operations
                        </li>
                    </ul>
                </div>
            </div>

            <div class="experience-card">
                <div class="experience-header">
                    <div style="flex: 1;">
                        <div class="job-title">Robotics & Simulation Engineer (Intern)</div>
                        <div class="company-name">Putumai Innovative Engineering Automation Private Limited</div>
                    </div>
                    <div class="duration-badge">March 2024 - May 2024</div>
                </div>
                
                <div class="key-achievements">
                    <ul class="achievements-list">
                        <li class="achievement-item">
                            <strong>Mastered RoboGuide simulation software</strong> for comprehensive FANUC robot programming and virtual commissioning
                        </li>
                        <li class="achievement-item">
                            <strong>Executed robot teaching and jogging operations</strong> on both KUKA and FANUC robotic platforms with precision and efficiency
                        </li>
                        <li class="achievement-item">
                            <strong>Designed complex mechanical systems</strong> using Fusion 360 CAD software, contributing to innovative automation solutions
                        </li>
                        <li class="achievement-item">
                            <strong>Conducted advanced robotics simulations</strong> using Gazebo simulator for testing and validation of robotic algorithms
                        </li>
                        <li class="achievement-item">
                            <strong>Contributed to quality improvement initiatives</strong> focused on enhancing manufacturing processes and reducing defect rates
                        </li>
                    </ul>
                </div>
            </div>
        </section>

        <!-- Technical Skills -->
        <section class="section">
            <h2 class="section-title">Technical Competencies</h2>
            
            <div class="skills-container">
                <div class="skill-group">
                    <div class="skill-group-title">
                        🤖 Robotics Platforms & Systems
                    </div>
                    <div class="skill-badges">
                        <span class="skill-badge">FANUC Industrial Robots</span>
                        <span class="skill-badge">KUKA Robotics Systems</span>
                        <span class="skill-badge">Robot Teaching & Programming</span>
                        <span class="skill-badge">Industrial Automation</span>
                        <span class="skill-badge">Process Integration</span>
                    </div>
                </div>

                <div class="skill-group">
                    <div class="skill-group-title">
                         Programming & Simulation
                    </div>
                    <div class="skill-badges">
                        <span class="skill-badge">C++ Programming</span>
                        <span class="skill-badge">RoboGuide Simulator</span>
                        <span class="skill-badge">Process Simulator</span>
                        <span class="skill-badge">Gazebo Robotics</span>
