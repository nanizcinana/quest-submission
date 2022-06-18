## Chapter 1
### Day 1

1. Explain what the Blockchain is in your own words.

Blockchain is a given dispersed basis of information that is located at the same time in many PCs connected friend to friend via the Internet.


2. Explain what a Smart Contract is. 


A smart contract is a given computer project that monitors and also guarantees the fulfillment of duties. Smart contract codes are executed on the blockchain.

3. Explain the difference between a script and a transaction. 

A transaction is a procedure for saving the blockchain, which represents crypto assets or other data among wallets. Due to the transaction, a special commission may be charged in connection with which blockchain you reside. Script is used to view information in the blockchain, someone does not change it in any way. And also, unlike a transaction, it is she who does not charge a commission in any way, due to the fact that absolutely nothing is needed.


1. What are the 5 Cadence Programming Language Pillars?

    Safety and Security: Security is the main security of every smart contract. Security is the elimination of attacks in line or smart contracts. Security and security are of prime importance in smart contracts due to the permanent nature of blockchains and also because they often have a problem along with valuable assets.
    Clarity: The cipher must be freely readable, and its significance must be extremely specific. Someone is also obliged to proceed with the purpose of control, so that the devices have the opportunity to help in ensuring security and also guaranteeing security.
    Approachability: Composing the program code as well as the formation of projects must be extremely accessible. Actual fixtures, documents and samples enable creators to quickly and effectively move to the formation of projects.
    Developer Experience: The Creator must be preserved throughout the current research cycle as a whole, from the initial logic of the addition up to the correction of errors in the chain.
    Intuiting Ownership with Resources: Resources - this component type of information, similar in texture, which expresses the direct possession of assets. Cadence funds directly merge the ability of the property into assets along with the account that someone relates to, keeping the source in the base of the ledger.

2. In your opinion, even without knowing anything about the Blockchain or coding, why could the 5 Pillars be useful? 

These 5 pillars enable an even greater number of creators to create harmless, freely parsable, and easily accessible smart contracts. In a similar way, the creators of the female will make this ecosystem

## chapter 2

### Day 1

![image](https://user-images.githubusercontent.com/106602127/174445815-1e4cc663-4cdc-40aa-b3b9-f0b2fd127fed.png)

![image](https://user-images.githubusercontent.com/106602127/174445843-2836cbc8-587e-4cc3-b7c8-a8bbcb7b139e.png)

### Day 2

    We don't call changeGreeting in the script because the script only allows you to view the information, but cannot change it.
    AuthAccount gives access to the data to the account of the user signing the transaction.
    prepare phase allows you to access the user's account data. What execute phase cannot do, but execute phase can call functions to change data in the blockchain.
    Added two new things inside contract.
    
    
![image](https://user-images.githubusercontent.com/106602127/174445886-dbb1fcfd-6e80-4449-b14c-524a1fb84678.png)


![image](https://user-images.githubusercontent.com/106602127/174445908-0c2e6ed4-6199-43c5-855c-f44bd20691b4.png)

![image](https://user-images.githubusercontent.com/106602127/174445931-562e845e-314d-4357-9877-b38be09aa4cb.png)

![image](https://user-images.githubusercontent.com/106602127/174445943-7ffa460e-4b32-4c73-be59-490ab2e4e913.png)

### day 3

In a script, initialize an array (that has length == 3) of your favourite people, represented as Strings, and log it.

![image](https://user-images.githubusercontent.com/106602127/174447502-70bbb030-4cf1-426d-a1ef-67276a2850dc.png)


In a script, initialize a dictionary that maps the Strings Facebook, Instagram, Twitter, YouTube, Reddit, and LinkedIn to a UInt64 that represents the order in which you use them from most to least. For example, YouTube --> 1, Reddit --> 2, etc. If you've never used one before, map it to 0!

![image](https://user-images.githubusercontent.com/106602127/174447535-d41d6f3e-774f-4002-8cee-6b6fb8a7cbc2.png)


Explain what the force unwrap operator ! does, with an example different from the one I showed you (you can just change the type).


**force unwrap** will take on the value of an optional parameter if there is one. someone will panic and also break off, if the given is not in this way.

What the error message means, Why we're getting this error, How to fix it

The oversight of the type mismatch, due to the fact that the predicted string existed "String", but you got the optional string "String?"

Because the lexicon gives meaning to which I am addressing, along with the optional aspect.

This error can be corrected together with the support of the forced sweep operator. Set "!" dispatcher at the end of the given line, in order to rotate the free view and also return practical significance.


### day 4
Deploy a new contract that has a Struct of your choosing inside of it (must be different than Profile). Create a dictionary or array that contains the Struct you defined. Create a function to add to that array/dictionary. Create a dictionary or array that contains the Struct you defined. Create a function to add to that array/dictionary.

![image](https://user-images.githubusercontent.com/106602127/174448531-f217471e-b880-4baa-9241-987b71de3458.png)

Yeah i done this i really good boy :3

## Chapter 3

### Day 1

List 3 reasons why structs are different from resources.


   - Resources cannot be copied only move
   - Resources cannot be overwritten
   - Resources can only be created within a contract




Describe a situation where a resource might be better to use than a struct. The resource is best used as an example of the NFT. Because Cadence guarantees that the resource will not be lost or overwritten unless the developer literally wants to delete it.

What is the keyword to make a new resource? Create

Can a resource be created in a script or transaction? No. A resource can only be created within a contract.

What is the type of the resource below?


-----------------
 pub resource Jacob {
-----------------


pub contract Test {

 	// Hint: There's nothing wrong here ;)
 	pub resource Jacob {
 		pub let rocks: Bool
 		init() {
 			self.rocks = true
 		}
 	}

 	pub fun createJacob(): Jacob { // there is 1 here
 		let myJacob = Jacob() // there are 2 here
 		return myJacob // there is 1 here
 	}
 }
 
 
 
 Bug fixes:

	pub contract Test {

		// Hint: There's nothing wrong here ;)
		pub resource Jacob {
			pub let rocks: Bool
			init() {
				self.rocks = true
			}
		}

		pub fun createJacob(): @Jacob { // there is 1 here
			let myJacob <- create Jacob() // there are 2 here
			return <- myJacob // there is 1 here
		}
	}



### Day 2

![image](https://user-images.githubusercontent.com/106602127/174448722-79d67852-47c8-424a-a6ce-12323d8143ef.png)


![image](https://user-images.githubusercontent.com/106602127/174448729-be5814ac-5371-43fd-acae-1e35c2687b54.png)

### Day 3



