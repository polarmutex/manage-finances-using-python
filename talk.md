[title slide]
Hello, my name is Brian Ryall. I am a software engineer for the University of Dayton Research Institute. Today I am going to give a overview of “How I use Python to manage my finances” using the beancount library. At the bottom of this slide is my contact info.

[features slide]
So what does beancount provide? 
First it is a **plaintext accounting** library which means all the input files are in readable and documented format on disk. What I like most about his I able to version control the source files to add context and additional input while committing changes. It is also easy to script into or out of the syntax it uses and there are many of these are already written for common budget programs
**Double-Entry Accounting**, which means every entry into an account has a opposite entry from a different account.
**Reports**, beancount can generate account balances, income vs expenses, and net worth reports
**API** api to import/export/change/add transactions contain in the source files
**CLI** cli for common used operations
**Investment** able to report profit/loss, trade lots, splits, cost basis adjustments, and more
**plugin architecture** that allows to transform your transactions or create new ones that are not contain in the source files

[plaintext format]
Now lets take a look at what transactions look like in the source files.
Here is an example of what a **transaction** and directive looks like. Each transaction has a date, flag(to denote pending and completed) and Payee string on the first line. The following lines contain entries that must sum to zero. each entry line contains on the left side of the entry represents the account followed a amount to be applied to that account.
**Directives** are ways to supplement metadata or supply checks into the source files. For example this directive states the balance of an account on a particular date to be a certain value. If the the balance of the account is not equal, an error will be generated. This is a great way to reconcile accounts and catch mistakes that might have been made

[Beancount Query Language]
Beancount also comes with its own powerful query language to refine and manipulate the data. For example here is a monthly expense report

[fava]
The final piece i want to show is fava which is a web view to view tables and charts of all the information available in beancount. Fava is also plugin api so you are able to add customized views or new features.

[end]
Finally here are some resources to get further information on beancount. I highly recommend the google group which contains a lot of the discussion and answers to common questions.

As a plug I am currently working on a envelope budgeting plugin for fava and making better tools to edit beancount files in the VIM editor. These can be found on my github page. 