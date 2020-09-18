# Use case 

The company runs the Sirius Custody system and defines the next policy to authorize transactions

# Transaction signature policy

-------------

### 1. The transaction with BTC and ETH and not a small amount should be approved by 2 employees of the customer support department or Jon from the finance control department

**Condition:** transaction total amount is more than 1 BTC or 10 ETH

**Requires:** get 2 votes

**Audience:**
name | position | number of votes (weight)
---- | -------- | ------------------------
Alise | officer of the customer support department | 1
Bob | officer of the customer support department | 1
Jon | officer of the finance department | 2

-------------

### 2. With an abnormally large volume of transfers during the day, transactions should be approved by someone from the finance control department

**Condition:** daily total amount, including this transaction, is more than 10 BTC or 30 ETH

**Requires:** get 1 votes

**Audience:**
name | position | number of votes (weight)
---- | -------- | ------------------------
Kristine | officer of the finance department | 1
Jon | officer of the finance department | 1
Vlad | head of the finance department | 1

-------------

### 3. Transactions with all other assets must be approved by the several employees of the finance department or by the head of the finance department

**Condition:** asset in the transaction is not BTC or ETH

**Requires:** get 2 votes

**Audience:**
name | position | number of votes (weight)
---- | -------- | ------------------------
Kristine | officer of the finance department | 1
Jon | officer of the finance department | 1
Vlad | head of the finance department | 2

-------------

### 4. It is forbidden to transfer large amounts for a single transaction using BTC and ETH

**Condition:** transaction total amount is more that 40 BTC or 400 ETH

**Requires:** Decline transaction

**Audience:**
name | position | number of votes (weight)
---- | -------- | ------------------------

-------------

### 5. All other transaction should be automatically sign

There are no special rules for this. If the previous 4 rules did not work, then the transaction will be approved


# Update transaction signature policy protocol

The company runs the Sirius Custody system with defined policy to authorize transactions. The company decide what to make any changes in  policy to authorize transactions need to validate a new policy definition with several emploee of finance department.

### 6. Any changes in the policy to authorize transactions should be aproved by finance departament

**Condition:** Change in the policy

**Requires:** get 2 votes

**Audience:**
name | position | number of votes (weight)
---- | -------- | ------------------------
Kristine | officer of the finance department | 1
Jon | officer of the finance department | 1
Vlad | head of the finance department | 1
