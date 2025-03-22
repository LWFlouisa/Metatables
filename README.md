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

~~~ruby
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

## Parallel Conditions
~~~ruby
parallel_conditions = {
  "epee"  => "ishi",
  "ishi"  => "bache",
  "bache" => "epee",
}, {
  "active"      => "semi-active",
  "semi-active" => "paused",
  "paused"      => "active",
}

possible_conditions = [
  [[parallel_conditions[0], parallel_conditions[0]], [parallel_conditions[0], parallel_conditions[1]]],
  [[parallel_conditions[1], parallel_conditions[0]], [parallel_conditions[1], parallel_conditions[1]]],
]

main_conditions      = possible_conditions[0][0][0]
secondary_conditions = possible_conditions[0][1][1]

puts main_conditions["epee"]
puts secondary_conditions["semi-active"]
~~~
