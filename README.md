# Metatables
Tables about tables.

A table is
~~~
    0   1   2
0 0,0 0,1 0,2
1 1,0 1,1 1,2
2 2,0 2,1 2,2
~~~

A table about tables
~~~
       table1 table2 table3
table1 t1,t1  t1,t2  t1,t3
table2 t2,t1  t2,t2  t2,t3
table3 t3,t1  t3,t2  t3,t3
~~~

We can then assume a table is a hash table:

~~~ruby
conditions = {
  "epee"  =>  "ishi",
  "ishi"  => "bache",
  "bache" =>  "epee",
}
~~~

This becomes:

~~~
parallel_conditons = {
  "epee"  => "ishi",
  "ishi"  => "bache",
  "bache" => "epee",
}, {
  "epee"  => "ishi",
  "ishi"  => "bache",
  "bache" => "epee",
}
~~~

Such as modifying a hash table without overwriting the previous hash table.
