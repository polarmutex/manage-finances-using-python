[title slide]
Hello, my name is Brian Ryall. I am a software engineer for the University of Dayton Research Institute. Today I am going to give a overview of “How I use Python to manage my finances” using the beancount and fava packages.

[Background]

First I want to give a background of managing my finances. I have used in the past spreadsheets, quicken, and you need a budget. But all these solutions had issues that prevented me from managing money the way I wanted. Spreadsheets with crazy long formulas over many tabs. Quicken with its large price. You need a budget with the lack of investment support. And with all of these the pain of importing/exporting your data in and out of these systems. Everything I have tried in the past just left we wanting a better solution.

[features slide]
So that brings me to beancount. Even though out of the box, it does not meet all my requirments in a financial system, it provides the ability to add them. beancount loads all your data and provides many ways to process and report on them.

So what does beancount provide? 
First it is a **plaintext accounting** library which means all the input files are in readable and documented format on disk. What I like most about his I able to version control the source files to add context and additional input while committing changes. (more time mention branch)
**Double-Entry Accounting**, which means every entry into an account has a opposite entry from a different account.
**Reports**, beancount can generate account balances, income vs expenses, and net worth reports
**API** api to import/export/change/add transactions contain in the source files
**CLI** command line interface apps for common used operations and reporting
**Investment** able to report profit/loss, trade lots, splits and more
**plugin architecture** that allows to transform your transactions or create new ones that are not contain in the source files

[source file]
To get started we need source files containing our transactions. Here is an example beancount file from github. There are many packages and scripts on github to convert many known apps data into beancount files. 

[plaintext format]
Now lets take a look at what transactions look like in the source files.
Here is an example of what a **transaction**  looks like. 
Each transaction has a date
flag (to denote pending and completed)
and Payee string on the first line. 

Each entry line contains a account on the left followed a amount and currency to be applied to that account on the right. 
Beancount uses a tree with account names using a colon to separate them. However the account names must start with one of the five names here.
Since beancount is using double entry accounting all the amounts must sum to zero.

**Directives** are ways to supplement metadata or supply checks into the source files. For example this directive states the balance of an account on a particular date to be a certain value. If the balance of the account is not equal, an error will be generated. This is a great way to reconcile accounts and catch mistakes that might have been made.
Other directives include open/close, notes, events, and options

[loading a source file]
Now that we have our source files, here is how we load them into beancount with the API. As you can see it returns a list with all the data from the source file. So you could just loop over the data and calculate what you want ....

But beancount provides a great feature to filter and calculate transactions ....

[Beancount Query Language]
Beancount also comes with its own powerful query language to refine and manipulate the data. For example here is a account balance report, a list of expenses for the month, and a monthly expenses report


[fava]
The final piece i want to show takes all these tools to the next level. Which is fava, a web view to view tables and charts of all the information available in beancount.
you can view account balances
you can view income vs expenses and networth

Fava is also has  plugin api so you are able to add customized views or new features.

[end]
Finally here are some resources to get further information on beancount. I highly recommend the mailing list which contains a lot of discussions and answers to common questions.

As a plug I am currently working on a envelope budgeting plugin for fava and making better tools to edit beancount files in the VIM editor. These can be found on my github page. 

Thanks for your time
