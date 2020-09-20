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
* ___Signature___ - response signature, see [signarure](#sign)

# Rules

num | condition | action | audience
--- | --------- | ------ | --------
1 | transaction total amount is more than 1 BTC or 10 ETH | requires 2 votes | Alise (1), Bob (1), Jon (2)
2 | daily total amount, including this transaction, is more than 10 BTC or 30 ETH | requires 1 votes | Jon(1), Kristine(1)
3 | asset in the transaction is not BTC or ETH | requires 2 votes | Michael (1), Jon (1), Vlad (2)
4 | transaction total amount is more that 40 BTC or 400 ETH| decline transaction | 


# Input and output table

hit rule | input<br>asset | input<br>amount | input<br>daily total amount | input<br>approved by | input<br>notified to | output<br>Resolution | output<br>Notify_validators 
-------- | -------------- | --------------- | --------------------------- | -------------------- | -------------------- | -------------------- | ---------------------------
| | BTC | 0.3 | 0 | - | - | :heavy_check_mark: approve | -
1 | BTC | 2 | 0 | - | - | :clock3: wait | Alise, Bob, Jon
1 | BTC | 2 | 0 | - | Alise, Bob, Jon | :clock3: wait | -
1 | BTC | 2 | 0 | Alise | Alise, Bob, Jon | :clock3: wait | -
1 | BTC | 2 | 0 | Alise, Bob | Alise, Bob, Jon | :heavy_check_mark: approve | -
1 | BTC | 2 | 0 | Jon | Alise, Bob, Jon | :heavy_check_mark: approve | -
1 | BTC | 2 | 0 | Alise | Alise, Bob | :clock3: wait | Jon
1 | BTC | 2 | 0 | Alise | Bob, Jon | :clock3: wait | Alise
1 | BTC | 2 | 0 | Michael, Vlad | Michael, Vlad | :clock3: wait | Alise, Bob, Jon
1 | ETH | 12 | 0 | - | - | :clock3: wait | Alise, Bob, Jon
1 | ETH | 12 | 0 | Alise, Bob | Alise, Bob, Jon | :heavy_check_mark: approve | -
1,2 | ETH | 12 | 40 | Alise | Alise, Bob, Jon, Kristine | :clock3: wait | -
1,2 | ETH | 12 | 40 | Alise, Bob | Alise, Bob, Jon, Kristine | :clock3: wait | -
1,2 | ETH | 12 | 40 | Alise, Bob, Jon | Alise, Bob, Jon, Kristine | :heavy_check_mark: approve | -
1,2 | ETH | 12 | 40 | Alise, Bob, Kristine | Alise, Bob, Jon, Kristine | :heavy_check_mark: approve | -
1,2 | ETH | 12 | 40 | Jon | Alise, Bob, Jon, Kristine | :heavy_check_mark: approve | -
1,2 | ETH | 12 | 40 | Kristine | Alise, Bob, Jon, Kristine | :clock3: wait | -
3 | XRP | 1 | 3 | - | - | :clock3: wait | Michael, Jon, Vlad
3 | XRP | 1 | 3 | - | Michael, Jon, Vlad | :clock3: wait | -
3 | XRP | 1 | 3 | Michael | Michael, Jon, Vlad | :clock3: wait | -
3 | XRP | 1 | 3 | Jon | Michael, Jon, Vlad | :clock3: wait | -
3 | XRP | 1 | 3 | Jon, Michael | Michael, Jon, Vlad | :heavy_check_mark: approve | -
3 | XRP | 1 | 3 | Michael, Jon | Michael, Jon, Vlad | :heavy_check_mark: approve | -
3 | XRP | 1 | 3 | Vlad | Michael, Jon, Vlad | :heavy_check_mark: approve | -
3 | XRP | 1 | 3 | Michael, Vlad | Michael, Jon, Vlad | :heavy_check_mark: approve | -
3 | XRP | 1 | 3 | Jon, Vlad | Michael, Jon, Vlad | :heavy_check_mark: approve | -
3 | XRP | 1 | 3 | Michael, Jon, Vlad | Michael, Jon, Vlad | :heavy_check_mark: approve | -
4 | BTC | 55 | 0 | - | - | :x: decline | -
4 | BTC | 55 | 0 | Michael, Vlad | Michael, Vlad, Alise, Bob, Jon | :x: decline | -
4 | ETH | 400 | 0 | - | - | :x: decline | -


# <a href="sign"></a> Response signature 

To make a signature for responce neet to use algorithm:
* Build an object with struct:
  * input.asset: string
  * input.amount: string
  * input.approvedBy: array of string
  * input.notifiedTo: array of string
  * resolution: string
* notifyValidators: array of string
* Serialize object to JSON
* Convert JSON to byte array use UTF8 format
* Get SHD256 hash-bytes from bate array
* Make a signature for hash-bytes using RSA with 2048 bit rsa key pair
* Serialize signature bytes to string using BASE64 encoding














