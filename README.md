git clone https://github.com/Ershath47/demo.git
cd demo

git checkout -b feature/add-student-tests
git checkout -b feature/edit-student-tests
git checkout -b feature/delete-student-tests

git add AddStudentTest.java
git commit -m "test(add-student): verify valid student addition"

git add AddStudentTest.java
git commit -m "test(add-student): check duplicate ID error"

git add AddStudentTest.java
git commit -m "test(add-student): handle underage student case"

git push origin feature/add-student-tests
git push origin feature/edit-student-tests
git push origin feature/delete-student-tests

git checkout main
git merge feature/add-student-tests
git merge feature/edit-student-tests
git merge feature/delete-student-tests
git push origin main

Fork → Clone → Branch → Commit → Push → Pull Request → Review → Merge

@Test
public void testAddStudentValid() {
    driver.get("https://cmdv-software-test.vercel.app/index.html");
    driver.findElement(By.id("studentId")).sendKeys("S001");
    driver.findElement(By.id("studentName")).sendKeys("Ali");
    driver.findElement(By.id("studentAge")).sendKeys("20");
    driver.findElement(By.id("addButton")).click();
    Assert.assertTrue(driver.findElement(By.id("studentTable")).getText().contains("Ali"));
}
