# CRUD-package

This package gives you a simple CRUD service for any initial development, or prototyping for web applications.

Package Features:

1. Saving to LocalStorage,
2. Synchronous, or asynchronous operation.
3. The total changes object - the package knows how to return  
   an object describing all the changes made to the data Array you have passed when creating the class instance.

## How to use

```
npm install crud-Suit
```

```
import CRUD from 'crud-suit'
const crudService = new CRUD([data | Array], [save to LocalStorage | boolean], [name of key in LocalStorage | string], [asynchronous CRUD | boolean])
```

## Methods

1. query - will return the data Array

```
crudService.query()
```

2. getById - will take un \_id and will return the object matching that \_id

```
crudService.getById(entityId)
```

3. remove - will take \_id end splice it from the data Array

```
crudService.remove(entityId)
```

4. getEmptyItem - will give return un empty item based on the first object in your data array

```
crudService.getEmptyItem()
```

5. add - will take a new data object and will add it to the data Array with un \_id

```
crudService.add(entity)
```

6. update - will take un object find it inside the data Array and replace it with the new object

```
crudService.update(entity)
```
