# ApiWithIdentityAndBlazor

This project is a simple example of a Clean Architecture with Minimal API and Blazor. 
It is based on the following references:
https://www.youtube.com/watch?v=IRwt1aILfPw

https://www.youtube.com/watch?v=b7OoeiG_BzU

## Folder Structure

- **src**: Source code folder.  
  -> Core:   
  	  |-> **ApiWithIdentityAndBlazor.Domain**: Domain project.  
  	  |-> **ApiWithIdentityAndBlazor.Application**: Application project.  
  -> Shared:   
      |-> **ApiWithIdentityAndBlazor.CrossCutting**: CrossCutting project.  
      |-> **ApiWithIdentityAndBlazor.Infrastructure**: Infrastructure project.  
  -> Apresentation:   
      |-> **ApiWithIdentityAndBlazor.API**: Minimal API project.  
      |-> **ApiWithIdentityAndBlazor.WebClient**: Blazor WebAssembly project.  
- **tests**: Test project.	 
  |-> **Domain.UnitTest**: Unit test project for the Domain project.  
  |-> **Application.UnitTest**: Unit test project for the Application project.	  
  |-> **Application.IntegrationTest**: Integration test project for the Application project.  

## Project references

- **ApiWithIdentityAndBlazor.Domain**  
   |-> No regferences   
- **ApiWithIdentityAndBlazor.Application**   
   |-> ApiWithIdentityAndBlazor.Domain  
- **ApiWithIdentityAndBlazor.Infrastructure**  
   |-> ApiWithIdentityAndBlazor.Application  
- **ApiWithIdentityAndBlazor.CrossCutting**  
   |-> ApiWithIdentityAndBlazor.Domain  
   |-> ApiWithIdentityAndBlazor.Application  
   |-> ApiWithIdentityAndBlazor.Infrastructure  
- **ApiWithIdentityAndBlazor.API**  
   |-> ApiWithIdentityAndBlazor.CrossCutting  
- **ApiWithIdentityAndBlazor.WebClient**  
   |-> No regferences  

### Test Project references  
- **Domain.UnitTest**  
   |-> ApiWithIdentityAndBlazor.Domain  
- **Application.UnitTest**  
   |-> ApiWithIdentityAndBlazor.Application  
- **Application.IntegrationTest**  
   |-> ApiWithIdentityAndBlazor.Application  
   |-> ApiWithIdentityAndBlazor.Domain  
   |-> ApiWithIdentityAndBlazor.Infrastructure  

## Importing libraries  

- In the Domain project, you can import libraries related to your specific domain.  
- In the Application project, you can import libraries like Mapster, MediatR, and FluentValidation.  
- In the Infrastructure project, you can import libraries like Entity Framework Core and SQL Server.  
  |-> Microsoft.EntityFrameworkCore.Tools  
  |-> Microsoft.EntityFrameworkCore.Design  
  |-> Microsoft.EntityFrameworkCore.SqlServer  
- In the CrossCutting project, you can import libraries for logging, authentication, and authorization.  
  |-> Microsoft.AspNetCore.Authentication.JwtBearer  
  |-> Microsoft.AspNetCore.Identity.EntityFrameworkCore  