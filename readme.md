# logs-analysis
Project Version 2.0 
## Description
An internal reporting tool for a newspaper website that determines: what are the most popular articles, who are the most popular authors, what percentage of requests returned errors and then prints out that information.
### Installation
Requires Udacity’s Linux-based virtual machine and associated news-website database.
Instructions for installing the VM and data follow.
#### *Download and Install*:
* [VirtualBox](https://www.virtualbox.org/wiki/Downloads)
* [Vagrant](https://www.vagrantup.com/downloads.html)
* [Newsdata](https://d17h27t6h515a5.cloudfront.net/topher/2016/August/57b5f748_newsdata/newsdata.zip)

Note: install Vagrant into a different directory from VirtualBox.

#### *Set-up the VM*
* Navigate to the Vagrant directory using the commandline.
* Set up the machine.
* Log in.
```
cd /path/fsnd-virtual-machine/vagrant
vagrant up
vagrant ssh
```
* Outside the machine, place unzipped data file into the vagrant directory.
* cd back into the vagrant directory
* Load the dataset.
```
psql -d news -f newsdata.sql
```

### Usage
Runs from the command line, specifically from the vagrant directory within the vagrant virtual machine. Ensure that you are logged into the machine.
```
vagrant ssh
vagrant@vagrant:~$ cd /vagrant
vagrant@vagrant:/vagrant$ python logs-analysis-rev.py
```
## Issues
**Cannot** be run from outside the virtual machine. Fails to connect to the virtual machine.

The order of the SQL queries contained in the list: *query_list* is crucial; *query_list* or elements thereof are passed into a number of functions which depend on the order of the elements in *query_list*. Specific functions that will need to be adjusted if query_list is modified are:
```
format_authors_articles()
format_errors()
final_solution_layout()
```
