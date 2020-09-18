# Use case to or rules

Company run Sirius Custody system and define next policy to authorise transactions.

-------------

### 1. Not small transaction should be approval by 2 emploee of customer support departament or Jon from finance control departamet

**Condition:** transaction total amount is more than 1 BTC or 10 ETH

**Requires:** get 2 votes

**Audience:**
name | position | number of votes (weight)
---- | -------- | ------------------------
Alise | officer of the customer support department | 1
Bob | officer of the customer support department | 1
Jon | officer of the finance department | 2

-------------

### 2. with an abnormally large volume of transfers during the day, transactions should be approved by someone from the finance control department

**Condition:** daily total amount, including this transaction, is more than 10 BTC or 30 ETH

**Requires:** get 1 votes

**Audience:**
name | position | number of votes (weight)
---- | -------- | ------------------------
Kristine | officer of the finance department | 1
Jon | officer of the finance department | 1

-------------

### 3. transactions with all other assets must be approved by the staff of the finance department

**Condition:** asset in the transaction is not BTC or ETH

**Requires:** get 2 votes

**Audience:**
name | position | number of votes (weight)
---- | -------- | ------------------------
Michael | officer of the finance department | 1
Kristine | officer of the finance department | 1
Jon | officer of the finance department | 1
Vlad | head of the finance department | 2

-------------

### 4. It is forbidden to transfer large amounts for 1 transaction using BTC and ETH

**Condition:** transaction total amount is more that 40 BTC or 400 ETH

**Requires:** Decline transaction

**Audience:**
name | position | number of votes (weight)
---- | -------- | ------------------------

-------------



