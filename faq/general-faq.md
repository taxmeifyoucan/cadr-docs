# General FAQ

## Who can use this repository?

All applications and tools handling them in this repository are Free and Open Source Software. Anybody is free to use them in any way they desire. 

{% hint style="success" %}
CADR is used by people who prefer security and respect their Bitcoin privacy. It is used daily by individuals, merchants, businesses, nonprofits and if you are reading this, you will hopefully become user soon! 
{% endhint %}

## Do I need to trust repository maintainer? 

Depends on whether you use ready-made repository or build it on your own. Just as in case of other Debian packages the maintainer has effectively root access to your system because of the way maintainer scripts work. There are multiple techniques to make this less of an issue:

* The packages are publicly visible and signed - presence of any backdoor can be detected and proven to others
* The maintainer built his reputation over long time and it'd be costly to destroy it
* The maintainer uses Qubes OS for building and practices good opsec, compromise should be unlikely
* Most of the packages are built deterministically

{% hint style="info" %}
For more details about security of this project, check [Security FAQ](security.md). 
{% endhint %}

## What does Cryptoanarchy mean?

Crypto-anarchy is a concept that seeks to enhance individual freedom not by the lack of power and coercion, but by effectively hiding the actions of the performer out of the public sight. Since the performer is unknown there is no one to be judged and punished. The realisation of cryptoanarchy lies in the cyberspace and through the methods of encryption, message concealing and pseudonymous and colective identitiese.

{% hint style="success" %}
For further info, look into [Cryptoanarchy Manifesto](https://activism.net/cypherpunk/crypto-anarchy.html) by Timothy C. May and watch [Project of Cryptoanarchy](https://www.youtube.com/watch?v=gTtbkguROdk) talk by Smuggler. 
{% endhint %}

## Why is this repository Bitcoin only?

Not that I'd hate shitcoins, I just don't have the time for them.

> There are countless reasons why it is the only logical choice to be [bitcoin-only](https://bitcoin-only.com) . With Bitcoin we have a once in a lifetime opportunity to manifest libre sound money. If we succeed, then an utmost beautiful agora of sovereign individuals may emerge. If we fail, then this will conjure up the most horrific Orwellian nightmare. There is no room for wasted time and energy, this great work requires our full attention. Any line of code written to support a random shitcoin takes away scarce developer time to work on real problems. \(Inspired by [Wasabi docs](https://docs.wasabiwallet.io/), thanks Max\)

## What to do if something doesn't work?

If there is an issue with your setup or something does not work as expected, make sure to read through this FAQ and chapter [What to be aware of](../usage/what-to-be-aware-of.md). If you don't find an answer how to troubleshoot your problem, feel free to [reach out to our community](../community/support-1.md#community) or open issue in [Github repository](https://github.com/Kixunil/cryptoanarchy-deb-repo-builder/issues). 

## How to change Bitcoin chain data directory?

Timechain  is biggest chunk of data your machine has to process and store. Default directory is `/var/lib` in root of your system. If you need to use other directory, for example external volume for this data, check [How to change Bitcoind data directory and other configuration](../usage/supported-software/bitcoin.md#changing-bitcoind-data-directory-and-other-settings). 

## Can I run this on Raspberry Pi? 

In theory, yes, in practice it's not well-tested, has known issues and Raspberry Pis are not that powerful, so th UX suffers. If you value your sats and your time you should prefer something more powerful and more tested.

If you insist on RPi, reach out for instructions to use the experimental repository.



