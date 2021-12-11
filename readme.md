# Table.lua
Basic table operations that every Lua programmer needs to know.

## Installation
```
require("utils.table")
```

## Copying
```
local t = {1,2,3}
local q = table.copy(t) -- Let's make a copy
--> q = {1,2,3}
q['foo'] = true
q['baz'] = false
table.copy(q, t) -- Now merge the values
--> t = {1,2,3,foo=true,baz=false}
table.clear(q) -- Clear one of the tables
--> q = {}
assert(not table.empty(q), "table is empty")
--> assertion failed!
```

## Counting
```
local t = {"A","A","B"}
local total = table.count(t) -- Count all elements
--> total = 3
local occurs, total = table.count(t, "A") -- Count the number of occurances
--> occurs = 2, total = 3
assert(table.unique(t), "table contains duplicates")
--> assertion failed!
```

## Reversal
```
local t = {1,2,3}
table.reverse(t) -- Reverse in place
--> t = {3,2,1}
local q = table.reverse(t, {}) -- Reverse and make a copy
--> q = {1,2,3}
```

## Randomization
```
local t = {1,2,3,4,5,6,7,8,9,10}
local rand, index = table.random(t) -- Get a random element
--> rand = 7, index = 7
table.shuffle(t) -- Shuffle the table in place
--> t = {3,2,6,9,10,1,7,5,4,8}
```

## Searching
```
local t = {"A","B","C","D","E"}
local first = table.find(t, "C") -- Find the first occurance
--> first = 3
table.insert(t, "C")
local last = table.rfind(t, "C") -- Find the last occurance
--> last = 6
table.find(t, nil) -- Search for a nil value
--> assertion failed!
```