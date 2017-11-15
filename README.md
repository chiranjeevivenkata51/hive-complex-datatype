# hive-complex-datatypes
Step1:
hive>create table complexes(sno int,name array<string>,no map<string,bigint>,co  struct<co:string,pincode:string>)row format delimited fields terminated by ' ' collection items terminated by ',' map keys terminated by ':';
hive> load data local inpath "/home/cloudera/at" into table complexes;
hive> select name[0],no['personal'],co.co from complexes;
OK
sai	268	India
chi	78	usa
Time taken: 0.188 seconds, Fetched: 2 row(s)
Data:
1 sai,chi personal:268,office:879 India,520002
2 chi,mani personal:78,office:877 usa,2598

