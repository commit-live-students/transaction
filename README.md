![GitHub Logo](https://s3.ap-south-1.amazonaws.com/greyatom-social/GreyAtom-logo.png)

# DBMS - Transaction

A transaction can be defined as a group of tasks. A single task is the minimum processing unit which cannot be divided further.

Let’s take an example of a simple transaction. Suppose a bank employee transfers Rs 500 from A's account to B's account. This very simple and small transaction involves several low-level tasks.

***A’s Account***

    Open_Account(A)
    Old_Balance = A.balance
    New_Balance = Old_Balance - 500
    A.balance = New_Balance
    Close_Account(A)


***B’s Account***

    Open_Account(B)
    Old_Balance = B.balance
    New_Balance = Old_Balance + 500
    B.balance = New_Balance
    Close_Account(B)

A transaction is a very small unit of a program and it may contain several lowlevel tasks. A transaction in a database system must maintain Atomicity, Consistency, Isolation, and Durability − commonly known as ACID properties − in order to ensure accuracy, completeness, and data integrity.

### States of Transactions
![Transaction States](https://s3.ap-south-1.amazonaws.com/greyatom-social/transaction_states.png)
* ***Active*** − In this state, the transaction is being executed. This is the initial state of every transaction.
* ***Partially Committed*** − When a transaction executes its final operation, it is said to be in a partially committed state.
* ***Failed*** − A transaction is said to be in a failed state if any of the checks made by the database recovery system fails. A failed transaction can no longer proceed further.
* ***Aborted*** − If any of the checks fails and the transaction has reached a failed state, then the recovery manager rolls back all its write operations on the database to bring the database back to its original state where it was prior to the execution of the transaction. Transactions in this state are called aborted. The database recovery module can select one of the two operations after a transaction aborts −
    - Re-start the transaction
    - Kill the transaction
* ***Committed*** − If a transaction executes all its operations successfully, it is said to be committed. All its effects are now permanently established on the database system.
