# Pizza Mama | CS50 Project

#### Video Demo:  <https://youtu.be/q0LYZMzz9cM>

#### Description: 

A web application of a pizzeria developed with . Net Core and C# allow customers to visit and see on the site, the different pizzas on the menu with the ingredients and the price. These pizzas come directly from the database created with EntityFramework Core. There is an administrator interface that is not visible to the customer allowing the administrator to manage the site and the data, to be able to create, modify or delete a pizza from the database. A Rest API was also developed to be able to retrieve pizzas from the database and transfer them to other applications such as a mobile application developed with Xamarin Form and CSharp for example. In the future, this application may contain a feature that will allow customers to order.

This project contains different Folder we can find first the Dependencies which will contain our packages including the nugets EntityFramework in order to create a database and to be able to store, modify or delete the pizzas in a database. We have Models Views Controllers folders.

There is Root which contains folders CSS, images, js, lib for all images, design, animations or content to add in our site.

The Models folder is the logic that is what reprsente our data that is here that I created my classes and that I have my objects. In this one we find the object Pizza which is represented by the name of class Pizza.cs. This file contains the properties: PizzaID, name, price, vegetarian and ingredients with a DisplayName to rename the names correctly in the eyes of the admin. A JsonIgnore to ignore the DisplayName. Then a condition and a Split() to spar the ingredients register if they are not null with ", ".

The Controllers folder saves the user’s request for example to access a page of the application and saves the data saved in the requested page and retrieves it in the Models and the database and returns it to the View which it will send to the browser for the user to receive it. It is a very useful and efficient pattern that allows to structure the project and if we change one thing it will not impact the rest of the files. Here my Controllers folder contains my ApiController used to retrieve all the pizzas saved in the database and display them in another application for example: a desktop application or a mobile and tablet application created with Xamarin Forms.

In the Data folder there is the DataContext which will allow me to link my Pizza data with EntityFramework and the database.
In the Pages folder there is the Admin folder and inside the Pizzas folder which contains the Razor pages which are pages between a mixture of Html and Csharp. We mainly find html tags like a form for example.
These are the Create, Delete, Edit and Index pages for administrator-managed pizza management and these pages have their own subpages of the same name to connect these pages to the EntityFramework Core database. In the file create.html.cs we can find lines of CSharp code that allow the connection to the database with dataContext and a creation of a pizza by adding it to the database and then saving the creation to the database with mainly these 2 elements to make it short: 
                               _context.Pizzas.Add(Pizza);
                              await _context.SaveChangesAsync();

And we find at the same level as the Pizzas folder, the index.cshtml page which is the home page of the Admin part, with the login and password for the connection.

Below is the Shared folder containing the _Layout.cshtml. This file is the body of the site with the links bootsrap, the head, the body and the footer. This page specifies the condition: If the administrator is authenticated on the admin page then the logOut link is displayed.

There are a lot of files you don’t need to take care of and don’t touch like _ValidationScripts
partial.cshtml, _ViewImports.cshtml, Error.cshtml which handles errors.

Then below is another index.cshtml page which is the Home Page of the website. The home page the customer sees before accessing the menu. Then there is the MenuPizzas page which contains the pizzas with name, price, ingredients and vegetarian badge or not.

The appsettings.json file is the one that has the connection codes for the authentication of the administrator and the link to the PizzaMama.dbdatabase.

Program.cs is our boot file like any . Net Core application. The README.md file below to discover the important information for the realization of this project.

And the startup.cs file that allows us to use app.UseAuthentication() authentication on the Razor pages; and app.UseAuthorization() authorization; but also the use of our ApiController with endpoints.MapControllers();
