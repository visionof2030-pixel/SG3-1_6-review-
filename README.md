
<html lang="en" dir="ltr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=5.0, user-scalable=yes">
    <title>Super Goal 3 - Interactive Learning System</title>
    <link href="https://fonts.googleapis.com/css2?family=Almarai:wght@300;400;700&family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #4361ee;
            --primary-dark: #3a56d4;
            --secondary: #06d6a0;
            --warning: #ffd166;
            --error: #ef476f;
            --info: #118ab2;
            --text-primary: #1a1a2e;
            --text-secondary: #6c757d;
            --background: #f8f9fa;
            --card-bg: #ffffff;
            --border: #e0e0e0;
            --shadow: 0 4px 20px rgba(0, 0, 0, 0.08);
            --radius: 12px;
            --final-test-color: #9d4edd;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            -webkit-tap-highlight-color: transparent;
        }

        body {
            font-family: 'Inter', sans-serif;
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
            color: var(--text-primary);
            line-height: 1.6;
            min-height: 100vh;
            padding: 12px 8px;
            direction: ltr;
            font-size: 15px;
            -webkit-font-smoothing: antialiased;
            -moz-osx-font-smoothing: grayscale;
            overflow-x: hidden;
            touch-action: manipulation;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 8px;
            width: 100%;
        }

        header {
            text-align: center;
            margin-bottom: 1.5rem;
            padding: 1.2rem 0.8rem;
            background: white;
            border-radius: var(--radius);
            box-shadow: var(--shadow);
            border-bottom: 4px solid var(--primary);
        }

        .logo-container {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 0.8rem;
            margin-bottom: 1rem;
            flex-wrap: wrap;
        }

        .logo {
            width: 50px;
            height: 50px;
            background: linear-gradient(135deg, var(--primary) 0%, var(--primary-dark) 100%);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 1.4rem;
            flex-shrink: 0;
        }

        h1 {
            font-size: 1.5rem;
            color: var(--text-primary);
            margin-bottom: 0.4rem;
            line-height: 1.3;
            font-weight: 800;
        }

        .subtitle {
            color: var(--text-secondary);
            font-size: 0.9rem;
            max-width: 100%;
            margin: 0 auto;
            line-height: 1.4;
        }

        .teacher-info {
            background: linear-gradient(135deg, var(--primary) 0%, var(--primary-dark) 100%);
            color: white;
            padding: 0.6rem 0.8rem;
            border-radius: 8px;
            margin-top: 0.8rem;
            font-size: 0.95rem;
            font-weight: 700;
            display: inline-block;
            box-shadow: 0 4px 12px rgba(67, 97, 238, 0.2);
        }

        .progress-section {
            background: white;
            border-radius: var(--radius);
            padding: 1.2rem 1rem;
            margin-bottom: 1.2rem;
            box-shadow: var(--shadow);
        }

        .progress-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 0.8rem;
        }

        .progress-header h2 {
            font-size: 1.1rem;
            font-weight: 700;
        }

        .progress-bar-container {
            width: 100%;
            height: 10px;
            background: #e9ecef;
            border-radius: 5px;
            overflow: hidden;
            margin: 0.8rem 0;
        }

        .progress-bar {
            height: 100%;
            background: linear-gradient(90deg, var(--secondary), var(--primary));
            border-radius: 5px;
            transition: width 0.5s ease;
        }

        .progress-details {
            display: flex;
            justify-content: space-between;
            margin-top: 0.5rem;
            color: var(--text-secondary);
            font-size: 0.85rem;
            flex-wrap: wrap;
            gap: 0.5rem;
        }

        .units-grid {
            display: grid;
            grid-template-columns: 1fr;
            gap: 1rem;
            margin-bottom: 2rem;
        }

        .unit-card {
            background: white;
            border-radius: var(--radius);
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            position: relative;
            border: 2px solid transparent;
            min-height: 180px;
        }

        .unit-card:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.12);
        }

        .unit-card.completed {
            border-color: var(--secondary);
        }

        .unit-color-bar {
            height: 5px;
            width: 100%;
        }

        .unit-header {
            padding: 1rem 0.9rem;
            display: flex;
            justify-content: space-between;
            align-items: flex-start;
            border-bottom: 1px solid var(--border);
        }

        .unit-info h3 {
            font-size: 1.1rem;
            margin-bottom: 0.3rem;
            color: var(--text-primary);
            font-family: 'Inter', sans-serif;
            font-weight: 700;
            line-height: 1.3;
        }

        .unit-info p {
            color: var(--text-secondary);
            font-size: 0.85rem;
            font-weight: 400;
            line-height: 1.4;
        }

        .unit-icon {
            width: 40px;
            height: 40px;
            border-radius: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.1rem;
            color: white;
            flex-shrink: 0;
        }

        .unit-progress {
            padding: 0.9rem 1rem;
        }

        .progress-label {
            display: flex;
            justify-content: space-between;
            margin-bottom: 0.4rem;
            font-size: 0.8rem;
            color: var(--text-secondary);
        }

        .unit-progress-bar {
            width: 100%;
            height: 8px;
            background: #e9ecef;
            border-radius: 4px;
            overflow: hidden;
            margin-top: 0.4rem;
        }

        .unit-progress-fill {
            height: 100%;
            border-radius: 4px;
            transition: width 0.5s ease;
        }

        .unit-actions {
            padding: 1rem;
            display: flex;
            flex-direction: column;
            gap: 0.6rem;
            border-top: 1px solid var(--border);
        }

        .btn {
            padding: 0.8rem 1rem;
            border: none;
            border-radius: 8px;
            font-family: 'Inter', sans-serif;
            font-weight: 500;
            cursor: pointer;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 0.5rem;
            transition: all 0.3s ease;
            font-size: 0.9rem;
            width: 100%;
            min-height: 44px;
            touch-action: manipulation;
            -webkit-tap-highlight-color: transparent;
        }

        .btn-primary {
            background: linear-gradient(135deg, var(--primary) 0%, var(--primary-dark) 100%);
            color: white;
        }

        .btn-secondary {
            background: #f8f9fa;
            color: var(--text-primary);
            border: 1px solid var(--border);
        }

        .btn-success {
            background: linear-gradient(135deg, var(--secondary) 0%, #05c490 100%);
            color: white;
        }

        .btn-danger {
            background: linear-gradient(135deg, var(--error) 0%, #d43f8d 100%);
            color: white;
        }

        .btn:disabled {
            opacity: 0.5;
            cursor: not-allowed;
        }

        .final-test-section {
            background: linear-gradient(135deg, var(--final-test-color) 0%, #7b2cbf 100%);
            border-radius: var(--radius);
            padding: 1.5rem 1rem;
            color: white;
            margin-bottom: 2rem;
            position: relative;
            overflow: hidden;
        }

        .test-badge {
            position: absolute;
            top: 0.8rem;
            right: 0.8rem;
            background: rgba(255, 255, 255, 0.2);
            padding: 0.3rem 0.6rem;
            border-radius: 20px;
            display: flex;
            align-items: center;
            gap: 0.4rem;
            font-size: 0.8rem;
            backdrop-filter: blur(10px);
        }

        .test-content h3 {
            font-size: 1.3rem;
            margin-bottom: 0.6rem;
            font-weight: 700;
        }

        .test-stats {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 0.8rem;
            margin: 1.2rem 0;
        }

        .stat-item {
            background: rgba(255, 255, 255, 0.1);
            padding: 0.7rem;
            border-radius: 8px;
            text-align: center;
            backdrop-filter: blur(10px);
        }

        .stat-number {
            font-size: 1.4rem;
            font-weight: 700;
            margin-bottom: 0.2rem;
        }

        .test-actions {
            display: flex;
            flex-direction: column;
            gap: 0.6rem;
            margin-top: 1.2rem;
        }

        .password-access {
            background: rgba(255, 255, 255, 0.15);
            border-radius: 10px;
            padding: 1rem;
            margin-top: 1.2rem;
            backdrop-filter: blur(5px);
            border: 1px solid rgba(255, 255, 255, 0.2);
        }

        .password-input-group {
            display: flex;
            flex-direction: column;
            gap: 0.6rem;
            margin-top: 0.8rem;
        }

        .password-input {
            width: 100%;
            padding: 0.8rem;
            border: none;
            border-radius: 8px;
            font-family: 'Inter', sans-serif;
            font-size: 16px;
            background: rgba(255, 255, 255, 0.9);
            min-height: 44px;
        }

        .modal {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.5);
            display: none;
            align-items: center;
            justify-content: center;
            z-index: 1000;
            padding: 10px;
            overflow-y: auto;
            -webkit-overflow-scrolling: touch;
        }

        .modal.active {
            display: flex;
        }

        .modal-content {
            background: white;
            border-radius: var(--radius);
            width: 100%;
            max-width: 100%;
            max-height: 90vh;
            display: flex;
            flex-direction: column;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
            overflow: hidden;
        }

        .modal-header {
            padding: 1rem;
            border-bottom: 1px solid var(--border);
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: linear-gradient(135deg, var(--primary) 0%, var(--primary-dark) 100%);
            color: white;
            border-radius: var(--radius) var(--radius) 0 0;
            flex-wrap: wrap;
            position: sticky;
            top: 0;
            z-index: 10;
        }

        .modal-close {
            background: none;
            border: none;
            color: white;
            font-size: 1.5rem;
            cursor: pointer;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: background 0.3s ease;
            flex-shrink: 0;
        }

        .modal-body {
            padding: 1rem;
            overflow-y: auto;
            flex: 1;
            -webkit-overflow-scrolling: touch;
        }

        .unit-questions-container {
            display: flex;
            flex-direction: column;
            gap: 1rem;
        }

        .unit-question-card {
            background: white;
            border-radius: 10px;
            padding: 1rem;
            border: 2px solid var(--border);
            transition: all 0.3s ease;
        }

        .unit-question-card.answered {
            border-color: #e0e0e0;
        }

        .unit-question-card.correct {
            border-color: var(--secondary);
            background: rgba(6, 214, 160, 0.05);
        }

        .unit-question-card.incorrect {
            border-color: var(--error);
            background: rgba(239, 71, 111, 0.05);
        }

        .question-header {
            display: flex;
            gap: 0.6rem;
            margin-bottom: 1rem;
            flex-wrap: wrap;
        }

        .question-number {
            width: 34px;
            height: 34px;
            background: linear-gradient(135deg, var(--primary) 0%, var(--primary-dark) 100%);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-weight: 700;
            flex-shrink: 0;
            font-size: 0.9rem;
        }

        .question-text {
            font-size: 0.95rem;
            font-weight: 600;
            margin-bottom: 0.4rem;
            color: var(--text-primary);
            line-height: 1.4;
            flex: 1;
        }

        .question-type {
            font-size: 0.75rem;
            color: var(--primary);
            background: rgba(67, 97, 238, 0.1);
            padding: 0.2rem 0.6rem;
            border-radius: 20px;
            display: inline-block;
        }

        .options-grid {
            display: grid;
            grid-template-columns: 1fr;
            gap: 0.6rem;
        }

        .option {
            padding: 0.8rem;
            border: 2px solid var(--border);
            border-radius: 8px;
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 0.6rem;
            transition: all 0.3s ease;
            min-height: 44px;
            -webkit-tap-highlight-color: transparent;
        }

        .option:hover {
            border-color: var(--primary);
            background: rgba(67, 97, 238, 0.05);
        }

        .option.selected {
            border-color: var(--primary);
            background: rgba(67, 97, 238, 0.1);
        }

        .option.correct {
            border-color: var(--secondary);
            background: rgba(6, 214, 160, 0.1);
        }

        .option.incorrect {
            border-color: var(--error);
            background: rgba(239, 71, 111, 0.1);
        }

        .option.answered {
            cursor: default;
        }

        .option-letter {
            display: none;
        }

        .option.correct .option-letter,
        .option.incorrect .option-letter {
            display: none;
        }

        .feedback-container {
            margin-top: 1rem;
            padding: 1rem;
            background: #f8f9fa;
            border-radius: 8px;
            border-left: 4px solid var(--primary);
            animation: slideIn 0.3s ease;
        }

        .feedback-header {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            margin-bottom: 0.6rem;
        }

        .feedback-icon {
            width: 26px;
            height: 26px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            font-size: 0.9rem;
        }

        .feedback-icon.correct {
            background: var(--secondary);
            color: white;
        }

        .feedback-icon.incorrect {
            background: var(--error);
            color: white;
        }

        .feedback-section {
            margin-top: 0.6rem;
        }

        .feedback-section-title {
            display: flex;
            align-items: center;
            gap: 0.4rem;
            margin-bottom: 0.3rem;
            color: var(--primary);
            font-weight: 600;
            font-size: 0.85rem;
        }

        .test-section {
            margin-bottom: 1.5rem;
            padding: 1rem;
            background: white;
            border-radius: 10px;
            border: 2px solid var(--border);
        }

        .section-header {
            display: flex;
            align-items: center;
            gap: 0.6rem;
            margin-bottom: 1rem;
            padding-bottom: 0.8rem;
            border-bottom: 2px solid var(--border);
            flex-wrap: wrap;
        }

        .section-icon {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.1rem;
            color: white;
            flex-shrink: 0;
        }

        .section-title {
            font-size: 1.1rem;
            color: var(--text-primary);
            margin: 0;
            font-weight: 700;
            flex: 1;
        }

        .section-score {
            background: var(--primary);
            color: white;
            padding: 0.3rem 0.6rem;
            border-radius: 20px;
            font-size: 0.8rem;
            flex-shrink: 0;
        }

        .vocabulary-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 15px;
            margin-bottom: 30px;
        }

        .vocab-item {
            background: #fff;
            border: 2px solid #e0e0e0;
            border-radius: 10px;
            padding: 15px;
            text-align: center;
            transition: all 0.3s ease;
            display: flex;
            flex-direction: column;
            align-items: center;
            min-height: 170px;
        }

        .vocab-item.correct {
            border-color: #06d6a0;
            background: rgba(6, 214, 160, 0.05);
        }

        .vocab-item.incorrect {
            border-color: #ef476f;
            background: rgba(239, 71, 111, 0.05);
        }

        .image-container {
            margin-bottom: 10px;
            width: 100%;
        }

        .image-card {
            border: 2px solid #2ec4b6;
            border-radius: 10px;
            padding: 8px;
            background: #ecfffb;
            text-align: center;
            width: 120px;
            margin: 0 auto;
            position: relative;
        }

        .image-letter {
            width: 28px;
            height: 28px;
            border-radius: 50%;
            background: #2ec4b6;
            color: #fff;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            margin: 0 auto 6px;
            font-size: 0.9rem;
        }

        .image-card img {
            width: 80px;
            height: 60px;
            object-fit: contain;
            border-radius: 5px;
        }

        .word-container {
            margin-top: 10px;
            width: 100%;
        }

        .answer-container {
            display: flex;
            gap: 8px;
            align-items: center;
            justify-content: center;
            margin-top: 8px;
            width: 100%;
        }

        .vocab-select {
            width: 100%;
            padding: 10px;
            border-radius: 6px;
            border: 2px solid #ccc;
            font-family: 'Inter', sans-serif;
            font-size: 0.95rem;
            background: white;
            text-align: center;
            cursor: pointer;
        }

        .vocab-select:focus {
            border-color: #4361ee;
            outline: none;
        }

        .vocab-select:disabled {
            background: #f5f5f5;
            cursor: not-allowed;
            opacity: 0.7;
        }

        .feedback-icon-vocab {
            width: 28px;
            height: 28px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            font-size: 0.9rem;
            flex-shrink: 0;
        }

        .correct-icon-vocab {
            background: #06d6a0;
            color: white;
        }

        .incorrect-icon-vocab {
            background: #ef476f;
            color: white;
        }

        .correct-hint {
            margin-top: 8px;
            padding: 6px;
            background: rgba(6, 214, 160, 0.1);
            border-radius: 4px;
            border-left: 2px solid #06d6a0;
            font-size: 0.85rem;
            color: #06d6a0;
            font-weight: 600;
            text-align: center;
        }

        .vocab-stats-container {
            margin-top: 20px;
            padding: 15px;
            background: #f8f9fa;
            border-radius: 10px;
            text-align: center;
        }

        .vocab-stats {
            display: flex;
            justify-content: center;
            gap: 25px;
            margin-bottom: 20px;
            flex-wrap: wrap;
        }

        .vocab-stat-item {
            text-align: center;
            min-width: 100px;
        }

        .vocab-stat-number {
            font-size: 1.8rem;
            font-weight: 800;
            margin-bottom: 5px;
        }

        .vocab-stat-label {
            font-size: 0.9rem;
            color: #666;
        }

        .vocab-buttons {
            display: flex;
            gap: 10px;
            justify-content: center;
            flex-wrap: wrap;
        }

        .vocab-btn {
            padding: 10px 20px;
            border: none;
            border-radius: 8px;
            font-family: 'Inter', sans-serif;
            font-weight: 500;
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 6px;
            font-size: 0.95rem;
            transition: all 0.3s ease;
            min-width: 160px;
            justify-content: center;
        }

        .vocab-btn-check {
            background: #4361ee;
            color: white;
        }

        .vocab-btn-show {
            background: #06d6a0;
            color: white;
        }

        .vocab-btn-reset {
            background: #ffd166;
            color: #333;
        }

        .vocab-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
        }

        .true-false-container {
            display: flex;
            flex-direction: column;
            gap: 1rem;
            margin-top: 1rem;
        }

        .true-false-question {
            display: flex;
            flex-direction: column;
            gap: 0.6rem;
            padding: 1rem;
            background: #f8f9fa;
            border-radius: 8px;
            border: 2px solid var(--border);
            position: relative;
        }

        .tf-options {
            display: flex;
            gap: 0.6rem;
            margin-top: 0.6rem;
            flex-wrap: wrap;
        }

        .tf-option {
            padding: 0.6rem 1rem;
            border: 2px solid var(--border);
            border-radius: 6px;
            cursor: pointer;
            transition: all 0.3s ease;
            font-weight: 600;
            flex: 1;
            text-align: center;
            min-width: 80px;
            min-height: 44px;
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            z-index: 1;
            -webkit-tap-highlight-color: transparent;
        }

        .tf-option:hover {
            border-color: var(--primary);
            background: rgba(67, 97, 238, 0.1);
        }

        .tf-option.selected {
            border-color: var(--primary);
            background: rgba(67, 97, 238, 0.1);
            color: var(--primary);
        }

        .tf-option.correct {
            border-color: var(--secondary);
            background: rgba(6, 214, 160, 0.1);
            color: var(--secondary);
            cursor: default;
        }

        .tf-option.incorrect {
            border-color: var(--error);
            background: rgba(239, 71, 111, 0.1);
            color: var(--error);
            cursor: default;
        }

        .writing-container {
            margin-top: 1rem;
        }

        .writing-instruction {
            background: #f8f9fa;
            padding: 0.8rem;
            border-radius: 8px;
            margin-bottom: 0.8rem;
            border-left: 4px solid var(--primary);
            font-size: 0.9rem;
        }

        .words-list {
            display: flex;
            flex-wrap: wrap;
            gap: 0.4rem;
            margin: 0.6rem 0;
            padding: 0.8rem;
            background: #f0f7ff;
            border-radius: 8px;
        }

        .word-tag {
            background: var(--primary);
            color: white;
            padding: 0.2rem 0.6rem;
            border-radius: 20px;
            font-size: 0.8rem;
        }

        .writing-textarea {
            width: 100%;
            height: 140px;
            padding: 0.8rem;
            border: 2px solid var(--border);
            border-radius: 8px;
            font-family: 'Inter', sans-serif;
            font-size: 16px;
            margin-top: 0.6rem;
            resize: vertical;
            min-height: 120px;
            line-height: 1.4;
        }

        .timer-container {
            display: flex;
            align-items: center;
            gap: 0.4rem;
            background: rgba(255, 255, 255, 0.2);
            padding: 0.3rem 0.6rem;
            border-radius: 20px;
            font-size: 0.85rem;
            flex-shrink: 0;
        }

        .footer {
            text-align: center;
            margin-top: 2rem;
            padding: 1.2rem 0.8rem;
            color: var(--text-secondary);
            font-size: 0.8rem;
            border-top: 1px solid var(--border);
        }

        .sample-answers {
            margin-top: 0.8rem;
            background: #f0f9ff;
            border-radius: 8px;
            padding: 0.8rem;
            border: 2px dashed #4361ee;
        }

        .sample-answer {
            background: white;
            border-radius: 6px;
            padding: 0.7rem;
            margin: 0.4rem 0;
            border: 1px solid #e0e0e0;
            cursor: pointer;
            transition: all 0.3s ease;
        }

        .sample-answer:hover {
            background: #e8f4ff;
            border-color: #4361ee;
        }

        .sample-answer h5 {
            color: #4361ee;
            margin-bottom: 0.4rem;
            display: flex;
            align-items: center;
            gap: 0.4rem;
            font-size: 0.9rem;
        }

        .sample-answer-content {
            font-size: 0.85rem;
            color: #333;
            line-height: 1.4;
        }

        .used-words {
            font-size: 0.75rem;
            color: #06d6a0;
            margin-top: 0.4rem;
            font-weight: 600;
        }

        @keyframes slideIn {
            from {
                opacity: 0;
                transform: translateY(-8px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Fix for Reading section click issues */
        .tf-option:not(.correct):not(.incorrect) {
            cursor: pointer;
            pointer-events: auto;
            user-select: none;
            -webkit-user-select: none;
            touch-action: manipulation;
        }

        .true-false-question * {
            pointer-events: auto;
        }

        .modal-body, .unit-questions-container, .test-section {
            pointer-events: auto !important;
        }

        .reading-feedback {
            margin-top: 0.8rem;
            padding: 0.7rem;
            background: #f8f9fa;
            border-radius: 6px;
            border-left: 3px solid var(--primary);
            animation: slideIn 0.3s ease;
        }

        /* New styles for test questions without numbering */
        .question-marker {
            width: 8px;
            height: 8px;
            background: #4361ee;
            border-radius: 50%;
            flex-shrink: 0;
            margin-top: 5px;
        }

        .question-marker-alt {
            width: 8px;
            height: 8px;
            background: #ffd166;
            border-radius: 50%;
            flex-shrink: 0;
            margin-top: 5px;
        }

        .question-marker-dash {
            width: 12px;
            height: 2px;
            background: #4361ee;
            flex-shrink: 0;
            margin-top: 8px;
        }

        .question-marker-dash-alt {
            width: 12px;
            height: 2px;
            background: #ffd166;
            flex-shrink: 0;
            margin-top: 8px;
        }

        .reading-marker {
            width: 8px;
            height: 8px;
            background: #118ab2;
            border-radius: 50%;
            flex-shrink: 0;
            margin-top: 5px;
        }

        @media (max-width: 900px) {
            .vocabulary-grid {
                grid-template-columns: repeat(2, 1fr);
                gap: 12px;
            }
            
            .image-card {
                width: 110px;
            }
            
            .image-card img {
                width: 70px;
                height: 55px;
            }
        }

        @media (max-width: 600px) {
            .vocabulary-grid {
                grid-template-columns: 1fr;
                gap: 10px;
            }
            
            .vocab-item {
                min-height: 160px;
                padding: 12px;
            }
            
            .image-card {
                width: 100px;
            }
            
            .image-card img {
                width: 65px;
                height: 50px;
            }
            
            .vocab-select {
                padding: 8px;
            }
            
            .vocab-stats {
                gap: 15px;
            }
            
            .vocab-stat-item {
                min-width: 80px;
            }
            
            .vocab-stat-number {
                font-size: 1.5rem;
            }
            
            .vocab-btn {
                min-width: 140px;
                padding: 8px 15px;
            }
            
            .vocab-buttons {
                gap: 8px;
            }
        }

        @media (max-width: 400px) {
            .image-card {
                width: 90px;
            }
            
            .image-card img {
                width: 60px;
                height: 45px;
            }
            
            .vocab-btn {
                min-width: 120px;
                font-size: 0.9rem;
            }
        }

        @media (min-width: 768px) {
            body {
                font-size: 16px;
                padding: 15px 10px;
            }
            
            .container {
                padding: 0 15px;
            }
            
            h1 {
                font-size: 1.8rem;
            }
            
            .subtitle {
                font-size: 1rem;
            }
            
            .units-grid {
                grid-template-columns: repeat(2, 1fr);
                gap: 1.2rem;
            }
            
            .unit-card {
                min-height: 200px;
            }
            
            .unit-info h3 {
                font-size: 1.3rem;
            }
            
            .btn {
                width: auto;
                min-width: 120px;
            }
            
            .unit-actions {
                flex-direction: row;
            }
            
            .test-actions {
                flex-direction: row;
                flex-wrap: wrap;
            }
            
            .password-input-group {
                flex-direction: row;
            }
            
            .password-input {
                min-width: 200px;
            }
            
            .modal-content {
                max-width: 90%;
            }
            
            .tf-options {
                flex-direction: row;
            }
            
            .test-stats {
                grid-template-columns: repeat(4, 1fr);
            }
        }

        @media (min-width: 1024px) {
            .units-grid {
                grid-template-columns: repeat(3, 1fr);
            }
            
            .modal-content {
                max-width: 900px;
            }
            
            .test-stats {
                grid-template-columns: repeat(4, 1fr);
            }
        }

        @media (max-width: 360px) {
            body {
                font-size: 14px;
                padding: 8px 5px;
            }
            
            h1 {
                font-size: 1.3rem;
            }
            
            .logo {
                width: 45px;
                height: 45px;
                font-size: 1.2rem;
            }
            
            .unit-info h3 {
                font-size: 1rem;
            }
            
            .option, .tf-option {
                min-height: 42px;
            }
            
            .btn {
                min-height: 42px;
                padding: 0.7rem 0.8rem;
            }
        }

        @media (max-width: 768px) {
            input, select, textarea {
                font-size: 16px !important;
            }
        }

        .modal-body, .unit-questions-container {
            -webkit-overflow-scrolling: touch;
        }

        .btn, .option, .tf-option {
            user-select: none;
            -webkit-user-select: none;
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <div class="logo-container">
                <div class="logo">
                    <i class="fas fa-bullseye"></i>
                </div>
                <div>
                    <h1>Super Goal 3</h1>
                    <p class="subtitle">Interactive Learning System - Practice English grammar and prepare for the final test</p>
                </div>
            </div>
            <div class="teacher-info">
                <i class="fas fa-chalkboard-teacher"></i>
                Teacher: Fahad Al-Khaldi
            </div>
        </header>

        <section class="progress-section">
            <div class="progress-header">
                <h2>Your Progress</h2>
                <span id="overallProgress">0%</span>
            </div>
            <div class="progress-bar-container">
                <div class="progress-bar" id="progressBar"></div>
            </div>
            <div class="progress-details">
                <span id="completedUnits">0/6 units completed</span>
                <span id="totalQuestions">0/30 questions answered</span>
            </div>
        </section>

        <section>
            <h2 style="margin-bottom: 1rem; color: var(--text-primary); font-size: 1.2rem;">Learning Units</h2>
            <div class="units-grid" id="unitsGrid">
                <!-- Units will be filled here -->
            </div>
        </section>

        <section class="final-test-section" id="finalTestCard">
            <div class="test-badge" id="testBadge">
                <i class="fas fa-lock"></i>
                <span>Locked</span>
            </div>
            <div class="test-content">
                <h3>Comprehensive Final Test</h3>
                <p style="font-size: 0.9rem;">Comprehensive test covering all topics from units 1 to 6</p>
                
                <div class="test-stats">
                    <div class="stat-item">
                        <div class="stat-number" id="testQuestionsAnswered">0</div>
                        <div>Questions Answered</div>
                    </div>
                    <div class="stat-item">
                        <div class="stat-number">5</div>
                        <div>Different Sections</div>
                    </div>
                    <div class="stat-item">
                        <div class="stat-number">60</div>
                        <div>Minutes</div>
                    </div>
                    <div class="stat-item">
                        <div class="stat-number" id="testProgress">0%</div>
                        <div>Test Progress</div>
                    </div>
                </div>

                <div class="test-actions">
                    <button class="btn btn-primary" onclick="app.startFinalTest()" id="startFinalTestBtn" disabled>
                        <i class="fas fa-play-circle"></i>
                        Start Final Test
                    </button>
                    <button class="btn btn-secondary" onclick="app.showTestPreview()">
                        <i class="fas fa-eye"></i>
                        Preview Test Structure
                    </button>
                    <button class="btn btn-danger" onclick="app.showPasswordAccess()">
                        <i class="fas fa-key"></i>
                        Access with Password
                    </button>
                </div>

                <div class="password-access" id="passwordAccess" style="display: none;">
                    <h4 style="margin-bottom: 0.6rem; font-size: 1rem;">Access with Password</h4>
                    <p style="margin-bottom: 0.6rem; font-size: 0.85rem;">Enter password to access the final test directly:</p>
                    <div class="password-input-group">
                        <input type="password" class="password-input" id="passwordInput" placeholder="Enter password">
                        <button class="btn btn-primary" onclick="app.checkPassword()">
                            <i class="fas fa-unlock"></i>
                            Unlock
                        </button>
                    </div>
                    <p id="passwordMessage" style="margin-top: 0.6rem; font-size: 0.85rem; display: none;"></p>
                </div>
            </div>
        </section>

        <footer class="footer">
            <p>© 2024 Super Goal 3 Interactive Learning System</p>
            <p style="margin-top: 0.4rem; color: var(--primary); font-weight: 600;">Prepared and designed by: Teacher Fahad Al-Khalidi</p>
            <button class="btn btn-secondary" onclick="app.resetProgress()" style="margin-top: 0.8rem; max-width: 200px; margin-left: auto; margin-right: auto;">
                <i class="fas fa-redo"></i>
                Reset Progress
            </button>
        </footer>
    </div>

    <!-- Unit Questions Modal -->
    <div class="modal" id="unitModal">
        <div class="modal-content">
            <div class="modal-header">
                <div>
                    <h3 id="unitModalTitle">Unit Name</h3>
                    <p id="unitModalDesc">Unit Description</p>
                </div>
                <button class="modal-close" onclick="app.closeUnitModal()">&times;</button>
            </div>
            <div class="modal-body">
                <div class="unit-questions-container" id="unitQuestionsContainer">
                    <!-- Questions will be filled here -->
                </div>
            </div>
            <div style="padding: 1rem; border-top: 1px solid var(--border); text-align: center;">
                <button class="btn btn-primary" onclick="app.checkAllQuestions()" style="padding: 0.8rem 1.5rem; font-size: 0.95rem; margin-bottom: 0.5rem;">
                    <i class="fas fa-check-circle"></i>
                    Complete Unit
                </button>
                <div style="color: var(--text-secondary); font-size: 0.85rem;">
                    <span id="unitProgressText">0/5 questions answered</span>
                </div>
            </div>
        </div>
    </div>

    <!-- Final Test Modal -->
    <div class="modal" id="finalTestModal">
        <div class="modal-content">
            <div class="modal-header">
                <div style="display: flex; align-items: center; flex-wrap: wrap; gap: 0.5rem; width: 100%;">
                    <h3 style="margin: 0; flex: 1; font-size: 1.1rem;">Comprehensive Final Test</h3>
                    <div class="timer-container">
                        <i class="fas fa-clock"></i>
                        <span id="timeRemaining">60:00</span>
                    </div>
                </div>
                <button class="modal-close" onclick="app.closeFinalTestModal()">&times;</button>
            </div>
            <div class="modal-body" id="finalTestContent">
                <!-- Test content will be filled here -->
            </div>
            <div style="padding: 1rem; border-top: 1px solid var(--border); text-align: center;">
                <button class="btn btn-success" onclick="app.submitFinalTest()" style="padding: 0.8rem 1.5rem; font-size: 0.95rem; margin-bottom: 0.5rem;">
                    <i class="fas fa-paper-plane"></i>
                    Submit Test
                </button>
                <div style="color: var(--text-secondary); font-size: 0.85rem;">
                    <span id="testProgressText">0/40 questions answered</span>
                </div>
            </div>
        </div>
    </div>

    <script>
        // البيانات
        const unitsData = [
            {
                id: 1,
                name: "Unit 1: Lifestyles",
                description: "Learn to express habits and daily routines",
                questionsNeeded: 5,
                questionsCompleted: 0,
                color: "#4361ee",
                icon: "fas fa-user-clock"
            },
            {
                id: 2,
                name: "Unit 2: Life Stories",
                description: "Past stories and personal experiences",
                questionsNeeded: 5,
                questionsCompleted: 0,
                color: "#06d6a0",
                icon: "fas fa-book-open"
            },
            {
                id: 3,
                name: "Unit 3: When Are You Traveling?",
                description: "Travel planning and future",
                questionsNeeded: 5,
                questionsCompleted: 0,
                color: "#ffd166",
                icon: "fas fa-plane-departure"
            },
            {
                id: 4,
                name: "Unit 4: What Do I Need to Buy?",
                description: "Shopping and ingredients",
                questionsNeeded: 5,
                questionsCompleted: 0,
                color: "#ef476f",
                icon: "fas fa-shopping-cart"
            },
            {
                id: 5,
                name: "Unit 5: Since When?",
                description: "Duration and extended time",
                questionsNeeded: 5,
                questionsCompleted: 0,
                color: "#118ab2",
                icon: "fas fa-hourglass-half"
            },
            {
                id: 6,
                name: "Unit 6: Do You Know Where It Is?",
                description: "Places and directions",
                questionsNeeded: 5,
                questionsCompleted: 0,
                color: "#9d4edd",
                icon: "fas fa-map-marker-alt"
            }
        ];

        const unitQuestionsData = {
            1: [
                {
                    id: 1,
                    question: "Rewrite using the adverb in parentheses: 'I usually eat vegetables.' → (hardly ever) - Which is correct?",
                    options: [
                        "I hardly ever eat vegetables.",
                        "I usually hardly eat vegetables.",
                        "I eat vegetables hardly ever.",
                        "I eat hardly vegetables ever."
                    ],
                    correctAnswer: 0,
                    explanation: {
                        correct: "Excellent! The correct sentence is 'I hardly ever eat vegetables.'",
                        wrong: "Wrong. Rule: Frequency adverbs like hardly ever come before the main verb.",
                        grammar: "Frequency adverbs (Adverbs of Frequency) come before the main verb: always, usually, often, sometimes, rarely, hardly ever, never",
                        example: "Example: I always drink coffee. She never eats meat. They sometimes go to the gym."
                    }
                },
                {
                    id: 2,
                    question: "Choose the correct question: ___ do you exercise?",
                    options: ["How long", "How often", "How much", "How many"],
                    correctAnswer: 1,
                    explanation: {
                        correct: "Correct! 'How often' asks about frequency.",
                        wrong: "Wrong. 'How often' is used to ask how frequently something happens.",
                        grammar: "Frequency questions: How often + do/does + subject + verb?",
                        example: "Example: How often do you go to the gym? How often does she visit her family?"
                    }
                },
                {
                    id: 3,
                    question: "'Frequently' means:",
                    options: ["never", "rarely", "often", "sometimes"],
                    correctAnswer: 2,
                    explanation: {
                        correct: "Correct! 'Frequently' means 'often' (frequently, many times).",
                        wrong: "Wrong. frequently = often = frequently, many times.",
                        grammar: "Frequency vocabulary: Always → Usually → Often/Frequently → Sometimes → Rarely/Seldom → Never",
                        example: "Example: She frequently visits the library. = She often visits the library."
                    }
                },
                {
                    id: 4,
                    question: "'Once in a while' means:",
                    options: ["every day", "always", "occasionally", "never"],
                    correctAnswer: 2,
                    explanation: {
                        correct: "Excellent! 'Once in a while' means 'occasionally' (sometimes, from time to time).",
                        wrong: "Wrong. once in a while = occasionally = sometimes, from time to time.",
                        grammar: "Time expressions: Once in a while = Occasionally = sometimes",
                        example: "Example: I go to the cinema once in a while. = I go to the cinema occasionally."
                    }
                },
                {
                    id: 5,
                    question: "Which sentence uses 'neither' correctly?",
                    options: [
                        "Neither of them drinks coffee.",
                        "Neither of them drink coffee.",
                        "They neither drink coffee.",
                        "Neither they drink coffee."
                    ],
                    correctAnswer: 0,
                    explanation: {
                        correct: "Correct! 'Neither of them drinks coffee.' is the correct sentence.",
                        wrong: "Wrong. Rule: Neither + of + plural noun + singular verb",
                        grammar: "Neither/Either: Neither of + plural noun + singular verb, Either of + plural noun + singular verb",
                        example: "Example: Neither of the books is interesting. Either of the answers is correct."
                    }
                }
            ],
            2: [
                {
                    id: 1,
                    question: "Choose the correct past tense: He ___ to the clinic yesterday.",
                    options: ["go", "going", "went", "goes"],
                    correctAnswer: 2,
                    explanation: {
                        correct: "Excellent! 'went' is the simple past form of the verb 'go'.",
                        wrong: "Wrong. The verb 'go' is conjugated in simple past: go → went → gone",
                        grammar: "Simple Past: Subject + verb(past form) + time expression",
                        example: "Example: I went to school yesterday. She visited her friend last week."
                    }
                },
                {
                    id: 2,
                    question: "Rewrite using 'used to': 'I walked to school every day.'",
                    options: [
                        "I use to walk to school every day.",
                        "I used to walk to school every day.",
                        "I was used to walk to school every day.",
                        "I use walking to school every day."
                    ],
                    correctAnswer: 1,
                    explanation: {
                        correct: "Correct! 'I used to walk to school every day.' is the correct sentence.",
                        wrong: "Wrong. Used to + base verb to express past habits that have stopped now.",
                        grammar: "Used to: Subject + used to + base verb (for past habits)",
                        example: "Example: I used to play football when I was young. She used to live in London."
                    }
                },
                {
                    id: 3,
                    question: "'Donated' means:",
                    options: ["bought", "gave for charity", "borrowed", "took"],
                    correctAnswer: 1,
                    explanation: {
                        correct: "Excellent! 'Donated' means 'gave for charity' (donated, gave to charitable organizations).",
                        wrong: "Wrong. donate = to give money, food, clothes, etc. to help people",
                        grammar: "Vocabulary: donate (verb) → donation (noun) → donor (agent noun)",
                        example: "Example: He donated money to the hospital. They donated clothes to the poor."
                    }
                },
                {
                    id: 4,
                    question: "'Appointment' means:",
                    options: ["a surprise visit", "a job", "a planned meeting", "a ceremony"],
                    correctAnswer: 2,
                    explanation: {
                        correct: "Correct! 'Appointment' means 'a planned meeting' (appointment, planned meeting).",
                        wrong: "Wrong. appointment = an arrangement to meet someone at a particular time",
                        grammar: "Related words: appointment (appointment) → schedule (schedule) → meeting (meeting)",
                        example: "Example: I have a doctor's appointment at 3 PM. She made an appointment with her lawyer."
                    }
                },
                {
                    id: 5,
                    question: "Choose the correct passive sentence:",
                    options: [
                        "He was called 'Athlete of the Year.'",
                        "He called 'Athlete of the Year.'",
                        "He was calling 'Athlete of the Year.'",
                        "He is call 'Athlete of the Year.'"
                    ],
                    correctAnswer: 0,
                    explanation: {
                        correct: "Correct! 'He was called 'Athlete of the Year.'' is the correct sentence.",
                        wrong: "Wrong. Passive voice form in simple past: was/were + past participle",
                        grammar: "Passive Voice (Simple Past): Subject + was/were + past participle",
                        example: "Example: The book was written in 2020. The house was built last year."
                    }
                }
            ],
            3: [
                {
                    id: 1,
                    question: "She ___ her luggage right now.",
                    options: ["checks", "is checking", "checked", "was checking"],
                    correctAnswer: 1,
                    explanation: {
                        correct: "Excellent! 'is checking' is the appropriate present continuous form with 'right now'.",
                        wrong: "Wrong. Present continuous is used for actions happening now: am/is/are + verb-ing",
                        grammar: "Present Continuous: Subject + am/is/are + verb-ing (for actions happening now)",
                        example: "Example: I am studying now. They are watching TV at the moment."
                    }
                },
                {
                    id: 2,
                    question: "I think it ___ rain tomorrow.",
                    options: ["going to", "will", "was", "did"],
                    correctAnswer: 1,
                    explanation: {
                        correct: "Correct! 'will' is used for predictions and instant decisions.",
                        wrong: "Wrong. Will + base verb is used for predictions, promises and decisions made at the moment of speaking.",
                        grammar: "Simple Future with will: Subject + will + base verb",
                        example: "Example: It will probably rain later. I will help you with your homework."
                    }
                },
                {
                    id: 3,
                    question: "'Itinerary' means:",
                    options: ["a travel plan", "a passport", "a suitcase", "an airport gate"],
                    correctAnswer: 0,
                    explanation: {
                        correct: "Correct! 'Itinerary' means 'a travel plan' (travel plan, schedule).",
                        wrong: "Wrong. itinerary = a plan or schedule of a trip",
                        grammar: "Travel vocabulary: itinerary (travel plan) → passport (passport) → luggage (luggage)",
                        example: "Example: The travel agency sent us the itinerary for our trip to Paris."
                    }
                },
                {
                    id: 4,
                    question: "'Departure' means:",
                    options: ["arrival", "waiting", "checking", "leaving"],
                    correctAnswer: 3,
                    explanation: {
                        correct: "Excellent! 'Departure' means 'leaving' (departure, leaving).",
                        wrong: "Wrong. departure = the act of leaving a place (departure) → arrival = arrival",
                        grammar: "Antonyms: departure (departure) ↔ arrival (arrival)",
                        example: "Example: The departure time is 6 PM. Arrival time is 8 PM."
                    }
                },
                {
                    id: 5,
                    question: "What is the function of the infinitive? 'He came early to study.'",
                    options: ["showing time", "giving a reason", "comparing two actions", "describing a person"],
                    correctAnswer: 1,
                    explanation: {
                        correct: "Correct! 'to study' gives the reason for coming early.",
                        wrong: "Wrong. to + verb (infinitive) can give a reason or purpose for the main action.",
                        grammar: "Infinitive to give reason: Subject + verb + to + base verb (to give reason or purpose)",
                        example: "Example: I went to the store to buy milk. She studies hard to get good grades."
                    }
                }
            ],
            4: [
                {
                    id: 1,
                    question: "There are ___ tomatoes left.",
                    options: ["much", "nothing", "a few", "enough"],
                    correctAnswer: 2,
                    explanation: {
                        correct: "Excellent! 'a few' is used with countable nouns (tomatoes).",
                        wrong: "Wrong. a few + plural countable nouns, a little + uncountable nouns",
                        grammar: "Quantity with nouns: a few (few) + plural countable, a little (little) + uncountable, enough (enough) + both",
                        example: "Example: There are a few apples. There is a little water. We have enough money."
                    }
                },
                {
                    id: 2,
                    question: "I need ___ to eat.",
                    options: ["nothing", "anything", "something", "no one"],
                    correctAnswer: 2,
                    explanation: {
                        correct: "Correct! 'something' is used in positive sentences when we don't know the specific thing.",
                        wrong: "Wrong. something (something) is used in positive sentences, anything (anything) in negative and interrogative sentences.",
                        grammar: "Indefinite words: something (in positive sentences), anything (in negation and questions), nothing (nothing)",
                        example: "Example: I want something to drink. Do you want anything? I have nothing to say."
                    }
                },
                {
                    id: 3,
                    question: "'Groceries' means:",
                    options: ["clothes", "food items", "electronics", "instructions"],
                    correctAnswer: 1,
                    explanation: {
                        correct: "Excellent! 'Groceries' means 'food items' (food items, groceries).",
                        wrong: "Wrong. groceries = food and other items sold at a grocery store or supermarket",
                        grammar: "Purchases: groceries (groceries) → supermarket (supermarket) → shopping list (shopping list)",
                        example: "Example: I need to buy groceries for the week. We're out of milk and bread."
                    }
                },
                {
                    id: 4,
                    question: "'Recipe' means:",
                    options: ["shopping list", "grocery store", "cooking steps", "food price"],
                    correctAnswer: 2,
                    explanation: {
                        correct: "Correct! 'Recipe' means 'cooking steps' (recipe, cooking steps).",
                        wrong: "Wrong. recipe = a set of instructions for preparing a particular dish",
                        grammar: "Cooking: recipe (recipe) → ingredients (ingredients) → instructions (instructions)",
                        example: "Example: This recipe for chocolate cake is delicious. Follow the recipe carefully."
                    }
                },
                {
                    id: 5,
                    question: "Choose the correct sentence:",
                    options: [
                        "He was tired, so he slept.",
                        "He slept, so he was tired.",
                        "He was tired because he slept.",
                        "He is tired so because slept."
                    ],
                    correctAnswer: 0,
                    explanation: {
                        correct: "Excellent! 'He was tired, so he slept.' is the correct sentence.",
                        wrong: "Wrong. so (so) means result, because (because) means reason.",
                        grammar: "Cause and effect: because (because) + cause, so (so) + result",
                        example: "Example: It was raining, so we stayed home. We stayed home because it was raining."
                    }
                }
            ],
            5: [
                {
                    id: 1,
                    question: "I ___ here since 2010.",
                    options: ["lived", "have lived", "am living", "live"],
                    correctAnswer: 1,
                    explanation: {
                        correct: "Correct! 'have lived' is the appropriate present perfect form with 'since'.",
                        wrong: "Wrong. Present perfect: have/has + past participle with since (since) or for (for)",
                        grammar: "Present Perfect: Subject + have/has + past participle + since/for + time",
                        example: "Example: She has worked here since 2015. They have known each other for ten years."
                    }
                },
                {
                    id: 2,
                    question: "___ have you had your phone?",
                    options: ["How many", "How long", "How often", "How soon"],
                    correctAnswer: 1,
                    explanation: {
                        correct: "Excellent! 'How long' asks about time duration.",
                        wrong: "Wrong. How long? (since when? / how long?) is used with present perfect.",
                        grammar: "Duration questions: How long + have/has + subject + past participle?",
                        example: "Example: How long have you studied English? How long has she lived in Riyadh?"
                    }
                },
                {
                    id: 3,
                    question: "'Recently' means:",
                    options: ["rarely", "long ago", "recently", "never"],
                    correctAnswer: 2,
                    explanation: {
                        correct: "Excellent! 'Recently' means 'recently' (recently, lately).",
                        wrong: "Wrong. recently = not long ago; in the recent past",
                        grammar: "Time expressions: recently (recently), lately (lately), these days (these days)",
                        example: "Example: I've been very busy recently. Have you seen any good movies recently?"
                    }
                },
                {
                    id: 4,
                    question: "'Invention' means:",
                    options: ["experiment", "discovery", "creation / invention", "improvement"],
                    correctAnswer: 2,
                    explanation: {
                        correct: "Correct! 'Invention' means 'creation / invention' (invention, innovation).",
                        wrong: "Wrong. invention = something that has been designed or created for the first time",
                        grammar: "Innovation: invention (invention) → inventor (inventor) → innovative (innovative)",
                        example: "Example: The telephone was an important invention. He has many inventions to his name."
                    }
                },
                {
                    id: 5,
                    question: "Choose the correct present perfect passive:",
                    options: [
                        "The phone has repaired.",
                        "The phone been repaired.",
                        "The phone has been repaired.",
                        "The phone repaired."
                    ],
                    correctAnswer: 2,
                    explanation: {
                        correct: "Excellent! 'The phone has been repaired.' is the correct form.",
                        wrong: "Wrong. Present perfect passive form: have/has + been + past participle",
                        grammar: "Present Perfect Passive: Subject + have/has + been + past participle",
                        example: "Example: The work has been completed. The letters have been sent."
                    }
                }
            ],
            6: [
                {
                    id: 1,
                    question: "This road is ___ than the other one.",
                    options: ["safe", "safest", "more safe", "safer"],
                    correctAnswer: 3,
                    explanation: {
                        correct: "Correct! 'safer' is the comparative form of the adjective 'safe'.",
                        wrong: "Wrong. Comparative form of short adjectives: adjective + -er + than",
                        grammar: "Comparative forms: Short adjectives: adjective + -er + than, Long adjectives: more + adjective + than",
                        example: "Example: big → bigger, small → smaller, beautiful → more beautiful"
                    }
                },
                {
                    id: 2,
                    question: "Do you know where ___ ?",
                    options: ["is the museum", "the museum is", "museum is where", "is museum"],
                    correctAnswer: 1,
                    explanation: {
                        correct: "Excellent! 'the museum is' is the correct form in indirect question.",
                        wrong: "Wrong. In indirect questions we use normal word order: subject + verb",
                        grammar: "Indirect questions: Do you know + question word + subject + verb?",
                        example: "Example: Can you tell me where the bank is? Do you know what time it is?"
                    }
                },
                {
                    id: 3,
                    question: "'Neighborhood' means:",
                    options: ["city", "shop", "neighborhood", "street"],
                    correctAnswer: 2,
                    explanation: {
                        correct: "Excellent! 'Neighborhood' means 'neighborhood' (neighborhood, residential area).",
                        wrong: "Wrong. neighborhood = a district or community within a town or city",
                        grammar: "Places: neighborhood (neighborhood) → city (city) → street (street) → district (district)",
                        example: "Example: It's a quiet neighborhood with good schools. We've lived in this neighborhood for years."
                    }
                },
                {
                    id: 4,
                    question: "'Crowded' means:",
                    options: ["empty", "full of people", "expensive", "dangerous"],
                    correctAnswer: 1,
                    explanation: {
                        correct: "Correct! 'Crowded' means 'full of people' (crowded, full of people).",
                        wrong: "Wrong. crowded = full of people, leaving little space to move",
                        grammar: "Place adjectives: crowded (crowded) → empty (empty) → quiet (quiet) → noisy (noisy)",
                        example: "Example: The market was very crowded on Friday. Avoid crowded places during flu season."
                    }
                },
                {
                    id: 5,
                    question: "Choose the correct use of 'the':",
                    options: [
                        "Riyadh is the capital of Saudi Arabia.",
                        "The Riyadh is capital of Saudi Arabia.",
                        "Riyadh the capital is of Saudi Arabia.",
                        "The Riyadh capital is Saudi Arabia."
                    ],
                    correctAnswer: 0,
                    explanation: {
                        correct: "Excellent! 'Riyadh is the capital of Saudi Arabia.' is the correct sentence.",
                        wrong: "Wrong. We use 'the' with unique places like capitals, but we don't use it with city names.",
                        grammar: "Definite article 'the': used with unique places (the capital, the moon) but not with city names.",
                        example: "Example: London is the capital of England. Paris is a beautiful city."
                    }
                }
            ]
        };

        const finalTestData = {
            grammar: [
                {
                    id: 1,
                    question: "He ____ plays football on weekends.",
                    options: ["never", "always", "rarely"],
                    correctAnswer: 1,
                    explanation: "Correct! 'always' means always or consistently. Correct sentence: He always plays football on weekends."
                },
                {
                    id: 2,
                    question: "How often ____ you drink coffee?",
                    options: ["do", "does", "did"],
                    correctAnswer: 0,
                    explanation: "Excellent! With the pronoun 'you' we use 'do'. Correct sentence: How often do you drink coffee?"
                },
                {
                    id: 3,
                    question: "My friends are ____ to the museum tomorrow.",
                    options: ["go", "going", "goes"],
                    correctAnswer: 1,
                    explanation: "Correct! We use 'going' with present continuous to express future. Correct sentence: My friends are going to the museum tomorrow."
                },
                {
                    id: 4,
                    question: "They both ____ English very well.",
                    options: ["speak", "speaks", "speaking"],
                    correctAnswer: 0,
                    explanation: "Excellent! With 'they' we use 'speak' without 's'. Correct sentence: They both speak English very well."
                },
                {
                    id: 5,
                    question: "I ____ to play with toys when I was a child.",
                    options: ["use", "used", "used to"],
                    correctAnswer: 2,
                    explanation: "Correct! 'used to' expresses a past habit. Correct sentence: I used to play with toys when I was a child."
                },
                {
                    id: 6,
                    question: "She was born ____ 2005.",
                    options: ["at", "in", "on"],
                    correctAnswer: 1,
                    explanation: "Excellent! We use 'in' with years. Correct sentence: She was born in 2005."
                },
                {
                    id: 7,
                    question: "He is ____ a haircut now.",
                    options: ["get", "got", "getting"],
                    correctAnswer: 2,
                    explanation: "Correct! 'getting' is the present continuous form. Correct sentence: He is getting a haircut now."
                },
                {
                    id: 8,
                    question: "I have lived here ____ three years.",
                    options: ["for", "since", "from"],
                    correctAnswer: 0,
                    explanation: "Excellent! We use 'for' with time duration. Correct sentence: I have lived here for three years."
                },
                {
                    id: 9,
                    question: "They didn't go to school when they ____ young.",
                    options: ["are", "were", "be"],
                    correctAnswer: 1,
                    explanation: "Correct! 'were' is the past form of the verb 'be'. Correct sentence: They didn't go to school when they were young."
                }
            ],
            orthography: [
                {
                    id: 10,
                    question: "Which letter completes the word? '_ilk'",
                    options: ["n", "m", "l"],
                    correctAnswer: 1,
                    explanation: "Correct! The correct word is 'milk'."
                },
                {
                    id: 11,
                    question: "Which letter completes the word? 'pota_oes'",
                    options: ["t", "d", "p"],
                    correctAnswer: 0,
                    explanation: "Excellent! The correct word is 'potatoes'."
                },
                {
                    id: 12,
                    question: "Which letter completes the word? 'bre_d'",
                    options: ["e", "a", "i"],
                    correctAnswer: 1,
                    explanation: "Correct! The correct word is 'bread'."
                },
                {
                    id: 13,
                    question: "Which letter completes the word? 'fru_t'",
                    options: ["e", "i", "o"],
                    correctAnswer: 1,
                    explanation: "Excellent! The correct word is 'fruit'."
                },
                {
                    id: 14,
                    question: "Which letter completes the word? 'mang_'",
                    options: ["o", "a", "u"],
                    correctAnswer: 0,
                    explanation: "Correct! The correct word is 'mango'."
                }
            ],
            vocabulary: [
                { id: 1, word: "avocado", correctMatch: "A" },
                { id: 2, word: "cereal", correctMatch: "B" },
                { id: 3, word: "olive oil", correctMatch: "C" },
                { id: 4, word: "lamb", correctMatch: "D" },
                { id: 5, word: "cheese", correctMatch: "E" },
                { id: 6, word: "mango", correctMatch: "F" },
                { id: 7, word: "carrot", correctMatch: "G" },
                { id: 8, word: "bread", correctMatch: "H" },
                { id: 9, word: "shrimp", correctMatch: "I" }
            ],
            reading: [
                {
                    id: 1,
                    question: "King Salman was born in Jeddah.",
                    correctAnswer: false,
                    explanation: "Wrong. King Salman was born in Riyadh, not Jeddah."
                },
                {
                    id: 2,
                    question: "He studied at the Princes' School.",
                    correctAnswer: true,
                    explanation: "Correct. He studied at the Princes' School."
                },
                {
                    id: 3,
                    question: "He became King in 2012.",
                    correctAnswer: false,
                    explanation: "Wrong. He became King in 2015, not 2012."
                },
                {
                    id: 4,
                    question: "He worked to develop the city of Riyadh.",
                    correctAnswer: true,
                    explanation: "Correct. He worked to develop the city of Riyadh."
                },
                {
                    id: 5,
                    question: "Riyadh became smaller during his leadership.",
                    correctAnswer: false,
                    explanation: "Wrong. Riyadh grew and became larger, not smaller."
                },
                {
                    id: 6,
                    question: "He supported humanitarian work.",
                    correctAnswer: true,
                    explanation: "Correct. He supported humanitarian work."
                },
                {
                    id: 7,
                    question: "He received awards for his projects.",
                    correctAnswer: false,
                    explanation: "Wrong. The text doesn't mention that he received awards."
                },
                {
                    id: 8,
                    question: "He helped develop cities outside the Kingdom.",
                    correctAnswer: true,
                    explanation: "Correct. He helped develop cities outside the Kingdom."
                },
                {
                    id: 9,
                    question: "The passage talks about King Salman's future plans.",
                    correctAnswer: false,
                    explanation: "Wrong. The text talks about his past achievements, not his future plans."
                }
            ],
            writing: {
                words: ["enjoy", "fitness", "work out", "spend time", "lifestyle", "herbal tea", "puzzle", "fan"],
                minSentences: 3,
                maxSentences: 5,
                minWords: 8
            }
        };

        const vocabularyImages = [
            { letter: "A", img: "https://i.ibb.co/bgBqr2vp/IMG-2038.jpg" },
            { letter: "B", img: "https://i.ibb.co/C3SrJVVT/IMG-2037.jpg" },
            { letter: "C", img: "https://i.ibb.co/8L6n4sm4/IMG-2036.jpg" },
            { letter: "D", img: "https://i.ibb.co/cSbBBhmg/IMG-2035.jpg" },
            { letter: "E", img: "https://i.ibb.co/v448HKNw/IMG-2034.jpg" },
            { letter: "F", img: "https://i.ibb.co/vCYy204h/IMG-2033.jpg" },
            { letter: "G", img: "https://i.ibb.co/3YNMrbDN/IMG-2031.webp" },
            { letter: "H", img: "https://i.ibb.co/20LtFPLR/IMG-2032.jpg" },
            { letter: "I", img: "https://i.ibb.co/P0g70Ls/IMG-2030.jpg" }
        ];

        const writingSamples = [
            {
                title: "Sample 1 (About Sports)",
                content: "I enjoy fitness. I work out every day. I spend time at the gym. This is my healthy lifestyle. I am a big fan of sports.",
                usedWords: ["enjoy", "fitness", "work out", "spend time", "lifestyle", "fan"],
                wordCount: 6
            },
            {
                title: "Sample 2 (About Daily Life)",
                content: "My lifestyle is healthy. I enjoy herbal tea. I work out three times a week. I spend time with my family. I am a fan of puzzles.",
                usedWords: ["lifestyle", "enjoy", "herbal tea", "work out", "spend time", "fan", "puzzle"],
                wordCount: 7
            },
            {
                title: "Sample 3 (About Healthy Habits)",
                content: "I enjoy a healthy lifestyle. I work out in the morning. I spend time drinking herbal tea. Sometimes I do a puzzle. I am a fitness fan.",
                usedWords: ["enjoy", "lifestyle", "work out", "spend time", "herbal tea", "puzzle", "fitness", "fan"],
                wordCount: 8
            }
        ];

        class SuperGoalApp {
            constructor() {
                this.units = [];
                this.currentUnit = null;
                this.unitAnswers = {};
                this.finalTestAnswers = {
                    grammar: {},
                    orthography: {},
                    vocabulary: {},
                    reading: {},
                    writing: ""
                };
                this.finalTestScore = 0;
                this.unlocked = false;
                this.passwordUnlocked = false;
                this.testTimer = null;
                this.timeRemaining = 60 * 60;
                
                this.currentUnitOrder = {};
                this.currentFinalTestOrder = {};
                this.vocabularyOptionsCache = {};
                
                this.init();
            }

            init() {
                this.loadProgress();
                this.renderUnits();
                this.updateProgressDisplay();
                this.updateFinalTestStatus();
                this.updateFinalTestProgress();
            }

            loadProgress() {
                const saved = localStorage.getItem('superGoal3_progress');
                if (saved) {
                    const data = JSON.parse(saved);
                    this.units = data.units || JSON.parse(JSON.stringify(unitsData));
                    this.unitAnswers = data.unitAnswers || {};
                    this.finalTestAnswers = data.finalTestAnswers || {
                        grammar: {},
                        orthography: {},
                        vocabulary: {},
                        reading: {},
                        writing: ""
                    };
                    this.finalTestScore = data.finalTestScore || 0;
                    this.passwordUnlocked = data.passwordUnlocked || false;
                    
                    this.units.forEach(unit => {
                        const unitAnswers = this.unitAnswers[unit.id];
                        if (unitAnswers) {
                            const answeredCount = Object.keys(unitAnswers.answers || {}).length;
                            unit.questionsCompleted = Math.min(answeredCount, unit.questionsNeeded);
                        } else {
                            unit.questionsCompleted = 0;
                        }
                    });
                } else {
                    this.units = JSON.parse(JSON.stringify(unitsData));
                }
            }

            saveProgress() {
                const data = {
                    units: this.units,
                    unitAnswers: this.unitAnswers,
                    finalTestAnswers: this.finalTestAnswers,
                    finalTestScore: this.finalTestScore,
                    passwordUnlocked: this.passwordUnlocked
                };
                localStorage.setItem('superGoal3_progress', JSON.stringify(data));
            }

            shuffleArray(array) {
                const shuffled = [...array];
                for (let i = shuffled.length - 1; i > 0; i--) {
                    const j = Math.floor(Math.random() * (i + 1));
                    [shuffled[i], shuffled[j]] = [shuffled[j], shuffled[i]];
                }
                return shuffled;
            }

            getShuffledUnitQuestions(unitId) {
                const originalQuestions = unitQuestionsData[unitId] || [];
                const shuffledQuestions = this.shuffleArray([...originalQuestions]);
                
                const processedQuestions = shuffledQuestions.map(question => {
                    const processedQuestion = { ...question };
                    const originalOptions = [...question.options];
                    const originalCorrectAnswer = question.correctAnswer;
                    const originalCorrectText = originalOptions[originalCorrectAnswer];
                    
                    const shuffledOptions = this.shuffleArray([...originalOptions]);
                    processedQuestion.options = shuffledOptions;
                    
                    const newCorrectIndex = shuffledOptions.indexOf(originalCorrectText);
                    processedQuestion.correctAnswer = newCorrectIndex;
                    
                    return processedQuestion;
                });
                
                this.currentUnitOrder[unitId] = processedQuestions;
                
                return processedQuestions;
            }

            getShuffledFinalTestQuestions(section) {
                const originalQuestions = finalTestData[section] || [];
                const shuffledQuestions = this.shuffleArray([...originalQuestions]);
                
                const processedQuestions = shuffledQuestions.map(question => {
                    const processedQuestion = { ...question };
                    
                    if (question.options) {
                        const originalOptions = [...question.options];
                        const originalCorrectAnswer = question.correctAnswer;
                        const originalCorrectText = originalOptions[originalCorrectAnswer];
                        
                        const shuffledOptions = this.shuffleArray([...originalOptions]);
                        processedQuestion.options = shuffledOptions;
                        
                        const newCorrectIndex = shuffledOptions.indexOf(originalCorrectText);
                        processedQuestion.correctAnswer = newCorrectIndex;
                    }
                    
                    return processedQuestion;
                });
                
                if (!this.currentFinalTestOrder[section]) {
                    this.currentFinalTestOrder[section] = {};
                }
                
                processedQuestions.forEach((q, index) => {
                    this.currentFinalTestOrder[section][q.id] = { 
                        order: index,
                        correctAnswer: q.correctAnswer 
                    };
                });
                
                return processedQuestions;
            }

            getShuffledVocabularyItems() {
                const originalVocabulary = [...finalTestData.vocabulary];
                const shuffledVocabulary = this.shuffleArray(originalVocabulary);
                this.currentFinalTestOrder.vocabulary = shuffledVocabulary;
                return shuffledVocabulary;
            }

            getShuffledReadingQuestions() {
                const originalQuestions = [...finalTestData.reading];
                const shuffledQuestions = this.shuffleArray(originalQuestions);
                
                if (!this.currentFinalTestOrder.reading) {
                    this.currentFinalTestOrder.reading = {};
                }
                
                shuffledQuestions.forEach((q, index) => {
                    this.currentFinalTestOrder.reading[q.id] = { 
                        order: index,
                        correctAnswer: q.correctAnswer 
                    };
                });
                
                return shuffledQuestions;
            }

            // دالة جديدة لإنشاء قائمة مفردات عشوائية لكل عنصر
            getRandomVocabularyOptionsForItem(currentItemId) {
                if (this.vocabularyOptionsCache[currentItemId]) {
                    return this.vocabularyOptionsCache[currentItemId];
                }
                
                const allWords = [...finalTestData.vocabulary];
                const shuffledWords = this.shuffleArray(allWords);
                
                this.vocabularyOptionsCache[currentItemId] = shuffledWords;
                return shuffledWords;
            }

            renderUnits() {
                const grid = document.getElementById('unitsGrid');
                grid.innerHTML = '';
                
                this.units.forEach(unit => {
                    const progress = (unit.questionsCompleted / unit.questionsNeeded) * 100;
                    const isCompleted = unit.questionsCompleted >= unit.questionsNeeded;
                    
                    const card = document.createElement('div');
                    card.className = `unit-card ${isCompleted ? 'completed' : ''}`;
                    card.onclick = () => this.openUnitModal(unit.id);
                    
                    card.innerHTML = `
                        <div class="unit-color-bar" style="background: ${unit.color}"></div>
                        <div class="unit-header">
                            <div class="unit-info">
                                <h3>${unit.name}</h3>
                                <p>${unit.description}</p>
                            </div>
                            <div class="unit-icon" style="background: ${unit.color}">
                                <i class="${unit.icon}"></i>
                            </div>
                        </div>
                        <div class="unit-progress">
                            <div class="progress-label">
                                <span>Progress</span>
                                <span>${unit.questionsCompleted}/${unit.questionsNeeded}</span>
                            </div>
                            <div class="unit-progress-bar">
                                <div class="unit-progress-fill" style="width: ${progress}%; background: ${unit.color}"></div>
                            </div>
                        </div>
                        <div class="unit-actions">
                            <button class="btn ${isCompleted ? 'btn-success' : 'btn-primary'}" onclick="event.stopPropagation(); app.openUnitModal(${unit.id})">
                                <i class="fas fa-${isCompleted ? 'check-circle' : 'play-circle'}"></i>
                                ${isCompleted ? 'Completed' : 'Start Practice'}
                            </button>
                            <button class="btn btn-secondary" onclick="event.stopPropagation(); app.reviewUnit(${unit.id})">
                                <i class="fas fa-book-open"></i>
                                Review
                            </button>
                        </div>
                    `;
                    
                    grid.appendChild(card);
                });
            }

            updateProgressDisplay() {
                let totalCompleted = 0;
                let totalNeeded = 0;
                let completedUnits = 0;
                let totalQuestionsAnswered = 0;
                let totalQuestionsNeeded = 0;
                
                this.units.forEach(unit => {
                    totalCompleted += unit.questionsCompleted;
                    totalNeeded += unit.questionsNeeded;
                    totalQuestionsAnswered += unit.questionsCompleted;
                    totalQuestionsNeeded += unit.questionsNeeded;
                    
                    if (unit.questionsCompleted >= unit.questionsNeeded) {
                        completedUnits++;
                    }
                });
                
                const progress = Math.round((totalCompleted / totalNeeded) * 100);
                document.getElementById('overallProgress').textContent = `${progress}%`;
                document.getElementById('progressBar').style.width = `${progress}%`;
                
                document.getElementById('completedUnits').textContent = `${completedUnits}/6 units completed`;
                document.getElementById('totalQuestions').textContent = `${totalQuestionsAnswered}/${totalQuestionsNeeded} questions answered`;
            }

            updateFinalTestStatus() {
                const allCompleted = this.units.every(unit => unit.questionsCompleted >= unit.questionsNeeded);
                const finalTestCard = document.getElementById('finalTestCard');
                const startButton = document.getElementById('startFinalTestBtn');
                const badge = document.getElementById('testBadge');
                
                if (allCompleted || this.passwordUnlocked) {
                    finalTestCard.classList.remove('locked');
                    startButton.disabled = false;
                    badge.innerHTML = '<i class="fas fa-unlock"></i><span>Unlocked</span>';
                    badge.style.background = 'linear-gradient(135deg, var(--secondary) 0%, #34d399 100%)';
                    this.unlocked = true;
                } else {
                    finalTestCard.classList.add('locked');
                    startButton.disabled = true;
                    badge.innerHTML = '<i class="fas fa-lock"></i><span>Locked</span>';
                    badge.style.background = 'linear-gradient(135deg, var(--final-test-color) 0%, #ec4899 100%)';
                    this.unlocked = false;
                }
            }

            updateFinalTestProgress() {
                let totalAnswered = 0;
                let totalQuestions = 0;
                
                totalAnswered += Object.keys(this.finalTestAnswers.grammar).length;
                totalQuestions += finalTestData.grammar.length;
                
                totalAnswered += Object.keys(this.finalTestAnswers.orthography).length;
                totalQuestions += finalTestData.orthography.length;
                
                totalAnswered += Object.keys(this.finalTestAnswers.vocabulary).length;
                totalQuestions += finalTestData.vocabulary.length;
                
                totalAnswered += Object.keys(this.finalTestAnswers.reading).length;
                totalQuestions += finalTestData.reading.length;
                
                if (this.finalTestAnswers.writing && this.finalTestAnswers.writing.trim().length > 0) {
                    totalAnswered += 1;
                }
                totalQuestions += 1;
                
                const testProgress = Math.round((totalAnswered / totalQuestions) * 100);
                
                document.getElementById('testQuestionsAnswered').textContent = totalAnswered;
                document.getElementById('testProgress').textContent = `${testProgress}%`;
                
                const testProgressText = document.getElementById('testProgressText');
                if (testProgressText) {
                    testProgressText.textContent = `${totalAnswered}/${totalQuestions} questions answered`;
                }
            }

            openUnitModal(unitId) {
                const unit = this.units.find(u => u.id === unitId);
                if (!unit) return;
                
                this.currentUnit = unit;
                
                document.getElementById('unitModalTitle').textContent = unit.name;
                document.getElementById('unitModalDesc').textContent = unit.description;
                
                this.renderUnitQuestions(unit);
                document.getElementById('unitModal').classList.add('active');
                
                setTimeout(() => {
                    document.querySelector('.modal-body').scrollTop = 0;
                }, 100);
            }

            closeUnitModal() {
                document.getElementById('unitModal').classList.remove('active');
                this.saveProgress();
                this.renderUnits();
                this.updateProgressDisplay();
                this.updateFinalTestStatus();
            }

            renderUnitQuestions(unit) {
                const container = document.getElementById('unitQuestionsContainer');
                container.innerHTML = '';
                
                const questions = this.getShuffledUnitQuestions(unit.id);
                const answeredCount = Object.keys(this.unitAnswers[unit.id]?.answers || {}).length;
                
                document.getElementById('unitProgressText').textContent = `${answeredCount}/${unit.questionsNeeded} questions answered`;
                
                questions.forEach((question, index) => {
                    const isAnswered = this.unitAnswers[unit.id]?.answers?.[question.id] !== undefined;
                    const selectedAnswer = isAnswered ? this.unitAnswers[unit.id].answers[question.id] : null;
                    
                    let isCorrect = false;
                    if (isAnswered && selectedAnswer !== null) {
                        const originalCorrectText = unitQuestionsData[unit.id]?.find(q => q.id === question.id)?.options[unitQuestionsData[unit.id]?.find(q => q.id === question.id)?.correctAnswer];
                        const selectedText = question.options[selectedAnswer];
                        isCorrect = selectedText === originalCorrectText;
                    }
                    
                    const questionCard = document.createElement('div');
                    questionCard.className = `unit-question-card ${isAnswered ? 'answered' : ''} ${isCorrect ? 'correct' : isAnswered ? 'incorrect' : ''}`;
                    questionCard.id = `unit-question-${unit.id}-${question.id}`;
                    
                    let questionType = "Grammar";
                    if (index === 2 || index === 3) questionType = "Vocabulary";
                    if (index === 4) questionType = "Form / Meaning / Function";
                    
                    questionCard.innerHTML = `
                        <div class="question-header">
                            <div class="question-number">${index + 1}</div>
                            <div style="flex: 1;">
                                <div class="question-text">${question.question}</div>
                                <div class="question-type">${questionType}</div>
                            </div>
                        </div>
                        <div class="options-grid">
                            ${question.options.map((opt, optIndex) => {
                                let optionClass = 'option';
                                if (isAnswered) {
                                    optionClass += ' answered';
                                    if (optIndex === question.correctAnswer) optionClass += ' correct';
                                    if (selectedAnswer === optIndex && optIndex !== question.correctAnswer) optionClass += ' incorrect';
                                    if (selectedAnswer === optIndex) optionClass += ' selected';
                                }
                                
                                return `
                                    <div class="${optionClass}" 
                                         onclick="app.selectUnitAnswer(${unit.id}, ${question.id}, ${optIndex})"
                                         data-option="${optIndex}">
                                        <div class="option-text">${opt}</div>
                                    </div>
                                `;
                            }).join('')}
                        </div>
                        ${isAnswered ? this.createFeedbackHTML(question, isCorrect) : ''}
                    `;
                    
                    container.appendChild(questionCard);
                });
            }

            createFeedbackHTML(question, isCorrect) {
                return `
                    <div class="feedback-container">
                        <div class="feedback-header">
                            <div class="feedback-icon ${isCorrect ? 'correct' : 'incorrect'}">
                                ${isCorrect ? '✓' : '✗'}
                            </div>
                            <div class="feedback-title">
                                <strong>${isCorrect ? 'Correct Answer!' : 'Wrong Answer!'}</strong>
                            </div>
                        </div>
                        <div class="feedback-section">
                            <div class="feedback-section-title">
                                <i class="fas fa-info-circle"></i>
                                <span>Explanation</span>
                            </div>
                            <div class="feedback-section-content">
                                ${isCorrect ? question.explanation.correct : question.explanation.wrong}
                            </div>
                        </div>
                        <div class="feedback-section">
                            <div class="feedback-section-title">
                                <i class="fas fa-book"></i>
                                <span>Grammar Rule</span>
                            </div>
                            <div class="feedback-section-content">
                                ${question.explanation.grammar}
                            </div>
                        </div>
                        <div class="feedback-section">
                            <div class="feedback-section-title">
                                <i class="fas fa-language"></i>
                                <span>Example</span>
                            </div>
                            <div class="feedback-section-content">
                                ${question.explanation.example}
                            </div>
                        </div>
                    </div>
                `;
            }

            selectUnitAnswer(unitId, questionId, optionIndex) {
                const unit = this.units.find(u => u.id === unitId);
                if (!unit || this.unitAnswers[unitId]?.answers?.[questionId] !== undefined) {
                    return;
                }
                
                if (!this.unitAnswers[unitId]) {
                    this.unitAnswers[unitId] = { answers: {}, completed: 0 };
                }
                
                this.unitAnswers[unitId].answers[questionId] = optionIndex;
                
                const answeredCount = Object.keys(this.unitAnswers[unitId].answers).length;
                this.unitAnswers[unitId].completed = answeredCount;
                
                unit.questionsCompleted = Math.min(answeredCount, unit.questionsNeeded);
                
                const questionCard = document.getElementById(`unit-question-${unitId}-${questionId}`);
                if (questionCard) {
                    const currentQuestion = this.currentUnitOrder[unitId]?.find(q => q.id === questionId);
                    if (!currentQuestion) return;
                    
                    const isCorrect = optionIndex === currentQuestion.correctAnswer;
                    
                    questionCard.className = `unit-question-card answered ${isCorrect ? 'correct' : 'incorrect'}`;
                    
                    const options = questionCard.querySelectorAll('.option');
                    options.forEach((opt, optIndex) => {
                        opt.className = 'option answered';
                        if (optIndex === currentQuestion.correctAnswer) opt.classList.add('correct');
                        if (optIndex === optionIndex && optIndex !== currentQuestion.correctAnswer) opt.classList.add('incorrect');
                        if (optIndex === optionIndex) opt.classList.add('selected');
                    });
                    
                    const existingFeedback = questionCard.querySelector('.feedback-container');
                    if (existingFeedback) {
                        existingFeedback.remove();
                    }
                    
                    const feedbackHTML = this.createFeedbackHTML(currentQuestion, isCorrect);
                    questionCard.insertAdjacentHTML('beforeend', feedbackHTML);
                }
                
                document.getElementById('unitProgressText').textContent = `${answeredCount}/${unit.questionsNeeded} questions answered`;
                
                this.saveProgress();
                this.updateProgressDisplay();
            }

            checkAllQuestions() {
                const unitId = this.currentUnit.id;
                const answeredCount = Object.keys(this.unitAnswers[unitId]?.answers || {}).length;
                
                if (answeredCount >= this.currentUnit.questionsNeeded) {
                    this.closeUnitModal();
                } else {
                    alert(`You need to answer ${this.currentUnit.questionsNeeded - answeredCount} more questions before completing.`);
                }
            }

            startFinalTest() {
                if (!this.unlocked) {
                    alert('You must complete all units first!');
                    return;
                }
                
                document.getElementById('finalTestModal').classList.add('active');
                this.renderFinalTest();
                this.startTestTimer();
                this.updateFinalTestProgress();
            }

            closeFinalTestModal() {
                document.getElementById('finalTestModal').classList.remove('active');
                this.stopTestTimer();
            }

            renderFinalTest() {
                const container = document.getElementById('finalTestContent');
                container.innerHTML = '';
                
                // Grammar Section
                const grammarSection = this.createTestSection(
                    "Grammar",
                    "fas fa-language",
                    "#4361ee",
                    "9 points"
                );
                
                const grammarQuestions = this.getShuffledFinalTestQuestions('grammar');
                
                grammarQuestions.forEach((question, index) => {
                    const isAnswered = this.finalTestAnswers.grammar[question.id] !== undefined;
                    const selectedAnswer = isAnswered ? this.finalTestAnswers.grammar[question.id] : null;
                    const isCorrect = isAnswered && selectedAnswer === question.correctAnswer;
                    
                    const questionElement = document.createElement('div');
                    questionElement.className = `unit-question-card ${isAnswered ? 'answered' : ''} ${isCorrect ? 'correct' : isAnswered && !isCorrect ? 'incorrect' : ''}`;
                    questionElement.id = `grammar-question-${question.id}`;
                    questionElement.innerHTML = `
                        <div class="question-header">
                            <div class="question-marker"></div>
                            <div style="flex: 1;">
                                <div class="question-text">${question.question}</div>
                                <div class="question-type">Choose the correct answer</div>
                            </div>
                        </div>
                        <div class="options-grid">
                            ${question.options.map((opt, optIndex) => {
                                let optionClass = 'option';
                                if (isAnswered) {
                                    optionClass += ' answered';
                                    if (optIndex === question.correctAnswer) optionClass += ' correct';
                                    if (selectedAnswer === optIndex && optIndex !== question.correctAnswer) optionClass += ' incorrect';
                                    if (selectedAnswer === optIndex) optionClass += ' selected';
                                }
                                
                                return `
                                    <div class="${optionClass}" 
                                         onclick="app.selectFinalTestAnswer('grammar', ${question.id}, ${optIndex})"
                                         data-option="${optIndex}">
                                        <div class="option-text">${opt}</div>
                                    </div>
                                `;
                            }).join('')}
                        </div>
                        ${isAnswered ? this.createFinalTestFeedbackHTML(question, isCorrect) : ''}
                    `;
                    grammarSection.appendChild(questionElement);
                });
                
                container.appendChild(grammarSection);
                
                // Orthography Section
                const orthographySection = this.createTestSection(
                    "Orthography",
                    "fas fa-spell-check",
                    "#ffd166",
                    "5 points"
                );
                
                const orthographyQuestions = this.getShuffledFinalTestQuestions('orthography');
                
                orthographyQuestions.forEach((question, index) => {
                    const isAnswered = this.finalTestAnswers.orthography[question.id] !== undefined;
                    const selectedAnswer = isAnswered ? this.finalTestAnswers.orthography[question.id] : null;
                    const isCorrect = isAnswered && selectedAnswer === question.correctAnswer;
                    
                    const questionElement = document.createElement('div');
                    questionElement.className = `unit-question-card ${isAnswered ? 'answered' : ''} ${isCorrect ? 'correct' : isAnswered && !isCorrect ? 'incorrect' : ''}`;
                    questionElement.id = `orthography-question-${question.id}`;
                    questionElement.innerHTML = `
                        <div class="question-header">
                            <div class="question-marker-dash-alt"></div>
                            <div style="flex: 1;">
                                <div class="question-text">${question.question}</div>
                                <div class="question-type">Choose the correct letter to complete the word</div>
                            </div>
                        </div>
                        <div class="options-grid">
                            ${question.options.map((opt, optIndex) => {
                                let optionClass = 'option';
                                if (isAnswered) {
                                    optionClass += ' answered';
                                    if (optIndex === question.correctAnswer) optionClass += ' correct';
                                    if (selectedAnswer === optIndex && optIndex !== question.correctAnswer) optionClass += ' incorrect';
                                    if (selectedAnswer === optIndex) optionClass += ' selected';
                                }
                                
                                return `
                                    <div class="${optionClass}" 
                                         onclick="app.selectFinalTestAnswer('orthography', ${question.id}, ${optIndex})"
                                         data-option="${optIndex}">
                                        <div class="option-text">${opt}</div>
                                    </div>
                                `;
                            }).join('')}
                        </div>
                        ${isAnswered ? this.createFinalTestFeedbackHTML(question, isCorrect) : ''}
                    `;
                    orthographySection.appendChild(questionElement);
                });
                
                container.appendChild(orthographySection);
                
                // Vocabulary Section
                const vocabularySection = this.createTestSection(
                    "Vocabulary",
                    "fas fa-book",
                    "#06d6a0",
                    "9 points"
                );
                
                const vocabularyContent = document.createElement('div');
                vocabularyContent.className = 'vocabulary-section';
                vocabularyContent.innerHTML = `
                    <div class="writing-instruction">
                        <i class="fas fa-info-circle"></i>
                        <strong>Instructions:</strong> Choose the appropriate word for each picture from the dropdown list. Your answer will be automatically corrected.
                    </div>
                `;
                
                vocabularySection.appendChild(vocabularyContent);
                
                const gridContainer = document.createElement('div');
                gridContainer.id = 'vocabularyGridFinalTest';
                gridContainer.className = 'vocabulary-grid';
                vocabularySection.appendChild(gridContainer);
                
                const controlsContainer = document.createElement('div');
                controlsContainer.className = 'vocab-stats-container';
                controlsContainer.innerHTML = `
                    <div class="vocab-stats">
                        <div class="vocab-stat-item">
                            <div class="vocab-stat-number" id="vocabAnsweredCount">0</div>
                            <div class="vocab-stat-label">Answered</div>
                        </div>
                        <div class="vocab-stat-item">
                            <div class="vocab-stat-number" id="vocabCorrectCount">0</div>
                            <div class="vocab-stat-label">Correct Answers</div>
                        </div>
                        <div class="vocab-stat-item">
                            <div class="vocab-stat-number" id="vocabIncorrectCount">0</div>
                            <div class="vocab-stat-label">Wrong Answers</div>
                        </div>
                    </div>
                    
                    <div class="vocab-buttons">
                        <button class="vocab-btn vocab-btn-check" onclick="app.checkAllVocabularyAnswers()">
                            <i class="fas fa-check-circle"></i>
                            Check All
                        </button>
                        <button class="vocab-btn vocab-btn-show" onclick="app.showAllCorrectVocabularyAnswers()">
                            <i class="fas fa-eye"></i>
                            Show Correct Answers
                        </button>
                        <button class="vocab-btn vocab-btn-reset" onclick="app.resetVocabularyAnswers()">
                            <i class="fas fa-redo"></i>
                            Try Again
                        </button>
                    </div>
                `;
                vocabularySection.appendChild(controlsContainer);
                
                container.appendChild(vocabularySection);
                
                // توليد عناصر المفردات
                this.generateVocabularyItems();
                
                // Reading Section - مع الخلط
                const readingSection = this.createTestSection(
                    "Reading",
                    "fas fa-book-reader",
                    "#118ab2",
                    "9 points"
                );
                
                const readingText = document.createElement('div');
                readingText.className = 'writing-instruction';
                readingText.innerHTML = `
                    <h4 style="font-size: 1rem;">Read the following paragraph:</h4>
                    <p style="margin-top: 0.8rem; line-height: 1.5; font-size: 0.9rem;">
                        King Salman bin Abdulaziz was born in Riyadh. He studied religion, science, and the Holy Qur'an at the Princes' School. 
                        He became King of Saudi Arabia in 2015. He helped Riyadh grow from a small town into a major modern city. 
                        He also supported humanitarian and cultural projects inside and outside the Kingdom.
                    </p>
                    <p style="margin-top: 0.8rem; font-weight: 600; font-size: 0.9rem;">Write T for true statement or F for false statement:</p>
                `;
                readingSection.appendChild(readingText);
                
                const readingQuestions = document.createElement('div');
                readingQuestions.className = 'true-false-container';
                
                const readingQuestionsShuffled = this.getShuffledReadingQuestions();
                
                readingQuestionsShuffled.forEach((question, index) => {
                    const isAnswered = this.finalTestAnswers.reading[question.id] !== undefined;
                    const selectedAnswer = isAnswered ? this.finalTestAnswers.reading[question.id] : null;
                    const isCorrect = isAnswered && selectedAnswer === question.correctAnswer;
                    
                    const questionElement = document.createElement('div');
                    questionElement.className = `true-false-question ${isAnswered ? 'answered' : ''} ${isCorrect ? 'correct' : isAnswered && !isCorrect ? 'incorrect' : ''}`;
                    questionElement.id = `reading-question-${question.id}`;
                    questionElement.setAttribute('data-question-id', question.id);
                    
                    questionElement.innerHTML = `
                        <div style="display: flex; align-items: flex-start; gap: 0.6rem;">
                            <div class="reading-marker"></div>
                            <div style="flex: 1;">
                                <div class="question-text" style="font-size: 0.9rem;">${question.question}</div>
                                <div class="tf-options">
                                    <div class="tf-option ${isAnswered && selectedAnswer === true ? (isCorrect ? 'correct' : 'incorrect') : ''} ${isAnswered && selectedAnswer === true ? 'selected' : ''}" 
                                         data-value="true">
                                        T (True)
                                    </div>
                                    <div class="tf-option ${isAnswered && selectedAnswer === false ? (isCorrect ? 'correct' : 'incorrect') : ''} ${isAnswered && selectedAnswer === false ? 'selected' : ''}" 
                                         data-value="false">
                                        F (False)
                                    </div>
                                </div>
                            </div>
                        </div>
                        ${isAnswered ? `
                            <div class="reading-feedback" style="border-left-color: ${isCorrect ? 'var(--secondary)' : 'var(--error)'}">
                                <div style="display: flex; align-items: center; gap: 0.4rem; margin-bottom: 0.3rem;">
                                    <div style="width: 22px; height: 22px; border-radius: 50%; background: ${isCorrect ? 'var(--secondary)' : 'var(--error)'}; color: white; display: flex; align-items: center; justify-content: center; font-size: 0.8rem;">
                                        ${isCorrect ? '✓' : '✗'}
                                    </div>
                                    <strong style="font-size: 0.9rem;">${isCorrect ? 'Correct Answer!' : 'Wrong Answer!'}</strong>
                                </div>
                                <div style="font-size: 0.85rem;">${question.explanation}</div>
                            </div>
                        ` : ''}
                    `;
                    readingQuestions.appendChild(questionElement);
                });
                
                readingSection.appendChild(readingQuestions);
                container.appendChild(readingSection);
                
                // إضافة event listeners لخيارات True/False
                setTimeout(() => {
                    this.setupReadingEventListeners();
                }, 100);
                
                // Writing Section
                const writingSection = this.createTestSection(
                    "Guided Composition",
                    "fas fa-edit",
                    "#9d4edd",
                    "8 points"
                );
                
                const writingContainer = document.createElement('div');
                writingContainer.className = 'writing-container';
                writingContainer.innerHTML = `
                    <div class="writing-instruction">
                        <h4 style="font-size: 1rem;">Guided Writing:</h4>
                        <p style="font-size: 0.9rem;">Write a coherent paragraph of 3-5 sentences using 8 words from the following list:</p>
                        <div class="words-list">
                            ${finalTestData.writing.words.map(word => 
                                `<span class="word-tag">${word}</span>`
                            ).join('')}
                        </div>
                        <p style="font-size: 0.9rem;"><strong>Hint:</strong> Try to write about a topic like: sports, health, or daily life.</p>
                        
                        <div class="sample-answers">
                            <h5 style="color: var(--primary); margin-bottom: 0.6rem; display: flex; align-items: center; gap: 0.4rem; font-size: 0.9rem;">
                                <i class="fas fa-lightbulb"></i>
                                Ready Samples (you can use one or get inspiration from them)
                            </h5>
                            ${writingSamples.map((sample, idx) => `
                                <div class="sample-answer" onclick="app.useWritingSample(${idx})">
                                    <h5><i class="fas fa-copy"></i> ${sample.title}</h5>
                                    <div class="sample-answer-content">${sample.content}</div>
                                    <div class="used-words">Used ${sample.wordCount} words from the list</div>
                                </div>
                            `).join('')}
                        </div>
                    </div>
                    <textarea class="writing-textarea" 
                              placeholder="Write your paragraph here... (3-5 sentences using at least 8 words from the list above)"
                              oninput="app.updateWritingAnswer(this.value)">${this.finalTestAnswers.writing || ''}</textarea>
                    <div style="margin-top: 0.8rem; color: var(--text-secondary); font-size: 0.8rem;">
                        <i class="fas fa-info-circle"></i> Your answer will be evaluated based on: use of required words, coherence between sentences, grammar, and clarity of ideas.
                    </div>
                `;
                
                writingSection.appendChild(writingContainer);
                container.appendChild(writingSection);
                
                this.updateFinalTestProgress();
                
                setTimeout(() => {
                    const modalBody = document.querySelector('.modal-body');
                    if (modalBody) {
                        modalBody.scrollTop = 0;
                    }
                }, 100);
            }

            setupReadingEventListeners() {
                const tfOptions = document.querySelectorAll('.tf-option:not(.correct):not(.incorrect)');
                tfOptions.forEach(option => {
                    option.addEventListener('click', (e) => {
                        e.stopPropagation();
                        const questionElement = option.closest('.true-false-question');
                        if (questionElement) {
                            const questionId = parseInt(questionElement.getAttribute('data-question-id'));
                            const value = option.getAttribute('data-value') === 'true';
                            this.selectTrueFalseAnswer(questionId, value);
                        }
                    });
                });
            }

            createTestSection(title, icon, color, score) {
                const section = document.createElement('div');
                section.className = 'test-section';
                
                const header = document.createElement('div');
                header.className = 'section-header';
                header.innerHTML = `
                    <div class="section-icon" style="background: ${color};">
                        <i class="${icon}"></i>
                    </div>
                    <h3 class="section-title">${title}</h3>
                    <span class="section-score">${score}</span>
                `;
                
                section.appendChild(header);
                return section;
            }

            createFinalTestFeedbackHTML(question, isCorrect) {
                return `
                    <div class="feedback-container">
                        <div class="feedback-header">
                            <div class="feedback-icon ${isCorrect ? 'correct' : 'incorrect'}">
                                ${isCorrect ? '✓' : '✗'}
                            </div>
                            <div class="feedback-title">
                                <strong>${isCorrect ? 'Correct Answer!' : 'Wrong Answer!'}</strong>
                            </div>
                        </div>
                        <div class="feedback-section">
                            <div class="feedback-section-title">
                                <i class="fas fa-info-circle"></i>
                                <span>Explanation</span>
                            </div>
                            <div class="feedback-section-content">
                                ${question.explanation}
                            </div>
                        </div>
                    </div>
                `;
            }

            selectFinalTestAnswer(section, questionId, optionIndex) {
                if (this.finalTestAnswers[section][questionId] !== undefined) {
                    return;
                }
                
                this.finalTestAnswers[section][questionId] = optionIndex;
                this.saveProgress();
                
                let question;
                const sectionQuestions = this.currentFinalTestOrder[section];
                
                if (Array.isArray(sectionQuestions)) {
                    question = sectionQuestions.find(q => q.id === questionId);
                } else if (sectionQuestions && sectionQuestions[questionId]) {
                    const allQuestions = finalTestData[section];
                    question = allQuestions.find(q => q.id === questionId);
                    
                    if (question && this.currentFinalTestOrder[section][questionId]) {
                        const currentOrder = this.currentFinalTestOrder[section][questionId];
                        question.correctAnswer = currentOrder.correctAnswer;
                    }
                }
                
                if (!question) return;
                
                const isCorrect = optionIndex === question.correctAnswer;
                
                const questionElementId = `${section}-question-${questionId}`;
                const targetQuestion = document.getElementById(questionElementId);
                
                if (targetQuestion) {
                    targetQuestion.className = `unit-question-card answered ${isCorrect ? 'correct' : 'incorrect'}`;
                    
                    const options = targetQuestion.querySelectorAll('.option');
                    options.forEach((opt, idx) => {
                        opt.className = 'option answered';
                        if (idx === question.correctAnswer) opt.classList.add('correct');
                        if (idx === optionIndex && idx !== question.correctAnswer) opt.classList.add('incorrect');
                        if (idx === optionIndex) opt.classList.add('selected');
                    });
                    
                    const existingFeedback = targetQuestion.querySelector('.feedback-container');
                    if (existingFeedback) {
                        existingFeedback.remove();
                    }
                    
                    const feedbackHTML = this.createFinalTestFeedbackHTML(question, isCorrect);
                    targetQuestion.insertAdjacentHTML('beforeend', feedbackHTML);
                }
                
                this.updateFinalTestProgress();
            }

            generateVocabularyItems() {
                const container = document.getElementById('vocabularyGridFinalTest');
                if (!container) return;
                
                container.innerHTML = '';
                this.vocabularyOptionsCache = {}; // إعادة تعيين الكاش
                
                const shuffledVocabulary = this.getShuffledVocabularyItems();
                
                shuffledVocabulary.forEach((wordItem, index) => {
                    const userAnswer = this.finalTestAnswers.vocabulary[wordItem.id];
                    const isCorrect = userAnswer === wordItem.correctMatch;
                    const hasAnswer = userAnswer !== undefined;
                    
                    const imgItem = vocabularyImages.find(img => img.letter === wordItem.correctMatch);
                    
                    if (!imgItem) return;
                    
                    // الحصول على قائمة خيارات عشوائية لهذا العنصر
                    const randomOptions = this.getRandomVocabularyOptionsForItem(wordItem.id);
                    
                    const item = document.createElement('div');
                    item.className = `vocab-item ${hasAnswer ? (isCorrect ? 'correct' : 'incorrect') : ''}`;
                    item.id = `vocab-item-final-${wordItem.id}`;
                    
                    item.innerHTML = `
                        <div class="image-container">
                            <div class="image-card">
                                <div class="image-letter">${imgItem.letter}</div>
                                <img src="${imgItem.img}" alt="Image ${imgItem.letter}" 
                                     onerror="this.src='https://via.placeholder.com/80x60?text=${imgItem.letter}'">
                            </div>
                        </div>
                        
                        <div class="word-container">
                            <div class="answer-container">
                                <select class="vocab-select" onchange="app.selectVocabularyAnswerFinal(${wordItem.id}, this.value)" 
                                        id="vocab-select-final-${wordItem.id}"
                                        ${hasAnswer && !isCorrect ? 'disabled' : ''}>
                                    <option value="">Choose the appropriate word</option>
                                    ${randomOptions.map((word, idx) => 
                                        `<option value="${word.correctMatch}" ${userAnswer === word.correctMatch ? 'selected' : ''}>
                                            ${word.word}
                                        </option>`
                                    ).join('')}
                                </select>
                                
                                ${hasAnswer ? `
                                    <div class="feedback-icon-vocab ${isCorrect ? 'correct-icon-vocab' : 'incorrect-icon-vocab'}">
                                        ${isCorrect ? '✓' : '✗'}
                                    </div>
                                ` : ''}
                            </div>
                            
                            ${hasAnswer && !isCorrect ? `
                                <div class="correct-hint">
                                    <i class="fas fa-lightbulb"></i>
                                    Correct answer: ${wordItem.word}
                                </div>
                            ` : ''}
                        </div>
                    `;
                    
                    container.appendChild(item);
                });
                
                this.updateVocabularyStats();
            }

            selectVocabularyAnswerFinal(id, value) {
                const wordItem = finalTestData.vocabulary.find(item => item.id === id);
                if (!wordItem) return;
                
                this.finalTestAnswers.vocabulary[id] = value;
                const isCorrect = value === wordItem.correctMatch;
                
                const item = document.getElementById(`vocab-item-final-${id}`);
                const select = document.getElementById(`vocab-select-final-${id}`);
                
                item.className = `vocab-item ${isCorrect ? 'correct' : 'incorrect'}`;
                
                const feedbackContainer = item.querySelector('.answer-container');
                const existingFeedback = feedbackContainer.querySelector('.feedback-icon-vocab');
                if (existingFeedback) {
                    existingFeedback.remove();
                }
                
                const feedbackIcon = document.createElement('div');
                feedbackIcon.className = `feedback-icon-vocab ${isCorrect ? 'correct-icon-vocab' : 'incorrect-icon-vocab'}`;
                feedbackIcon.innerHTML = isCorrect ? '✓' : '✗';
                feedbackContainer.appendChild(feedbackIcon);
                
                const existingHint = item.querySelector('.correct-hint');
                if (!isCorrect) {
                    if (!existingHint) {
                        const hint = document.createElement('div');
                        hint.className = 'correct-hint';
                        hint.innerHTML = `<i class="fas fa-lightbulb"></i> Correct answer: ${wordItem.word}`;
                        item.querySelector('.word-container').appendChild(hint);
                    }
                    if (select) select.disabled = true;
                } else if (existingHint) {
                    existingHint.remove();
                }
                
                this.saveProgress();
                this.updateVocabularyStats();
                this.updateFinalTestProgress();
            }

            updateVocabularyStats() {
                const answered = Object.keys(this.finalTestAnswers.vocabulary)
                    .filter(k => this.finalTestAnswers.vocabulary[k]).length;
                const correct = finalTestData.vocabulary.filter(item => 
                    this.finalTestAnswers.vocabulary[item.id] === item.correctMatch
                ).length;
                const incorrect = finalTestData.vocabulary.filter(item => 
                    this.finalTestAnswers.vocabulary[item.id] && 
                    this.finalTestAnswers.vocabulary[item.id] !== item.correctMatch
                ).length;
                
                document.getElementById('vocabAnsweredCount').textContent = answered;
                document.getElementById('vocabCorrectCount').textContent = correct;
                document.getElementById('vocabIncorrectCount').textContent = incorrect;
            }

            checkAllVocabularyAnswers() {
                finalTestData.vocabulary.forEach(item => {
                    const select = document.getElementById(`vocab-select-final-${item.id}`);
                    if (select && select.value) {
                        this.selectVocabularyAnswerFinal(item.id, select.value);
                    }
                });
            }

            showAllCorrectVocabularyAnswers() {
                if (confirm('Do you want to show all correct answers? Selection will be disabled.')) {
                    finalTestData.vocabulary.forEach(item => {
                        const select = document.getElementById(`vocab-select-final-${item.id}`);
                        const itemElement = document.getElementById(`vocab-item-final-${item.id}`);
                        
                        if (select && itemElement) {
                            select.value = item.correctMatch;
                            this.finalTestAnswers.vocabulary[item.id] = item.correctMatch;
                            
                            itemElement.className = 'vocab-item correct';
                            select.disabled = true;
                            
                            const feedbackContainer = itemElement.querySelector('.answer-container');
                            const existingFeedback = feedbackContainer.querySelector('.feedback-icon-vocab');
                            if (existingFeedback) {
                                existingFeedback.remove();
                            }
                            
                            const feedbackIcon = document.createElement('div');
                            feedbackIcon.className = 'feedback-icon-vocab correct-icon-vocab';
                            feedbackIcon.innerHTML = '✓';
                            feedbackContainer.appendChild(feedbackIcon);
                            
                            const existingHint = itemElement.querySelector('.correct-hint');
                            if (existingHint) {
                                existingHint.remove();
                            }
                        }
                    });
                    
                    this.saveProgress();
                    this.updateVocabularyStats();
                    this.updateFinalTestProgress();
                }
            }

            resetVocabularyAnswers() {
                if (confirm('Do you want to reset all vocabulary answers?')) {
                    finalTestData.vocabulary.forEach(item => {
                        delete this.finalTestAnswers.vocabulary[item.id];
                    });
                    
                    this.vocabularyOptionsCache = {};
                    this.generateVocabularyItems();
                    this.saveProgress();
                    this.updateFinalTestProgress();
                }
            }

            selectTrueFalseAnswer(questionId, value) {
                if (this.finalTestAnswers.reading[questionId] !== undefined) {
                    return;
                }
                
                this.finalTestAnswers.reading[questionId] = value;
                this.saveProgress();
                
                const questionElement = document.getElementById(`reading-question-${questionId}`);
                if (!questionElement) return;
                
                const questionInfo = this.currentFinalTestOrder.reading?.[questionId];
                let question;
                if (questionInfo) {
                    question = finalTestData.reading.find(q => q.id === questionId);
                    if (question) {
                        question.correctAnswer = questionInfo.correctAnswer;
                    }
                } else {
                    question = finalTestData.reading.find(q => q.id === questionId);
                }
                
                if (!question) return;
                
                const isCorrect = value === question.correctAnswer;
                
                // تحديث واجهة المستخدم
                questionElement.className = `true-false-question answered ${isCorrect ? 'correct' : 'incorrect'}`;
                
                // تحديث الخيارات
                const trueOption = questionElement.querySelector('.tf-option[data-value="true"]');
                const falseOption = questionElement.querySelector('.tf-option[data-value="false"]');
                
                if (trueOption && falseOption) {
                    // إزالة جميع الفئات أولاً
                    trueOption.classList.remove('selected', 'correct', 'incorrect');
                    falseOption.classList.remove('selected', 'correct', 'incorrect');
                    
                    // تحديث الخيار المختار
                    if (value === true) {
                        trueOption.classList.add('selected');
                        if (isCorrect) {
                            trueOption.classList.add('correct');
                        } else {
                            trueOption.classList.add('incorrect');
                        }
                        // تلوين الخيار الصحيح
                        if (!isCorrect) {
                            falseOption.classList.add('correct');
                        }
                    } else {
                        falseOption.classList.add('selected');
                        if (isCorrect) {
                            falseOption.classList.add('correct');
                        } else {
                            falseOption.classList.add('incorrect');
                        }
                        // تلوين الخيار الصحيح
                        if (!isCorrect) {
                            trueOption.classList.add('correct');
                        }
                    }
                }
                
                // إزالة أي تعليقات سابقة
                const existingFeedback = questionElement.querySelector('.reading-feedback');
                if (existingFeedback) {
                    existingFeedback.remove();
                }
                
                // إضافة تعليق جديد
                const feedback = document.createElement('div');
                feedback.className = 'reading-feedback';
                feedback.style.borderLeftColor = isCorrect ? 'var(--secondary)' : 'var(--error)';
                feedback.innerHTML = `
                    <div style="display: flex; align-items: center; gap: 0.4rem; margin-bottom: 0.3rem;">
                        <div style="width: 22px; height: 22px; border-radius: 50%; background: ${isCorrect ? 'var(--secondary)' : 'var(--error)'}; color: white; display: flex; align-items: center; justify-content: center; font-size: 0.8rem;">
                            ${isCorrect ? '✓' : '✗'}
                        </div>
                        <strong style="font-size: 0.9rem;">${isCorrect ? 'Correct Answer!' : 'Wrong Answer!'}</strong>
                    </div>
                    <div style="font-size: 0.85rem;">${question.explanation}</div>
                `;
                
                questionElement.appendChild(feedback);
                
                // تحديث event listeners لمنع النقر مرة أخرى
                this.setupReadingEventListeners();
                
                this.updateFinalTestProgress();
            }

            useWritingSample(index) {
                if (index >= 0 && index < writingSamples.length) {
                    const sample = writingSamples[index];
                    const textarea = document.querySelector('.writing-textarea');
                    if (textarea) {
                        textarea.value = sample.content;
                        this.updateWritingAnswer(sample.content);
                        alert(`Used sample "${sample.title}". You can modify it as you want!`);
                    }
                }
            }

            updateWritingAnswer(value) {
                this.finalTestAnswers.writing = value;
                this.saveProgress();
                this.updateFinalTestProgress();
            }

            startTestTimer() {
                this.updateTimerDisplay();
                this.testTimer = setInterval(() => {
                    this.timeRemaining--;
                    this.updateTimerDisplay();
                    
                    if (this.timeRemaining <= 0) {
                        this.stopTestTimer();
                        alert('Test time is over!');
                        this.submitFinalTest();
                    }
                }, 1000);
            }

            stopTestTimer() {
                if (this.testTimer) {
                    clearInterval(this.testTimer);
                    this.testTimer = null;
                }
            }

            updateTimerDisplay() {
                const minutes = Math.floor(this.timeRemaining / 60);
                const seconds = this.timeRemaining % 60;
                document.getElementById('timeRemaining').textContent = 
                    `${minutes.toString().padStart(2, '0')}:${seconds.toString().padStart(2, '0')}`;
                
                if (this.timeRemaining < 300) {
                    document.getElementById('timeRemaining').parentElement.style.background = 'rgba(239, 71, 111, 0.2)';
                } else if (this.timeRemaining < 600) {
                    document.getElementById('timeRemaining').parentElement.style.background = 'rgba(255, 209, 102, 0.2)';
                }
            }

            submitFinalTest() {
                this.stopTestTimer();
                
                let totalScore = 0;
                let maxScore = 40;
                let details = [];
                
                let grammarScore = 0;
                finalTestData.grammar.forEach(q => {
                    if (this.finalTestAnswers.grammar[q.id] === q.correctAnswer) {
                        grammarScore++;
                    }
                });
                totalScore += grammarScore;
                details.push(`Grammar: ${grammarScore}/9`);
                
                let orthographyScore = 0;
                finalTestData.orthography.forEach(q => {
                    if (this.finalTestAnswers.orthography[q.id] === q.correctAnswer) {
                        orthographyScore++;
                    }
                });
                totalScore += orthographyScore;
                details.push(`Orthography: ${orthographyScore}/5`);
                
                let vocabularyScore = 0;
                finalTestData.vocabulary.forEach(item => {
                    if (this.finalTestAnswers.vocabulary[item.id] === item.correctMatch) {
                        vocabularyScore++;
                    }
                });
                totalScore += vocabularyScore;
                details.push(`Vocabulary: ${vocabularyScore}/9`);
                
                let readingScore = 0;
                finalTestData.reading.forEach(q => {
                    if (this.finalTestAnswers.reading[q.id] === q.correctAnswer) {
                        readingScore++;
                    }
                });
                totalScore += readingScore;
                details.push(`Reading: ${readingScore}/9`);
                
                let writingScore = 0;
                const writingAnswer = this.finalTestAnswers.writing || '';
                if (writingAnswer.trim().length > 0) {
                    const usedWords = finalTestData.writing.words.filter(word => 
                        writingAnswer.toLowerCase().includes(word.toLowerCase())
                    ).length;
                    
                    const sentenceCount = (writingAnswer.match(/[.!?]/g) || []).length;
                    
                    if (usedWords >= 8 && sentenceCount >= 3 && sentenceCount <= 5) {
                        writingScore = 8;
                    } else if (usedWords >= 6 && sentenceCount >= 2) {
                        writingScore = 6;
                    } else if (usedWords >= 4 && sentenceCount >= 1) {
                        writingScore = 4;
                    } else if (writingAnswer.trim().length > 20) {
                        writingScore = 2;
                    }
                }
                totalScore += writingScore;
                details.push(`Writing: ${writingScore}/8`);
                
                this.finalTestScore = totalScore;
                this.saveProgress();
                
                const percentage = Math.round((totalScore / maxScore) * 100);
                
                const resultHTML = `
                    <div style="text-align: center; padding: 1.2rem;">
                        <div style="background: ${percentage >= 60 ? 'linear-gradient(135deg, var(--secondary) 0%, #05c490 100%)' : 'linear-gradient(135deg, var(--error) 0%, #d43f8d 100%)'}; 
                            width: 80px; height: 80px; border-radius: 50%; display: flex; align-items: center; justify-content: center; margin: 0 auto 1.2rem;">
                            <i class="fas fa-${percentage >= 60 ? 'trophy' : 'graduation-cap'}" style="font-size: 2.2rem; color: white;"></i>
                        </div>
                        
                        <h3 style="color: var(--text-primary); margin-bottom: 0.8rem; font-size: 1.1rem;">Final Test Result</h3>
                        
                        <div style="background: white; border-radius: 12px; padding: 1.2rem; max-width: 500px; margin: 0 auto 1.2rem; box-shadow: var(--shadow);">
                            <div style="font-size: 2.2rem; font-weight: 800; color: ${percentage >= 60 ? 'var(--secondary)' : 'var(--error)'}; margin-bottom: 0.8rem;">
                                ${totalScore}/${maxScore}
                            </div>
                            <div style="font-size: 1.1rem; color: var(--text-primary); margin-bottom: 0.8rem;">
                                ${percentage}%
                            </div>
                            <div style="color: var(--text-secondary); margin-bottom: 1rem; font-size: 0.9rem;">
                                ${percentage >= 60 ? '✅ Pass - Well done!' : '⏳ Need more practice'}
                            </div>
                            
                            <div style="text-align: left; margin-top: 1.2rem; background: #f8f9fa; padding: 0.8rem; border-radius: 8px; font-size: 0.9rem;">
                                <div style="margin-bottom: 0.4rem; font-weight: 600;">Result Details:</div>
                                ${details.map(detail => `<div style="margin-bottom: 0.2rem;">${detail}</div>`).join('')}
                                <div style="margin-top: 0.8rem; padding-top: 0.8rem; border-top: 1px solid var(--border); font-weight: 600;">
                                    Total Score: ${totalScore}/40
                                </div>
                            </div>
                        </div>
                        
                        <button class="btn btn-primary" onclick="app.closeFinalTestModal()" style="padding: 0.8rem 1.5rem; font-size: 0.95rem;">
                            <i class="fas fa-check-circle"></i>
                            OK
                        </button>
                    </div>
                `;
                
                document.getElementById('finalTestContent').innerHTML = resultHTML;
            }

            showTestPreview() {
                const container = document.getElementById('finalTestContent');
                container.innerHTML = `
                    <div style="text-align: center; padding: 1.2rem;">
                        <div style="background: linear-gradient(135deg, var(--final-test-color) 0%, #7b2cbf 100%); width: 70px; height: 70px; border-radius: 50%; display: flex; align-items: center; justify-content: center; margin: 0 auto 1.2rem;">
                            <i class="fas fa-graduation-cap" style="font-size: 2rem; color: white;"></i>
                        </div>
                        
                        <h3 style="color: var(--text-primary); margin-bottom: 1rem; font-size: 1.1rem;">Final Test Preview</h3>
                        
                        <div style="max-width: 800px; margin: 0 auto 1.5rem; text-align: left; font-size: 0.9rem;">
                            <h4 style="color: var(--primary); margin-bottom: 0.8rem; border-bottom: 2px solid var(--primary); padding-bottom: 0.4rem; font-size: 1rem;">Test Structure:</h4>
                            
                            <div style="display: grid; grid-template-columns: 1fr; gap: 1rem; margin-top: 1.2rem;">
                                <div style="background: white; padding: 1rem; border-radius: 12px; border: 2px solid var(--primary); box-shadow: 0 4px 15px rgba(0,0,0,0.1); text-align: center;">
                                    <div style="display: flex; align-items: center; justify-content: center; gap: 0.6rem; margin-bottom: 0.8rem;">
                                        <div style="width: 34px; height: 34px; background: var(--primary); color: white; border-radius: 50%; display: flex; align-items: center; justify-content: center;">
                                            <i class="fas fa-language"></i>
                                        </div>
                                        <div style="text-align: left;">
                                            <div style="font-size: 1.4rem; font-weight: 800; color: var(--primary);">9</div>
                                            <div style="font-weight: 600; color: var(--text-primary); font-size: 0.85rem;">Grammar</div>
                                        </div>
                                    </div>
                                    <div style="color: var(--text-secondary); font-size: 0.8rem;">Choose the correct answer</div>
                                </div>
                                
                                <div style="background: white; padding: 1rem; border-radius: 12px; border: 2px solid var(--warning); box-shadow: 0 4px 15px rgba(0,0,0,0.1); text-align: center;">
                                    <div style="display: flex; align-items: center; justify-content: center; gap: 0.6rem; margin-bottom: 0.8rem;">
                                        <div style="width: 34px; height: 34px; background: var(--warning); color: white; border-radius: 50%; display: flex; align-items: center; justify-content: center;">
                                            <i class="fas fa-spell-check"></i>
                                        </div>
                                        <div style="text-align: left;">
                                            <div style="font-size: 1.4rem; font-weight: 800; color: var(--warning);">5</div>
                                            <div style="font-weight: 600; color: var(--text-primary); font-size: 0.85rem;">Orthography</div>
                                        </div>
                                    </div>
                                    <div style="color: var(--text-secondary); font-size: 0.8rem;">Choose the correct letter</div>
                                </div>
                                
                                <div style="background: white; padding: 1rem; border-radius: 12px; border: 2px solid var(--secondary); box-shadow: 0 4px 15px rgba(0,0,0,0.1); text-align: center;">
                                    <div style="display: flex; align-items: center; justify-content: center; gap: 0.6rem; margin-bottom: 0.8rem;">
                                        <div style="width: 34px; height: 34px; background: var(--secondary); color: white; border-radius: 50%; display: flex; align-items: center; justify-content: center;">
                                            <i class="fas fa-book"></i>
                                        </div>
                                        <div style="text-align: left;">
                                            <div style="font-size: 1.4rem; font-weight: 800; color: var(--secondary);">9</div>
                                            <div style="font-weight: 600; color: var(--text-primary); font-size: 0.85rem;">Vocabulary</div>
                                        </div>
                                    </div>
                                    <div style="color: var(--text-secondary); font-size: 0.8rem;">Choose the word that matches the picture</div>
                                </div>
                                
                                <div style="background: white; padding: 1rem; border-radius: 12px; border: 2px solid var(--info); box-shadow: 0 4px 15px rgba(0,0,0,0.1); text-align: center;">
                                    <div style="display: flex; align-items: center; justify-content: center; gap: 0.6rem; margin-bottom: 0.8rem;">
                                        <div style="width: 34px; height: 34px; background: var(--info); color: white; border-radius: 50%; display: flex; align-items: center; justify-content: center;">
                                            <i class="fas fa-book-reader"></i>
                                        </div>
                                        <div style="text-align: left;">
                                            <div style="font-size: 1.4rem; font-weight: 800; color: var(--info);">9</div>
                                            <div style="font-weight: 600; color: var(--text-primary); font-size: 0.85rem;">Reading</div>
                                        </div>
                                    </div>
                                    <div style="color: var(--text-secondary); font-size: 0.8rem;">True or False</div>
                                </div>
                                
                                <div style="background: white; padding: 1rem; border-radius: 12px; border: 2px solid var(--error); box-shadow: 0 4px 15px rgba(0,0,0,0.1); text-align: center;">
                                    <div style="display: flex; align-items: center; justify-content: center; gap: 0.6rem; margin-bottom: 0.8rem;">
                                        <div style="width: 34px; height: 34px; background: var(--error); color: white; border-radius: 50%; display: flex; align-items: center; justify-content: center;">
                                            <i class="fas fa-edit"></i>
                                        </div>
                                        <div style="text-align: left;">
                                            <div style="font-size: 1.4rem; font-weight: 800; color: var(--error);">8</div>
                                            <div style="font-weight: 600; color: var(--text-primary); font-size: 0.85rem;">Writing</div>
                                        </div>
                                    </div>
                                    <div style="color: var(--text-secondary); font-size: 0.8rem;">Write a short paragraph</div>
                                </div>
                            </div>
                            
                            <div style="margin-top: 1.5rem; padding: 1.2rem; background: linear-gradient(135deg, var(--final-test-color) 0%, #7b2cbf 100%); border-radius: 12px; color: white;">
                                <div style="display: flex; justify-content: space-around; flex-wrap: wrap; gap: 1.2rem;">
                                    <div style="text-align: center;">
                                        <div style="font-size: 1.8rem; font-weight: 800;">40</div>
                                        <div style="font-size: 0.8rem;">Total Questions</div>
                                    </div>
                                    <div style="text-align: center;">
                                        <div style="font-size: 1.8rem; font-weight: 800;">60</div>
                                        <div style="font-size: 0.8rem;">Minutes (Time)</div>
                                    </div>
                                    <div style="text-align: center;">
                                        <div style="font-size: 1.8rem; font-weight: 800;">100</div>
                                        <div style="font-size: 0.8rem;">Full Score</div>
                                    </div>
                                </div>
                            </div>
                        </div>
                        
                        <div style="margin-top: 1.5rem;">
                            <button class="btn btn-primary" onclick="app.startFinalTest()" style="padding: 0.8rem 1.5rem; font-size: 0.95rem; margin: 0 0.4rem 0.4rem;">
                                <i class="fas fa-play-circle"></i>
                                Start Test Now
                            </button>
                            <button class="btn btn-secondary" onclick="app.closeFinalTestModal()" style="padding: 0.8rem 1.2rem; font-size: 0.95rem;">
                                <i class="fas fa-times-circle"></i>
                                Close
                            </button>
                        </div>
                    </div>
                `;
                
                document.getElementById('finalTestModal').classList.add('active');
            }

            showPasswordAccess() {
                const passwordAccess = document.getElementById('passwordAccess');
                passwordAccess.style.display = 'block';
                document.getElementById('passwordMessage').style.display = 'none';
            }

            checkPassword() {
                const passwordInput = document.getElementById('passwordInput');
                const passwordMessage = document.getElementById('passwordMessage');
                
                if (passwordInput.value === '7245') {
                    this.passwordUnlocked = true;
                    this.saveProgress();
                    this.updateFinalTestStatus();
                    
                    passwordMessage.textContent = '✅ Final test unlocked successfully!';
                    passwordMessage.style.color = 'var(--secondary)';
                    passwordMessage.style.display = 'block';
                    
                    setTimeout(() => {
                        document.getElementById('passwordAccess').style.display = 'none';
                        passwordInput.value = '';
                    }, 2000);
                } else {
                    passwordMessage.textContent = '❌ Wrong password!';
                    passwordMessage.style.color = 'var(--error)';
                    passwordMessage.style.display = 'block';
                    passwordInput.value = '';
                }
            }

            reviewUnit(unitId) {
                const unit = this.units.find(u => u.id === unitId);
                if (!unit) return;
                
                const answeredCount = Object.keys(this.unitAnswers[unit.id]?.answers || {}).length;
                const correctCount = answeredCount > 0 ? 
                    Object.keys(this.unitAnswers[unit.id]?.answers || {}).filter(qId => {
                        const question = unitQuestionsData[unit.id].find(q => q.id == qId);
                        return question && this.unitAnswers[unit.id].answers[qId] === question.correctAnswer;
                    }).length : 0;
                
                alert(`Review ${unit.name}\n\n` +
                      `Questions Answered: ${answeredCount}/${unit.questionsNeeded}\n` +
                      `Correct Answers: ${correctCount}/${answeredCount}\n` +
                      `Accuracy: ${answeredCount > 0 ? Math.round((correctCount / answeredCount) * 100) : 0}%\n\n` +
                      `${unit.questionsCompleted >= unit.questionsNeeded ? 
                        '✅ Unit Completed!' : 
                        `⏳ You need to complete ${unit.questionsNeeded - unit.questionsCompleted} more questions`}`);
            }

            resetProgress() {
                if (confirm('Are you sure you want to reset progress? All answers and progress will be deleted.')) {
                    localStorage.removeItem('superGoal3_progress');
                    location.reload();
                }
            }
        }

        const app = new SuperGoalApp();
    </script>
</body>
</html>
