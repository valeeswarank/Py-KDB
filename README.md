# Py-KDB
Python kdb+ concepts

Python Details
======================================
Python 3.7.9 (64 bit)
Windows 10 Home Edition


KDB+ Details
======================================
Please follow the same instruction as per the documentation to copy the q.exe. It should be in the same directory
structure. As well as copy the license file in the outer directory.

C:\q\w64\q.exe


# dates
dates:2018.01.01+1000000?31
# times

times:1000000?24:00:00.0000
# qty
qtys:100*1+1000000?100

# iteration
ixs:1000000?3

# symbol
syms:`appl`amzn`googl ixs
# price
pxs:(1+1000000?.03)*172.0 1189.0 1073.0 ixs

# creating table
t:([] date:dates; time:times; sym:syms;qty:qtys;px:pxs)

# accessing table
t
t:`date`time xasc t
# display only 5 rows
5#t
15#t
-15#t
select date, time, px from t

select date, time, px from t

select date, time, qty, px from t

select date, time, qty, syms, px from t

select date, time, qty, px from t where syms=`appl

\t select date,time,qty,px from t where syms=`appl

select open:first px, close:last px by date, time from t where syms=`appl

5#select open:first px, close:last px by date, time from t where syms=`appl

5#select open:first px, close:last px, lo:min px, hi: max px by date, time from t where syms=`appl

select mins px from t where syms=`appl

\t select mins px from t where syms=`appl

# Opening port
\p 4242
cub3:{x*x*x}
cub3:{0N!x*x*x}

# access from client 
h:hopen `::4242
h "6*7"
h (`cub3; 5)
(neg h) (`cub3; 5)

`abc`def
count `abc`def
("valee"; "bhuvana"; "rishi"; "vaishu")
count ("valee"; "bhuvana"; "rishi"; "vaishu")
`:names.txt 0:("valee"; "bhuvana"; "rishi"; "vaishu")
read0 `:names.txt
