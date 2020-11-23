
# Assignment

## Input

There is family-tree.csv with 999999 records.
data format is following:
id (int), parent (int), full name

## Task

We need to create utility that renders subtree.

$ python tree.py [start_id] [depth] [--up/--down] [--tree/--csv]

All arguments are optional.

### start_id
This is position where the new subtree starts.
Corespondents to "id" in the source data.

Default value: 1

### depth
Defines how many steps up or down should be taken.
Take this as "render radius", by tae into account direction.

a) When direction is down, just render as many nodes in all branches,
as it is defined in "depth".
b) When direction is "up", go "up" as many steps as defined in "depth",
and render from that node down using "depth" value, same as a).

### direction
Defines direction of tree traversal. See "depth", for details.

NB! --up --down can be used together. 

Default value: --down

### format
Result output format.

--csv renders in source format into console (csv without header):
id (int), parent (int), full name

--tree renders pseudo-graphics using asciitree library, or similar

Default value: --tree 

## Examples

$ python tree.py
Renders 10 nodes down starting from 1 in ascitree format.

$ python tree.py 1001 100 --csv
Renders 10 nodes down starting from 1001 in csv format.

$ python tree.py 1001 100 --up --down --csv
Renders 10 nodes up and down starting from 1001 in csv format.
 
