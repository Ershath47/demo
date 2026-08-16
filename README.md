# Demo Project – CI/CD with GitHub Actions

## Git Workflow

```bash
# Clone the repository
git clone https://github.com/Ershath47/demo.git
cd demo

# Add Student Tests
git checkout -b feature/add-student-tests
git add AddStudentTest.java
git commit -m "test(add-student): verify valid student addition"
git commit -m "test(add-student): check duplicate ID error"
git commit -m "test(add-student): handle underage student case"
git push origin feature/add-student-tests

# Edit Student Tests
git checkout main
git checkout -b feature/edit-student-tests
git add EditStudentTest.java
git commit -m "test(edit-student): verify student edit functionality"
git push origin feature/edit-student-tests

# Delete Student Tests
git checkout main
git checkout -b feature/delete-student-tests
git add DeleteStudentTest.java
git commit -m "test(delete-student): verify student deletion"
git push origin feature/delete-student-tests

# Merge branches into main
git checkout main
git merge feature/add-student-tests
git merge feature/edit-student-tests
git merge feature/delete-student-tests
git push origin main
