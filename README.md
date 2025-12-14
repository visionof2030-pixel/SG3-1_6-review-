<!DOCTYPE html>
<html lang="ar" dir="rtl">
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
            font-family: 'Almarai', sans-serif;
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
            color: var(--text-primary);
            line-height: 1.6;
            min-height: 100vh;
            padding: 12px 8px;
            direction: rtl;
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

        /* Header */
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

        /* Progress */
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

        /* Units Grid */
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

        /* Buttons */
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

        /* Final Test */
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
            left: 0.8rem;
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
            font-family: 'Almarai', sans-serif;
            font-size: 16px;
            background: rgba(255, 255, 255, 0.9);
            min-height: 44px;
        }

        /* Modals */
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

        /* Questions */
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
            width: 26px;
            height: 26px;
            border-radius: 50%;
            background: #f8f9fa;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: 700;
            color: var(--text-primary);
            flex-shrink: 0;
            font-size: 0.85rem;
        }

        .option.correct .option-letter {
            background: var(--secondary);
            color: white;
        }

        .option.incorrect .option-letter {
            background: var(--error);
            color: white;
        }

        /* Feedback */
        .feedback-container {
            margin-top: 1rem;
            padding: 1rem;
            background: #f8f9fa;
            border-radius: 8px;
            border-right: 4px solid var(--primary);
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

        /* Test Sections */
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

        /* Vocabulary - التصميم الجديد من الملف السابق */
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
            font-family: 'Almarai', sans-serif;
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
            border-right: 2px solid #06d6a0;
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
            font-family: 'Almarai', sans-serif;
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

        /* True/False */
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
        }

        .tf-option.incorrect {
            border-color: var(--error);
            background: rgba(239, 71, 111, 0.1);
            color: var(--error);
        }

        /* Writing */
        .writing-container {
            margin-top: 1rem;
        }

        .writing-instruction {
            background: #f8f9fa;
            padding: 0.8rem;
            border-radius: 8px;
            margin-bottom: 0.8rem;
            border-right: 4px solid var(--primary);
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
            font-family: 'Almarai', sans-serif;
            font-size: 16px;
            margin-top: 0.6rem;
            resize: vertical;
            min-height: 120px;
            line-height: 1.4;
        }

        /* Timer */
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

        /* Footer */
        .footer {
            text-align: center;
            margin-top: 2rem;
            padding: 1.2rem 0.8rem;
            color: var(--text-secondary);
            font-size: 0.8rem;
            border-top: 1px solid var(--border);
        }

        /* Sample Answers */
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

        /* Animations */
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

        /* تعديلات للشاشات المتوسطة */
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

        /* تعديلات للهواتف */
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

        /* تعديلات للهواتف الصغيرة جداً */
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

        /* Tablet Styles */
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

        /* Desktop Styles */
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

        /* Very Small Screens */
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

        /* Prevent iOS zoom on input focus */
        @media (max-width: 768px) {
            input, select, textarea {
                font-size: 16px !important;
            }
        }

        /* Smooth scrolling for iOS */
        .modal-body, .unit-questions-container {
            -webkit-overflow-scrolling: touch;
        }

        /* Prevent text selection on buttons */
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
                    <p class="subtitle">نظام التعلم التفاعلي - تدرب على قواعد اللغة الإنجليزية وتحضّر للاختبار النهائي</p>
                </div>
            </div>
            <div class="teacher-info">
                <i class="fas fa-chalkboard-teacher"></i>
                معلم المادة: فهد الخالدي
            </div>
        </header>

        <section class="progress-section">
            <div class="progress-header">
                <h2>تقدمك العام</h2>
                <span id="overallProgress">0%</span>
            </div>
            <div class="progress-bar-container">
                <div class="progress-bar" id="progressBar"></div>
            </div>
            <div class="progress-details">
                <span id="completedUnits">0/6 وحدات مكتملة</span>
                <span id="totalQuestions">0/30 سؤالاً مجاباً</span>
            </div>
        </section>

        <section>
            <h2 style="margin-bottom: 1rem; color: var(--text-primary); font-size: 1.2rem;">الوحدات التعليمية</h2>
            <div class="units-grid" id="unitsGrid">
                <!-- سيتم تعبئة الوحدات هنا -->
            </div>
        </section>

        <section class="final-test-section" id="finalTestCard">
            <div class="test-badge" id="testBadge">
                <i class="fas fa-lock"></i>
                <span>مقفل</span>
            </div>
            <div class="test-content">
                <h3>الاختبار النهائي الشامل</h3>
                <p style="font-size: 0.9rem;">اختبار شامل يغطي جميع مواضيع الوحدات من 1 إلى 6</p>
                
                <div class="test-stats">
                    <div class="stat-item">
                        <div class="stat-number" id="testQuestionsAnswered">0</div>
                        <div>أسئلة مجابة</div>
                    </div>
                    <div class="stat-item">
                        <div class="stat-number">5</div>
                        <div>أقسام مختلفة</div>
                    </div>
                    <div class="stat-item">
                        <div class="stat-number">60</div>
                        <div>دقيقة</div>
                    </div>
                    <div class="stat-item">
                        <div class="stat-number" id="testProgress">0%</div>
                        <div>تقدم الاختبار</div>
                    </div>
                </div>

                <div class="test-actions">
                    <button class="btn btn-primary" onclick="app.startFinalTest()" id="startFinalTestBtn" disabled>
                        <i class="fas fa-play-circle"></i>
                        بدء الاختبار النهائي
                    </button>
                    <button class="btn btn-secondary" onclick="app.showTestPreview()">
                        <i class="fas fa-eye"></i>
                        معاينة هيكل الاختبار
                    </button>
                    <button class="btn btn-danger" onclick="app.showPasswordAccess()">
                        <i class="fas fa-key"></i>
                        الدخول بكلمة مرور
                    </button>
                </div>

                <div class="password-access" id="passwordAccess" style="display: none;">
                    <h4 style="margin-bottom: 0.6rem; font-size: 1rem;">الدخول بكلمة مرور</h4>
                    <p style="margin-bottom: 0.6rem; font-size: 0.85rem;">أدخل كلمة المرور للوصول إلى الاختبار النهائي مباشرة:</p>
                    <div class="password-input-group">
                        <input type="password" class="password-input" id="passwordInput" placeholder="أدخل كلمة المرور">
                        <button class="btn btn-primary" onclick="app.checkPassword()">
                            <i class="fas fa-unlock"></i>
                            فتح
                        </button>
                    </div>
                    <p id="passwordMessage" style="margin-top: 0.6rem; font-size: 0.85rem; display: none;"></p>
                </div>
            </div>
        </section>

        <footer class="footer">
            <p>© 2024 Super Goal 3 Interactive Learning System</p>
            <p style="margin-top: 0.4rem; color: var(--primary); font-weight: 600;">إعداد وتصميم: معلم المادة فهد الخالدي</p>
            <button class="btn btn-secondary" onclick="app.resetProgress()" style="margin-top: 0.8rem; max-width: 200px; margin-left: auto; margin-right: auto;">
                <i class="fas fa-redo"></i>
                إعادة تعيين التقدم
            </button>
        </footer>
    </div>

    <!-- Unit Questions Modal -->
    <div class="modal" id="unitModal">
        <div class="modal-content">
            <div class="modal-header">
                <div>
                    <h3 id="unitModalTitle">اسم الوحدة</h3>
                    <p id="unitModalDesc">وصف الوحدة</p>
                </div>
                <button class="modal-close" onclick="app.closeUnitModal()">&times;</button>
            </div>
            <div class="modal-body">
                <div class="unit-questions-container" id="unitQuestionsContainer">
                    <!-- سيتم تعبئة الأسئلة هنا -->
                </div>
            </div>
            <div style="padding: 1rem; border-top: 1px solid var(--border); text-align: center;">
                <button class="btn btn-primary" onclick="app.checkAllQuestions()" style="padding: 0.8rem 1.5rem; font-size: 0.95rem; margin-bottom: 0.5rem;">
                    <i class="fas fa-check-circle"></i>
                    إنهاء الوحدة
                </button>
                <div style="color: var(--text-secondary); font-size: 0.85rem;">
                    <span id="unitProgressText">0/5 أسئلة مجابة</span>
                </div>
            </div>
        </div>
    </div>

    <!-- Final Test Modal -->
    <div class="modal" id="finalTestModal">
        <div class="modal-content">
            <div class="modal-header">
                <div style="display: flex; align-items: center; flex-wrap: wrap; gap: 0.5rem; width: 100%;">
                    <h3 style="margin: 0; flex: 1; font-size: 1.1rem;">الاختبار النهائي الشامل</h3>
                    <div class="timer-container">
                        <i class="fas fa-clock"></i>
                        <span id="timeRemaining">60:00</span>
                    </div>
                </div>
                <button class="modal-close" onclick="app.closeFinalTestModal()">&times;</button>
            </div>
            <div class="modal-body" id="finalTestContent">
                <!-- سيتم تعبئة محتوى الاختبار هنا -->
            </div>
            <div style="padding: 1rem; border-top: 1px solid var(--border); text-align: center;">
                <button class="btn btn-success" onclick="app.submitFinalTest()" style="padding: 0.8rem 1.5rem; font-size: 0.95rem; margin-bottom: 0.5rem;">
                    <i class="fas fa-paper-plane"></i>
                    تسليم الاختبار
                </button>
                <div style="color: var(--text-secondary); font-size: 0.85rem;">
                    <span id="testProgressText">0/40 سؤالاً مجاباً</span>
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
                description: "تعلم التعبير عن العادات والروتين اليومي",
                questionsNeeded: 5,
                questionsCompleted: 0,
                color: "#4361ee",
                icon: "fas fa-user-clock"
            },
            {
                id: 2,
                name: "Unit 2: Life Stories",
                description: "قصص الماضي والتجارب الشخصية",
                questionsNeeded: 5,
                questionsCompleted: 0,
                color: "#06d6a0",
                icon: "fas fa-book-open"
            },
            {
                id: 3,
                name: "Unit 3: When Are You Traveling?",
                description: "التخطيط للسفر والمستقبل",
                questionsNeeded: 5,
                questionsCompleted: 0,
                color: "#ffd166",
                icon: "fas fa-plane-departure"
            },
            {
                id: 4,
                name: "Unit 4: What Do I Need to Buy?",
                description: "التسوق والمقادير",
                questionsNeeded: 5,
                questionsCompleted: 0,
                color: "#ef476f",
                icon: "fas fa-shopping-cart"
            },
            {
                id: 5,
                name: "Unit 5: Since When?",
                description: "المدة والزمن الممتد",
                questionsNeeded: 5,
                questionsCompleted: 0,
                color: "#118ab2",
                icon: "fas fa-hourglass-half"
            },
            {
                id: 6,
                name: "Unit 6: Do You Know Where It Is?",
                description: "الأماكن والتوجيهات",
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
                    question: "Rewrite using the adverb in parentheses: 'I usually eat vegetables.' → (hardly ever) - ما الجملة الصحيحة؟",
                    options: [
                        "I hardly ever eat vegetables.",
                        "I usually hardly eat vegetables.",
                        "I eat vegetables hardly ever.",
                        "I eat hardly vegetables ever."
                    ],
                    correctAnswer: 0,
                    explanation: {
                        correct: "ممتاز! الجملة الصحيحة هي 'I hardly ever eat vegetables.'",
                        wrong: "خطأ. القاعدة: ظروف التكثير مثل hardly ever تأتي قبل الفعل الرئيسي.",
                        grammar: "ظروف التكثير (Adverbs of Frequency) تأتي قبل الفعل الرئيسي: always, usually, often, sometimes, rarely, hardly ever, never",
                        example: "مثال: I always drink coffee. She never eats meat. They sometimes go to the gym."
                    }
                },
                {
                    id: 2,
                    question: "Choose the correct question: ___ do you exercise?",
                    options: ["How long", "How often", "How much", "How many"],
                    correctAnswer: 1,
                    explanation: {
                        correct: "صحيح! 'How often' تسأل عن التكرار.",
                        wrong: "خطأ. 'How often' تستخدم للسؤال عن تكرار حدوث الشيء.",
                        grammar: "أسئلة التكرار: How often + do/does + subject + verb?",
                        example: "مثال: How often do you go to the gym? How often does she visit her family?"
                    }
                },
                {
                    id: 3,
                    question: "'Frequently' means:",
                    options: ["never", "rarely", "often", "sometimes"],
                    correctAnswer: 2,
                    explanation: {
                        correct: "صحيح! 'Frequently' تعني 'often' (غالباً، كثيراً).",
                        wrong: "خطأ. frequently = often = بشكل متكرر، كثيراً.",
                        grammar: "مفردات التكرار: Always (دائماً) → Usually (عادة) → Often/Frequently (كثيراً) → Sometimes (أحياناً) → Rarely/Seldom (نادراً) → Never (أبداً)",
                        example: "مثال: She frequently visits the library. = She often visits the library."
                    }
                },
                {
                    id: 4,
                    question: "'Once in a while' means:",
                    options: ["every day", "always", "occasionally", "never"],
                    correctAnswer: 2,
                    explanation: {
                        correct: "ممتاز! 'Once in a while' تعني 'occasionally' (من حين لآخر).",
                        wrong: "خطأ. once in a while = occasionally = أحياناً، من وقت لآخر.",
                        grammar: "التعبيرات الزمنية: Once in a while = Occasionally = أحياناً",
                        example: "مثال: I go to the cinema once in a while. = I go to the cinema occasionally."
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
                        correct: "صحيح! 'Neither of them drinks coffee.' هي الجملة الصحيحة.",
                        wrong: "خطأ. القاعدة: Neither + of + plural noun + singular verb",
                        grammar: "Neither/Either: Neither of + plural noun + singular verb, Either of + plural noun + singular verb",
                        example: "مثال: Neither of the books is interesting. Either of the answers is correct."
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
                        correct: "ممتاز! 'went' هي صيغة الماضي البسيط للفعل 'go'.",
                        wrong: "خطأ. الفعل 'go' تصريفه في الماضي البسيط: go → went → gone",
                        grammar: "الماضي البسيط: Subject + verb(past form) + time expression",
                        example: "مثال: I went to school yesterday. She visited her friend last week."
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
                        correct: "صحيح! 'I used to walk to school every day.' هي الجملة الصحيحة.",
                        wrong: "خطأ. Used to + base verb للتعبير عن العادات في الماضي التي توقفت الآن.",
                        grammar: "Used to: Subject + used to + base verb (للعادات في الماضي)",
                        example: "مثال: I used to play football when I was young. She used to live in London."
                    }
                },
                {
                    id: 3,
                    question: "'Donated' means:",
                    options: ["bought", "gave for charity", "borrowed", "took"],
                    correctAnswer: 1,
                    explanation: {
                        correct: "ممتاز! 'Donated' تعني 'gave for charity' (تبرع، أعطى للجمعيات الخيرية).",
                        wrong: "خطأ. donate = to give money, food, clothes, etc. to help people",
                        grammar: "المفردات: donate (فعل) → donation (اسم) → donor (اسم الفاعل)",
                        example: "مثال: He donated money to the hospital. They donated clothes to the poor."
                    }
                },
                {
                    id: 4,
                    question: "'Appointment' means:",
                    options: ["a surprise visit", "a job", "a planned meeting", "a ceremony"],
                    correctAnswer: 2,
                    explanation: {
                        correct: "صحيح! 'Appointment' تعني 'a planned meeting' (موعد، لقاء مخطط).",
                        wrong: "خطأ. appointment = an arrangement to meet someone at a particular time",
                        grammar: "كلمات مرتبطة: appointment (موعد) → schedule (جدول) → meeting (اجتماع)",
                        example: "مثال: I have a doctor's appointment at 3 PM. She made an appointment with her lawyer."
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
                        correct: "صحيح! 'He was called 'Athlete of the Year.'' هي الجملة الصحيحة.",
                        wrong: "خطأ. صيغة المبني للمجهول في الماضي البسيط: was/were + past participle",
                        grammar: "المبني للمجهول (الماضي البسيط): Subject + was/were + past participle",
                        example: "مثال: The book was written in 2020. The house was built last year."
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
                        correct: "ممتاز! 'is checking' هي صيغة المضارع المستمر المناسبة مع 'right now'.",
                        wrong: "خطأ. المضارع المستمر يستخدم للأفعال الجارية الآن: am/is/are + verb-ing",
                        grammar: "المضارع المستمر: Subject + am/is/are + verb-ing (للأفعال الجارية الآن)",
                        example: "مثال: I am studying now. They are watching TV at the moment."
                    }
                },
                {
                    id: 2,
                    question: "I think it ___ rain tomorrow.",
                    options: ["going to", "will", "was", "did"],
                    correctAnswer: 1,
                    explanation: {
                        correct: "صحيح! 'will' تستخدم للتنبؤات والقرارات اللحظية.",
                        wrong: "خطأ. Will + base verb تستخدم للتنبؤات والوعود والقرارات التي تتخذ في لحظة التكلم.",
                        grammar: "المستقبل البسيط بـ will: Subject + will + base verb",
                        example: "مثال: It will probably rain later. I will help you with your homework."
                    }
                },
                {
                    id: 3,
                    question: "'Itinerary' means:",
                    options: ["a travel plan", "a passport", "a suitcase", "an airport gate"],
                    correctAnswer: 0,
                    explanation: {
                        correct: "صحيح! 'Itinerary' تعني 'a travel plan' (خطة السفر، البرنامج الزمني).",
                        wrong: "خطأ. itinerary = a plan or schedule of a trip",
                        grammar: "مفردات السفر: itinerary (برنامج الرحلة) → passport (جواز سفر) → luggage (أمتعة)",
                        example: "مثال: The travel agency sent us the itinerary for our trip to Paris."
                    }
                },
                {
                    id: 4,
                    question: "'Departure' means:",
                    options: ["arrival", "waiting", "checking", "leaving"],
                    correctAnswer: 3,
                    explanation: {
                        correct: "ممتاز! 'Departure' تعني 'leaving' (مغادرة، انطلاق).",
                        wrong: "خطأ. departure = the act of leaving a place (مغادرة) → arrival = الوصول",
                        grammar: "كلمات متضادة: departure (مغادرة) ↔ arrival (وصول)",
                        example: "مثال: The departure time is 6 PM. Arrival time is 8 PM."
                    }
                },
                {
                    id: 5,
                    question: "What is the function of the infinitive? 'He came early to study.'",
                    options: ["showing time", "giving a reason", "comparing two actions", "describing a person"],
                    correctAnswer: 1,
                    explanation: {
                        correct: "صحيح! 'to study' تعطي سبب المجيء مبكراً.",
                        wrong: "خطأ. to + verb (المصدر) يمكن أن يعطي سبباً أو هدفاً للفعل الرئيسي.",
                        grammar: "المصدر لإعطاء السبب: Subject + verb + to + base verb (لإعطاء السبب أو الهدف)",
                        example: "مثال: I went to the store to buy milk. She studies hard to get good grades."
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
                        correct: "ممتاز! 'a few' تستخدم مع الأسماء المعدودة (tomatoes).",
                        wrong: "خطأ. a few + plural countable nouns, a little + uncountable nouns",
                        grammar: "كمية مع الأسماء: a few (قليل) + plural countable, a little (قليل) + uncountable, enough (كافي) + both",
                        example: "مثال: There are a few apples. There is a little water. We have enough money."
                    }
                },
                {
                    id: 2,
                    question: "I need ___ to eat.",
                    options: ["nothing", "anything", "something", "no one"],
                    correctAnswer: 2,
                    explanation: {
                        correct: "صحيح! 'something' تستخدم في الجمل الإيجابية عندما لا نعرف الشيء بالتحديد.",
                        wrong: "خطأ. something (شيء ما) تستخدم في الجمل الإيجابية، anything (أي شيء) في الجمل المنفية والاستفهامية.",
                        grammar: "كلمات غير محددة: something (في الجمل الإيجابية), anything (في النفي والاستفهام), nothing (لا شيء)",
                        example: "مثال: I want something to drink. Do you want anything? I have nothing to say."
                    }
                },
                {
                    id: 3,
                    question: "'Groceries' means:",
                    options: ["clothes", "food items", "electronics", "instructions"],
                    correctAnswer: 1,
                    explanation: {
                        correct: "ممتاز! 'Groceries' تعني 'food items' (مواد غذائية، بقالة).",
                        wrong: "خطأ. groceries = food and other items sold at a grocery store or supermarket",
                        grammar: "المشتريات: groceries (بقالة) → supermarket (سوبرماركت) → shopping list (قائمة تسوق)",
                        example: "مثال: I need to buy groceries for the week. We're out of milk and bread."
                    }
                },
                {
                    id: 4,
                    question: "'Recipe' means:",
                    options: ["shopping list", "grocery store", "cooking steps", "food price"],
                    correctAnswer: 2,
                    explanation: {
                        correct: "صحيح! 'Recipe' تعني 'cooking steps' (وصفة طهي، خطوات الطبخ).",
                        wrong: "خطأ. recipe = a set of instructions for preparing a particular dish",
                        grammar: "الطبخ: recipe (وصفة) → ingredients (مكونات) → instructions (تعليمات)",
                        example: "مثال: This recipe for chocolate cake is delicious. Follow the recipe carefully."
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
                        correct: "ممتاز! 'He was tired, so he slept.' هي الجملة الصحيحة.",
                        wrong: "خطأ. so (لذا) تعني النتيجة، because (لأن) تعني السبب.",
                        grammar: "السبب والنتيجة: because (لأن) + السبب, so (لذا) + النتيجة",
                        example: "مثال: It was raining, so we stayed home. We stayed home because it was raining."
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
                        correct: "صحيح! 'have lived' هي صيغة المضارع التام المناسبة مع 'since'.",
                        wrong: "خطأ. المضارع التام: have/has + past participle مع since (منذ) أو for (لمدة)",
                        grammar: "المضارع التام: Subject + have/has + past participle + since/for + time",
                        example: "مثال: She has worked here since 2015. They have known each other for ten years."
                    }
                },
                {
                    id: 2,
                    question: "___ have you had your phone?",
                    options: ["How many", "How long", "How often", "How soon"],
                    correctAnswer: 1,
                    explanation: {
                        correct: "ممتاز! 'How long' تسأل عن المدة الزمنية.",
                        wrong: "خطأ. How long? (منذ متى؟ / ما المدة؟) تستخدم مع المضارع التام.",
                        grammar: "أسئلة المدة: How long + have/has + subject + past participle?",
                        example: "مثال: How long have you studied English? How long has she lived in Riyadh?"
                    }
                },
                {
                    id: 3,
                    question: "'Recently' means:",
                    options: ["rarely", "long ago", "recently", "never"],
                    correctAnswer: 2,
                    explanation: {
                        correct: "ممتاز! 'Recently' تعني 'recently' (مؤخراً، حديثاً).",
                        wrong: "خطأ. recently = not long ago; in the recent past",
                        grammar: "التعبيرات الزمنية: recently (مؤخراً), lately (في الآونة الأخيرة), these days (هذه الأيام)",
                        example: "مثال: I've been very busy recently. Have you seen any good movies recently?"
                    }
                },
                {
                    id: 4,
                    question: "'Invention' means:",
                    options: ["experiment", "discovery", "creation / invention", "improvement"],
                    correctAnswer: 2,
                    explanation: {
                        correct: "صحيح! 'Invention' تعني 'creation / invention' (اختراع، ابتكار).",
                        wrong: "خطأ. invention = something that has been designed or created for the first time",
                        grammar: "الابتكار: invention (اختراع) → inventor (مخترع) → innovative (مبتكر)",
                        example: "مثال: The telephone was an important invention. He has many inventions to his name."
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
                        correct: "ممتاز! 'The phone has been repaired.' هي الصيغة الصحيحة.",
                        wrong: "خطأ. صيغة المضارع التام المبني للمجهول: have/has + been + past participle",
                        grammar: "المضارع التام المبني للمجهول: Subject + have/has + been + past participle",
                        example: "مثال: The work has been completed. The letters have been sent."
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
                        correct: "صحيح! 'safer' هي صيغة المقارنة للصفة 'safe'.",
                        wrong: "خطأ. صيغة المقارنة للصفات القصيرة: adjective + -er + than",
                        grammar: "صيغ المقارنة: Short adjectives: adjective + -er + than, Long adjectives: more + adjective + than",
                        example: "مثال: big → bigger, small → smaller, beautiful → more beautiful"
                    }
                },
                {
                    id: 2,
                    question: "Do you know where ___ ?",
                    options: ["is the museum", "the museum is", "museum is where", "is museum"],
                    correctAnswer: 1,
                    explanation: {
                        correct: "ممتاز! 'the museum is' هي الصيغة الصحيحة في الجملة غير المباشرة.",
                        wrong: "خطأ. في الجمل غير المباشرة (indirect questions) نستخدم ترتيب الكلمات العادي: subject + verb",
                        grammar: "الجمل غير المباشرة: Do you know + question word + subject + verb?",
                        example: "مثال: Can you tell me where the bank is? Do you know what time it is?"
                    }
                },
                {
                    id: 3,
                    question: "'Neighborhood' means:",
                    options: ["city", "shop", "neighborhood", "street"],
                    correctAnswer: 2,
                    explanation: {
                        correct: "ممتاز! 'Neighborhood' تعني 'neighborhood' (حي، منطقة سكنية).",
                        wrong: "خطأ. neighborhood = a district or community within a town or city",
                        grammar: "الأماكن: neighborhood (حي) → city (مدينة) → street (شارع) → district (منطقة)",
                        example: "مثال: It's a quiet neighborhood with good schools. We've lived in this neighborhood for years."
                    }
                },
                {
                    id: 4,
                    question: "'Crowded' means:",
                    options: ["empty", "full of people", "expensive", "dangerous"],
                    correctAnswer: 1,
                    explanation: {
                        correct: "صحيح! 'Crowded' تعني 'full of people' (مزدحم، مليء بالناس).",
                        wrong: "خطأ. crowded = full of people, leaving little space to move",
                        grammar: "صفات الأماكن: crowded (مزدحم) → empty (فارغ) → quiet (هادئ) → noisy (صاخب)",
                        example: "مثال: The market was very crowded on Friday. Avoid crowded places during flu season."
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
                        correct: "ممتاز! 'Riyadh is the capital of Saudi Arabia.' هي الجملة الصحيحة.",
                        wrong: "خطأ. نستخدم 'the' مع الأماكن الفريدة مثل العواصم، لكن لا نستخدمها مع أسماء المدن.",
                        grammar: "أداة التعريف 'the': تستخدم مع الأماكن الفريدة (the capital, the moon) لكن ليس مع أسماء المدن.",
                        example: "مثال: London is the capital of England. Paris is a beautiful city."
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
                    explanation: "صحيح! 'always' تعني دائمًا أو باستمرار. الجملة الصحيحة: He always plays football on weekends."
                },
                {
                    id: 2,
                    question: "How often ____ you drink coffee?",
                    options: ["do", "does", "did"],
                    correctAnswer: 0,
                    explanation: "ممتاز! مع الضمير 'you' نستخدم 'do'. الجملة الصحيحة: How often do you drink coffee?"
                },
                {
                    id: 3,
                    question: "My friends are ____ to the museum tomorrow.",
                    options: ["go", "going", "goes"],
                    correctAnswer: 1,
                    explanation: "صحيح! نستخدم 'going' مع المضارع المستمر للتعبير عن المستقبل. الجملة الصحيحة: My friends are going to the museum tomorrow."
                },
                {
                    id: 4,
                    question: "They both ____ English very well.",
                    options: ["speak", "speaks", "speaking"],
                    correctAnswer: 0,
                    explanation: "ممتاز! مع 'they' نستخدم 'speak' بدون 's'. الجملة الصحيحة: They both speak English very well."
                },
                {
                    id: 5,
                    question: "I ____ to play with toys when I was a child.",
                    options: ["use", "used", "used to"],
                    correctAnswer: 2,
                    explanation: "صحيح! 'used to' تعبر عن عادة في الماضي. الجملة الصحيحة: I used to play with toys when I was a child."
                },
                {
                    id: 6,
                    question: "She was born ____ 2005.",
                    options: ["at", "in", "on"],
                    correctAnswer: 1,
                    explanation: "ممتاز! نستخدم 'in' مع السنوات. الجملة الصحيحة: She was born in 2005."
                },
                {
                    id: 7,
                    question: "He is ____ a haircut now.",
                    options: ["get", "got", "getting"],
                    correctAnswer: 2,
                    explanation: "صحيح! 'getting' هي صيغة المضارع المستمر. الجملة الصحيحة: He is getting a haircut now."
                },
                {
                    id: 8,
                    question: "I have lived here ____ three years.",
                    options: ["for", "since", "from"],
                    correctAnswer: 0,
                    explanation: "ممتاز! نستخدم 'for' مع المدة الزمنية. الجملة الصحيحة: I have lived here for three years."
                },
                {
                    id: 9,
                    question: "They didn't go to school when they ____ young.",
                    options: ["are", "were", "be"],
                    correctAnswer: 1,
                    explanation: "صحيح! 'were' هي صيغة الماضي للفعل 'be'. الجملة الصحيحة: They didn't go to school when they were young."
                }
            ],
            orthography: [
                {
                    id: 10,
                    question: "Which letter completes the word? '_ilk'",
                    options: ["n", "m", "l"],
                    correctAnswer: 1,
                    explanation: "صحيح! الكلمة الصحيحة هي 'milk' (حليب)."
                },
                {
                    id: 11,
                    question: "Which letter completes the word? 'pota_oes'",
                    options: ["t", "d", "p"],
                    correctAnswer: 0,
                    explanation: "ممتاز! الكلمة الصحيحة هي 'potatoes' (بطاطس)."
                },
                {
                    id: 12,
                    question: "Which letter completes the word? 'bre_d'",
                    options: ["e", "a", "i"],
                    correctAnswer: 1,
                    explanation: "صحيح! الكلمة الصحيحة هي 'bread' (خبز)."
                },
                {
                    id: 13,
                    question: "Which letter completes the word? 'fru_t'",
                    options: ["e", "i", "o"],
                    correctAnswer: 1,
                    explanation: "ممتاز! الكلمة الصحيحة هي 'fruit' (فاكهة)."
                },
                {
                    id: 14,
                    question: "Which letter completes the word? 'mang_'",
                    options: ["o", "a", "u"],
                    correctAnswer: 0,
                    explanation: "صحيح! الكلمة الصحيحة هي 'mango' (مانجو)."
                }
            ],
            vocabulary: [
                { id: 1, word: "avocado", correctMatch: "A" },
                { id: 2, word: "cereal", correctMatch: "B" },
                { id: 3, word: "olive oil", correctMatch: "C" },
                { id: 4, word: "lamb", correctMatch: "D" },
                { id: 5, word: "cheese", correctMatch: "E" },
                { id: 6, word: "mango", correctMatch: "F" },
                { id: 7, word: "bread", correctMatch: "G" },
                { id: 8, word: "carrot", correctMatch: "H" },
                { id: 9, word: "shrimp", correctMatch: "I" }
            ],
            reading: [
                {
                    id: 1,
                    question: "King Salman was born in Jeddah.",
                    correctAnswer: false,
                    explanation: "خطأ. الملك سلمان وُلد في الرياض، وليس في جدة."
                },
                {
                    id: 2,
                    question: "He studied at the Princes' School.",
                    correctAnswer: true,
                    explanation: "صحيح. درس في مدرسة الأمراء."
                },
                {
                    id: 3,
                    question: "He became King in 2012.",
                    correctAnswer: false,
                    explanation: "خطأ. أصبح ملكاً في عام 2015، وليس 2012."
                },
                {
                    id: 4,
                    question: "He worked to develop the city of Riyadh.",
                    correctAnswer: true,
                    explanation: "صحيح. عمل على تطوير مدينة الرياض."
                },
                {
                    id: 5,
                    question: "Riyadh became smaller during his leadership.",
                    correctAnswer: false,
                    explanation: "خطأ. الرياض نمت وأصبحت أكبر، وليس أصغر."
                },
                {
                    id: 6,
                    question: "He supported humanitarian work.",
                    correctAnswer: true,
                    explanation: "صحيح. دعم العمل الإنساني."
                },
                {
                    id: 7,
                    question: "He received awards for his projects.",
                    correctAnswer: false,
                    explanation: "خطأ. النص لم يذكر أنه حصل على جوائز."
                },
                {
                    id: 8,
                    question: "He helped develop cities outside the Kingdom.",
                    correctAnswer: true,
                    explanation: "صحيح. ساعد في تطوير مدن خارج المملكة."
                },
                {
                    id: 9,
                    question: "The passage talks about King Salman's future plans.",
                    correctAnswer: false,
                    explanation: "خطأ. النص يتحدث عن إنجازاته السابقة، وليس خططه المستقبلية."
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
                title: "النموذج الأول (عن الرياضة)",
                content: "I enjoy fitness. I work out every day. I spend time at the gym. This is my healthy lifestyle. I am a big fan of sports.",
                usedWords: ["enjoy", "fitness", "work out", "spend time", "lifestyle", "fan"],
                wordCount: 6
            },
            {
                title: "النموذج الثاني (عن الحياة اليومية)",
                content: "My lifestyle is healthy. I enjoy herbal tea. I work out three times a week. I spend time with my family. I am a fan of puzzles.",
                usedWords: ["lifestyle", "enjoy", "herbal tea", "work out", "spend time", "fan", "puzzle"],
                wordCount: 7
            },
            {
                title: "النموذج الثالث (عن العادات الصحية)",
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
                                <span>التقدم</span>
                                <span>${unit.questionsCompleted}/${unit.questionsNeeded}</span>
                            </div>
                            <div class="unit-progress-bar">
                                <div class="unit-progress-fill" style="width: ${progress}%; background: ${unit.color}"></div>
                            </div>
                        </div>
                        <div class="unit-actions">
                            <button class="btn ${isCompleted ? 'btn-success' : 'btn-primary'}" onclick="event.stopPropagation(); app.openUnitModal(${unit.id})">
                                <i class="fas fa-${isCompleted ? 'check-circle' : 'play-circle'}"></i>
                                ${isCompleted ? 'مكتمل' : 'بدء التدريب'}
                            </button>
                            <button class="btn btn-secondary" onclick="event.stopPropagation(); app.reviewUnit(${unit.id})">
                                <i class="fas fa-book-open"></i>
                                مراجعة
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
                
                document.getElementById('completedUnits').textContent = `${completedUnits}/6 وحدات مكتملة`;
                document.getElementById('totalQuestions').textContent = `${totalQuestionsAnswered}/${totalQuestionsNeeded} سؤالاً مجاباً`;
            }

            updateFinalTestStatus() {
                const allCompleted = this.units.every(unit => unit.questionsCompleted >= unit.questionsNeeded);
                const finalTestCard = document.getElementById('finalTestCard');
                const startButton = document.getElementById('startFinalTestBtn');
                const badge = document.getElementById('testBadge');
                
                if (allCompleted || this.passwordUnlocked) {
                    finalTestCard.classList.remove('locked');
                    startButton.disabled = false;
                    badge.innerHTML = '<i class="fas fa-unlock"></i><span>مفتوح</span>';
                    badge.style.background = 'linear-gradient(135deg, var(--secondary) 0%, #34d399 100%)';
                    this.unlocked = true;
                } else {
                    finalTestCard.classList.add('locked');
                    startButton.disabled = true;
                    badge.innerHTML = '<i class="fas fa-lock"></i><span>مقفل</span>';
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
                    testProgressText.textContent = `${totalAnswered}/${totalQuestions} سؤالاً مجاباً`;
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
                
                const questions = unitQuestionsData[unit.id];
                
                const answeredCount = Object.keys(this.unitAnswers[unit.id]?.answers || {}).length;
                
                document.getElementById('unitProgressText').textContent = `${answeredCount}/${unit.questionsNeeded} أسئلة مجابة`;
                
                questions.forEach((question, index) => {
                    const isAnswered = this.unitAnswers[unit.id]?.answers?.[question.id] !== undefined;
                    const selectedAnswer = isAnswered ? this.unitAnswers[unit.id].answers[question.id] : null;
                    const isCorrect = isAnswered && selectedAnswer === question.correctAnswer;
                    
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
                                        <div class="option-letter">${String.fromCharCode(65 + optIndex)}</div>
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
                                <strong>${isCorrect ? 'إجابة صحيحة!' : 'إجابة خاطئة!'}</strong>
                            </div>
                        </div>
                        <div class="feedback-section">
                            <div class="feedback-section-title">
                                <i class="fas fa-info-circle"></i>
                                <span>التفسير</span>
                            </div>
                            <div class="feedback-section-content">
                                ${isCorrect ? question.explanation.correct : question.explanation.wrong}
                            </div>
                        </div>
                        <div class="feedback-section">
                            <div class="feedback-section-title">
                                <i class="fas fa-book"></i>
                                <span>القاعدة النحوية</span>
                            </div>
                            <div class="feedback-section-content">
                                ${question.explanation.grammar}
                            </div>
                        </div>
                        <div class="feedback-section">
                            <div class="feedback-section-title">
                                <i class="fas fa-language"></i>
                                <span>مثال</span>
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
                    const question = unitQuestionsData[unitId].find(q => q.id === questionId);
                    const isCorrect = optionIndex === question.correctAnswer;
                    
                    questionCard.className = `unit-question-card answered ${isCorrect ? 'correct' : 'incorrect'}`;
                    
                    const options = questionCard.querySelectorAll('.option');
                    options.forEach((opt, optIndex) => {
                        opt.className = 'option answered';
                        if (optIndex === question.correctAnswer) opt.classList.add('correct');
                        if (optIndex === optionIndex && optIndex !== question.correctAnswer) opt.classList.add('incorrect');
                        if (optIndex === optionIndex) opt.classList.add('selected');
                    });
                    
                    const existingFeedback = questionCard.querySelector('.feedback-container');
                    if (existingFeedback) {
                        existingFeedback.remove();
                    }
                    
                    const feedbackHTML = this.createFeedbackHTML(question, isCorrect);
                    questionCard.insertAdjacentHTML('beforeend', feedbackHTML);
                }
                
                document.getElementById('unitProgressText').textContent = `${answeredCount}/${unit.questionsNeeded} أسئلة مجابة`;
                
                this.saveProgress();
                this.updateProgressDisplay();
            }

            checkAllQuestions() {
                const unitId = this.currentUnit.id;
                const answeredCount = Object.keys(this.unitAnswers[unitId]?.answers || {}).length;
                
                if (answeredCount >= this.currentUnit.questionsNeeded) {
                    this.closeUnitModal();
                } else {
                    alert(`يجب الإجابة على ${this.currentUnit.questionsNeeded - answeredCount} أسئلة أخرى قبل الإنهاء.`);
                }
            }

            startFinalTest() {
                if (!this.unlocked) {
                    alert('يجب إكمال جميع الوحدات أولاً!');
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
                    "القواعد (Grammar)",
                    "fas fa-language",
                    "#4361ee",
                    "9 درجات"
                );
                
                finalTestData.grammar.forEach((question, index) => {
                    const isAnswered = this.finalTestAnswers.grammar[question.id] !== undefined;
                    const selectedAnswer = isAnswered ? this.finalTestAnswers.grammar[question.id] : null;
                    const isCorrect = isAnswered && selectedAnswer === question.correctAnswer;
                    
                    const questionElement = document.createElement('div');
                    questionElement.className = `unit-question-card ${isAnswered ? 'answered' : ''} ${isCorrect ? 'correct' : isAnswered && !isCorrect ? 'incorrect' : ''}`;
                    questionElement.innerHTML = `
                        <div class="question-header">
                            <div class="question-number">${index + 1}</div>
                            <div style="flex: 1;">
                                <div class="question-text">${question.question}</div>
                                <div class="question-type">اختر الإجابة الصحيحة</div>
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
                                        <div class="option-letter">${String.fromCharCode(97 + optIndex)}</div>
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
                    "الإملاء (Orthography)",
                    "fas fa-spell-check",
                    "#ffd166",
                    "5 درجات"
                );
                
                finalTestData.orthography.forEach((question, index) => {
                    const isAnswered = this.finalTestAnswers.orthography[question.id] !== undefined;
                    const selectedAnswer = isAnswered ? this.finalTestAnswers.orthography[question.id] : null;
                    const isCorrect = isAnswered && selectedAnswer === question.correctAnswer;
                    
                    const questionElement = document.createElement('div');
                    questionElement.className = `unit-question-card ${isAnswered ? 'answered' : ''} ${isCorrect ? 'correct' : isAnswered && !isCorrect ? 'incorrect' : ''}`;
                    questionElement.innerHTML = `
                        <div class="question-header">
                            <div class="question-number">${index + 10}</div>
                            <div style="flex: 1;">
                                <div class="question-text">${question.question}</div>
                                <div class="question-type">اختر الحرف الصحيح لإكمال الكلمة</div>
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
                                        <div class="option-letter">${String.fromCharCode(97 + optIndex)}</div>
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
                
                // Vocabulary Section - التصميم الجديد من الملف السابق
                const vocabularySection = this.createTestSection(
                    "المفردات (Vocabulary)",
                    "fas fa-book",
                    "#06d6a0",
                    "9 درجات"
                );
                
                const vocabularyContent = document.createElement('div');
                vocabularyContent.className = 'vocabulary-section';
                vocabularyContent.innerHTML = `
                    <div class="writing-instruction">
                        <i class="fas fa-info-circle"></i>
                        <strong>التعليمات:</strong> اختر الكلمة المناسبة لكل صورة من القائمة المنسدلة. سيتم تصحيح إجابتك تلقائياً.
                    </div>
                `;
                
                vocabularySection.appendChild(vocabularyContent);
                
                // إنشاء وعرض عناصر المفردات
                const gridContainer = document.createElement('div');
                gridContainer.id = 'vocabularyGridFinalTest';
                gridContainer.className = 'vocabulary-grid';
                vocabularySection.appendChild(gridContainer);
                
                // إنشاء وعرض إحصائيات وأزرار التحكم
                const controlsContainer = document.createElement('div');
                controlsContainer.className = 'vocab-stats-container';
                controlsContainer.innerHTML = `
                    <div class="vocab-stats">
                        <div class="vocab-stat-item">
                            <div class="vocab-stat-number" id="vocabAnsweredCount">0</div>
                            <div class="vocab-stat-label">تمت الإجابة</div>
                        </div>
                        <div class="vocab-stat-item">
                            <div class="vocab-stat-number" id="vocabCorrectCount">0</div>
                            <div class="vocab-stat-label">إجابات صحيحة</div>
                        </div>
                        <div class="vocab-stat-item">
                            <div class="vocab-stat-number" id="vocabIncorrectCount">0</div>
                            <div class="vocab-stat-label">إجابات خاطئة</div>
                        </div>
                    </div>
                    
                    <div class="vocab-buttons">
                        <button class="vocab-btn vocab-btn-check" onclick="app.checkAllVocabularyAnswers()">
                            <i class="fas fa-check-circle"></i>
                            تصحيح الكل
                        </button>
                        <button class="vocab-btn vocab-btn-show" onclick="app.showAllCorrectVocabularyAnswers()">
                            <i class="fas fa-eye"></i>
                            عرض الإجابات الصحيحة
                        </button>
                        <button class="vocab-btn vocab-btn-reset" onclick="app.resetVocabularyAnswers()">
                            <i class="fas fa-redo"></i>
                            إعادة المحاولة
                        </button>
                    </div>
                `;
                vocabularySection.appendChild(controlsContainer);
                
                container.appendChild(vocabularySection);
                
                // توليد عناصر المفردات
                this.generateVocabularyItems();
                
                // Reading Section
                const readingSection = this.createTestSection(
                    "القراءة (Reading)",
                    "fas fa-book-reader",
                    "#118ab2",
                    "9 درجات"
                );
                
                const readingText = document.createElement('div');
                readingText.className = 'writing-instruction';
                readingText.innerHTML = `
                    <h4 style="font-size: 1rem;">اقرأ الفقرة التالية:</h4>
                    <p style="margin-top: 0.8rem; line-height: 1.5; font-size: 0.9rem;">
                        King Salman bin Abdulaziz was born in Riyadh. He studied religion, science, and the Holy Qur'an at the Princes' School. 
                        He became King of Saudi Arabia in 2015. He helped Riyadh grow from a small town into a major modern city. 
                        He also supported humanitarian and cultural projects inside and outside the Kingdom.
                    </p>
                    <p style="margin-top: 0.8rem; font-weight: 600; font-size: 0.9rem;">اكتب T للجملة الصحيحة أو F للجملة الخاطئة:</p>
                `;
                readingSection.appendChild(readingText);
                
                const readingQuestions = document.createElement('div');
                readingQuestions.className = 'true-false-container';
                
                finalTestData.reading.forEach((question, index) => {
                    const isAnswered = this.finalTestAnswers.reading[question.id] !== undefined;
                    const selectedAnswer = isAnswered ? this.finalTestAnswers.reading[question.id] : null;
                    const isCorrect = isAnswered && selectedAnswer === question.correctAnswer;
                    
                    const questionElement = document.createElement('div');
                    questionElement.className = `true-false-question ${isAnswered ? 'answered' : ''} ${isCorrect ? 'correct' : isAnswered && !isCorrect ? 'incorrect' : ''}`;
                    questionElement.innerHTML = `
                        <div style="display: flex; align-items: flex-start; gap: 0.6rem;">
                            <div class="question-number">${index + 19}</div>
                            <div style="flex: 1;">
                                <div class="question-text" style="font-size: 0.9rem;">${question.question}</div>
                                <div class="tf-options">
                                    <div class="tf-option ${isAnswered && selectedAnswer === true ? (isCorrect ? 'correct' : 'incorrect') : ''} ${isAnswered && selectedAnswer === true ? 'selected' : ''}" 
                                         onclick="app.selectTrueFalseAnswer(${question.id}, true)">
                                        T (صح)
                                    </div>
                                    <div class="tf-option ${isAnswered && selectedAnswer === false ? (isCorrect ? 'correct' : 'incorrect') : ''} ${isAnswered && selectedAnswer === false ? 'selected' : ''}" 
                                         onclick="app.selectTrueFalseAnswer(${question.id}, false)">
                                        F (خطأ)
                                    </div>
                                </div>
                            </div>
                        </div>
                        ${isAnswered ? `
                            <div style="margin-top: 0.8rem; padding: 0.7rem; background: #f8f9fa; border-radius: 6px; border-right: 3px solid ${isCorrect ? 'var(--secondary)' : 'var(--error)'};">
                                <div style="display: flex; align-items: center; gap: 0.4rem; margin-bottom: 0.3rem;">
                                    <div style="width: 22px; height: 22px; border-radius: 50%; background: ${isCorrect ? 'var(--secondary)' : 'var(--error)'}; color: white; display: flex; align-items: center; justify-content: center; font-size: 0.8rem;">
                                        ${isCorrect ? '✓' : '✗'}
                                    </div>
                                    <strong style="font-size: 0.9rem;">${isCorrect ? 'إجابة صحيحة!' : 'إجابة خاطئة!'}</strong>
                                </div>
                                <div style="font-size: 0.85rem;">${question.explanation}</div>
                            </div>
                        ` : ''}
                    `;
                    readingQuestions.appendChild(questionElement);
                });
                
                readingSection.appendChild(readingQuestions);
                container.appendChild(readingSection);
                
                // Writing Section
                const writingSection = this.createTestSection(
                    "التعبير الكتابي (Guided Composition)",
                    "fas fa-edit",
                    "#9d4edd",
                    "8 درجات"
                );
                
                const writingContainer = document.createElement('div');
                writingContainer.className = 'writing-container';
                writingContainer.innerHTML = `
                    <div class="writing-instruction">
                        <h4 style="font-size: 1rem;">الكتابة الموجهة:</h4>
                        <p style="font-size: 0.9rem;">اكتب فقرة متماسكة من 3–5 جمل باستخدام 8 كلمات من الكلمات التالية:</p>
                        <div class="words-list">
                            ${finalTestData.writing.words.map(word => 
                                `<span class="word-tag">${word}</span>`
                            ).join('')}
                        </div>
                        <p style="font-size: 0.9rem;"><strong>تلميح:</strong> حاول أن تكتب عن موضوع مثل: الرياضة، الصحة، أو الحياة اليومية.</p>
                        
                        <div class="sample-answers">
                            <h5 style="color: var(--primary); margin-bottom: 0.6rem; display: flex; align-items: center; gap: 0.4rem; font-size: 0.9rem;">
                                <i class="fas fa-lightbulb"></i>
                                نماذج جاهزة (يمكنك استخدام أحدها أو الاستلهام منها)
                            </h5>
                            ${writingSamples.map((sample, idx) => `
                                <div class="sample-answer" onclick="app.useWritingSample(${idx})">
                                    <h5><i class="fas fa-copy"></i> ${sample.title}</h5>
                                    <div class="sample-answer-content">${sample.content}</div>
                                    <div class="used-words">تم استخدام ${sample.wordCount} كلمات من القائمة</div>
                                </div>
                            `).join('')}
                        </div>
                    </div>
                    <textarea class="writing-textarea" 
                              placeholder="اكتب فقرتك هنا... (3-5 جمل باستخدام 8 كلمات على الأقل من القائمة أعلاه)"
                              oninput="app.updateWritingAnswer(this.value)">${this.finalTestAnswers.writing || ''}</textarea>
                    <div style="margin-top: 0.8rem; color: var(--text-secondary); font-size: 0.8rem;">
                        <i class="fas fa-info-circle"></i> سيتم تقييم إجابتك بناء على: استخدام الكلمات المطلوبة، الترابط بين الجمل، القواعد النحوية، ووضوح الأفكار.
                    </div>
                `;
                
                writingSection.appendChild(writingContainer);
                container.appendChild(writingSection);
                
                this.updateFinalTestProgress();
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
                                <strong>${isCorrect ? 'إجابة صحيحة!' : 'إجابة خاطئة!'}</strong>
                            </div>
                        </div>
                        <div class="feedback-section">
                            <div class="feedback-section-title">
                                <i class="fas fa-info-circle"></i>
                                <span>التفسير</span>
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
                if (section === 'grammar') {
                    question = finalTestData.grammar.find(q => q.id === questionId);
                } else if (section === 'orthography') {
                    question = finalTestData.orthography.find(q => q.id === questionId);
                }
                
                if (!question) return;
                
                const isCorrect = optionIndex === question.correctAnswer;
                
                const questionElements = document.querySelectorAll('.unit-question-card');
                let targetQuestion;
                
                for (const qElement of questionElements) {
                    const questionText = qElement.querySelector('.question-text');
                    if (questionText && questionText.textContent.includes(question.question.substring(0, 30))) {
                        targetQuestion = qElement;
                        break;
                    }
                }
                
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

            // توليد عناصر المفردات للاختبار النهائي
            generateVocabularyItems() {
                const container = document.getElementById('vocabularyGridFinalTest');
                if (!container) return;
                
                container.innerHTML = '';
                
                vocabularyImages.forEach((imgItem, index) => {
                    const wordItem = finalTestData.vocabulary[index];
                    if (!wordItem) return;
                    
                    const userAnswer = this.finalTestAnswers.vocabulary[wordItem.id];
                    const isCorrect = userAnswer === wordItem.correctMatch;
                    const hasAnswer = userAnswer !== undefined;
                    
                    const item = document.createElement('div');
                    item.className = `vocab-item ${hasAnswer ? (isCorrect ? 'correct' : 'incorrect') : ''}`;
                    item.id = `vocab-item-final-${wordItem.id}`;
                    
                    const reversedOptions = finalTestData.vocabulary.slice().reverse();
                    
                    item.innerHTML = `
                        <div class="image-container">
                            <div class="image-card">
                                <div class="image-letter">${imgItem.letter}</div>
                                <img src="${imgItem.img}" alt="صورة ${imgItem.letter}" 
                                     onerror="this.src='https://via.placeholder.com/80x60?text=${imgItem.letter}'">
                            </div>
                        </div>
                        
                        <div class="word-container">
                            <div class="answer-container">
                                <select class="vocab-select" onchange="app.selectVocabularyAnswerFinal(${wordItem.id}, this.value)" 
                                        id="vocab-select-final-${wordItem.id}"
                                        ${hasAnswer && !isCorrect ? 'disabled' : ''}>
                                    <option value="">اختر الكلمة المناسبة</option>
                                    ${reversedOptions.map((word, idx) => 
                                        `<option value="${word.correctMatch}" ${userAnswer === word.correctMatch ? 'selected' : ''}>
                                            ${idx + 1}. ${word.word}
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
                                    الإجابة الصحيحة: ${wordItem.word}
                                </div>
                            ` : ''}
                        </div>
                    `;
                    
                    container.appendChild(item);
                });
                
                this.updateVocabularyStats();
            }

            // اختيار إجابة للمفردات في الاختبار النهائي
            selectVocabularyAnswerFinal(id, value) {
                const wordItem = finalTestData.vocabulary.find(item => item.id === id);
                if (!wordItem) return;
                
                this.finalTestAnswers.vocabulary[id] = value;
                const isCorrect = value === wordItem.correctMatch;
                
                const item = document.getElementById(`vocab-item-final-${id}`);
                const select = document.getElementById(`vocab-select-final-${id}`);
                
                // تحديث العنصر
                item.className = `vocab-item ${isCorrect ? 'correct' : 'incorrect'}`;
                
                // تحديث أيقونة التغذية الراجعة
                const feedbackContainer = item.querySelector('.answer-container');
                const existingFeedback = feedbackContainer.querySelector('.feedback-icon-vocab');
                if (existingFeedback) {
                    existingFeedback.remove();
                }
                
                const feedbackIcon = document.createElement('div');
                feedbackIcon.className = `feedback-icon-vocab ${isCorrect ? 'correct-icon-vocab' : 'incorrect-icon-vocab'}`;
                feedbackIcon.innerHTML = isCorrect ? '✓' : '✗';
                feedbackContainer.appendChild(feedbackIcon);
                
                // إضافة تلميح الإجابة الصحيحة إذا كانت خاطئة
                const existingHint = item.querySelector('.correct-hint');
                if (!isCorrect) {
                    if (!existingHint) {
                        const hint = document.createElement('div');
                        hint.className = 'correct-hint';
                        hint.innerHTML = `<i class="fas fa-lightbulb"></i> الإجابة الصحيحة: ${wordItem.word}`;
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

            // تحديث إحصائيات المفردات للاختبار النهائي
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

            // تصحيح جميع إجابات المفردات
            checkAllVocabularyAnswers() {
                finalTestData.vocabulary.forEach(item => {
                    const select = document.getElementById(`vocab-select-final-${item.id}`);
                    if (select && select.value) {
                        this.selectVocabularyAnswerFinal(item.id, select.value);
                    }
                });
            }

            // عرض جميع الإجابات الصحيحة للمفردات
            showAllCorrectVocabularyAnswers() {
                if (confirm('هل تريد عرض جميع الإجابات الصحيحة؟ سيتم تعطيل الاختيار.')) {
                    finalTestData.vocabulary.forEach(item => {
                        const select = document.getElementById(`vocab-select-final-${item.id}`);
                        const itemElement = document.getElementById(`vocab-item-final-${item.id}`);
                        
                        if (select && itemElement) {
                            select.value = item.correctMatch;
                            this.finalTestAnswers.vocabulary[item.id] = item.correctMatch;
                            
                            itemElement.className = 'vocab-item correct';
                            select.disabled = true;
                            
                            // تحديث أيقونة التغذية الراجعة
                            const feedbackContainer = itemElement.querySelector('.answer-container');
                            const existingFeedback = feedbackContainer.querySelector('.feedback-icon-vocab');
                            if (existingFeedback) {
                                existingFeedback.remove();
                            }
                            
                            const feedbackIcon = document.createElement('div');
                            feedbackIcon.className = 'feedback-icon-vocab correct-icon-vocab';
                            feedbackIcon.innerHTML = '✓';
                            feedbackContainer.appendChild(feedbackIcon);
                            
                            // إزالة أي تلميح سابق
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

            // إعادة تعيين إجابات المفردات
            resetVocabularyAnswers() {
                if (confirm('هل تريد إعادة تعيين جميع إجابات المفردات؟')) {
                    finalTestData.vocabulary.forEach(item => {
                        delete this.finalTestAnswers.vocabulary[item.id];
                    });
                    
                    this.generateVocabularyItems();
                    this.saveProgress();
                    this.updateFinalTestProgress();
                }
            }

            selectTrueFalseAnswer(questionId, value) {
                this.finalTestAnswers.reading[questionId] = value;
                this.saveProgress();
                
                const question = finalTestData.reading.find(q => q.id === questionId);
                if (!question) return;
                
                const isCorrect = value === question.correctAnswer;
                
                const questionElements = document.querySelectorAll('.true-false-question');
                let targetQuestion;
                
                for (const qElement of questionElements) {
                    const questionText = qElement.querySelector('.question-text');
                    if (questionText && questionText.textContent.includes(question.question.substring(0, 30))) {
                        targetQuestion = qElement;
                        break;
                    }
                }
                
                if (targetQuestion) {
                    targetQuestion.className = `true-false-question answered ${isCorrect ? 'correct' : 'incorrect'}`;
                    
                    const options = targetQuestion.querySelectorAll('.tf-option');
                    options.forEach(opt => {
                        opt.classList.remove('selected', 'correct', 'incorrect');
                    });
                    
                    const selectedOption = targetQuestion.querySelector(`.tf-option[onclick*="${value}"]`);
                    if (selectedOption) {
                        selectedOption.classList.add('selected');
                        if (isCorrect) {
                            selectedOption.classList.add('correct');
                        } else {
                            selectedOption.classList.add('incorrect');
                        }
                    }
                    
                    const existingFeedback = targetQuestion.querySelector('div[style*="margin-top: 0.8rem"]');
                    if (existingFeedback) {
                        existingFeedback.remove();
                    }
                    
                    const feedbackHTML = `
                        <div style="margin-top: 0.8rem; padding: 0.7rem; background: #f8f9fa; border-radius: 6px; border-right: 3px solid ${isCorrect ? 'var(--secondary)' : 'var(--error)'};">
                            <div style="display: flex; align-items: center; gap: 0.4rem; margin-bottom: 0.3rem;">
                                <div style="width: 22px; height: 22px; border-radius: 50%; background: ${isCorrect ? 'var(--secondary)' : 'var(--error)'}; color: white; display: flex; align-items: center; justify-content: center; font-size: 0.8rem;">
                                    ${isCorrect ? '✓' : '✗'}
                                </div>
                                <strong style="font-size: 0.9rem;">${isCorrect ? 'إجابة صحيحة!' : 'إجابة خاطئة!'}</strong>
                            </div>
                            <div style="font-size: 0.85rem;">${question.explanation}</div>
                        </div>
                    `;
                    
                    const questionContent = targetQuestion.querySelector('div[style*="flex: 1"]');
                    if (questionContent) {
                        questionContent.insertAdjacentHTML('afterend', feedbackHTML);
                    }
                }
                
                this.updateFinalTestProgress();
            }

            useWritingSample(index) {
                if (index >= 0 && index < writingSamples.length) {
                    const sample = writingSamples[index];
                    const textarea = document.querySelector('.writing-textarea');
                    if (textarea) {
                        textarea.value = sample.content;
                        this.updateWritingAnswer(sample.content);
                        alert(`تم استخدام النموذج "${sample.title}". يمكنك تعديله كما تريد!`);
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
                        alert('انتهى وقت الاختبار!');
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
                details.push(`القواعد: ${grammarScore}/9`);
                
                let orthographyScore = 0;
                finalTestData.orthography.forEach(q => {
                    if (this.finalTestAnswers.orthography[q.id] === q.correctAnswer) {
                        orthographyScore++;
                    }
                });
                totalScore += orthographyScore;
                details.push(`الإملاء: ${orthographyScore}/5`);
                
                let vocabularyScore = 0;
                finalTestData.vocabulary.forEach(item => {
                    if (this.finalTestAnswers.vocabulary[item.id] === item.correctMatch) {
                        vocabularyScore++;
                    }
                });
                totalScore += vocabularyScore;
                details.push(`المفردات: ${vocabularyScore}/9`);
                
                let readingScore = 0;
                finalTestData.reading.forEach(q => {
                    if (this.finalTestAnswers.reading[q.id] === q.correctAnswer) {
                        readingScore++;
                    }
                });
                totalScore += readingScore;
                details.push(`القراءة: ${readingScore}/9`);
                
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
                details.push(`الكتابة: ${writingScore}/8`);
                
                this.finalTestScore = totalScore;
                this.saveProgress();
                
                const percentage = Math.round((totalScore / maxScore) * 100);
                
                const resultHTML = `
                    <div style="text-align: center; padding: 1.2rem;">
                        <div style="background: ${percentage >= 60 ? 'linear-gradient(135deg, var(--secondary) 0%, #05c490 100%)' : 'linear-gradient(135deg, var(--error) 0%, #d43f8d 100%)'}; 
                            width: 80px; height: 80px; border-radius: 50%; display: flex; align-items: center; justify-content: center; margin: 0 auto 1.2rem;">
                            <i class="fas fa-${percentage >= 60 ? 'trophy' : 'graduation-cap'}" style="font-size: 2.2rem; color: white;"></i>
                        </div>
                        
                        <h3 style="color: var(--text-primary); margin-bottom: 0.8rem; font-size: 1.1rem;">نتيجة الاختبار النهائي</h3>
                        
                        <div style="background: white; border-radius: 12px; padding: 1.2rem; max-width: 500px; margin: 0 auto 1.2rem; box-shadow: var(--shadow);">
                            <div style="font-size: 2.2rem; font-weight: 800; color: ${percentage >= 60 ? 'var(--secondary)' : 'var(--error)'}; margin-bottom: 0.8rem;">
                                ${totalScore}/${maxScore}
                            </div>
                            <div style="font-size: 1.1rem; color: var(--text-primary); margin-bottom: 0.8rem;">
                                ${percentage}%
                            </div>
                            <div style="color: var(--text-secondary); margin-bottom: 1rem; font-size: 0.9rem;">
                                ${percentage >= 60 ? '✅ ناجح - أحسنت!' : '⏳ تحتاج إلى مزيد من الممارسة'}
                            </div>
                            
                            <div style="text-align: right; margin-top: 1.2rem; background: #f8f9fa; padding: 0.8rem; border-radius: 8px; font-size: 0.9rem;">
                                <div style="margin-bottom: 0.4rem; font-weight: 600;">تفاصيل النتيجة:</div>
                                ${details.map(detail => `<div style="margin-bottom: 0.2rem;">${detail}</div>`).join('')}
                                <div style="margin-top: 0.8rem; padding-top: 0.8rem; border-top: 1px solid var(--border); font-weight: 600;">
                                    المجموع النهائي: ${totalScore}/40
                                </div>
                            </div>
                        </div>
                        
                        <button class="btn btn-primary" onclick="app.closeFinalTestModal()" style="padding: 0.8rem 1.5rem; font-size: 0.95rem;">
                            <i class="fas fa-check-circle"></i>
                            حسناً
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
                        
                        <h3 style="color: var(--text-primary); margin-bottom: 1rem; font-size: 1.1rem;">معاينة الاختبار النهائي</h3>
                        
                        <div style="max-width: 800px; margin: 0 auto 1.5rem; text-align: right; font-size: 0.9rem;">
                            <h4 style="color: var(--primary); margin-bottom: 0.8rem; border-bottom: 2px solid var(--primary); padding-bottom: 0.4rem; font-size: 1rem;">هيكل الاختبار:</h4>
                            
                            <div style="display: grid; grid-template-columns: 1fr; gap: 1rem; margin-top: 1.2rem;">
                                <div style="background: white; padding: 1rem; border-radius: 12px; border: 2px solid var(--primary); box-shadow: 0 4px 15px rgba(0,0,0,0.1); text-align: center;">
                                    <div style="display: flex; align-items: center; justify-content: center; gap: 0.6rem; margin-bottom: 0.8rem;">
                                        <div style="width: 34px; height: 34px; background: var(--primary); color: white; border-radius: 50%; display: flex; align-items: center; justify-content: center;">
                                            <i class="fas fa-language"></i>
                                        </div>
                                        <div style="text-align: right;">
                                            <div style="font-size: 1.4rem; font-weight: 800; color: var(--primary);">9</div>
                                            <div style="font-weight: 600; color: var(--text-primary); font-size: 0.85rem;">القواعد</div>
                                        </div>
                                    </div>
                                    <div style="color: var(--text-secondary); font-size: 0.8rem;">اختر الإجابة الصحيحة</div>
                                </div>
                                
                                <div style="background: white; padding: 1rem; border-radius: 12px; border: 2px solid var(--warning); box-shadow: 0 4px 15px rgba(0,0,0,0.1); text-align: center;">
                                    <div style="display: flex; align-items: center; justify-content: center; gap: 0.6rem; margin-bottom: 0.8rem;">
                                        <div style="width: 34px; height: 34px; background: var(--warning); color: white; border-radius: 50%; display: flex; align-items: center; justify-content: center;">
                                            <i class="fas fa-spell-check"></i>
                                        </div>
                                        <div style="text-align: right;">
                                            <div style="font-size: 1.4rem; font-weight: 800; color: var(--warning);">5</div>
                                            <div style="font-weight: 600; color: var(--text-primary); font-size: 0.85rem;">الإملاء</div>
                                        </div>
                                    </div>
                                    <div style="color: var(--text-secondary); font-size: 0.8rem;">اختر الحرف الصحيح</div>
                                </div>
                                
                                <div style="background: white; padding: 1rem; border-radius: 12px; border: 2px solid var(--secondary); box-shadow: 0 4px 15px rgba(0,0,0,0.1); text-align: center;">
                                    <div style="display: flex; align-items: center; justify-content: center; gap: 0.6rem; margin-bottom: 0.8rem;">
                                        <div style="width: 34px; height: 34px; background: var(--secondary); color: white; border-radius: 50%; display: flex; align-items: center; justify-content: center;">
                                            <i class="fas fa-book"></i>
                                        </div>
                                        <div style="text-align: right;">
                                            <div style="font-size: 1.4rem; font-weight: 800; color: var(--secondary);">9</div>
                                            <div style="font-weight: 600; color: var(--text-primary); font-size: 0.85rem;">المفردات</div>
                                        </div>
                                    </div>
                                    <div style="color: var(--text-secondary); font-size: 0.8rem;">اختر الكلمة المناسبة للصورة</div>
                                </div>
                                
                                <div style="background: white; padding: 1rem; border-radius: 12px; border: 2px solid var(--info); box-shadow: 0 4px 15px rgba(0,0,0,0.1); text-align: center;">
                                    <div style="display: flex; align-items: center; justify-content: center; gap: 0.6rem; margin-bottom: 0.8rem;">
                                        <div style="width: 34px; height: 34px; background: var(--info); color: white; border-radius: 50%; display: flex; align-items: center; justify-content: center;">
                                            <i class="fas fa-book-reader"></i>
                                        </div>
                                        <div style="text-align: right;">
                                            <div style="font-size: 1.4rem; font-weight: 800; color: var(--info);">9</div>
                                            <div style="font-weight: 600; color: var(--text-primary); font-size: 0.85rem;">القراءة</div>
                                        </div>
                                    </div>
                                    <div style="color: var(--text-secondary); font-size: 0.8rem;">صح أم خطأ</div>
                                </div>
                                
                                <div style="background: white; padding: 1rem; border-radius: 12px; border: 2px solid var(--error); box-shadow: 0 4px 15px rgba(0,0,0,0.1); text-align: center;">
                                    <div style="display: flex; align-items: center; justify-content: center; gap: 0.6rem; margin-bottom: 0.8rem;">
                                        <div style="width: 34px; height: 34px; background: var(--error); color: white; border-radius: 50%; display: flex; align-items: center; justify-content: center;">
                                            <i class="fas fa-edit"></i>
                                        </div>
                                        <div style="text-align: right;">
                                            <div style="font-size: 1.4rem; font-weight: 800; color: var(--error);">8</div>
                                            <div style="font-weight: 600; color: var(--text-primary); font-size: 0.85rem;">الكتابة</div>
                                        </div>
                                    </div>
                                    <div style="color: var(--text-secondary); font-size: 0.8rem;">كتابة فقرة موجزة</div>
                                </div>
                            </div>
                            
                            <div style="margin-top: 1.5rem; padding: 1.2rem; background: linear-gradient(135deg, var(--final-test-color) 0%, #7b2cbf 100%); border-radius: 12px; color: white;">
                                <div style="display: flex; justify-content: space-around; flex-wrap: wrap; gap: 1.2rem;">
                                    <div style="text-align: center;">
                                        <div style="font-size: 1.8rem; font-weight: 800;">40</div>
                                        <div style="font-size: 0.8rem;">سؤال شامل</div>
                                    </div>
                                    <div style="text-align: center;">
                                        <div style="font-size: 1.8rem; font-weight: 800;">60</div>
                                        <div style="font-size: 0.8rem;">دقيقة (الوقت)</div>
                                    </div>
                                    <div style="text-align: center;">
                                        <div style="font-size: 1.8rem; font-weight: 800;">100</div>
                                        <div style="font-size: 0.8rem;">درجة كاملة</div>
                                    </div>
                                </div>
                            </div>
                        </div>
                        
                        <div style="margin-top: 1.5rem;">
                            <button class="btn btn-primary" onclick="app.startFinalTest()" style="padding: 0.8rem 1.5rem; font-size: 0.95rem; margin: 0 0.4rem 0.4rem;">
                                <i class="fas fa-play-circle"></i>
                                بدء الاختبار الآن
                            </button>
                            <button class="btn btn-secondary" onclick="app.closeFinalTestModal()" style="padding: 0.8rem 1.2rem; font-size: 0.95rem;">
                                <i class="fas fa-times-circle"></i>
                                إغلاق
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
                    
                    passwordMessage.textContent = '✅ تم فتح الاختبار النهائي بنجاح!';
                    passwordMessage.style.color = 'var(--secondary)';
                    passwordMessage.style.display = 'block';
                    
                    setTimeout(() => {
                        document.getElementById('passwordAccess').style.display = 'none';
                        passwordInput.value = '';
                    }, 2000);
                } else {
                    passwordMessage.textContent = '❌ كلمة المرور غير صحيحة!';
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
                
                alert(`مراجعة ${unit.name}\n\n` +
                      `الأسئلة المجابة: ${answeredCount}/${unit.questionsNeeded}\n` +
                      `الإجابات الصحيحة: ${correctCount}/${answeredCount}\n` +
                      `الدقة: ${answeredCount > 0 ? Math.round((correctCount / answeredCount) * 100) : 0}%\n\n` +
                      `${unit.questionsCompleted >= unit.questionsNeeded ? 
                        '✅ الوحدة مكتملة!' : 
                        `⏳ تحتاج إلى إكمال ${unit.questionsNeeded - unit.questionsCompleted} أسئلة أخرى`}`);
            }

            resetProgress() {
                if (confirm('هل أنت متأكد من إعادة تعيين التقدم؟ سيتم حذف جميع الإجابات والتقدم.')) {
                    localStorage.removeItem('superGoal3_progress');
                    location.reload();
                }
            }
        }

        const app = new SuperGoalApp();
    </script>
</body>
</html>
