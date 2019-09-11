# Txido 

_A way of addressing a specific output of a particular transaction_

A txido is a (normal) transaction ID followed by an indication of a specific output.

A "Normal" reference to a transaction ID: 

`a3907e5b910f798c8d0fb450d483a0aefa5ce40ac74064b377603e5ea51deccb`

Starting with the transaction ID a txido is constructed by indication of a specific output by 

- First, concatenate the decimal number for the index of the output (0 indexed) 
- secondary concatenate the result of `(n - 1) % 9 + 1` where n is the output index. 

Txido reference to the 2nd output (index 1)

    a3907e5b910f798c8d0fb450d483a0aefa5ce40ac74064b377603e5ea51deccb11

Txido reference to the 3rd output (index 2)

    a3907e5b910f798c8d0fb450d483a0aefa5ce40ac74064b377603e5ea51deccb22

Txido reference to the 16th output (index 15)

    a3907e5b910f798c8d0fb450d483a0aefa5ce40ac74064b377603e5ea51deccb156

**Please note that**

- The first output (index 0) must always be referenced with the original transaction ID. An indication of the first output (by adding `00`) is therefore always invalid. 

- Output index must be larger than 0 and no larger than 2147483647

- A valid txido will never be longer than 75 chars and will always match the regular expression `/^[a-fA-F0-9]{64}[1-9]\d{,9}\d$/`


