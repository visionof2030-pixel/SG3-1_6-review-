
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Super Goal 3 - Grammar Reference</title>
    <link href="https://fonts.googleapis.com/css2?family=Almarai:wght@300;400;700&family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            /* Color Palette - Professional Gradient */
            --primary: #4f46e5;
            --primary-light: #6366f1;
            --primary-dark: #4338ca;
            --secondary: #7c3aed;
            --accent: #0ea5e9;
            --success: #10b981;
            --warning: #f59e0b;
            --error: #ef4444;
            
            /* Neutral Colors */
            --bg-primary: #f8fafc;
            --bg-secondary: #f1f5f9;
            --bg-card: #ffffff;
            --text-primary: #1e293b;
            --text-secondary: #475569;
            --text-light: #94a3b8;
            --border: #e2e8f0;
            --border-light: #f1f5f9;
            --shadow: rgba(0, 0, 0, 0.05);
            
            /* Unit Colors */
            --unit1-color: #4f46e5;
            --unit2-color: #ef4444;
            --unit3-color: #10b981;
            --unit4-color: #f59e0b;
            --unit5-color: #8b5cf6;
            --unit6-color: #0ea5e9;
            
            /* UI Properties */
            --radius-sm: 6px;
            --radius-md: 10px;
            --radius-lg: 14px;
            --radius-xl: 18px;
            --transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Almarai', 'Inter', sans-serif;
            background: linear-gradient(135deg, #f8fafc 0%, #f1f5f9 100%);
            color: var(--text-primary);
            line-height: 1.6;
            min-height: 100vh;
        }

        /* Compact Header */
        .main-header {
            background: linear-gradient(135deg, var(--primary) 0%, var(--primary-dark) 100%);
            color: white;
            padding: 0.4rem 0;
            position: sticky;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 10px rgba(79, 70, 229, 0.2);
        }

        .header-container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 1.5rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .brand {
            display: flex;
            align-items: center;
            gap: 0.6rem;
        }

        .logo {
            width: 36px;
            height: 36px;
            background: white;
            border-radius: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: 800;
            font-size: 1rem;
            color: var(--primary);
            box-shadow: 0 2px 6px rgba(0, 0, 0, 0.1);
            transition: var(--transition);
        }

        .brand-text h1 {
            font-family: 'Almarai', sans-serif;
            font-size: 1.1rem;
            margin-bottom: 0.1rem;
            font-weight: 700;
            line-height: 1.2;
        }

        /* Teacher info styling */
        .teacher-info {
            display: flex;
            flex-direction: column;
            gap: 0.1rem;
        }

        .teacher-name {
            font-size: 0.7rem;
            opacity: 0.9;
            font-weight: 400;
            color: rgba(255, 255, 255, 0.95);
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            padding-top: 0.2rem;
            margin-top: 0.2rem;
        }

        /* Compact Dropdown Menu */
        .header-nav {
            display: flex;
            gap: 0.8rem;
            align-items: center;
        }

        .units-dropdown {
            position: relative;
        }

        .dropdown-toggle {
            background: rgba(255, 255, 255, 0.15);
            border: 1.5px solid rgba(255, 255, 255, 0.2);
            color: white;
            padding: 0.5rem 1rem;
            border-radius: 20px;
            font-weight: 600;
            font-size: 0.85rem;
            cursor: pointer;
            transition: var(--transition);
            display: flex;
            align-items: center;
            gap: 0.5rem;
            min-width: 180px;
        }

        .dropdown-toggle:hover {
            background: rgba(255, 255, 255, 0.25);
            border-color: rgba(255, 255, 255, 0.3);
            transform: translateY(-1px);
        }

        .dropdown-toggle.active i.fa-chevron-down {
            transform: rotate(180deg);
        }

        .dropdown-menu {
            position: absolute;
            top: 100%;
            left: 0;
            width: 320px;
            background: white;
            border-radius: var(--radius-md);
            box-shadow: 0 10px 40px rgba(0, 0, 0, 0.15);
            margin-top: 0.5rem;
            opacity: 0;
            visibility: hidden;
            transform: translateY(-8px);
            transition: var(--transition);
            z-index: 1000;
            border: 1px solid var(--border);
            max-height: 500px;
            display: flex;
            flex-direction: column;
        }

        .dropdown-menu.show {
            opacity: 1;
            visibility: visible;
            transform: translateY(0);
        }

        .dropdown-header {
            padding: 1rem;
            border-bottom: 1px solid var(--border);
            background: linear-gradient(135deg, var(--primary) 0%, var(--primary-dark) 100%);
            color: white;
            border-radius: var(--radius-md) var(--radius-md) 0 0;
            flex-shrink: 0;
        }

        .units-list {
            overflow-y: auto;
            padding: 0.5rem;
            flex: 1;
            max-height: 400px;
        }

        .unit-item {
            display: flex;
            align-items: center;
            padding: 0.8rem;
            border-radius: var(--radius-sm);
            margin-bottom: 0.4rem;
            cursor: pointer;
            transition: var(--transition);
            text-decoration: none;
            color: var(--text-primary);
            border: 1.5px solid transparent;
        }

        .unit-item:hover {
            background: var(--bg-secondary);
            transform: translateX(-3px);
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
        }

        .unit-item.active {
            background: var(--bg-primary);
            border-color: var(--border);
        }

        .unit-color {
            width: 12px;
            height: 36px;
            border-radius: 4px;
            margin-left: 0.8rem;
            flex-shrink: 0;
        }

        .unit-info {
            flex: 1;
            min-width: 0;
        }

        .unit-name {
            font-weight: 700;
            font-size: 0.9rem;
            margin-bottom: 0.2rem;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }

        .unit-desc {
            font-size: 0.75rem;
            color: var(--text-secondary);
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }

        .header-actions {
            display: flex;
            gap: 0.5rem;
        }

        .header-btn {
            padding: 0.5rem 1rem;
            border-radius: 20px;
            border: 1.5px solid rgba(255, 255, 255, 0.2);
            background: rgba(255, 255, 255, 0.1);
            color: white;
            text-decoration: none;
            font-weight: 600;
            font-size: 0.8rem;
            transition: var(--transition);
            display: flex;
            align-items: center;
            gap: 0.4rem;
        }

        /* Main Container */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem 1.5rem;
        }

        /* Unit Hero Section */
        .unit-hero {
            background: linear-gradient(135deg, var(--bg-card) 0%, #f8fafc 100%);
            border-radius: var(--radius-lg);
            padding: 2rem;
            margin-bottom: 2rem;
            box-shadow: 0 4px 20px var(--shadow);
            border: 1px solid var(--border);
            position: relative;
            overflow: hidden;
        }

        .unit-hero::before {
            content: '';
            position: absolute;
            top: 0;
            right: 0;
            width: 100%;
            height: 3px;
            background: linear-gradient(90deg, var(--unit1-color) 0%, var(--accent) 100%);
        }

        .unit-badge {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            background: linear-gradient(135deg, var(--unit1-color) 0%, var(--primary) 100%);
            color: white;
            padding: 0.5rem 1rem;
            border-radius: 20px;
            font-weight: 700;
            font-size: 0.85rem;
            margin-bottom: 1rem;
            box-shadow: 0 3px 10px rgba(79, 70, 229, 0.2);
        }

        .unit-title {
            display: flex;
            justify-content: space-between;
            align-items: flex-start;
            margin-bottom: 1.5rem;
            flex-wrap: wrap;
            gap: 1.5rem;
        }

        .title-content h2 {
            font-family: 'Almarai', sans-serif;
            font-size: 1.8rem;
            color: var(--text-primary);
            margin-bottom: 0.5rem;
            font-weight: 800;
            line-height: 1.2;
        }

        .title-content p {
            color: var(--text-secondary);
            font-size: 1rem;
            max-width: 800px;
            line-height: 1.5;
        }

        .unit-tags {
            display: flex;
            gap: 0.4rem;
            flex-wrap: wrap;
            margin-top: 1rem;
        }

        .tag {
            background: linear-gradient(135deg, var(--bg-primary) 0%, #f1f5f9 100%);
            border: 1px solid var(--border);
            color: var(--text-secondary);
            padding: 0.3rem 0.8rem;
            border-radius: 15px;
            font-size: 0.75rem;
            font-weight: 500;
            transition: var(--transition);
        }

        .progress-mini {
            display: flex;
            align-items: center;
            gap: 0.8rem;
            background: linear-gradient(135deg, var(--bg-primary) 0%, #f8fafc 100%);
            padding: 0.8rem 1.2rem;
            border-radius: var(--radius-md);
            border: 1px solid var(--border);
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
        }

        .progress-circle-mini {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: conic-gradient(var(--success) 75%, var(--border) 0%);
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
        }

        .progress-circle-mini::before {
            content: '';
            position: absolute;
            width: 32px;
            height: 32px;
            background: white;
            border-radius: 50%;
        }

        .progress-percent-mini {
            position: relative;
            font-weight: 700;
            font-size: 0.8rem;
            color: var(--success);
        }

        /* Grammar Grid */
        .grammar-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 1.2rem;
            margin-bottom: 2rem;
        }

        .grammar-card {
            background: white;
            border-radius: var(--radius-md);
            padding: 1.5rem;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.05);
            transition: var(--transition);
            border: 1px solid var(--border);
            position: relative;
            overflow: hidden;
            height: 100%;
        }

        .grammar-card:hover {
            transform: translateY(-4px);
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.1);
            border-color: var(--primary-light);
        }

        .grammar-card::before {
            content: '';
            position: absolute;
            top: 0;
            right: 0;
            width: 100%;
            height: 2px;
            background: linear-gradient(90deg, var(--unit1-color) 0%, transparent 100%);
        }

        .card-header {
            display: flex;
            align-items: center;
            gap: 0.8rem;
            margin-bottom: 1rem;
        }

        .card-icon {
            width: 36px;
            height: 36px;
            background: linear-gradient(135deg, var(--unit1-color) 0%, var(--primary) 100%);
            color: white;
            border-radius: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 0.9rem;
            font-weight: 700;
            flex-shrink: 0;
            box-shadow: 0 2px 8px rgba(79, 70, 229, 0.2);
        }

        .card-title {
            font-size: 1.1rem;
            color: var(--text-primary);
            font-weight: 700;
            flex: 1;
        }

        .arabic-explanation {
            background: linear-gradient(135deg, #f0f9ff 0%, #e0f2fe 100%);
            border-right: 3px solid var(--unit1-color);
            padding: 1rem;
            border-radius: var(--radius-sm);
            margin: 1rem 0;
            font-size: 0.95rem;
            color: var(--text-primary);
            line-height: 1.6;
        }

        .english-syntax {
            background: #f8fafc;
            border: 1.5px solid var(--border);
            border-radius: var(--radius-sm);
            padding: 1rem;
            margin: 1rem 0;
            font-family: 'Inter', monospace;
            font-size: 0.9rem;
            color: var(--text-primary);
            line-height: 1.6;
            direction: ltr;
        }

        .example-container {
            display: grid;
            gap: 0.8rem;
            margin-top: 1rem;
        }

        .example-item {
            background: var(--bg-primary);
            border-radius: var(--radius-sm);
            padding: 1rem;
            border: 1px solid var(--border);
            transition: var(--transition);
        }

        .example-arabic {
            color: var(--unit1-color);
            font-weight: 600;
            margin-bottom: 0.3rem;
            font-size: 0.9rem;
        }

        .example-english {
            color: var(--text-primary);
            font-family: 'Inter', sans-serif;
            font-size: 1rem;
            direction: ltr;
            text-align: left;
        }

        /* Vocabulary Section */
        .vocabulary-section {
            margin: 2.5rem 0;
            padding-top: 1.5rem;
            border-top: 2px solid var(--border);
        }

        .vocabulary-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 1.5rem;
            padding: 1.2rem;
            background: linear-gradient(135deg, #f8fafc 0%, #f1f5f9 100%);
            border-radius: var(--radius-md);
            border: 1px solid var(--border);
        }

        .vocabulary-title h3 {
            font-family: 'Almarai', sans-serif;
            font-size: 1.4rem;
            color: var(--text-primary);
            margin-bottom: 0.3rem;
        }

        .vocabulary-title p {
            color: var(--text-secondary);
            font-size: 0.9rem;
        }

        .vocabulary-badge {
            background: linear-gradient(135deg, var(--accent) 0%, #0ea5e9 100%);
            color: white;
            padding: 0.5rem 1rem;
            border-radius: 15px;
            font-weight: 700;
            font-size: 0.8rem;
            display: flex;
            align-items: center;
            gap: 0.4rem;
            box-shadow: 0 2px 6px rgba(14, 165, 233, 0.2);
        }

        .vocabulary-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 1rem;
            margin-bottom: 1.5rem;
        }

        .vocabulary-card {
            background: white;
            border-radius: var(--radius-md);
            padding: 1.2rem;
            border: 1px solid var(--border);
            transition: var(--transition);
            box-shadow: 0 2px 6px rgba(0, 0, 0, 0.05);
            display: flex;
            align-items: center;
            gap: 1rem;
        }

        .vocabulary-card:hover {
            transform: translateY(-3px);
            border-color: var(--accent);
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
        }

        .word-number {
            width: 32px;
            height: 32px;
            background: linear-gradient(135deg, var(--accent) 0%, #0ea5e9 100%);
            color: white;
            border-radius: 6px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: 700;
            font-size: 0.85rem;
            flex-shrink: 0;
        }

        .word-content {
            flex: 1;
            display: flex;
            flex-direction: column;
            gap: 0.3rem;
        }

        .english-word {
            font-family: 'Inter', sans-serif;
            font-size: 1rem;
            font-weight: 600;
            color: var(--text-primary);
            direction: ltr;
            text-align: left;
        }

        .arabic-meaning {
            font-size: 0.9rem;
            color: var(--text-secondary);
            font-weight: 500;
        }

        .vocabulary-stats {
            background: linear-gradient(135deg, var(--bg-primary) 0%, #f1f5f9 100%);
            border-radius: var(--radius-md);
            padding: 1rem;
            border: 1px solid var(--border);
            text-align: center;
            font-size: 0.9rem;
            color: var(--text-secondary);
        }

        .vocabulary-stats strong {
            color: var(--accent);
            font-weight: 700;
        }

        /* Unit Test Section */
        .unit-test-section {
            margin-top: 3rem;
            padding-top: 2rem;
            border-top: 2px solid var(--border);
        }

        .unit-test-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 1.5rem;
            padding: 1.2rem;
            background: linear-gradient(135deg, #f8fafc 0%, #f1f5f9 100%);
            border-radius: var(--radius-md);
            border: 1px solid var(--border);
        }

        .unit-test-title h3 {
            font-family: 'Almarai', sans-serif;
            font-size: 1.4rem;
            color: var(--text-primary);
            margin-bottom: 0.3rem;
        }

        .unit-test-title p {
            color: var(--text-secondary);
            font-size: 0.9rem;
        }

        .unit-test-badge {
            background: linear-gradient(135deg, var(--warning) 0%, #f97316 100%);
            color: white;
            padding: 0.5rem 1rem;
            border-radius: 15px;
            font-weight: 700;
            font-size: 0.8rem;
            display: flex;
            align-items: center;
            gap: 0.4rem;
            box-shadow: 0 2px 6px rgba(245, 158, 11, 0.2);
        }

        .unit-test-container {
            background: linear-gradient(135deg, var(--bg-card) 0%, #f8fafc 100%);
            border-radius: var(--radius-lg);
            padding: 1.5rem;
            box-shadow: 0 4px 15px var(--shadow);
            border: 1px solid var(--border);
            position: relative;
            overflow: hidden;
        }

        .unit-test-container::before {
            content: '';
            position: absolute;
            top: 0;
            right: 0;
            width: 100%;
            height: 2px;
            background: linear-gradient(90deg, var(--warning) 0%, var(--accent) 100%);
        }

        .unit-questions-container {
            margin-bottom: 1.5rem;
        }

        .unit-question-card {
            background: white;
            border-radius: var(--radius-md);
            padding: 1.5rem;
            margin-bottom: 1.5rem;
            border: 1.5px solid var(--border);
            transition: var(--transition);
            box-shadow: 0 2px 6px rgba(0, 0, 0, 0.05);
            display: none;
        }

        .unit-question-card.active {
            display: block;
            border-color: var(--unit1-color);
            box-shadow: 0 0 0 2px rgba(79, 70, 229, 0.1);
            animation: fadeIn 0.3s ease;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(8px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .unit-question-number {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            width: 32px;
            height: 32px;
            background: var(--unit1-color);
            color: white;
            border-radius: 6px;
            font-weight: 700;
            font-size: 0.9rem;
            margin-bottom: 1rem;
        }

        .unit-question-text {
            font-family: 'Inter', sans-serif;
            font-size: 1rem;
            font-weight: 600;
            margin-bottom: 1rem;
            color: var(--text-primary);
            line-height: 1.4;
            direction: ltr;
            text-align: left;
        }

        /* Immediate Feedback Section */
        .feedback-section {
            margin-top: 1.5rem;
            padding: 1.2rem;
            border-radius: var(--radius-sm);
            background: linear-gradient(135deg, #f8fafc 0%, #f1f5f9 100%);
            border: 1.5px solid var(--border);
            display: none;
        }

        .feedback-section.show {
            display: block;
            animation: slideIn 0.3s ease;
        }

        @keyframes slideIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .feedback-header {
            display: flex;
            align-items: center;
            gap: 0.8rem;
            margin-bottom: 1rem;
            padding-bottom: 0.8rem;
            border-bottom: 1px solid var(--border);
        }

        .feedback-icon {
            width: 32px;
            height: 32px;
            border-radius: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 0.9rem;
            font-weight: 700;
        }

        .feedback-icon.correct {
            background: linear-gradient(135deg, var(--success) 0%, #34d399 100%);
            color: white;
        }

        .feedback-icon.incorrect {
            background: linear-gradient(135deg, var(--error) 0%, #ef4444 100%);
            color: white;
        }

        .feedback-title {
            font-size: 1.1rem;
            font-weight: 700;
            color: var(--text-primary);
        }

        .feedback-content {
            display: grid;
            gap: 1rem;
        }

        .feedback-item {
            background: white;
            padding: 1rem;
            border-radius: var(--radius-sm);
            border: 1px solid var(--border);
        }

        .feedback-item-title {
            font-weight: 700;
            color: var(--text-primary);
            margin-bottom: 0.5rem;
            font-size: 0.95rem;
        }

        .feedback-item-content {
            color: var(--text-secondary);
            line-height: 1.6;
            font-size: 0.9rem;
        }

        .feedback-note {
            margin-top: 1rem;
            padding: 0.8rem;
            background: linear-gradient(135deg, #fef3c7 0%, #fef9c3 100%);
            border-radius: var(--radius-sm);
            border: 1px solid var(--warning);
            color: var(--text-primary);
            font-size: 0.85rem;
            font-weight: 500;
        }

        .feedback-note i {
            color: var(--warning);
            margin-left: 0.5rem;
        }

        .unit-options-grid {
            display: grid;
            grid-template-columns: 1fr;
            gap: 0.8rem;
        }

        @media (min-width: 768px) {
            .unit-options-grid {
                grid-template-columns: repeat(2, 1fr);
            }
            
            .vocabulary-grid {
                grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            }
        }

        .unit-option {
            background: var(--bg-primary);
            border: 1px solid var(--border);
            border-radius: var(--radius-sm);
            padding: 0.8rem;
            cursor: pointer;
            transition: var(--transition);
            display: flex;
            align-items: center;
            gap: 0.8rem;
            direction: ltr;
            text-align: left;
            position: relative;
        }

        .unit-option:hover {
            border-color: var(--unit1-color);
            background: linear-gradient(135deg, #f0f9ff 0%, #e0f2fe 100%);
        }

        .unit-option.selected {
            border-color: var(--unit1-color);
            background: linear-gradient(135deg, #f0f9ff 0%, #e0f2fe 100%);
        }

        .unit-option.correct {
            border-color: var(--success);
            background: linear-gradient(135deg, #f0fdf4 0%, #dcfce7 100%);
        }

        .unit-option.incorrect {
            border-color: var(--error);
            background: linear-gradient(135deg, #fef2f2 0%, #fee2e2 100%);
        }

        .unit-option.disabled {
            opacity: 0.7;
            cursor: not-allowed;
        }

        .unit-option.disabled:hover {
            border-color: var(--border);
            background: var(--bg-primary);
            transform: none;
        }

        .unit-option-letter {
            width: 28px;
            height: 28px;
            border-radius: 4px;
            background: var(--border);
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: 700;
            color: var(--text-secondary);
            font-family: 'Inter', sans-serif;
            flex-shrink: 0;
            transition: var(--transition);
            font-size: 0.8rem;
        }

        .unit-option.selected .unit-option-letter {
            background: var(--unit1-color);
            color: white;
        }

        .unit-option.correct .unit-option-letter {
            background: var(--success);
            color: white;
        }

        .unit-option.incorrect .unit-option-letter {
            background: var(--error);
            color: white;
        }

        .unit-option-text {
            flex: 1;
            font-family: 'Inter', sans-serif;
            font-size: 0.9rem;
            color: var(--text-primary);
            font-weight: 500;
        }

        .unit-test-controls {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-top: 1.5rem;
            padding-top: 1.2rem;
            border-top: 1px solid var(--border);
        }

        .unit-test-buttons {
            display: flex;
            gap: 0.8rem;
        }

        .unit-test-btn {
            padding: 0.6rem 1.2rem;
            border-radius: var(--radius-sm);
            border: none;
            font-family: 'Inter', sans-serif;
            font-weight: 600;
            font-size: 0.85rem;
            cursor: pointer;
            transition: var(--transition);
            display: flex;
            align-items: center;
            gap: 0.4rem;
        }

        .unit-test-btn.primary {
            background: linear-gradient(135deg, var(--unit1-color) 0%, var(--primary-dark) 100%);
            color: white;
            box-shadow: 0 2px 6px rgba(79, 70, 229, 0.2);
        }

        .unit-test-btn.primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 4px 12px rgba(79, 70, 229, 0.3);
        }

        .unit-test-btn.secondary {
            background: white;
            color: var(--unit1-color);
            border: 1px solid var(--border);
        }

        .unit-test-btn.secondary:hover {
            background: var(--bg-primary);
            border-color: var(--unit1-color);
        }

        .unit-test-btn:disabled {
            opacity: 0.5;
            cursor: not-allowed;
            transform: none !important;
        }

        .unit-test-info {
            display: flex;
            align-items: center;
            gap: 0.8rem;
        }

        .unit-question-counter {
            background: var(--bg-primary);
            padding: 0.5rem 1rem;
            border-radius: var(--radius-sm);
            border: 1px solid var(--border);
            font-weight: 600;
            font-size: 0.85rem;
        }

        .unit-results-display {
            background: linear-gradient(135deg, var(--success) 0%, #34d399 100%);
            color: white;
            border-radius: var(--radius-md);
            padding: 1.5rem;
            margin: 1rem 0;
            text-align: center;
            display: none;
            box-shadow: 0 4px 15px rgba(16, 185, 129, 0.2);
        }

        .unit-results-display.show {
            display: block;
        }

        .unit-score-circle {
            width: 80px;
            height: 80px;
            background: rgba(255, 255, 255, 0.2);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 1rem;
            position: relative;
        }

        .unit-score-number {
            font-size: 2rem;
            font-weight: 800;
            line-height: 1;
            position: relative;
            z-index: 1;
        }

        .unit-score-total {
            font-size: 1.2rem;
            opacity: 0.8;
            margin-right: 0.2rem;
        }

        .unit-score-message {
            font-size: 1.1rem;
            font-weight: 700;
            margin-bottom: 0.5rem;
        }

        .unit-score-details {
            font-size: 0.85rem;
            opacity: 0.9;
            max-width: 300px;
            margin: 0 auto;
        }

        /* Footer */
        .main-footer {
            background: white;
            padding: 1.5rem;
            margin-top: 3rem;
            border-top: 1px solid var(--border);
            box-shadow: 0 -2px 10px rgba(0, 0, 0, 0.05);
        }

        .footer-content {
            max-width: 1400px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 0.8rem;
        }

        .copyright {
            color: var(--text-secondary);
            font-size: 0.8rem;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .header-container {
                flex-direction: column;
                gap: 0.8rem;
                padding: 0 1rem;
            }
            
            .header-nav {
                width: 100%;
                justify-content: center;
                flex-direction: column;
                gap: 0.8rem;
            }
            
            .dropdown-toggle {
                min-width: 100%;
                justify-content: center;
            }
            
            .header-actions {
                width: 100%;
                justify-content: center;
            }
            
            .unit-hero, .unit-test-container, .vocabulary-header {
                padding: 1.5rem;
            }
            
            .unit-title {
                flex-direction: column;
                text-align: center;
            }
            
            .title-content {
                text-align: center;
            }
            
            .unit-tags {
                justify-content: center;
            }
            
            .progress-mini {
                width: 100%;
                justify-content: center;
            }
            
            .unit-test-header, .vocabulary-header {
                flex-direction: column;
                text-align: center;
                align-items: center;
                gap: 1rem;
            }
            
            .unit-test-controls {
                flex-direction: column;
                gap: 0.8rem;
            }
            
            .unit-test-buttons {
                width: 100%;
            }
            
            .unit-test-btn {
                flex: 1;
                justify-content: center;
            }
            
            .footer-content {
                flex-direction: column;
                text-align: center;
            }
            
            .grammar-grid, .vocabulary-grid {
                grid-template-columns: 1fr;
            }
            
            .dropdown-menu {
                width: 280px;
                left: 50%;
                transform: translateX(-50%) translateY(-8px);
            }
            
            .dropdown-menu.show {
                transform: translateX(-50%) translateY(0);
            }
        }

        /* Scrollbar Styling */
        .units-list::-webkit-scrollbar {
            width: 6px;
        }

        .units-list::-webkit-scrollbar-track {
            background: var(--bg-primary);
            border-radius: 3px;
        }

        .units-list::-webkit-scrollbar-thumb {
            background: var(--primary-light);
            border-radius: 3px;
        }
        
        .units-list::-webkit-scrollbar-thumb:hover {
            background: var(--primary);
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header class="main-header">
        <div class="header-container">
            <div class="brand">
                <div class="logo">SG3</div>
                <div class="brand-text">
                    <h1>Super Goal 3 - Grammar</h1>
                    <div class="teacher-info">
                        <p>Units 1-6 Reference</p>
                        <p class="teacher-name">معلم المادة: فهد الخالدي</p>
                    </div>
                </div>
            </div>
            
            <div class="header-nav">
                <div class="units-dropdown">
                    <button class="dropdown-toggle" id="dropdownToggle">
                        <i class="fas fa-book-open"></i>
                        <span>Unit 1 - Simple Present</span>
                        <i class="fas fa-chevron-down"></i>
                    </button>
                    
                    <div class="dropdown-menu" id="dropdownMenu">
                        <div class="dropdown-header">
                            <h3>Super Goal 3 Units</h3>
                            <p>Select a unit to study</p>
                        </div>
                        <div class="units-list" id="unitsList">
                            <!-- Units will be loaded dynamically -->
                        </div>
                    </div>
                </div>
                
                <div class="header-actions">
                    <a href="#" class="header-btn">
                        <i class="fas fa-home"></i>
                        <span>Home</span>
                    </a>
                    <button class="header-btn" id="scrollToTestBtn">
                        <i class="fas fa-file-alt"></i>
                        <span>Test</span>
                    </button>
                </div>
            </div>
        </div>
    </header>

    <!-- Main Content -->
    <div class="container">
        <!-- Unit Content will be loaded here dynamically -->
        <div id="main-content"></div>
    </div>

    <!-- Footer -->
    <footer class="main-footer">
        <div class="footer-content">
            <div class="copyright">
                © 2024 Super Goal 3 Grammar Reference
            </div>
            <div class="footer-nav">
                <a href="#" class="footer-link">Home</a>
                <a href="#" class="footer-link">Units</a>
                <a href="#" class="footer-link">About</a>
                <a href="#" class="footer-link">Contact</a>
            </div>
        </div>
    </footer>

    <script>
        // Vocabulary Data
        const vocabulary = {
            "Unit 1 - Simple Present": {
                "lifestyle": "أسلوب حياة",
                "routine": "روتين",
                "habit": "عادة",
                "rarely": "نادرًا",
                "often": "غالبًا",
                "usually": "عادةً",
                "sometimes": "أحيانًا",
                "always": "دائمًا",
                "never": "أبدًا",
                "healthy": "صحي",
                "unhealthy": "غير صحي",
                "diet": "نظام غذائي",
                "exercise": "تمارين",
                "fitness": "لياقة",
                "active": "نشيط",
                "lazy": "كسول",
                "meal": "وجبة",
                "breakfast": "فطور",
                "lunch": "غداء",
                "dinner": "عشاء",
                "average": "متوسط",
                "spend time": "يقضي وقت",
                "stay up": "يسهر",
                "wake up": "يستيقظ",
                "get up": "ينهض",
                "go to bed": "يذهب للنوم"
            },
            "Unit 2 - Simple Past": {
                "biography": "سيرة ذاتية",
                "childhood": "طفولة",
                "grow up": "يكبر",
                "was born": "وُلِد",
                "invented": "اخترع",
                "discovered": "اكتشف",
                "died": "مات",
                "lived": "عاش",
                "moved": "انتقل",
                "traveled": "سافر",
                "experience": "تجربة",
                "memory": "ذكرى",
                "event": "حدث",
                "fact": "حقيقة",
                "achievement": "إنجاز",
                "career": "مهنة",
                "success": "نجاح",
                "famous": "مشهور",
                "become": "يصبح",
                "award": "جائزة",
                "won": "فاز",
                "collected": "جمع",
                "past": "الماضي"
            },
            "Unit 3 - Future Forms": {
                "travel": "يسافر",
                "trip": "رحلة",
                "journey": "رحلة طويلة",
                "flight": "رحلة طيران",
                "ticket": "تذكرة",
                "reservation": "حجز",
                "schedule": "جدول",
                "plan": "خطة",
                "arrangement": "ترتيب",
                "airport": "مطار",
                "boarding": "صعود الطائرة",
                "check-in": "تسجيل دخول",
                "luggage": "أمتعة",
                "suitcase": "حقيبة سفر",
                "passport": "جواز سفر",
                "visa": "تأشيرة",
                "delay": "تأخير",
                "departure": "المغادرة",
                "arrival": "الوصول",
                "tour": "جولة",
                "guide": "مرشد",
                "destination": "وجهة",
                "opportunity": "فرصة",
                "promise": "وعد"
            },
            "Unit 4 - Quantifiers": {
                "ingredient": "مكوّن",
                "recipe": "وصفة",
                "mix": "يخلط",
                "boil": "يغلي",
                "bake": "يخبز",
                "fry": "يقلي",
                "chop": "يقطع",
                "slice": "يقطع شرائح",
                "stir": "يحرك",
                "heat": "يسخّن",
                "add": "يضيف",
                "serve": "يقدّم",
                "taste": "طعم",
                "flavor": "نكهة",
                "sour": "حامض",
                "sweet": "حلو",
                "salty": "مالح",
                "spicy": "حار",
                "bland": "بدون نكهة",
                "a few": "قليل (معدود)",
                "a little": "قليل (غير معدود)",
                "enough": "كافٍ",
                "many": "كثير (معدود)",
                "much": "كثير (غير معدود)",
                "something": "شيء",
                "anything": "أي شيء",
                "nothing": "لا شيء",
                "sequence": "تسلسل خطوات"
            },
            "Unit 5 - Present Perfect": {
                "experience": "تجربة",
                "ever": "في أي وقت",
                "never": "أبدًا",
                "already": "مسبقًا",
                "yet": "حتى الآن",
                "just": "للتو",
                "for": "لمدة",
                "since": "منذ",
                "recently": "مؤخرًا",
                "lately": "في الآونة الأخيرة",
                "adventure": "مغامرة",
                "explore": "يستكشف",
                "discover": "يكتشف",
                "achievement": "إنجاز",
                "volunteer": "يتطوع",
                "improve": "يتحسن",
                "progress": "تقدّم",
                "complete": "يكمل",
                "project": "مشروع",
                "success": "نجاح",
                "challenge": "تحدي"
            },
            "Unit 6 - Comparatives": {
                "compare": "يقارن",
                "comparison": "مقارنة",
                "similar": "مشابه",
                "different": "مختلف",
                "bigger": "أكبر",
                "smaller": "أصغر",
                "cheaper": "أرخص",
                "more expensive": "أغلى",
                "faster": "أسرع",
                "slower": "أبطأ",
                "the best": "الأفضل",
                "the worst": "الأسوأ",
                "polite": "مهذب",
                "indirect question": "سؤال غير مباشر",
                "wonder": "يتساءل",
                "explain": "يشرح",
                "describe": "يصف",
                "opinion": "رأي",
                "reason": "سبب",
                "as...as": "مثل",
                "less": "أقل",
                "most": "الأكثر"
            }
        };

        // Unit Data (Grammar content - remains as before but shortened for space)
        const units = {
            1: {
                id: 1,
                name: "Unit 1 - Simple Present",
                title: "Simple Present - أنماط الحياة",
                description: "استخدام المضارع البسيط للتعبير عن العادات، الروتينات، والحقائق الثابتة في الحياة اليومية",
                color: "#4f46e5",
                progress: 75,
                tags: ["Habits & Routines", "Facts & Truths", "Timetables", "Frequency Adverbs"],
                grammar: [
                    {
                        title: "الجمل المثبتة (Affirmative)",
                        icon: "✓",
                        arabic: "تستخدم للتعبير عن العادات والروتينات اليومية، الحقائق العلمية، والجداول الزمنية الثابتة.",
                        syntax: "I / You / We / They + base verb<br>He / She / It + verb + s / es / ies",
                        examples: [
                            { arabic: "هي تعزف البيانو كل يوم", english: "She <strong>plays</strong> the piano every day." },
                            { arabic: "القطار يغادر في الساعة 6 مساءً", english: "The train <strong>leaves</strong> at 6 PM." }
                        ]
                    },
                    {
                        title: "الجمل المنفية (Negative)",
                        icon: "✗",
                        arabic: "تستخدم لنفي العادات أو الحقائق، وتتكون من don't أو doesn't مع الفعل الأساسي.",
                        syntax: "I/You/We/They + do not (don't) + base verb<br>He/She/It + does not (doesn't) + base verb",
                        examples: [
                            { arabic: "هو لا يأكل اللحم", english: "He <strong>doesn't eat</strong> meat." },
                            { arabic: "نحن لا نشرب القهوة", english: "We <strong>don't drink</strong> coffee." }
                        ]
                    }
                ],
                testQuestions: [
                    {
                        id: 1,
                        question: "Choose the correct form: He ______ (play) football every day.",
                        options: ["play", "plays", "playing", "played"],
                        correct: 1,
                        explanation: {
                            english: "For third person singular (he/she/it), we add 's' to the base verb: play → plays",
                            arabic: "لضمير الغائب المفرد (هو/هي/ذلك)، نضيف 's' إلى الفعل الأساسي: play → plays"
                        }
                    },
                    {
                        id: 2,
                        question: "Select the correct negative sentence:",
                        options: [
                            "She don't like coffee.",
                            "She doesn't likes coffee.",
                            "She doesn't like coffee.",
                            "She not like coffee."
                        ],
                        correct: 2,
                        explanation: {
                            english: "For third person singular negative, we use 'doesn't' + base verb (without 's')",
                            arabic: "للجملة المنفية مع ضمير الغائب المفرد، نستخدم 'doesn't' + الفعل الأساسي (بدون 's')"
                        }
                    }
                ]
            },
            2: {
                id: 2,
                name: "Unit 2 - Simple Past",
                title: "Simple Past / Used to - قصص الحياة",
                description: "الماضي البسيط، العادات في الماضي، والمبني للمجهول في الماضي لحكاية القصص والأخبار",
                color: "#ef4444",
                progress: 40,
                tags: ["Past Events", "Past Habits", "Biography", "Passive Voice"],
                grammar: [
                    {
                        title: "الماضي البسيط (Simple Past)",
                        icon: "⏳",
                        arabic: "يستخدم للتعبير عن حدث انتهى في الماضي مع وقت محدد.",
                        syntax: "Subject + verb + ed (regular)<br>Subject + irregular past form (went, saw)",
                        examples: [
                            { arabic: "زرت باريس السنة الماضية", english: "I <strong>visited</strong> Paris last year." },
                            { arabic: "ذهب إلى المدرسة أمس", english: "He <strong>went</strong> to school yesterday." }
                        ]
                    }
                ],
                testQuestions: [
                    {
                        id: 1,
                        question: "Choose the correct past form: She ______ (go) to the market yesterday.",
                        options: ["go", "goes", "went", "going"],
                        correct: 2,
                        explanation: {
                            english: "'go' is an irregular verb: go → went → gone",
                            arabic: "'go' فعل غير منتظم: go → went → gone"
                        }
                    },
                    {
                        id: 2,
                        question: "Which sentence uses 'used to' correctly?",
                        options: [
                            "I use to live in Dubai.",
                            "I used to living in Dubai.",
                            "I used to live in Dubai.",
                            "I am used to live in Dubai."
                        ],
                        correct: 2,
                        explanation: {
                            english: "'used to' is always followed by base verb (infinitive without 'to')",
                            arabic: "'used to' يتبع دائمًا بالفعل الأساسي (المصدر بدون 'to')"
                        }
                    }
                ]
            },
            3: {
                id: 3,
                name: "Unit 3 - Future Forms",
                title: "Future Forms - التخطيط للمستقبل",
                description: "استخدام أشكال المستقبل للتعبير عن الخطط، النوايا، والتنبؤات",
                color: "#10b981",
                progress: 60,
                tags: ["Future Plans", "Intentions", "Predictions", "Arrangements"],
                grammar: [
                    {
                        title: "Going to للمستقبل",
                        icon: "📅",
                        arabic: "تستخدم للتعبير عن الخطط والنية المسبقة.",
                        syntax: "Subject + am/is/are + going to + base verb",
                        examples: [
                            { arabic: "سأزور جدي غداً", english: "I <strong>am going to visit</strong> my grandfather tomorrow." },
                            { arabic: "سيشتري سيارة جديدة", english: "He <strong>is going to buy</strong> a new car." }
                        ]
                    }
                ],
                testQuestions: [
                    {
                        id: 1,
                        question: "Which sentence is correct for a future plan?",
                        options: [
                            "I will go to the cinema tonight.",
                            "I am going to go to the cinema tonight.",
                            "I go to the cinema tonight.",
                            "I went to the cinema tonight."
                        ],
                        correct: 1,
                        explanation: {
                            english: "'going to' is used for plans and intentions made before speaking",
                            arabic: "'going to' يستخدم للخطط والنوايا المصممة قبل التحدث"
                        }
                    }
                ]
            },
            4: {
                id: 4,
                name: "Unit 4 - Quantifiers",
                title: "Quantifiers - الكمية والتقدير",
                description: "استخدام كلمات الكمية للتعبير عن الكميات في التسوق والوصفات",
                color: "#f59e0b",
                progress: 50,
                tags: ["Shopping", "Recipes", "Countable", "Uncountable"],
                grammar: [
                    {
                        title: "كمية للاسماء المعدودة",
                        icon: "🔢",
                        arabic: "تستخدم كلمات الكمية للتعبير عن كمية الأسماء المعدودة.",
                        syntax: "many, a few, few, several",
                        examples: [
                            { arabic: "هناك العديد من الكتب على الرف", english: "There are <strong>many</strong> books on the shelf." },
                            { arabic: "اشتريت بعض التفاح", english: "I bought <strong>a few</strong> apples." }
                        ]
                    }
                ],
                testQuestions: [
                    {
                        id: 1,
                        question: "Which quantifier is used with countable nouns?",
                        options: ["much", "a little", "many", "a lot of"],
                        correct: 2,
                        explanation: {
                            english: "'many' is used with countable plural nouns",
                            arabic: "'many' يستخدم مع الأسماء المعدودة الجمع"
                        }
                    }
                ]
            },
            5: {
                id: 5,
                name: "Unit 5 - Present Perfect",
                title: "Present Perfect - الخبرة والاستمرارية",
                description: "استخدام المضارع التام للتعبير عن الخبرة الحياتية والمدة الزمنية",
                color: "#8b5cf6",
                progress: 65,
                tags: ["Experience", "Duration", "Unfinished Time", "Results"],
                grammar: [
                    {
                        title: "التجربة الحياتية",
                        icon: "📚",
                        arabic: "تستخدم المضارع التام للتعبير عن التجارب الحياتية.",
                        syntax: "Subject + have/has + past participle",
                        examples: [
                            { arabic: "لقد زرت لندن من قبل", english: "I <strong>have visited</strong> London before." },
                            { arabic: "لقد قرأت هذا الكتاب", english: "She <strong>has read</strong> this book." }
                        ]
                    }
                ],
                testQuestions: [
                    {
                        id: 1,
                        question: "Which sentence is in the present perfect?",
                        options: [
                            "I visited London last year.",
                            "I have visited London.",
                            "I am visiting London.",
                            "I will visit London."
                        ],
                        correct: 1,
                        explanation: {
                            english: "Present perfect: have/has + past participle (visited)",
                            arabic: "المضارع التام: have/has + التصريف الثالث (visited)"
                        }
                    }
                ]
            },
            6: {
                id: 6,
                name: "Unit 6 - Comparatives",
                title: "Comparatives - المقارنات والتفضيل",
                description: "استخدام المقارنات وأدوات الاستفهام للسؤال والمقارنة بين الأشياء",
                color: "#0ea5e9",
                progress: 80,
                tags: ["Comparisons", "Questions", "Superlatives", "Adjectives"],
                grammar: [
                    {
                        title: "المقارنة بين شيئين",
                        icon: "⚖️",
                        arabic: "تستخدم صيغة المقارنة للمقارنة بين شيئين.",
                        syntax: "adjective + er + than OR more + adjective + than",
                        examples: [
                            { arabic: "أخي أطول مني", english: "My brother is <strong>taller than</strong> me." },
                            { arabic: "هذا الكتاب أكثر إثارة من ذاك", english: "This book is <strong>more exciting than</strong> that one." }
                        ]
                    }
                ],
                testQuestions: [
                    {
                        id: 1,
                        question: "What is the comparative form of 'big'?",
                        options: ["bigger", "more big", "biggest", "the biggest"],
                        correct: 0,
                        explanation: {
                            english: "For one-syllable adjectives, add -er: big → bigger",
                            arabic: "للصفات ذات المقطع الواحد، نضيف -er: big → bigger"
                        }
                    }
                ]
            }
        };

        // State Management
        let currentUnitId = 1;
        let currentTestQuestionIndex = 0;
        let testAnswers = [];
        let testSubmitted = false;
        let selectedAnswers = {}; // Track selected answers per question

        // DOM Elements
        const mainContent = document.getElementById('main-content');
        const unitsList = document.getElementById('unitsList');
        const dropdownToggle = document.getElementById('dropdownToggle');
        const dropdownMenu = document.getElementById('dropdownMenu');
        const scrollToTestBtn = document.getElementById('scrollToTestBtn');

        // Initialize
        document.addEventListener('DOMContentLoaded', () => {
            initDropdown();
            loadUnitsList();
            loadUnit(currentUnitId);
            
            // Scroll to test button
            scrollToTestBtn.addEventListener('click', () => {
                const testSection = document.querySelector('.unit-test-section');
                if (testSection) {
                    testSection.scrollIntoView({ behavior: 'smooth' });
                }
            });
        });

        // Initialize dropdown
        function initDropdown() {
            dropdownToggle.addEventListener('click', (e) => {
                e.stopPropagation();
                dropdownMenu.classList.toggle('show');
                dropdownToggle.classList.toggle('active');
            });

            document.addEventListener('click', (e) => {
                if (!dropdownToggle.contains(e.target) && !dropdownMenu.contains(e.target)) {
                    dropdownMenu.classList.remove('show');
                    dropdownToggle.classList.remove('active');
                }
            });
        }

        // Load units list
        function loadUnitsList() {
            unitsList.innerHTML = '';
            
            Object.values(units).forEach(unit => {
                const unitItem = document.createElement('a');
                unitItem.href = '#';
                unitItem.className = `unit-item ${unit.id === currentUnitId ? 'active' : ''}`;
                unitItem.dataset.unit = unit.id;
                
                unitItem.innerHTML = `
                    <div class="unit-color" style="background: ${unit.color};"></div>
                    <div class="unit-info">
                        <div class="unit-name">${unit.name}</div>
                        <div class="unit-desc">${unit.description.substring(0, 60)}...</div>
                    </div>
                `;
                
                unitItem.addEventListener('click', (e) => {
                    e.preventDefault();
                    const unitId = parseInt(unitItem.dataset.unit);
                    if (unitId !== currentUnitId) {
                        currentUnitId = unitId;
                        loadUnit(unitId);
                        
                        // Update active state
                        document.querySelectorAll('.unit-item').forEach(item => {
                            item.classList.remove('active');
                        });
                        unitItem.classList.add('active');
                        
                        // Update dropdown text
                        dropdownToggle.querySelector('span').textContent = unit.name;
                        
                        // Close dropdown
                        dropdownMenu.classList.remove('show');
                        dropdownToggle.classList.remove('active');
                        
                        // Scroll to top
                        window.scrollTo({ top: 0, behavior: 'smooth' });
                    }
                });
                
                unitsList.appendChild(unitItem);
            });
        }

        // Load unit content
        function loadUnit(unitId) {
            const unit = units[unitId];
            if (!unit) return;
            
            // Reset answers when changing unit
            selectedAnswers = {};
            
            // Update CSS variable
            document.documentElement.style.setProperty('--unit1-color', unit.color);
            
            // Get vocabulary for this unit
            const unitVocabulary = vocabulary[unit.name] || {};
            
            // Build unit content
            mainContent.innerHTML = `
                <!-- Unit Hero Section -->
                <section class="unit-hero">
                    <div class="unit-badge">
                        <i class="fas fa-star"></i>
                        <span>${unit.name}</span>
                    </div>
                    
                    <div class="unit-title">
                        <div class="title-content">
                            <h2>${unit.title}</h2>
                            <p>${unit.description}</p>
                            
                            <div class="unit-tags">
                                ${unit.tags.map(tag => `<span class="tag">${tag}</span>`).join('')}
                            </div>
                        </div>
                        
                        <div class="progress-mini">
                            <div class="progress-circle-mini" style="background: conic-gradient(${unit.color} ${unit.progress}%, var(--border) 0%);">
                                <div class="progress-percent-mini" style="color: ${unit.color};">${unit.progress}%</div>
                            </div>
                            <div class="progress-text-mini">
                                <h4>Unit Progress</h4>
                                <p>${Math.floor(unit.progress/25)}/${unit.grammar.length} topics completed</p>
                            </div>
                        </div>
                    </div>
                </section>

                <!-- Grammar Content -->
                <section class="grammar-grid" id="grammar-content">
                    ${unit.grammar.map(item => `
                        <div class="grammar-card">
                            <div class="card-header">
                                <div class="card-icon">${item.icon}</div>
                                <h3 class="card-title">${item.title}</h3>
                            </div>
                            
                            <div class="arabic-explanation">
                                ${item.arabic}
                            </div>
                            
                            <div class="english-syntax">
                                ${item.syntax}
                            </div>
                            
                            <div class="example-container">
                                ${item.examples.map(example => `
                                    <div class="example-item">
                                        <div class="example-arabic">${example.arabic}</div>
                                        <div class="example-english">${example.english}</div>
                                    </div>
                                `).join('')}
                            </div>
                        </div>
                    `).join('')}
                </section>

                <!-- Vocabulary Section -->
                <section class="vocabulary-section">
                    <div class="vocabulary-header">
                        <div class="vocabulary-title">
                            <h3>Unit Vocabulary - مفردات الوحدة</h3>
                            <p>الكلمات المهمة في هذه الوحدة مع ترجمتها العربية</p>
                        </div>
                        
                        <div class="vocabulary-badge">
                            <i class="fas fa-book"></i>
                            <span>${Object.keys(unitVocabulary).length} words</span>
                        </div>
                    </div>
                    
                    <div class="vocabulary-grid" id="vocabulary-grid">
                        ${Object.entries(unitVocabulary).map(([english, arabic], index) => `
                            <div class="vocabulary-card">
                                <div class="word-number">${index + 1}</div>
                                <div class="word-content">
                                    <div class="english-word">${english}</div>
                                    <div class="arabic-meaning">${arabic}</div>
                                </div>
                            </div>
                        `).join('')}
                    </div>
                    
                    <div class="vocabulary-stats">
                        تمتلك هذه الوحدة <strong>${Object.keys(unitVocabulary).length}</strong> كلمة أساسية تساعدك في فهم مواضيع الوحدة.
                    </div>
                </section>

                <!-- Unit Test Section -->
                <section class="unit-test-section">
                    <div class="unit-test-header">
                        <div class="unit-test-title">
                            <h3>${unit.name} Test</h3>
                            <p>Test your understanding with ${unit.testQuestions.length} multiple choice questions</p>
                        </div>
                        
                        <div class="unit-test-badge">
                            <i class="fas fa-clock"></i>
                            <span>${Math.ceil(unit.testQuestions.length * 1.5)} minutes</span>
                        </div>
                    </div>
                    
                    <div class="unit-test-container">
                        <div class="unit-questions-container" id="unit-questions-container"></div>
                        
                        <div class="unit-results-display" id="unit-results-display">
                            <div class="unit-score-circle">
                                <div class="unit-score-number">
                                    <span class="unit-score-total" id="unit-score-total">0</span>/${unit.testQuestions.length}
                                </div>
                            </div>
                            <div class="unit-score-message" id="unit-score-message">Test Results</div>
                            <div class="unit-score-details" id="unit-score-details">
                                Your performance will be shown here after submitting the test.
                            </div>
                        </div>
                        
                        <div class="unit-test-controls">
                            <div class="unit-test-buttons">
                                <button class="unit-test-btn secondary" id="unit-prev-btn">
                                    <i class="fas fa-arrow-right"></i>
                                    <span>Previous</span>
                                </button>
                                <button class="unit-test-btn secondary" id="unit-next-btn">
                                    <span>Next</span>
                                    <i class="fas fa-arrow-left"></i>
                                </button>
                            </div>
                            
                            <div class="unit-test-info">
                                <div class="unit-question-counter" id="unit-question-counter">Question 1 of ${unit.testQuestions.length}</div>
                                <button class="unit-test-btn primary" id="unit-submit-btn">
                                    <i class="fas fa-paper-plane"></i>
                                    <span>Submit Test</span>
                                </button>
                            </div>
                        </div>
                    </div>
                </section>
            `;
            
            // Load test questions
            loadTestQuestions(unit);
        }

        // Load test questions (same as before but shortened for space)
        function loadTestQuestions(unit) {
            const questionsContainer = document.getElementById('unit-questions-container');
            if (!questionsContainer) return;
            
            questionsContainer.innerHTML = '';
            testAnswers = new Array(unit.testQuestions.length).fill(null);
            currentTestQuestionIndex = 0;
            testSubmitted = false;
            
            unit.testQuestions.forEach((question, index) => {
                const questionCard = document.createElement('div');
                questionCard.className = `unit-question-card ${index === 0 ? 'active' : ''}`;
                questionCard.id = `unit-question-${index}`;
                
                questionCard.innerHTML = `
                    <div class="unit-question-number">${index + 1}</div>
                    <div class="unit-question-text">${question.question}</div>
                    <div class="unit-options-grid">
                        ${question.options.map((option, optIndex) => `
                            <div class="unit-option" 
                                 data-question="${index}" 
                                 data-option="${optIndex}"
                                 data-correct="${optIndex === question.correct}">
                                <div class="unit-option-letter">${String.fromCharCode(65 + optIndex)}</div>
                                <div class="unit-option-text">${option}</div>
                            </div>
                        `).join('')}
                    </div>
                    
                    <!-- Feedback Section -->
                    <div class="feedback-section" id="feedback-${index}">
                        <div class="feedback-header">
                            <div class="feedback-icon ${selectedAnswers[index] === question.correct ? 'correct' : 'incorrect'}" id="feedback-icon-${index}">
                                ${selectedAnswers[index] === question.correct ? '✓' : '✗'}
                            </div>
                            <div class="feedback-title" id="feedback-title-${index}">
                                ${selectedAnswers[index] === question.correct ? 'إجابة صحيحة!' : 'إجابة خاطئة!'}
                            </div>
                        </div>
                        
                        <div class="feedback-content">
                            <div class="feedback-item">
                                <div class="feedback-item-title">Explanation (English):</div>
                                <div class="feedback-item-content" id="feedback-english-${index}">
                                    ${question.explanation.english}
                                </div>
                            </div>
                            
                            <div class="feedback-item">
                                <div class="feedback-item-title">الشرح (بالعربية):</div>
                                <div class="feedback-item-content" id="feedback-arabic-${index}">
                                    ${question.explanation.arabic}
                                </div>
                            </div>
                            
                            <div class="feedback-item">
                                <div class="feedback-item-title">الإجابة الصحيحة:</div>
                                <div class="feedback-item-content">
                                    <strong>${String.fromCharCode(65 + question.correct)}. ${question.options[question.correct]}</strong>
                                </div>
                            </div>
                        </div>
                        
                        <div class="feedback-note">
                            <i class="fas fa-exclamation-circle"></i>
                            <strong>ملاحظة مهمة:</strong> لا يمكن تغيير الإجابة بعد اختيارها. هذه ميزة مصممة لمساعدتك على التعلم من أخطائك.
                        </div>
                    </div>
                `;
                
                questionsContainer.appendChild(questionCard);
                
                // Add event listeners to options for this question
                const options = questionCard.querySelectorAll('.unit-option');
                options.forEach(option => {
                    option.addEventListener('click', function() {
                        handleAnswerSelection(unit, index, parseInt(this.dataset.option), question);
                    });
                });
                
                // If this question was already answered, show the feedback
                if (selectedAnswers[index] !== undefined) {
                    showFeedback(unit, index, selectedAnswers[index], question);
                }
            });
            
            // Initialize test navigation
            updateTestNavigation();
            
            // Add event listeners to test buttons
            document.getElementById('unit-prev-btn').addEventListener('click', () => {
                if (currentTestQuestionIndex > 0) {
                    currentTestQuestionIndex--;
                    updateTestNavigation();
                }
            });
            
            document.getElementById('unit-next-btn').addEventListener('click', () => {
                if (currentTestQuestionIndex < unit.testQuestions.length - 1) {
                    currentTestQuestionIndex++;
                    updateTestNavigation();
                }
            });
            
            document.getElementById('unit-submit-btn').addEventListener('click', () => {
                submitTest(unit);
            });
        }

        // Handle answer selection (same as before)
        function handleAnswerSelection(unit, questionIndex, selectedOption, question) {
            if (testSubmitted) return;
            
            // Check if answer already selected for this question
            if (selectedAnswers[questionIndex] !== undefined) {
                alert('لا يمكن تغيير الإجابة بعد اختيارها. هذه ميزة مصممة لمساعدتك على التعلم من أخطائك.');
                return;
            }
            
            // Store the selected answer
            selectedAnswers[questionIndex] = selectedOption;
            testAnswers[questionIndex] = selectedOption;
            
            // Disable all options for this question
            const options = document.querySelectorAll(`[data-question="${questionIndex}"]`);
            options.forEach(opt => {
                opt.classList.add('disabled');
                opt.style.pointerEvents = 'none';
            });
            
            // Show feedback immediately
            showFeedback(unit, questionIndex, selectedOption, question);
            
            // Update next button state
            const nextBtn = document.getElementById('unit-next-btn');
            if (nextBtn && questionIndex === currentTestQuestionIndex) {
                nextBtn.disabled = false;
            }
            
            // Scroll to show feedback
            const feedbackSection = document.getElementById(`feedback-${questionIndex}`);
            if (feedbackSection) {
                setTimeout(() => {
                    feedbackSection.scrollIntoView({ behavior: 'smooth', block: 'center' });
                }, 300);
            }
        }

        // Show feedback for an answer (same as before)
        function showFeedback(unit, questionIndex, selectedOption, question) {
            const feedbackSection = document.getElementById(`feedback-${questionIndex}`);
            const feedbackIcon = document.getElementById(`feedback-icon-${questionIndex}`);
            const feedbackTitle = document.getElementById(`feedback-title-${questionIndex}`);
            const feedbackEnglish = document.getElementById(`feedback-english-${questionIndex}`);
            const feedbackArabic = document.getElementById(`feedback-arabic-${questionIndex}`);
            
            if (!feedbackSection || !feedbackIcon || !feedbackTitle) return;
            
            // Update feedback content
            const isCorrect = selectedOption === question.correct;
            
            feedbackIcon.className = `feedback-icon ${isCorrect ? 'correct' : 'incorrect'}`;
            feedbackIcon.innerHTML = isCorrect ? '✓' : '✗';
            
            feedbackTitle.textContent = isCorrect ? 'إجابة صحيحة!' : 'إجابة خاطئة!';
            
            if (feedbackEnglish) feedbackEnglish.textContent = question.explanation.english;
            if (feedbackArabic) feedbackArabic.textContent = question.explanation.arabic;
            
            // Show the feedback section
            feedbackSection.classList.add('show');
            
            // Highlight correct and incorrect answers
            const options = document.querySelectorAll(`[data-question="${questionIndex}"]`);
            options.forEach(opt => {
                const optIndex = parseInt(opt.dataset.option);
                
                // Remove previous classes
                opt.classList.remove('selected', 'correct', 'incorrect');
                
                // Add appropriate classes
                if (optIndex === question.correct) {
                    opt.classList.add('correct');
                } else if (optIndex === selectedOption && selectedOption !== question.correct) {
                    opt.classList.add('incorrect');
                } else if (optIndex === selectedOption) {
                    opt.classList.add('selected');
                }
            });
        }

        // Update test navigation (same as before)
        function updateTestNavigation() {
            const unit = units[currentUnitId];
            const totalQuestions = unit.testQuestions.length;
            const prevBtn = document.getElementById('unit-prev-btn');
            const nextBtn = document.getElementById('unit-next-btn');
            const counter = document.getElementById('unit-question-counter');
            
            if (prevBtn) prevBtn.disabled = currentTestQuestionIndex === 0;
            if (nextBtn) nextBtn.disabled = currentTestQuestionIndex === totalQuestions - 1;
            if (counter) counter.textContent = `Question ${currentTestQuestionIndex + 1} of ${totalQuestions}`;
            
            // Show active question
            document.querySelectorAll('.unit-question-card').forEach(card => {
                card.classList.remove('active');
            });
            document.getElementById(`unit-question-${currentTestQuestionIndex}`).classList.add('active');
        }

        // Submit test (same as before)
        function submitTest(unit) {
            if (testSubmitted) return;
            
            // Check for unanswered questions
            const unanswered = Object.keys(selectedAnswers).length;
            const totalQuestions = unit.testQuestions.length;
            
            if (unanswered < totalQuestions) {
                if (!confirm(`You have ${totalQuestions - unanswered} unanswered question(s). Submit anyway?`)) {
                    return;
                }
            }
            
            testSubmitted = true;
            
            // Calculate score
            let score = 0;
            unit.testQuestions.forEach((question, index) => {
                if (selectedAnswers[index] === question.correct) {
                    score++;
                }
            });
            
            // Show final results
            showResults(score, unit.testQuestions.length);
            
            // Disable all options
            document.querySelectorAll('.unit-option').forEach(opt => {
                opt.style.pointerEvents = 'none';
            });
            
            // Update submit button
            const submitBtn = document.getElementById('unit-submit-btn');
            if (submitBtn) {
                submitBtn.textContent = 'Test Submitted';
                submitBtn.disabled = true;
                submitBtn.classList.remove('primary');
                submitBtn.classList.add('secondary');
            }
        }

        // Show results (same as before)
        function showResults(score, total) {
            const scoreElement = document.getElementById('unit-score-total');
            const messageElement = document.getElementById('unit-score-message');
            const detailsElement = document.getElementById('unit-score-details');
            const resultsDisplay = document.getElementById('unit-results-display');
            
            if (!scoreElement || !messageElement || !detailsElement || !resultsDisplay) return;
            
            scoreElement.textContent = score;
            
            const percentage = (score / total) * 100;
            let message = '';
            let details = '';
            
            if (percentage >= 90) {
                message = "ممتاز! نتيجة رائعة! 🎉";
                details = "لقد أتقنت هذه الوحدة. عمل رائع!";
            } else if (percentage >= 70) {
                message = "جيد جداً! 👍";
                details = "لديك فهم قوي. استمر في الممارسة!";
            } else if (percentage >= 50) {
                message = "جهد جيد 💪";
                details = "تفهم الأساسيات. راجع قواعد القواعد مرة أخرى.";
            } else {
                message = "بحاجة للتحسين 📚";
                details = "راجع شروحات القواعد وحاول مرة أخرى.";
            }
            
            messageElement.textContent = message;
            detailsElement.textContent = details;
            resultsDisplay.classList.add('show');
            
            // Scroll to results
            resultsDisplay.scrollIntoView({ behavior: 'smooth', block: 'center' });
        }
    </script>
</body>
</html> 
