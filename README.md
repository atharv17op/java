
Problem Statement: Create a class called Employee that includes three pieces of information as
instance variables- first name, a last name and a monthly salary. Your class should have a constructor
that initializes the three instance variables. Provide a set and a get method for each instance variable. If
the monthly salary is not positive, set it to 0.0. Write a test application named EmployeeTest that
demonstrates class Employee's capabilities. Create two Employee objects and display each object's
yearly salary. Then give each Employee a 10% raise and display each Employee's yearly salary again.


class Employee {
 private String firstName;
 private String lastName;
 private double monthlySalary;
 public Employee(String firstName, String lastName, double monthlySalary) {
 this.firstName = firstName;
 this.lastName = lastName;
 this.monthlySalary = (monthlySalary > 0) ? monthlySalary : 0.0;
 }
 public String getFirstName() {
 return firstName;
 }
 public void setFirstName(String firstName) {
 this.firstName = firstName;
 }
 public String getLastName() {
 return lastName;
 }
 public void setLastName(String lastName) {
 this.lastName = lastName;
 }
 public double getMonthlySalary() {
 return monthlySalary;
 }
 public void setMonthlySalary(double monthlySalary) {
 if (monthlySalary > 0) {
 this.monthlySalary = monthlySalary;
 } else {
 this.monthlySalary = 0.0;
 }
 }
 public double getYearlySalary() {
 return monthlySalary * 12;
 }
 public void giveRaise(double percentage) {
 if (percentage > 0) {
 this.monthlySalary += this.monthlySalary * (percentage / 100);
 }
 }
}
public class EmployeeDemo{
 public static void main(String[] args) {
 Employee emp1 = new Employee("John", "Doe", 3000);
 Employee emp2 = new Employee("Jane", "Smith", 4000);
 System.out.println("Yearly Salary of " + emp1.getFirstName() + " " + emp1.getLastName() + ": $" +
emp1.getYearlySalary());
 System.out.println("Yearly Salary of " + emp2.getFirstName() + " " + emp2.getLastName() + ": $" +
emp2.getYearlySalary());
 emp1.giveRaise(10);
 emp2.giveRaise(10);
 System.out.println("After 10% raise:");
 System.out.println("Yearly Salary of " + emp1.getFirstName() + " " + emp1.getLastName() + ": $" +
emp1.getYearlySalary());
 System.out.println("Yearly Salary of " + emp2.getFirstName() + " " + emp2.getLastName() + ": $" +
emp2.getYearlySalary());
 }
}
