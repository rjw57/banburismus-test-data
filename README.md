# Test Enigma data for implementing Banburismus

This repository contains some useful test data if you want to play with
Banburismus. There are two files, one containing indicators which are nearby
and one containing random indicators. Having pinched the bigram cipher tables
for these intercepts, you can assume that the ciphertext and indicators are
known. The challenge is to recover the plaintext and, along with it, the Enigma
settings for the day.

The data files include the plaintext for comparison which is English text drawn
from the Project Gutenberg corpus. Note that Banburismus as descibed
historically was tuned for the statistics of (abbreviated) German but it should
work with English wish some minor modification.

In order to facilitate the use of 'Eins' tables, the plaintext uses 'STOP' to
indicate full-stops. One may also have luck using 'OTHE' as a very common
tetragram in English text.

## Encryption procedure

A German Naval cipher operator would begin by selecting a three letter
'indicator' to encrypt the message with. There was a procedure for doing this
but that is beyond the scope of this exercise. For our purposes we can assume
they were chosen at random. This was transmitted at the start and end of the
message using a hand bigram substitution cipher which was known to Project
Ultra. For convenience's sake, it is assumed that this indicator has already
been decrypted and is provided in the test data.

The operator then sets up the machine according to the day's settings. These
are reproduced below for checking your result but should be viewed as 'unknown'
and requiring reconstruction. The three-letter indicator is typed into the
Enigma machine resulting in three letters of output. The operator notes these
letters and sets the Enigma machine's display to match. The message is then
enciphered essentially using the enciphered indicator as a key.

## Machine settings

The Enigma machine settings for the day, which should be recovered from the
ciphertexts and indicators, are:

* Walzenlage: VII, IV, V
* Reflector: B (thin)
* Ringstellung: RJW
* Steckerverbindungen: AC LS BQ WN MY UV FJ PZ TR OK
* Grundstellung: WJF

## Resources

* [py-enigma](https://pypi.python.org/pypi/py-enigma/) is a simulation of a
  wartime Enimgma machine in Python.
