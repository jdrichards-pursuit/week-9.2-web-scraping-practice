# Team Generator Project Specification (Tier 1)
People Operations Department

## Project Description
Build an automated team formation tool to streamline the sprint team creation process.

[VIDEO EXAMPLE](https://drive.google.com/file/d/18YJBZF9fcPqI_sU9NHRBvoj5nUzh9wQM/view?usp=sharing) - a possible example of what your program should do

## Core Requirements
Your script needs to:
1. Scrape all student names and total points from https://pursuit.codetrack.dev/ site from the `Chrome Browser`
2. Store these names in a CSV for record-keeping
3. Randomize the student order from the CSV file in order to send to the Gemini API for fair distribution
4. Use AI to generate creative team names and group students into teams of 5
5. Output the results in a formatted text file with team names, emojis, and members

**GOTCHAS** 
- Study the Pursuit Codetrack site and understand how it works
- The site is dynamic and has pagination, you need to scrape all pages
- Not all cards in the Pursuit Codetrack have names, you should skip those cards without names without throwing an error. Your program should keep running



## Technical Specifications

### Suggested Libraries
You may add any libraries you'd like to your project.

```python
# Core libraries
import os
from dotenv import load_dotenv  # For API key management
from selenium import webdriver  # For web automation
from bs4 import BeautifulSoup  # For HTML parsing
import csv                     # For data storage
import random                  # For randomization
import time                    # For rate limiting
```

### Suggested Function Structure
- `setup_api()`: Configure API credentials and return client
- `scrape_student_data(url, num_students)`: Web scraping logic
- `save_to_csv(data, filename)`: Data export functionality
- `load_and_randomize_data(filename)`: Data processing
- `generate_teams(students, team_size)`: Team creation logic
- `save_team_assignments(teams, filename)`: Output generation

### Recommended Output Format for Text File
```
🚀 [Team Name]
• [Student Name]
• [Student Name]
• [Student Name]
• [Student Name]
• [Student Name]

[Next team...]
```

## Deliverables
1. Python script that runs end-to-end with error handling using try..except blocks
2. Generated CSV file with student names
3. Final text file with team assignments

## Technical Resources
- [Python Virtual Environment Setup](https://github.com/jdrichards-pursuit/python-virtual-environment-setup) - remember you do not need to select the ipykernel or select the shell using a .py file
- [Web Scraping In ClassTheory Training](https://github.com/jdrichards-pursuit/week-9.1-web-scraping-and-sentiment-analysis-theory)
- [BeautifulSoup Documentation](https://beautiful-soup-4.readthedocs.io/en/latest/)
- [Selenium Documentation](https://selenium-python.readthedocs.io/)
- [Pathlib Documentation](https://docs.python.org/3/library/pathlib.html)
- [CSV Documentation](https://docs.python.org/3/library/csv.html)
- [JSON Documentation](https://docs.python.org/3/library/json.html)
- [Random Documentation](https://docs.python.org/3/library/random.html)
- [Time Documentation](https://docs.python.org/3/library/time.html)
- [Gemini API](https://cloud.google.com/vertex-ai/generative-ai/gemini/gemini-1.5-flash)
- [Chrome Browser](https://www.google.com/chrome/)
- [Gemini API Documentation](https://ai.google.dev/gemini-api/docs)
- [Python Documentation](https://docs.python.org/3/)

## Technical Stretch Goals
- Implement rate limiting for web scraping
- Handle API rate limits
- Clean data validation

[Back to Assignment Brief](./readme.md)