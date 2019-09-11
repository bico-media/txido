# txido = transaction ID output 

_A transaction ID followed by an indication of a specific output._

A "Normal" reference to a transaction ID:

`a3907e5b910f798c8d0fb450d483a0aefa5ce40ac74064b377603e5ea51deccb`

Starting with the transaction ID one can add an indication of a specific output by adding the decimal number for the index of the output (0 indexed) followed by the result of `(n - 1) % 9 + 1` where n is the the output index (Check part). 


Txido reference to the 2nd output (index 1)
a3907e5b910f798c8d0fb450d483a0aefa5ce40ac74064b377603e5ea51deccb11

Txido reference to the 3nd output (index 2)
a3907e5b910f798c8d0fb450d483a0aefa5ce40ac74064b377603e5ea51deccb22

Txido reference to the 11th output (index 10)
a3907e5b910f798c8d0fb450d483a0aefa5ce40ac74064b377603e5ea51deccb101

**Please note that**

- The first output (index 0) is always referenced with the original transaction ID. An indication of the first output (by adding ´00´) therefore always invalid. 

- Output index must be larger than 0 and but no larger than 2147483647

A valid txido will never be longer than 75 chars and will always match the regexp `/^[a-fA-F0-9]{64}[1-9]\d{,9}\d$/`


