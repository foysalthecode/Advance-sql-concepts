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


