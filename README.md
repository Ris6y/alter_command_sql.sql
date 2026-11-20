# alter_command_sql.sql
drop database if exists ddl_commands;
create database ddl_commands;
use ddl_commands;

create table my_table(
id int,
name varchar(100) not null,
age int not null,
created_at timestamp default current_timestamp);
insert into my_table (id, name, age)
values
(1, 'Rohit', 25),
(2, 'Sachin', 35),
(3, 'Vikas', 28);
-- create my_table2
-- create my_table2
create table my_table2(
     id int,
     description varchar(255) not null
     );
     
-- insert data into my_table2
insert into my_table2 (id, description)
values
(1, 'Item 1'),
(2, 'Item 2'),
(3, 'Item 3');

select * from my_table;
select * from my_table2;

-- #1
alter table my_table
change column name full_name varchar(100) not null;

-- #2
alter table my_table
modify age bigint not null;

-- #3 
alter table my_table
add column email varchar(100) not null;

-- #4
alter table my_table
add column middle_name varchar(50) after full_name;

-- #5
alter table my_table 
add column EMP_Rank int first;

-- #6
alter table my_table
modify created_at datetime;

-- #7
alter table my_table
modify description text;

-- #8
alter table my_table
modify column full_name varchar(255) null;

-- #9
alter table my_table
add primary key(id);

-- #10
alter table my_table
drop column middle_name;

-- #11
alter table my_table
rename column email to email_add;

-- #12
alter table my_table
modify age int null;

-- #13
alter table my_table2
add constraint fk_id
foreign key (id)
references my_table(id);

-- #14
alter table my_table2
drop foreign key fk_id;

-- #15
alter table my_table2
modify full_name varchar(200) not null;

-- #16
drop table my_table2;

-- #18
alter table my_table
drop primary key;

-- #19
alter table my_table
drop column age;

-- #20
drop database ddl_commands;   
   
          
