# bip39tool
Command-line tool to interact with BIP39 mnemonics.

You can use `bip39tool` to generate BIP39 mnemonic seeds, to convert a mnemonic into a seed or entropy,
and to convert entropy into a seed or mnemonic. It supports passphrases for seed generation. It does not
support any mnemonic languages other than English.

## Installation
Use `pip` to install `mnemonic`:

    pip install mnemonic

and then either use `bip39tool` straight from this directory, or copy it into your path:

    cp bip39tool ~/bin

## Usage
See `bip39tool --help`:

    Usage: bip39tool [-g] [-o words|seed|entropy] [-p PASSPHRASE] [INPUT]
    
    Options:
      -g,--generate     Generate entropy instead of reading it from INPUT.
      -o,--output       Output format (words,seed,entropy). Default: seed
      -p,--passphrase   Passphrase. Only relevant with output format "seed". Default: (empty string)
    
    INPUT format is detected automatically. Either mnemonic words or 32-byte entropy are acceptable.
    
    Examples:
      (test vectors from https://github.com/trezor/python-mnemonic/blob/master/vectors.json)
      bip39tool -o words --generate
      bip39tool -o words 7f7f7f7f7f7f7f7f7f7f7f7f7f7f7f7f
      bip39tool -o entropy legal winner thank year wave sausage worth useful legal winner thank yellow
      bip39tool -o seed --passphrase TREZOR 7f7f7f7f7f7f7f7f7f7f7f7f7f7f7f7f
      bip39tool -o seed --passphrase TREZOR legal winner thank year wave sausage worth useful legal winner thank yellow
    
    Help:
      See the github project at https://github.com/jes/bip39tool
      Please email james@incoherency.co.uk if you want to get in touch
