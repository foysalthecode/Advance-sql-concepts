# SUB QUERY

## find the highest salary

    select max(salary) from employees

## find which employee get the highest salary

    select * from employees where salary = (select max(salary) from employees)

## find employees who earn more than the avg salary

    select * from employees where salary > (select avg(salary) from employees)

## name of the employee who gets the highest salary in the HR Department

    select * from employees where salary = (
    select max(salary) from employees where department = 'HR'
    )

# FUNCTION OR PROCEDURE

    Function ke procedure bole sql er language a

## show how many employees are there by function

    create function emp_count()
    returns int
    language sql
    as
    $$
      select count(*) from employees
    $$

    select emp_count()

## delete a employee by a function

    create function delete_emp_id(emp_id int)
    returns void
    language sql
    as
    $$
      delete from employees where id = emp_id
    $$

    select delete_emp_id(5) --> this will delete the employee whos id is 5
