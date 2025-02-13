# CRUD-suit

This package gives you a simple CRUD service for any initial development, or prototyping for web applications.

Package Features:

1. Saving to LocalStorage,
2. Synchronous, or asynchronous operation.
3. Total changes Array - the package will record any action done by the service,  
   and will give access to that Array of changes. Each action will be timestamped.
4. timestamp and updatedStamp.

## How to use

```bash
npm install crud-suit
```

```
import CRUD from './node_modules/crud-suit/index.js'
const crudService = new CRUD([data | Array], [save to LocalStorage | boolean], [name of key in LocalStorage | string], [asynchronous CRUD | boolean])
```

## Methods

1. query - will return the data Array  
   When calling this function, a timestamp key will be generated on each object in the Array.

```
crudService.query()
```

2. getById - will take un \_id and will return the object matching that \_id

```
crudService.getById(entityId)
```

3. remove - will take \_id end splice it from the data Array. will not return any data.

```
crudService.remove(entityId)
```

4. getEmptyItem - will return un empty item based on the first object in your data Array

```
crudService.getEmptyItem()
```

5. add - will take a new data object, add it to the data Array with un \_id  
   will return the new object that was created with the \_id.  
   When calling this function, a timestamp key will be generated on the added object.

```
crudService.add(entity)
```

6. update - will take un object find it inside the data Array and replace it with the new object.  
   will not return any data.  
   When calling this function, an updatedStamp key will be created on each object in the Array.

```
crudService.update(entity)
```

7. undoAction - will able you to undo last actions based on snapShot of your data before any crud action.  
   It will return the last snapShot of you'r data before the changes.
   this method will not save the snapShot Array to localStorage.

```
crudService.undoAction()
```

8. getActivities - will keep record of all actions done by the service and timestamp it.
   It will return an activities Array with objects describing the action.

```
crudService.getActivities()
```

# Parameters

```
new CRUD([data | Array], [save to LocalStorage | boolean], [name of key in LocalStorage | string], [asynchronous CRUD | boolean])
```

# First parameter - data | Array

## How to insert your data

The CRUD class instance would take a data Array, containing object items as it's  
first parameter.
In order to ensure all methods are working properly, do not insert your data with id key.  
\_id key for every object will be generated by the CRUD instance.

# Second & third parameter - LocalStorage | boolean, key | String

## working with LocalStorage

LocalStorage will take a Key Value pair to store.
In order to save yor data to local storage, you will need two parameters.
The first parameter is a boolean in order to determine whether the information  
will be kept or not, to LocalStorage.
The third parameter is a string to determine the key for the localStorage collection.

# Fourth parameter - asynchronous | boolean

## Working synchronously and asynchronously

This parameter will take a boolean value to determine whether your CRUD instance will return a simple data format or a Promise based format.
