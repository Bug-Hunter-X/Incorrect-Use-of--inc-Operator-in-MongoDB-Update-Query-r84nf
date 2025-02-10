# MongoDB $inc Operator Bug
This repository demonstrates a common error when using the `$inc` operator in MongoDB update queries.

The bug arises from using a string value instead of a numeric value with `$inc`. This prevents the field from being incremented correctly.

## Bug
The `bug.js` file shows the incorrect usage of the `$inc` operator:
```javascript
db.collection('myCollection').updateOne({ _id: 1 }, { $inc: { field: '1' } });
```
The solution is in the file `bugSolution.js`

## Solution
The `bugSolution.js` file demonstrates the correct usage:
```javascript
db.collection('myCollection').updateOne({ _id: 1 }, { $inc: { field: 1 } });
```
By using the numeric value `1` instead of the string `'1'`, the `$inc` operator functions as expected.