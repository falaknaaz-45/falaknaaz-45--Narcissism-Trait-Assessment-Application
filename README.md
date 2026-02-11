# 🎭 Narcissism Trait Assessment Application

A web-based personality assessment tool that evaluates narcissistic traits using scenario-based questions and multiple-choice options. Built with Python, Gradio, and SQLite.

![Python](https://img.shields.io/badge/python-3.8+-blue.svg)
![Gradio](https://img.shields.io/badge/gradio-latest-orange.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Technologies](#technologies)
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Assessment Details](#assessment-details)
- [Database Schema](#database-schema)
- [Screenshots](#screenshots)
- [Disclaimer](#disclaimer)
- [Team](#team)
- [License](#license)

## 🎯 Overview

This application is an educational prototype developed as part of a Final Integrated Project (FIP) for Software Engineering at Riphah International University. It implements a voice-based narcissism trait assessment system using scenario-based questions derived from the Narcissistic Personality Inventory (NPI).

The tool presents users with 20 real-life scenarios and asks them to select from multiple-choice responses that best represent their typical behavior or feelings. The system then calculates a narcissism score and provides detailed feedback across seven personality dimensions.

## ✨ Features

- ✅ **20 Scenario-Based Questions** - Real-life situations based on NPI framework
- ✅ **Multiple-Choice Interface** - Simple click-to-select options (0-3 points each)
- ✅ **Scientific Scoring System** - Based on Narcissistic Personality Inventory (NPI-40)
- ✅ **Category Breakdown** - Analysis across 7 narcissism dimensions:
  - Authority
  - Self-Sufficiency
  - Superiority
  - Exhibitionism
  - Exploitativeness
  - Vanity
  - Entitlement
- ✅ **Detailed Results** - Comprehensive interpretation with trait level classification
- ✅ **Data Persistence** - SQLite database stores all assessment results
- ✅ **Clean Web Interface** - Modern, responsive design using Gradio
- ✅ **Ethical Design** - Clear disclaimers and informed consent
- ✅ **Privacy-Focused** - Anonymous data collection, no personal information stored

## 🛠️ Technologies

### Core Technologies
- **Python 3.8+** - Primary programming language
- **Gradio** - Web interface framework
- **SQLite3** - Local database for data persistence

### Key Libraries
- `gradio` - Web UI and interaction
- `sqlite3` - Database operations (built-in)

## 📦 Installation

### Prerequisites
- Python 3.8 or higher
- pip (Python package manager)

### Step-by-Step Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/narcissism-assessment.git
   cd narcissism-assessment
   ```

2. **Create virtual environment** (recommended)
   ```bash
   python -m venv venv
   
   # On Windows
   venv\Scripts\activate
   
   # On macOS/Linux
   source venv/bin/activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Run the application**
   ```bash
   python app.py
   ```

5. **Open in browser**
   - Navigate to: `http://127.0.0.1:7860`
   - The application will open automatically

## 🚀 Usage

### Taking an Assessment

1. **Start Assessment** - Click the "Start Assessment" button on the welcome screen
2. **Read Consent** - Review the disclaimer and click "I Agree & Continue"
3. **Answer Questions** - Read each scenario and select the option that best describes you
4. **View Results** - After completing all 20 questions, view your:
   - Overall narcissism score and percentage
   - Trait level classification (Low/Moderate/High/Very High)
   - Detailed interpretation
   - Category breakdown across 7 dimensions
5. **Retake** - Option to take the assessment again

### Assessment Duration
- **Time Required:** 5-10 minutes
- **Questions:** 20 scenario-based questions
- **Format:** Multiple-choice (4 options per question)

## 📁 Project Structure

```
narcissism-assessment/
│
├── app.py                      # Main Gradio application
├── database.py                 # Database operations
├── scoring.py                  # Scoring logic and interpretations
├── questions.py                # Question definitions (20 NPI scenarios)
├── requirements.txt            # Python dependencies
├── README.md                   # Project documentation
├── .gitignore                  # Git ignore file
│
└── data/
    └── narcissism_assessment.db  # SQLite database (auto-created)
```

### File Descriptions

- **`app.py`** - Main application file containing Gradio interface and event handlers
- **`database.py`** - Handles all database operations (create, read, write)
- **`scoring.py`** - Contains scoring algorithms and result interpretations
- **`questions.py`** - Stores all 20 scenario-based questions with options
- **`requirements.txt`** - Lists all Python package dependencies

## 📊 Assessment Details

### Scoring System

- **Points per question:** 0-3
- **Total possible score:** 60 points
- **Percentage calculation:** (Total Score / 60) × 100

### Trait Level Classification

| Percentage | Trait Level | Description |
|------------|-------------|-------------|
| 0-25% | Low | Healthy self-esteem, constructive feedback acceptance |
| 26-50% | Moderate | Generally healthy with occasional validation needs |
| 51-75% | High | Strong need for admiration, difficulty with criticism |
| 76-100% | Very High | Intense validation needs, relationship challenges |

### Seven Narcissism Dimensions

The assessment evaluates traits across these categories:

1. **Authority** - Need for power and control
2. **Self-Sufficiency** - Belief in independence from others
3. **Superiority** - Sense of being better than others
4. **Exhibitionism** - Need for attention and admiration
5. **Exploitativeness** - Tendency to use others for personal gain
6. **Vanity** - Focus on physical appearance and charm
7. **Entitlement** - Expectation of special treatment

## 🗄️ Database Schema

### Tables

#### `assessments`
| Column | Type | Description |
|--------|------|-------------|
| id | INTEGER | Primary key (auto-increment) |
| timestamp | TEXT | ISO format datetime |
| total_score | INTEGER | Sum of all question scores |
| percentage | REAL | Score as percentage |
| trait_level | TEXT | Classification (Low/Moderate/High/Very High) |
| responses | TEXT | JSON array of all responses |

#### `responses`
| Column | Type | Description |
|--------|------|-------------|
| id | INTEGER | Primary key (auto-increment) |
| assessment_id | INTEGER | Foreign key to assessments |
| question_id | INTEGER | Question number (1-20) |
| selected_option | INTEGER | Option index (0-3) |
| option_score | INTEGER | Points awarded (0-3) |

## 📸 Screenshots

### Welcome Screen
Clean, informative landing page with assessment overview.

### Scenario Question
Real-life scenario with four multiple-choice options.

### Results Screen
Comprehensive results with score, interpretation, and category breakdown.

## ⚠️ Disclaimer

### Important Information

**This is an educational tool and NOT a clinical diagnostic instrument.**

- ❌ **Not for clinical diagnosis** - Cannot diagnose Narcissistic Personality Disorder (NPD)
- ❌ **Not a substitute for professional evaluation** - Consult licensed mental health professionals
- ❌ **Not for medical decision-making** - Results are for self-reflection only

### What This Tool Is

- ✅ Educational prototype for academic purposes
- ✅ Self-reflection instrument based on NPI framework
- ✅ Research tool for understanding personality traits
- ✅ Demonstration of rule-based personality assessment

### Ethical Considerations

- No personal identifying information is collected
- All data stored anonymously in local database
- Clear informed consent obtained before assessment
- Comprehensive disclaimers provided throughout
- Results emphasize traits vs. disorders

### Professional Guidance

If you have concerns about narcissistic personality patterns affecting your relationships or well-being, please consult a licensed mental health professional for proper evaluation and support.

## 👥 Team

**Riphah International University, Islamabad**  
**Faculty of Computing**  
**Senior Design Project**

- **Falak Irfan** (50029) - BSSE - [50029@students.riphah.edu.pk](mailto:50029@students.riphah.edu.pk)
- **Anisa Kanwal** (44527) - BSSE - [44527@students.riphah.edu.pk](mailto:44527@students.riphah.edu.pk)
- **Aroosa Nadeem** (44880) - BSSE - [44880@students.riphah.edu.pk](mailto:44880@students.riphah.edu.pk)

## 🔮 Future Enhancements

Potential improvements for future versions:

- [ ] Integration of AI-based NLP for open-ended responses
- [ ] Multi-language support
- [ ] Export results to PDF
- [ ] Admin dashboard for viewing aggregate data
- [ ] Dark Triad assessment (Narcissism, Machiavellianism, Psychopathy)
- [ ] Mobile app development (Flutter/React Native)
- [ ] Cloud deployment with user authentication
- [ ] Comparative analysis with population norms
- [ ] Progress tracking across multiple assessments

## 📄 License

This project is licensed under the MIT License - see below for details:

```
MIT License

Copyright (c) 2025 Riphah International University

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

## 🙏 Acknowledgments

- Narcissistic Personality Inventory (NPI) framework
- Riphah International University Faculty of Computing
- Gradio team for the excellent web framework
- All contributors and testers

## 📞 Contact & Support

For questions, issues, or contributions:

- **Email:** [50029@students.riphah.edu.pk](mailto:50029@students.riphah.edu.pk)
- **GitHub Issues:** [Report a bug or request a feature](https://github.com/yourusername/narcissism-assessment/issues)

---

**⭐ If you find this project helpful, please consider giving it a star on GitHub!**

---

*Developed with ❤️ by Falak Irfan Undergraduate Software Engineer *
