News Portal Application
Welcome to the News Portal – a web application built using ASP.NET and SQL Server. This platform allows users to view the latest news, submit contact inquiries, and provides an admin panel for managing content.

Key Features ✨
News Section: Users can view news articles with titles, categories, descriptions, and images.
Contact Form: Users can submit inquiries through the contact form, which are stored for admin review.
Admin Panel: Admins can manage the content of the news articles and handle contact form submissions.
Database Schema 🗄
Tables:
News

Stores news articles with fields for the title, category, description, image path, and creation date.

CREATE TABLE [dbo].[News] (
    [NewsID]      INT            IDENTITY (1, 1) NOT NULL,
    [Title]       NVARCHAR (255) NOT NULL,
    [Category]    NVARCHAR (50)  NOT NULL,
    [Description] TEXT           NOT NULL,
    [ImagePath]   NVARCHAR (255) NOT NULL,
    [CreatedAt]   DATETIME       DEFAULT (getdate()) NULL,
    PRIMARY KEY CLUSTERED ([NewsID] ASC)
);
ContactForm

Stores user inquiries with fields for name, email, subject, message, and submission date.

CREATE TABLE [dbo].[ContactForm] (
    [ContactID]     INT           IDENTITY (1, 1) NOT NULL,
    [Name]          VARCHAR (255) NOT NULL,
    [Email]         VARCHAR (255) NOT NULL,
    [Subject]       VARCHAR (255) NOT NULL,
    [Message]       TEXT          NOT NULL,
    [SubmittedDate] DATETIME      DEFAULT (getdate()) NULL,
    PRIMARY KEY CLUSTERED ([ContactID] ASC)
);
Admins

Stores admin credentials with fields for username, email, password, reset token, and token expiry.

CREATE TABLE [dbo].[Admins] (
    [ID]          INT            IDENTITY (1, 1) NOT NULL,
    [Username]    NVARCHAR (50)  NOT NULL,
    [Email]       NVARCHAR (100) NOT NULL,
    [Password]    NVARCHAR (255) NOT NULL,
    [ResetToken]  NVARCHAR (255) NULL,
    [TokenExpiry] DATETIME       NULL,
    PRIMARY KEY CLUSTERED ([ID] ASC),
    UNIQUE NONCLUSTERED ([Username] ASC),
    UNIQUE NONCLUSTERED ([Email] ASC)
);
Getting Started 🚀
2. Set Up the Database:
Create a new database in SQL Server and run the SQL scripts provided above to create the necessary tables.
3. Configure Connection String:
Open the appsettings.json file and update the connection string to point to your SQL Server instance.
4. Run the Application:
Open the project in Visual Studio and run the application.
.
Technologies Used 🖥
ASP.NET (Backend Framework)
SQL Server (Database)
HTML, CSS, JavaScript (Frontend)
Bootstrap (UI Framework)
Connect with Me 🔗
If you have any questions or want to collaborate, feel free to reach out:

💼 LinkedIn: www.linkedin.com/in/kishor-goraniya29
📧 Email: kishorgoraniya2@gmail.com
