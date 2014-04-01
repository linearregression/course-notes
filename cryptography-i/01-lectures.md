# Unit 1

## What is cryptography?

Cryptography core:

1. Establish shared secret key
2. Communicate securely

Additional things crypto can do:

* digital signatures - unlike the physical world, we can't use the exact same artifact to sign everything, since an attacker could just copy and paste it. the answer: make the signature a function that operates on the content to be signed.
* anonymous communication - mix net is a sequence of proxies that anonymize the sender by encrypting / decrypting the message repeatedly
* anonymous digital cash - detach identity from spending (as it is in the physical world), but you run into the problem of how you prevent double-spending

### Protocols

Election problem: winner of an election is the party that received more votes. How do you compute the winner without revealing anything else about the vote?

* Use an election center to verify authorization and uniqueness of votes, then produce (only) the winner

Private auctions: same problem, just reveal the winner and the price to be paid (e.g., victory auction where winner is highest bidder, who pays the amount of the 2nd highest bid)

* Use an auction center to compute the winner and the 2nd highest bid

Both are examples of **secure multi-party computation**
* participants have secret data
* goal is to compute a function across the participants' data

Insecure: use a "trusted authority"

THEOREM: any computation you can do with a trusted authority, you can do **without** a trusted authority.

### Magic!
* Privately outsourcing computation - you can run algorithms on encrypted data without decrypting the query OR the results

* Zero knowledge / proof of knowledge - assume a number `N` that is the product of huge nums `p` and `q`. Alice knows all three; Bob knows on `N`. Alice can prove to Bob that she knows `p` and `q` without revealing those values.

Crypto is a rigorous science. The three steps are:
1. Precisely specify the threat model
2. Propose a construction
3. Prove that breaking construction under threat mode will solve an underlying hard problem
