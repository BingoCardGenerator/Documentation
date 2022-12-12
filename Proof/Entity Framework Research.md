# How can Entity Framework speed up the development of the Bingo Card Generator project?

## Table of Contents

- [How can Entity Framework speed up the development of the Bingo Card Generator project?](#how-can-entity-framework-speed-up-the-development-of-the-bingo-card-generator-project)
  - [Table of Contents](#table-of-contents)
  - [Subquestions](#subquestions)
    - [What is the entity framework? (Library research)](#what-is-the-entity-framework-library-research)
    - [How does entity framework work? (library research)](#how-does-entity-framework-work-library-research)
    - [How to implement EF in the bingo card APIs? (Prototype)](#how-to-implement-ef-in-the-bingo-card-apis-prototype)
  - [Conclusion](#conclusion)
  - [Scources](#scources)

## Subquestions

### What is the entity framework? (Library research)

Entity framework is a lightweight data acess framework. It makes it easy to make, intergrate and maitain a SQL database for your project.
It can serve an ORM wich enabels you to use your database with .NET objects. And makes it so you do not have to write Data acces code.

### How does entity framework work? (library research)

With EF core, data acces is done trough a model.
A model consists of entity classes and a context object wich represents the database session. The context object does the queriying and the saving of the data.

To use entity framwork you have to first make a model. You can either generate one from an exsiting database or you can make one yourself by hand. Once a model has been created EF Migrations has to make a databse from the model. Migrations alow evolving the database as the model changes.

### How to implement EF in the bingo card APIs? (Prototype)

To intergrate EF into the APIs the NUGet packages first have to be installed. Once this is done a model (context) can be created.
![EFDataContext](EFDataContext.png)

Then the comand Add-Migration MyMigration can be ran (where MyMigration is the name of the migration). This command will then generate the migration that EF uses to create the database
![EFMigration](EFMigration.png)

Optinally a database seed can be created that will run when the application starts and will fill the database with some predetermined data. But this is not part of EF and not required.

## Conclusion

Entity Framework can help implement and maintain the databse in the bingo card generator project by trivializing the quering of data as well as creating the databse. It does all the annoying database work for you and alows you to focus on actually creating the application.

## Scources

[used on 12-12-22](https://learn.microsoft.com/en-us/ef/core/)
