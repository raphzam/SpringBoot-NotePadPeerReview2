#SpringBoot Peer Review 2

//HomeControl.java   import org.springframework......  @Controller public class HomeControl {  @GetMapping("/employeeform") public String loadFormPage(Model model) { model.addAttribute("employee", new Employee()); return "employeeform";  }  @PostMapping("/employeeform") public String loadFromPage(@ModelAttribute Employee employee, Model model) { model.addAttribute("employee", Employee); return "confirmemployee"; } } 
From Nora Yu to Me: (Privately) (4:41 PM)
 //employeeform.html <!DOCTYPE html> <html lang="en" xmlns:th="http://www.thymeleaf.org"> <head> <meta charset="UTF-8"> <title>Title</title> </head> <body>   <form th:action="@{/employeeform}" th:object="${employee}" method="post"> First Name: <input type="text" th:field="*{lastName}" /> <br/> Last Name: <input type="text" th:field="*{lastName}" /> <br/> Email Address: <input type="text" th:field="*{emailAddress}" /> <br/> Phone Number: <input type="number" th:field="*{phoneNumber}" /> <br/> Address: <input type="text" th:field="*{address}" /> <br/> City: <input type="text" th:field="*{city}" /> <br/> State: <input type="text" th:field="*{state}" /> <br/> Zipcode: <input type="number" th:field="*{zipCode}" /> <br/>  <input type="submit" value="Submit"/>   </form> </body> </html> 
From Nora Yu to Me: (Privately) (4:42 PM)
 //confirmemployee.html   <!DOCTYPE html> <html lang="en" xmlns:th="http://www.thymeleaf.org"> <head> <meta charset="UTF-8"> <title>Title</title> </head> <body>  <p th:inline="text"> First name is: [[${Employee.firstName}]] <br/> Last name is: [[${Employee.lastName}]] <br/> Email Address: [[${Employee.emailAddress}]] <br/> Phone Number: [[${Employee.phoneNumber}]] <br/> Address: [[${Employee.address}]] <br/> City: [[${Employee.city}]] <br/> State: [[${Employee.state}]] <br/> Zipcode: [[${Employee.zipCode}]] <br/> </p>  </body> </html>