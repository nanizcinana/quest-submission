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

![image](https://user-images.githubusercontent.com/106602127/175394783-fc4fa0ef-bcc6-47f7-aee5-2564dc2d07c0.png)

### Day 4
![image](https://user-images.githubusercontent.com/106602127/175395358-46d5b7cd-2083-410e-ab0f-0167ed79a025.png)

### Day 5

![image](https://user-images.githubusercontent.com/106602127/175395945-fcab7ed8-24d2-4fd6-9803-8d6fc2e3b995.png)

![image](https://user-images.githubusercontent.com/106602127/175396004-128b235a-5abc-47c2-8bbf-a0da3fdef03e.png)

![image](https://user-images.githubusercontent.com/106602127/175396104-5703b1d6-669f-4f19-baca-12fb65c6244e.png)


## Chapter 4



    What lives in an account are as follows:
        Contract code: This is the smart contract you have deployed with the said account.
        Account storage: This is where all your data is stored and it contains 3 different paths to get certain data.

    Difference between the 3 paths:
        /storage/: Only the owner of the account can access whatever data is stored here
        /public/: This is for data that anyone can have access to.
        /private/: This is for data that only the owner has access to(duh) but can also give access to other people if they want to.
        .save() is used to save data to the account storage and can only be done by the owner (signer). whateer is saved here is saved to a /storage/ path.
        .load() is used to extract data from the account storage
        .borrow() is used inline with a reference to basically borrow some data from the account. This way, the data can be viewed but also restricts some access to it.

    This is because saving data to the account storage requires a transaction due to the fact that it modifies the blockchain and you cannot perform transactions in a script.

    You cannot save to another person's account because you do not have that person's authaccount used for signing and giving approval to perform such actions.

    Contract: pub contract Test {

    pub resource Food { pub var name: String init() { self.name = "Pasta" } }

    pub fun createFood(): @Food { return <- create Food() }

    }

i) import Test from 0x02 transaction() { prepare(signer: AuthAccount) { let foodResource <- Test.createFood() signer.save(<- foodResource, to: /storage/MyFoodResource) let testResources <- signer.load<@Test.Food>(from: /storage/MyFoodResource) ?? panic("A @Test.Food resource does not live here.") log(testResources.name) // "Jacob"

    destroy testResources
  }

  execute {

  }
}

ii) import Test from 0x02 transaction() { prepare(signer: AuthAccount) { let foodResource <- Test.createFood() signer.save(<- foodResource, to: /storage/MyFoodResource) let testResources = signer.borrow<&Test.Food>(from: /storage/MyFoodResource) ?? panic("A @Test.Food resource does not live here.") log(testResources.name) // "Jacob"

    }

    execute {

    }
  }



/* 1. .link() is responsible for linking and providing access, a resource located in the storage of a user's account to either a public path (meaning everyone will have access to this, or private path (meaning only selected people will have access). It takes in 2 parameters; the private or public path and the target path (account storage, only accessible by the owner) */


/* 2. A resource interface works by restricting access to the main resource, acting somewhat like an extension of the main resource and only allowing the end user to see and interact with it in the way the owner has set. This will be acheived by linking the location of the main resource (/storage/) to the path you want; either /private/ or /public/. */


3.  // Smart contract
pub contract Pokedex {

  pub resource interface IPokemon {
    pub var name: String
  }

  // `Test` now implements `ITest`
  pub resource Pokemon: IPokemon {
    pub var name: String
    pub var type: String

    pub fun changeName(newName: String) {
      self.name = newName
    }

    pub fun changeType(newType: String) {
      self.type = newType  
    }

    init() {
      self.name = "Charizard"
      self.type = "fire"

    }
  }

  pub fun createPokemon(): @Pokemon {
    return <- create Pokemon()
  }

}


// transaction to save and link the resource
import Pokedex from 0x01
transaction() {
  prepare(signer: AuthAccount) {
    // Save the resource to account storage
    signer.save(<- Pokedex.createPokemon(), to: /storage/MyPokesource)

    signer.link<&Pokedex.Pokemon{Pokedex.IPokemon}>(/public/MyPokedexResource, target: /storage/MyTestResource)
  }

  execute {

  }
}


// Transaction trying to access what wasn't made available
import Pokedex from 0x01
transaction(address: Address) {

  prepare(signer: AuthAccount) {

  }

  execute {
    let publicCapability: Capability<&Pokedex.Pokemon{Pokedex.IPokemon}> =
      getAccount(address).getCapability<&Pokedex.Pokemon{Pokedex.IPokemon}>(/public/MyPokedexResource)
    let testResource: &Pokedex.Pokemon{Pokedex.IPokemon} = publicCapability.borrow() ?? panic("The capability doesn't exist or you did not specify the right type when you got the capability.")

    testResource.changeName(newName: "Sarah")
  }
}




// Script accessing what is available
import Pokedex from 0x01
pub fun main(address: Address): String {
    let publicCapability: Capability<&Pokedex.Pokemon{Pokedex.IPokemon}> =
      getAccount(address).getCapability<&Pokedex.Pokemon{Pokedex.IPokemon}>(/public/MyPokedexResource)
    let testResource: &Pokedex.Pokemon{Pokedex.IPokemon} = publicCapability.borrow() ?? panic("The capability doesn't exist or you did not specify the right type when you got the capability.")

    return testResource.name
 
}






    We added a collection to the contract to allow for multiple items to be stored in the same storage path.

    You would have to use the destroy function to destroy those nested resources.
        Set some conditions so not just anyone will be able to mint
        Put nft data into a struct rather than a resource



pub contract CryptoPoops {
  pub var totalSupply: UInt64

  // This is an NFT resource that contains a name,
  // favouriteFood, and luckyNumber
  pub resource NFT {
    pub let id: UInt64

    pub let name: String
    pub let favouriteFood: String
    pub let luckyNumber: Int
  
    // Initialise the Nft upon deployment
    init(_name: String, _favouriteFood: String, _luckyNumber: Int) {
      self.id = self.uuid

      self.name = _name
      self.favouriteFood = _favouriteFood
      self.luckyNumber = _luckyNumber
    }
  }

  // This is a resource interface that gives us access and allows us to deposit, get the id of and borrow an NFT.
  pub resource interface CollectionPublic {
    pub fun deposit(token: @NFT)
    pub fun getIDs(): [UInt64]
    pub fun borrowNFT(id: UInt64): &NFT
  }

  // This is a collection which allows for the storage of multiple nfts to the same account storage path
  pub resource Collection: CollectionPublic {
    pub var ownedNFTs: @{UInt64: NFT}
  
    // function that deposits or adds an nft to a collection
    pub fun deposit(token: @NFT) {
      self.ownedNFTs[token.id] <-! token
    }
    
    // function that withdraws an nft with a specific ID from the collection
    pub fun withdraw(withdrawID: UInt64): @NFT {
      let nft <- self.ownedNFTs.remove(key: withdrawID) 
              ?? panic("This NFT does not exist in this Collection.")
      return <- nft
    }
    
    // use to get all the NFTs owned by a user
    pub fun getIDs(): [UInt64] {
      return self.ownedNFTs.keys
    }
    
    // returns a reference to a Specific NFT by ID
    pub fun borrowNFT(id: UInt64): &NFT {
      return &self.ownedNFTs[id] as &NFT
    }
     // Initialise and empty collection
    init() {
      self.ownedNFTs <- {}
    }
    
    
    // destroy any nested resources
    destroy() {
      destroy self.ownedNFTs
    }
  }
  
  
  // created an empty collection where nfts will be stored
  pub fun createEmptyCollection(): @Collection {
    return <- create Collection()
  }
  
  
  // Minter resource to allow owner to create a minter and mint an NFT
  pub resource Minter {
     
     // Mint NFT
    pub fun createNFT(name: String, favouriteFood: String, luckyNumber: Int): @NFT {
      return <- create NFT(_name: name, _favouriteFood: favouriteFood, _luckyNumber: luckyNumber)
    }
    
    
    // Create new Minter
    pub fun createMinter(): @Minter {
      return <- create Minter()
    }

  }

  // initialise contract, set total supply to 0 and save the minter resource to the account that deploys the contract
  init() {
    self.totalSupply = 0
    self.account.save(<- create Minter(), to: /storage/Minter)
  }
}


## Chapter 4



    An event is a way for the smart contract to give updates to the outside world based on an action taken or modification made on the blockchain (i.e an NFT being minted). the whole point of an event is so that other clients or frontend users can use this information to do other things on the frontend of the DAPP.

    pub contract Test {

pub event PokemonNamed(name: String)

pub resource NamePokemon { pub var name: String

pub fun updateName(namee: String) {
pre {
  namee.length > 0 : "Please type a proper name"
}
post {
  namee.length == 5 : "seems you typed in a 5 letter name"
}
  self.name = namee
}

init() {
  self.name = ""

  emit PokemonNamed(name: self.name)
}

}

}

    pub contract Test {

// TODO // Tell me whether or not this function will log the name. // name: 'Jacob' pub fun numberOne(name: String) { pre { name.length == 5: "This name is not cool enough." } log(name) } // Yes the function will log Jacob because it passes the condition of being of 5 characters

// TODO // Tell me whether or not this function will return a value. // name: 'Jacob' pub fun numberTwo(name: String): String { pre { name.length >= 0: "You must input a valid name." } post { result == "Jacob Tucker" } return name.concat(" Tucker") } // Yes it will return Jacob Tucker because it passes both conditions of having more than 1 character and also matching the name Jacob Tucker after being concatenated.

pub resource TestResource { pub var number: Int

// TODO
// Tell me whether or not this function will log the updated number.
// Also, tell me the value of `self.number` after it's run.
pub fun numberThree(): Int {
  post {
    // This will fail because the result will be equals to 1 which isn't the original number before the function. It is meant to be "result - 1" 
    //  to check that the number before the function is run is one less than the new number after it is run.
    before(self.number) == result + 1
  }
  self.number = self.number + 1
  return self.number
}
init() {
  self.number = 0
}

}

}




    Standards are beneficial to the flow ecosystem because it creates a set of rules and requirements which not only make things easier, but also allow for interoperability when it comes to certain things like tokens and NFTs. As a result of standards, you can go to a marketplace on flow and it would pick up on the token you own and allow you to carry out various actions with it. All with the same codebase and functionalities.

    Plantains haha...

    pub contract Test: ITest { pub var number: Int

pub fun updateNumber(newNumber: Int) { self.number = newNumber }

pub resource interface IStuff { pub var favouriteActivity: String }

pub resource Stuff: ITest.IStuff { pub var favouriteActivity: String

init() {
  self.favouriteActivity = "Playing League of Legends."
}

}

init() { self.number = 0 } }




    What does "force casting" with as! do? Why is it useful in our Collection?

force casting with as! is used to take a more generic type and make it more specific by downcasting it and it's useful because it prevents people from depositing just any NFT into our collection. Let's imagine you store apples but not just any apples, only red apples. You wouldn;t want anyone dropping in any kind of apples even tho they're all under the same "apple" standard, you would need to specify the kind of apples that YOU collect, which in this case are red apples.

    What does auth do? When do we use it?

auth is used as a reference to allow downcasting of other more generic references.

import NonFungibleToken from 0x02 pub contract CryptoPoops: NonFungibleToken { pub var totalSupply: UInt64

pub event ContractInitialized()
pub event Withdraw(id: UInt64, from: Address?)
pub event Deposit(id: UInt64, to: Address?)

pub resource NFT: NonFungibleToken.INFT {
    pub let id: UInt64

    pub let name: String
    pub let favouriteFood: String
    pub let luckyNumber: Int

    init(_name: String, _favouriteFood: String, _luckyNumber: Int) {
    self.id = self.uuid

    self.name = _name
    self.favouriteFood = _favouriteFood
    self.luckyNumber = _luckyNumber
    }
}

pub resource interface CollectionPublic {
    pub fun deposit(token: @NonFungibleToken.NFT)
    pub fun getIDs(): [UInt64]
    pub fun borrowNFT(id: UInt64): &NonFungibleToken.NFT
    pub fun borrowAuthNFT(id: UInt64): &NFT
}

pub resource Collection: NonFungibleToken.Provider, NonFungibleToken.Receiver, NonFungibleToken.CollectionPublic, CollectionPublic {
    pub var ownedNFTs: @{UInt64: NonFungibleToken.NFT}

    pub fun withdraw(withdrawID: UInt64): @NonFungibleToken.NFT {
    let nft <- self.ownedNFTs.remove(key: withdrawID) 
            ?? panic("This NFT does not exist in this Collection.")
    emit Withdraw(id: nft.id, from: self.owner?.address)
    return <- nft
    }

    pub fun deposit(token: @NonFungibleToken.NFT) {
    let nft <- token as! @NFT
    emit Deposit(id: nft.id, to: self.owner?.address)
    self.ownedNFTs[nft.id] <-! nft
    }

    pub fun getIDs(): [UInt64] {
    return self.ownedNFTs.keys
    }

    pub fun borrowNFT(id: UInt64): &NonFungibleToken.NFT {
    return &self.ownedNFTs[id] as &NonFungibleToken.NFT
    }

    pub fun borrowAuthNFT(id: UInt64): &NFT {
        let ref = &self.ownedNFTs[id] as auth &NonFungibleToken.NFT
        return ref as! &NFT
    }

    init() {
    self.ownedNFTs <- {}
    }

    destroy() {
    destroy self.ownedNFTs
    }
}

pub fun createEmptyCollection(): @NonFungibleToken.Collection {
    return <- create Collection()
}

pub resource Minter {

    pub fun createNFT(name: String, favouriteFood: String, luckyNumber: Int): @NFT {
    return <- create NFT(_name: name, _favouriteFood: favouriteFood, _luckyNumber: luckyNumber)
    }

    pub fun createMinter(): @Minter {
    return <- create Minter()
    }

}

init() {
    self.totalSupply = 0
    emit ContractInitialized()
    self.account.save(<- create Minter(), to: /storage/Minter)
}

}

Transaction import CryptoPoops from 0x02

transaction() {

prepare(signer: AuthAccount) {
    let newCollection <- CryptoPoops.createEmptyCollection()
    signer.save(<- newCollection, to: /storage/MyCollection)

    signer.link<&CryptoPoops.Collection{CryptoPoops.CollectionPublic}>(/public/MyCollection, target: /storage/MyCollection)
}

}

Mint and transfer import CryptoPoops from 0x02

transaction(recipient: Address) {

prepare(signer: AuthAccount) {
    let minter = signer.borrow<&CryptoPoops.Minter>(from: /storage/Minter) ?? panic("This signer is not the one who deployed the contract.")

    let recipientsCollection = getAccount(recipient).getCapability(/public/MyCollection).borrow<&CryptoPoops.Collection{CryptoPoops.CollectionPublic}>() ?? panic("the user does not have a collection")

    let nft <- minter.createNFT(name: "pelz", favouriteFood: "plantain", luckyNumber: 6)

    recipientsCollection.deposit(token: <- nft)
}

}

Get ID import CryptoPoops from 0x02

pub fun main(address: Address): [UInt64] { let recipientsCollection = getAccount(address).getCapability(/public/MyCollection).borrow<&CryptoPoops.Collection{CryptoPoops.CollectionPublic}>() ?? panic("the user does not have a collection")

return recipientsCollection.getIDs()

}

import CryptoPoops from 0x02

pub fun main(address: Address): String { let recipientsCollection = getAccount(address).getCapability(/public/MyCollection).borrow<&CryptoPoops.Collection{CryptoPoops.CollectionPublic}>() ?? panic("the user does not have a collection")

let recipientsNFT = recipientsCollection.borrowAuthNFT(id: 2)
return "Name: ".concat(recipientsNFT.name).concat(", 
my favourite food is ").concat(recipientsNFT.favouriteFood).concat(", 
lucky number is ").concat(recipientsNFT.luckyNumber.toString())

}




