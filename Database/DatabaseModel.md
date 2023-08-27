# Database

## ACID properties

1.  A : Atomicity --> either all the changes should reflect or none of them should be there
2.  C : Consistency --> after making all the changes they should not violate any DB rule
3.  I : Isolation --> all the transactions that are happening should not affect one another
4.  D : Durability --> after changes are committed they should be there forever

```python
               PARTIALLY COMMITTED -------> COMITTED
               ^            \
              /              \
             /                V
    ACTIVE ----------------> FAILED -------> ABORTED
```

## Isolation

You can ensure isolation using serializability

1. Conflict serializability
2. View serializability
    - Cascadeless scheduling :- you sould read the values of committed writes only otherwise you need to rollback in cascade fashion.

## Database transctions design

If you put two saperate database like order and products in same place then majorly these problems may arise

1. Dependance - They will depend on each other and they can not exist without the other one.
2. Slow - Updation on one product will be very slow because now you need to update all the products

## Database design

Here are the important points to keep in mind before creating database

1. First Normal form
2. Second Normal form
3. Third Normal form
4. Boyce cott normal form
5. Functional dependancy
