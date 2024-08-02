1.Model Creation and validation:
  
   a) First I have created MVC Project and named it as MVCAssignment1.In Model Folder I have Created Employee.cs class. Model is used for accessing data from the database. so in model class i have written  getter and setter methods for properties such as "Id"(Int),"Name"(String),ëmail(String),"Age"(Int).

   b) Now to provide validation for the email property we have written annotation as [EmailAddress(ErrorMessage = "Invalid Email Address")] .EmailAddress annotation ensures that email follows valid email format. and if the email is not in valid format than message will be printed as "Invalid email Address".

   c)Purpose and Benefits of  using data annotation : 
                                                Data Annotation is used for data validation for developing web based applications.We can apply validation to our attributes using different data annotations.Examples Data annotations are Required, StringLength, MaxLength, Range, Bind, DisplayFormat, Displayname etc.
     Data Annotation helps us to provide validation  to establish controls to model properties. In above example we have used "EmailAddress" annotation to ensure valid email format.In the same way there are different annotation for validation like using "Required" indicates that the property is required field ,"StringLength" annotation defines maximum length for string field, "Range" annotation is used to define the range between two numbers etc.


 2.Controller Action and Routing:
                                  In Controller folder I have Created EmployeeController.cs class. First I have created list of employees.

 i) The first actionmethod is Index which shows list of all employees.

 ii) than second action method is Create which is used to add new employees in list.Above this method we have mentioned as [HttpGet] because the values of attributes are taken  from server.when the crete form is submitted the downword method create accepting employee object will execute. Add employee will be added in our list.Above this method we have used [HttpPost]  because values are stored in our list.

 iii) Than next method is Edit to update the list values. Edit method accept id parameter value.First we check do we have employee record with that id value .if is not there than it will print not found.and if it is there than it returns view.Above this method we have written [httpGet] to take values of employee attributes from server which has user entered in edit form.when submit button is clicked then Edit action method accepting employee object will be executed.in this method we have updated values of employee attributes.

   iv)  The last actionmethod is delete.This method   accept value of id .this id value is checked with list values ,if the record is not present in list it will show not found and if it is id value match than that employee record is deleted from list.And Shows the employee details.

  The routing is provided in Program.cs  file.

3.View Rendering and Data Binding:  

a) To create view right click on action method and click on add view and name it as same as actionmethod.In this view using html and css the view for showing employees,add, edit,delete   is created.  

b)In Asp.net Mvc,binding data between model and views is done by Razor View Engine.The razor view engine allows you to create dynamic Html content using C# code syntax embedded within html. 
The view is typed using @model Employee so that we can get the access to the properties of the model.In edit or update view we have used "asp-for"  which automatically binds the input fields to the model properties and handles validation messages.In Index.cshtml class used to display employee details  we have used Razor syntax to loop through the collecton of employee objects passed to the view and display their properties in a table. when user submits the form in create.cshtml the data will be bound to the Employee object in the controller .so we can process this data to save in the list or database.           

4.Data Access and persistence:
  
  CRUD using Entity Framework
   *First MVC Project is created.
   * right click on project->select manage nuget package->click on browse ->search Microsoft.EntitiFrameworkCore.SqlServer ->click on install.
   *In the same way Microsoft.EntityFramework.Core.Tools.
   *click on Tools->select nuget package manager->click on package manager console->here we have to write command to install model classes

Scaffold-DbContext "server=server name; Database=database name; Trusted_Connection=True; TrustServerCertificte=True;" Microsoft.EntityFrameworkCore.SqlServer -outputdir Models

*Add dbContext line in Program.cs.
*Generate Controllers- 
  right click on the controller folder -> select add-> controller->choose Mvc controller  with views,using entity Framework"from the list.->choose the model class and the dbcontext class that we have created->click add 

 * now run the project.


 Actually I know Entity Framework .I have done crud operation using  entityframework during my training in Fujitsu company.I have written all the steps .I was trying to do this but while running command i got error.And i am unable to solve that error.Thats why i have done crud operation using web forms and shared with you.




