package Java1Lesson5HW;

import java.util.Arrays;

public class MainApp {
    public static void main(String[] args) {
        Employee[] employees = {
                new Employee("Ivanov", "Smith", "QA Engineer", "smith@gmail.com", "718-555-5555", 5000, 41),
                new Employee("Petrov", "Peter", "QA Engineer", "peter@gmail.com", "718-111-1111", 6000, 55),
                new Employee("Pavlov", "Paul", "Developer", "paul@gmail.com", "718-222-2222", 9000, 35),
                new Employee("Semenov", "George", "QA Lead", "george@gmail.com", "718-333-3333", 7000, 36),
                new Employee("Grigorova", "Nicole", "Product Owner", "nicole@gmail.com", "718-444-4444", 8000, 75)
        };
        System.out.println("List of all employees");
        System.out.println();
        for (int i = 0; i < employees.length; i++){
            employees[i].info();
        }
        System.out.println();
        System.out.println("List of employees older than 40");
        System.out.println();
       for (int i = 0; i < employees.length; i++){
         if (employees[i].getAge() > 40){
             employees[i].info();
         };
       }
        System.out.println();
        System.out.println("List for payroll");
        System.out.println();
        for (int i = 0; i < employees.length; i++){
            employees[i].getPaycheck();
            employees[i].paycheck();
        }
    }
}

