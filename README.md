# MongoDB $inc operator error
This example demonstrates an incorrect usage of the $inc operator in MongoDB update operations. The $inc operator is used to increment or decrement a numeric field by a specified value. However, in this example, a string value is provided as the increment value, which results in an error.

## Bug
The bug is in the following line of code:
```javascript
db.collection.updateOne({"_id": 1}, {"$inc": {"field": "1"}});
```
The value "1" is a string, not a number, resulting in an error when MongoDB attempts to perform the increment operation. 

## Solution
The solution is to provide a numeric value to the $inc operator, as shown in the following code:
```javascript
db.collection.updateOne({"_id": 1}, {"$inc": {"field": 1}});
```