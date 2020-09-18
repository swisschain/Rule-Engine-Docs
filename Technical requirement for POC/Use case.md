# Table of contents
1. [Use case](#usecase)
2. [Transaction signature policy](#policy)
    1. [The transaction with BTC and ETH and not a small amount should be approved by 2 employees of the customer support department or Jon from the finance control department](#policy1)
    2. [With an abnormally large volume of transfers during the day, transactions should be approved by someone from the finance control department](#policy2)
    3. [Transactions with all other assets must be approved by the several employees of the finance department or by the head of the finance department](#policy3)
    4. [It is forbidden to transfer large amounts for a single transaction using BTC and ETH](#policy4)
    5. [All other transaction should be automatically sign](#policy5)
3. [Update transaction signature policy protocol](#update)
    1. [Any changes in the policy to authorize transactions should be aproved by finance departament](#policy6)

# Use case <a name="usecase"></a>

The company runs the Sirius Custody system and defines the next policy to authorize transactions

* The transaction with BTC and ETH and not a small amount should be approved by 2 employees of the customer support department or Jon from the finance control department
* With an abnormally large volume of transfers during the day, transactions should be approved by someone from the finance control department
* Transactions with all other assets must be approved by the several employees of the finance department or by the head of the finance department
* It is forbidden to transfer large amounts for a single transaction using BTC and ETH
* All other transaction should be automatically sign
* Any changes in the policy to authorize transactions should be aproved by finance departament


# Transaction signature policy <a name="policy"></a>

-------------

### 1. <a name="policy1"></a> The transaction with BTC and ETH and not a small amount should be approved by 2 employees of the customer support department or Jon from the finance control department

**Condition:** transaction total amount is more than 1 BTC or 10 ETH

**Requires:** get 2 votes

**Audience:**
name | position | number of votes (weight)
---- | -------- | ------------------------
Alise | officer of the customer support department | 1
Bob | officer of the customer support department | 1
Jon | officer of the finance department | 2

-------------

### 2. <a name="policy2"></a> With an abnormally large volume of transfers during the day, transactions should be approved by someone from the finance control department

**Condition:** daily total amount, including this transaction, is more than 10 BTC or 30 ETH

**Requires:** get 1 votes

**Audience:**
name | position | number of votes (weight)
---- | -------- | ------------------------
Kristine | officer of the finance department | 1
Jon | officer of the finance department | 1
Vlad | head of the finance department | 1

-------------

### 3. <a name="policy3"></a> Transactions with all other assets must be approved by the several employees of the finance department or by the head of the finance department

**Condition:** asset in the transaction is not BTC or ETH

**Requires:** get 2 votes

**Audience:**
name | position | number of votes (weight)
---- | -------- | ------------------------
Kristine | officer of the finance department | 1
Jon | officer of the finance department | 1
Vlad | head of the finance department | 2

-------------

### 4. <a name="policy4"></a> It is forbidden to transfer large amounts for a single transaction using BTC and ETH

**Condition:** transaction total amount is more that 40 BTC or 400 ETH

**Requires:** Decline transaction

**Audience:**
name | position | number of votes (weight)
---- | -------- | ------------------------

-------------

### 5. <a name="policy5"></a> All other transaction should be automatically sign

There are no special rules for this. If the previous 4 rules did not work, then the transaction will be approved


# Update transaction signature policy protocol <a name="update"></a>

The company runs the Sirius Custody system with defined policy to authorize transactions. The company decide what to make any changes in  policy to authorize transactions need to validate a new policy definition with several emploee of finance department.

### 1. <a name="policy6"></a> Any changes in the policy to authorize transactions should be aproved by finance departament

**Condition:** Change in the policy

**Requires:** get 2 votes

**Audience:**
name | position | number of votes (weight)
---- | -------- | ------------------------
Kristine | officer of the finance department | 1
Jon | officer of the finance department | 1
Vlad | head of the finance department | 1
