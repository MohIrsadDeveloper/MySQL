Id firstName lastName Age Education City 

<!-- Practice -->
<!-- 
        select * from familyList where age >= 18 AND age <= 25;
    select * from familyList where age = 18 or age = 16;
    select * from familyList where not age = 25 and not age = 18;
    select * from familyList where age in (18, 25, 19, 33, 26) and city in ("mumbai");
    select * from familyList where age = 18;
    select * from familyList where firstName like "a%";
    select * from familyList where firstName like "a%l";
    select * from familyList where firstName like "%a";
    select * from familyList where firstName like "%__%";
    select * from familyList where firstName like "_sm%_";
    select * from familyList where firstName like "_f%__l";
    select * from familyList where firstName like "%as%";
    select * from familyList where age between 20 and 30;
    select * from familyList where age not between 20 and 30;
    select * from familylist order by age ASC;
    select * from familylist order by age DESC;
    select distinct lastName from familylist;
    select distinct city from familylist;
    select distinct education from familylist;
    select * from familylist limit 4;
    select * from familylist limit 4 offset 4;
    select count(firstName) from familylist;
    select sum(age) from familylist;
    select max(age) from familylist;
    select min(age) from familylist;
    select avg(age) from familylist;
 -->

<!-- Set to authentication for nodejs -->
 ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
flush privileges;

show databases;
drop database time;
create database time;
use time;
create table event(
	id int primary key auto_increment not null,
    ts timestamp,
    description varchar(20)
);
select * from event;
insert into event(ts, description) values (current_timestamp(),"first");
SELECT * 
FROM event 
WHERE ADDTIME(now(), '02:00:00') > ts;
update event set ts=addtime(now(), "02:00:00") where id=1;
select * from event where ts>now();