# Open Source Contribution Project

*Author :* Martin Meerts

*Date :* December2020 2020

*NOMA :* 80721400


## My motivation to follow a course on open source software

I'm a Linux lover. I read the book " Just for fun, the story of an accidental revolutionary". It's the story of Linux written by Linus Torvalds, its creator ! It was a motivation for me to learn more about the concept of Open Source because it literally changed the world and created a huge community ! If Linus Torvalds was alone for Linux, we would probably be using windows or mach.
I think that open source is a faster way to improve our systems because when a group owns a licence on something, it's very difficult to reuse it and to propagate the new technology. 
I know that multipath-TCP was built within the UCLouvain. It's an improvement of TCP allowing this protocol to use different channels of communications (like 4G and wifi simultaneously) in order to reduce the latencies. 
Apple found that very interesting because when you were about to leave your house while using Siri, it was very painful to use due to the loss of wifi connection and the waiting time needed to pair on 4G. So Apple could use it freely
and make multi-path TCP a standard in the smartphones today !

The other motivation that made me choose this course, is the way we discuss in class. It's open and we can discuss about anything (related to open source of course). It's a good motivation to get up at 8:26 on a Thursday morning (4 minutes are sufficient to open teams). We are in a world where everyone only discusses about money and growth. Open Source projects are, for a lot them, not based on the profit, but more on the sharing part. People can have their place, they can feel useful and be interested in project without fear of being fired. If you do something wrong, the consensus will discard your work and force you to do better. So it's a good way to learn freely!


## Research and Selection of the Project

### What I was looking for :
I follow the security classes and I'm very interested about cryptography (not the elliptical curves with prime numbers part...). But I think that there are a lot of topics very interesting, so I started earlier to look after git repos related to these topics.

### First attempt: 
For my first attempt, I started with an [Awsome project](https://github.com/qazbnm456/awesome-web-security) about security.  documentation about security issues and attacks. The last year, I followed a course about cryptanalyst and ways to hack an electronic device. I saw nothing on the repo about Side-Channels attacks so I posted a small paper that describes what is about. I failed [my first PR] (https://github.com/qazbnm456/awesome-web-security/pull/82) because I didn't format it really well. After some discussion with the supervisor of the project, I managed my PR to be accepted. It was not too difficult, but it was my really first contribution to a git repository where a lot of people are collaborating !
If you're interested in a way to eavedrop 100% of the noise inside a room, only by observing the variation of light that is reflected by a light bulb, with a telescope : [this paper](https://www.csoonline.com/article/3388647/what-is-a-side-channel-attack-how-these-end-runs-around-encryption-put-everyone-at-risk.html) is for you ! They managed to hear a conversation of Donald Trump ! 

### Second attempt: 
I was a little bit more ambitious! I'm doing my master thesis about blockchains and smart contracts so I tried to find a project related to that topic. I found a block chain implemented in python. I tried to install the requirements and I've been stuck with an error. This error was related to Pipenv. Pipenv is a packaging tool for Python that aggregates yarn, npm, cargo, etc. It's very useful to manage packaging and requirement settings in order to improve the portability of your python program. The error that I ensured was too hard for me, but I found another [issue](https://github.com/pypa/pipenv/issues/4538) about a regular expression wrongly written. This regular expressions made the program to crash and I knew how to solve it easily ! But unfortunately, someone ( in 3 hours) stole me the [pull request](https://github.com/pypa/pipenv/pull/4540) ! I was sad and disappointed because it was a project with a huge community (323 contributors for the moment). His pull request passed the checks.  But anyway , I had to bounce back !

### Third attempt:
I saw another kind of awesome [project](https://github.com/Xel/Blockchain-stuff) was collecting a lot of information about blockchains and cryptocurrencies. As I said earlier, I'm really interested about this topic, so I decided to contribute by adding some information about how to write efficient smart-contracts deployed on the Ethereum Blockchain.
For instance, smart-contracts are like an automated and transparent third-party. We can take the example of Vinted, the clothes selling app: I'm bob and I want to sell a T-shirt to Alice. Me and Alice , are sending the T-shirt and the money to Vinted. When it has validated the reception, send the T-shirt to Alice. If Alice is satisfied, Vinted finally send the money to myself. A smart-contract works exactly the same, but with virtual data. It allows secure transactions between peers. For this one, I posted this [Pull Request](https://github.com/Xel/Blockchain-stuff/pull/38) and it's still pending.

​

### Last attempt:
I wanted to try another contribution on a bigger project ! I chose [python-bitcoinlib](https://github.com/petertodd/python-bitcoinlib) A Bitcoin's blockchain emulator with python ! I tried to run this by myself and I found that funny ! For another course, We had to implement a blockchain in python that allows us to make an election : We append encrypted ballots in this blockchain and we should post it on the darkweb. So , due to the similarity, I found interesting to try this.
I found that [some functions were depreciated and not working anymore](https://github.com/petertodd/python-bitcoinlib/issues/244), like getting information about my wallet, about the nodes inside the network. So I wrote 3 functions in order to update the depreciated one, and fixed 3 bugs about exception handling. I was working fine, so I created a [Pull Request](https://github.com/petertodd/python-bitcoinlib/pull/252) for that. I'm waiting for a response from the owners and I hope they will ! 

```python
def getnetworkinfo(self):
        """Return a JSON object containing information about the network"""
        return self._call('getnetworkinfo')
        
def getwalletinfo(self):
    """Return a JSON object containing information about the wallet"""
    r = self._call('getwalletinfo')
    if 'balance' in r:
        r['balance'] = int(r['balance'] * COIN)
    if 'paytxfee' in r:
        r['paytxfee'] = int(r['paytxfee'] * COIN)
    return r

def getblockchaininfo(self):
    """Return a JSON object containing Blockchain-related information"""
    return self._call('getblockchaininfo')
```


## Conclusion

I found that communities in github's network are most of the time very kind! They usually give you a template to follow in order to contribute. If you make a mistake or write something wrong, an advisor will correct you and sometimes tell you what to change. Sometimes, there are so many contributors and it's difficult to commit your changes in times before them. It happened to me and it's fair. This concurrency improve the quality of the work so it's not a bad idea. 








