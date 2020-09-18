# Imput format

* ___asset___ - digital asset transferred in a transaction
* ___amount___ - the amount of the digital asset transferred in a transaction
* ___approved by___ - the list of validator who already vote for approve transaction
* ___notified to___ - the list of validator who already was nofied about transaction

# Output format

* ___Resolution___ - the decision regarding a transaction with the following options: 
  * ___Approve___ - the transaction can be signed and executed
  * ___Decline___ - the transaction must be declined
  * ___Wait___ - delay the transaction and check again later
* ___Notify validators___ - list of validators who should be notified

# Rules

condition | action | audience
--------- | ------ | --------
1. transaction total amount is more than 1 BTC or 10 ETH | requires 2 votes | Alise (1), Bob (1), Jon (2)
2. daily total amount, including this transaction, is more than 10 BTC or 30 ETH | requires 1 votes | Jon(1), Kristine(1)
3. asset in the transaction is not BTC or ETH | requires 2 votes | Michael (1), Jon (1), Vlad (2)
4. transaction fee amount is more than 0.001 BTC or 0.0001 ETH | require 1 vote | Alex(1), Simon(1)
5. transaction total amount is more that 40 BTC or 400 ETH| decline transaction | 


# Input and output table

hit rule | input<br>asset | input<br>amount | input<br>approved by | input<br>notified to | output<br>Resolution | output<br>Notify_validators 
-------- | ----- | ------ | ----------- | ----------- | ---------- | -----------------
| | BTC | 0.3 | - | - | :heavy_check_mark: approve | -
1 | BTC | 2 | - | - | :clock3: wait | Alise, Bob, Jon
1 | BTC | 2 | - | Alise, Bob, Jon | :clock3: wait | -
1 | BTC | 2 | Alise | Alise, Bob, Jon | :clock3: wait | -
1 | BTC | 2 | Alise, Bob | Alise, Bob, Jon | :heavy_check_mark: approve | -
1 | BTC | 2 | Jon | Alise, Bob, Jon | :heavy_check_mark: approve | -
1 | BTC | 2 | Alise | Alise, Bob | :clock3: wait | Jon
1 | BTC | 2 | Alise | Bob, Jon | :clock3: wait | Alise
1 | BTC | 2 | Michael, Vlad | Michael, Vlad | :clock3: wait | Alise, Bob, Jon
5 | BTC | 55 | - | - | :x: decline | -
5 | BTC | 55 | Michael, Vlad | Michael, Vlad, Alise, Bob, Jon | :x: decline | -

















