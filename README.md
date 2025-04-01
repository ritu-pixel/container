# Python YAML Use Case

This project demonstrates how to use **PyYAML** to read, process, and filter YAML data in Python. The script loads student data from a YAML file and filters students based on a user-defined GPA threshold.

## Features
- Reads student information from a YAML file
- Displays all student records
- Filters students based on a GPA threshold entered by the user

## Prerequisites
Ensure you have Python installed. You can check your Python version using:
```bash
python --version
```

Install the required package **PyYAML**:
```bash
pip install pyyaml
```
![image](https://github.com/user-attachments/assets/cdd7f1d4-f137-4bf1-b882-771344d9aeae)

## Project Structure
```
📂 Python_YAML_Use_Case
│── students.yaml  # YAML file containing student data
│── app.py         # Python script to process YAML data
│── README.md      # Project documentation
```

## Getting Started

### 1. Create `students.yaml`
Create a file named `students.yaml` and add the following sample data:
```yaml
students:
  - name: Alice
    age: 21
    major: Computer Science
    gpa: 3.8
  - name: Bob
    age: 22
    major: Mathematics
    gpa: 3.5
  - name: Charlie
    age: 20
    major: Physics
    gpa: 3.9
  - name: David
    age: 23
    major: Chemistry
    gpa: 3.2
  - name: Eva
    age: 21
    major: Computer Science
    gpa: 3.7
```

### 2. Create `app.py`
Create a Python script `app.py` with the following code:
```python
import yaml

def load_data(file_path):
    with open(file_path, 'r') as file:
        data = yaml.safe_load(file)
    return data

def display_students(students):
    print("\nAll Students:")
    for student in students:
        print(f"Name: {student['name']}, Age: {student['age']}, Major: {student['major']}, GPA: {student['gpa']}")

def filter_students_by_gpa(students, min_gpa):
    filtered_students = [s for s in students if s['gpa'] >= min_gpa]
    print(f"\nStudents with GPA >= {min_gpa}:")
    for student in filtered_students:
        print(f"Name: {student['name']}, Age: {student['age']}, Major: {student['major']}, GPA: {student['gpa']}")

def main():
    data = load_data('students.yaml')
    students = data['students']
    display_students(students)
    min_gpa = float(input("\nEnter minimum GPA to filter students: "))
    filter_students_by_gpa(students, min_gpa)

if __name__ == "__main__":
    main()
```

### 3. Run the Script
Execute the Python script by running:
```bash
python app.py
```

### 4. Expected Output
```
All Students:
Name: Alice, Age: 21, Major: Computer Science, GPA: 3.8
Name: Bob, Age: 22, Major: Mathematics, GPA: 3.5
Name: Charlie, Age: 20, Major: Physics, GPA: 3.9
Name: David, Age: 23, Major: Chemistry, GPA: 3.2
Name: Eva, Age: 21, Major: Computer Science, GPA: 3.7

Enter minimum GPA to filter students: 3.6

Students with GPA >= 3.6:
Name: Alice, Age: 21, Major: Computer Science, GPA: 3.8
Name: Charlie, Age: 20, Major: Physics, GPA: 3.9
Name: Eva, Age: 21, Major: Computer Science, GPA: 3.7
```
![image](https://github.com/user-attachments/assets/16a62304-f499-4c5d-8444-6d9555254a00)

## Troubleshooting
- If `import yaml` fails, install `PyYAML` using:
  ```bash
  pip install pyyaml
  ```
- If using a virtual environment, activate it before running the script:
  ```bash
  source venv/bin/activate  # macOS/Linux
  venv\Scripts\activate     # Windows
  ```
- Ensure you run the script from the correct directory where `students.yaml` is located.
Push to Github
![image](https://github.com/user-attachments/assets/ea67b1a8-a2ae-422c-b991-c27bb938b6e5)

## License
This project is open-source and free to use for learning purposes.

## Author
Developed by [Ritu Raput]

