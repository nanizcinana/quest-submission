# quest-submissions

## Chapter 1 day 1

### Explain what the Blockchain is in your own words.

blockchain is an open (anyone can interact with it), decentralized (no one owner) public database


### Explain what a Smart Contract is. 

smart contract is a program that contains a set of functions and data located in a specific blockchain address


### Explain the difference between a script and a transaction

A **transaction** is a group of sequential operations with a database, which is a logical unit of work with data. A transaction can either complete and complete successfully, respecting data integrity and regardless of other concurrent transactions, or not complete at all, in which case it should have no effect.

the **script** is reading information from the blockchain, it does not require anything and does not cost anything

## Chapter 1 day 2


### What are the 5 Cadence Programming Language Pillars?

Developer Experience

Resource Oriented Programming

Approachability  

Safety and Security

Clarity

### In your opinion, even without knowing anything about the Blockchain or coding, why could the 5 Pillars be useful (you don't have to answer this for #5)?
1. Decentralization

The blockchain does not have a single control center or storage location, and all network participants, whose nodes are located all over the world, are directly involved in maintaining the functionality. Accordingly, decisions regarding the operation of such a network are made in the most democratic way, and the network itself is extremely stable. Blockchain is extremely difficult to hack, it is not subject to censorship, and the management of a single company or state is impossible.

2. Data security

Multiple duplication of data among its participants guarantees the safety and immutability of the information entered into the blockchain. Moreover, due to the specifics of the blockchain device, this information cannot be changed, edited or deleted. And the use of consensus algorithms indicates that all transactions included in the blockchain are confirmed.

3. Transparency of transactions

Each network member has access to the entire transaction history, up to the very first transaction. Therefore, in order to check whether a particular transaction went through between two addresses, you just need to refer to their history stored in the blockchain.

4. High transaction speed

Since blockchain networks are peer-to-peer, transactions occur directly between users, regardless of their location and without the participation of intermediaries. Moreover, the network is always available to users, it does not have limited hours of operation and does not go offline on holidays.

5. Reduce transaction costs

Due to the fact that blockchain networks are peer-to-peer, there is no need to resort to the services of intermediaries in order to conduct a transaction. Thus, thanks to the blockchain, users can simplify the verification of transactions, reduce the time for transaction validation, increase liquidity and minimize the risks of fraud. Moreover, users of the blockchain network pay fees for confirming transactions, which, compared to traditional financial institutions such as banks, are much lower.


___________________________________________________________________________________________________________________________________________________________________

## Chapter 2

### Day 1

deploy a contract
![image](https://user-images.githubusercontent.com/106597629/173200602-6d2dbcac-b143-4c8e-87b4-90efc95672f1.png)

execute script
![image](https://user-images.githubusercontent.com/106597629/173200738-6c343f13-8e24-428b-8dfd-8fc3db31e3a6.png)


### Day 2

Explain why we wouldn't call changeGreeting in a script.

    because the script can only read the information, but not change it. To make changes, use a transaction


What does the AuthAccount mean in the prepare phase of the transaction?

    we access user account data in a preliminary phase

What is the difference between the prepare phase and the execute phase in the transaction?

    in prepare phase we have access the information/data in your account. in execute phase we don't have

Add two new things inside your contract: A variable named myNumber that has type Int (set it to 0 when the contract is deployed) A function named updateMyNumber that takes in a new number named newNumber as a parameter that has type Int and updates myNumber to be newNumber

![image](https://user-images.githubusercontent.com/106597629/173202693-3b7b1ae2-3539-4027-b762-ba0e092867ae.png)


Add a script that reads myNumber from the contract


![image](https://user-images.githubusercontent.com/106597629/173202727-ce524908-d02b-4907-9836-8a225417a299.png)


Add a transaction that takes in a parameter named myNewNumber and passes it into the updateMyNumber function. Verify that your number changed by running the script again.

YAY thats works!
![image](https://user-images.githubusercontent.com/106597629/173203240-29d4af00-0560-4493-b2ac-49298bff8732.png)

and 
![image](https://user-images.githubusercontent.com/106597629/173203249-66caadda-749a-4b8c-9829-3e28a6b9d290.png)

![image](https://user-images.githubusercontent.com/106597629/173203262-3d416ebd-5a82-4ba6-ab9a-f4c353397370.png)


Day 3

```cadence

In a script, initialize an array (that has length == 3) of your favourite people, represented as Strings, and log it.

pub fun main() {
    var favPpl: [String] = ["Nko Belic", "jusus", "Batman"]
    log(favPpl)
}

```

```cadence

In a script, initialize a dictionary that maps the Strings Facebook, Instagram, Twitter, YouTube, Reddit, and LinkedIn to a UInt64 that represents the order in which you use them from most to least. For example, YouTube --> 1, Reddit --> 2, etc. If you've never used one before, map it to 0!

pub fun main() {
    var socialMedias: {String: UInt64} = {"Facebook": 0, "Instagram": 0, "Twitter": 1, "YouTube": 2, "Reddit": 0, "LinkedIn" : 0}
    log(socialMedias)
}

```

Explain what the force unwrap operator ! does, with an example different from the one I showed you (you can just change the type).

    Dictionaries return an optional value, meaning it could be a nil value. The force unwrap tells the code to error if the value is nil instead of the type it expects. In the social media example above, if we tried to read the number value for "TikTok" it would return nil because the dictionary entry does not exist, and the force unwrap operator is needed to error the program

Using this picture below, explain...

What the error message means

    We are wanting to return a String, but actually returning an Optional String Why we're getting this error
    due to dictionaries returning optionals when accessed. This is because the entry you are looking for may not exist. How to fix it
    Ideally, return the optional "String?" and let the accessor handle any errors. Alternatively, use the Force Unwrap "thing[0x03]!" operator in the return statement to error when nil

### Day 4

**Deploy a new contract that has a Struct of your choosing inside of it (must be different than Profile). Create a dictionary or array that contains the Struct you defined. Create a function to add to that array/dictionary.**



**Create a dictionary or array that contains the Struct you defined.**

**Create a function to add to that array/dictionary.**


```cadence

pub contract Auth {

    pub var profiles: {Address: Profile}
    
    pub struct Profile {
        pub let codename: String
        pub let order: Int
        pub let account: Address

        init(_codename: String, _order: Int, _account: Address) {
            self.codename = _codename
            self.order = _order
            self.account = _account
        }
    }

    pub fun addProfile(codename: String, order: Int, account: Address) {
        let newProfile = Profile(_codename: codename, _order: order, _account: account)
        self.profiles[account] = newProfile
    }

    init() {
        self.profiles = {}
    }

}

```

**Add a transaction to call that function in step 3.**

```cadence

import Auth from 0x01

transaction(codename: String, order: Int, account: Address) {

    prepare(signer: AuthAccount) {}

    execute {
        Auth.addProfile(codename: codename, order: order,  account: account)
        log("i think it's done.")
    }
}

```


**Add a script to read the Struct you defined.**

```cadence

import Auth from 0x01

pub fun main(account: Address): Auth.Profile {
    return Auth.people[account]!
}

```
_______________________________________________________________________________________________________________________________________________________________________

## Chapter 3
### Day 1

**In words, list 3 reasons why structs are different from resources.**

Only 1 version of a resource can ever exist
resources must be "moved" between locations and cannot be lost
Resources must be specially created and destroyed
    


**Describe a situation where a resource might be better to use than a struct.**

i think thats NFT's

**What is the keyword to make a new resource?**

create

**Can a resource be created in a script or transaction (assuming there isn't a public function to create one)?**

No. the create keyword can only be used inside the contract level

**What is the type of the resource below?**

it is a Jacob type resource, right?

**Let's play the "I Spy" game from when we were kids. I Spy 4 things wrong with this code. Please fix them.**

FIXED:

```cadence

pub contract Test {

    // Hint: There's nothing wrong here ;)
    pub resource Jacob {
        pub let rocks: Bool
        init() {
            self.rocks = true
        }
    }

    pub fun createJacob(): @Jacob { 
        let myJacob <- create Jacob() 
        return <- myJacob 
    }
}

```


### Day 2

```Cadence

pub contract myOwnSmartContract {

    pub var myArray: @[Elem1]
    pub var myDictionary: @{String: Elem1}

    pub resource Elem1 {
        pub let message: String

        init() {
            self.message = "i'm message for array"
        }
    }


    pub fun addInMyArray(Elem1: @Elem1) {
        self.myArray.append(<- Elem1)
    }

    pub fun addInDicrionary(Elem1: @Elem1) {
        let key = Elem1.message

        let oldElem1 <- self.myDictionary[key] <- Elem1
        destroy oldElem1
    }


    pub fun removeFromMyArray(index: Int): @Elem1 {
        return <- self.myArray.remove(at: index)

    }

    pub fun removeFromDictionary(key: String): @Elem1 {
        let Elem1 <- self.myDictionary.remove(key: key) ?? panic("Could not find element")
        return <- Elem1
    }




    init() {
        self.myArray <- []
        self.myDictionary <- {}
    }

}


```



### Day 3

**Define your own contract that stores a dictionary of resources. Add a function to get a reference to one of the resources in the dictionary.**

```cadence

pub contract dogNFTs {

    pub var NFTset: @{UInt64: catNFT}

    pub fun dogReference(key: UInt64): &catNFT {
        return &self.NFTset[key] as &catNFT
    }

    pub fun addNFT(id: UInt64, catName: String, gender: String, color: String) {
        let catNFTdetail <- create catNFT(_id: id, _catName: catName, _gender: gender, _color: color)
        self.NFTset[catNFTdetail.id] <-! catNFTdetail
    }

    pub resource catNFT {
        pub var id: UInt64
        pub var catName: String
        pub var gender: String
        pub var color: String

        init(_id: UInt64, _catName: String, _gender: String, _color: String, _age: UInt64) {
            self.id = _id
            self.catName = _catName
            self.gender = _gender
            self.color = _color
        }
    }

    init(){
        self.NFTset <- {}
    }
}
```

**Create a script that reads information from that resource using the reference from the function you defined in part 1.**

```cedence

script that reads information
import dogNFTs from 0x01

pub fun main(key: UInt64): &catNFTs.catNFT {
  
  return catNFTs.catReference(key: key)
}

```


**you can use the links to get information about their non-movement, very convenient**



### Day 4

Explain, in your own words, the 2 things resource interfaces can be used for (we went over both in today's content)

    Restricting access to state information or functions - If a Beer resource has a Recipe associated with it, the brewer should be able to see it, but the graphic designer may not need to
    Creating different rulesets for different applications using the same Resource - a Beer resource could be used by a Retailer or a Consumer and each may have different capabilities or information, but both could use the same physical Beer resource

Define your own contract. Make your own resource interface and a resource that implements the interface. Create 2 functions. In the 1st function, show an example of not restricting the type of the resource and accessing its content. In the 2nd function, show an example of restricting the type of the resource and NOT being able to access its content.


```cadence

pub resource interface Wine {
        pub var name: String
        pub var retailPrice : UFix64
    }

    pub resource Beer : Wine {
        pub var wholesalePrice : UFix64
        pub var retailPrice : UFix64
        pub var name: String
        pub var style: String
        pub var abv : UFix64
        pub var ibu : UFix64

        init(_WineName: String, _style: String, _abv : UFix64, _ibu : UFix64){
            self.name = _beerName
            self.style = _style
            self.abv = _abv
            self.ibu = _ibu
            self.retailPrice = 0.0
            self.wholesalePrice = 0.0
        }
    }

```
**How would we fix this code?**

FIXED:

```cadence

pub contract Stuff {

    pub struct interface ITest {
      pub var greeting: String
      pub var favouriteFruit: String
      pub fun changeGreeting(newGreeting: String): String //added
    }

    pub struct Test: ITest {
      pub var greeting: String
      pub var favouriteFruit: String //added

      pub fun changeGreeting(newGreeting: String): String {
        self.greeting = newGreeting
        return self.greeting // returns the new greeting
      }

      init() {
        self.greeting = "Hello!"
        self.favouriteFruit = "Apple" //added
      }
    }

    pub fun fixThis() {
      let test: Test{ITest} = Test()
      let newGreeting = test.changeGreeting(newGreeting: "Bonjour!")
      log(newGreeting)
    }
}

```

### Day 5

```cadence

access(all) contract SomeContract {
    pub var testStruct: SomeStruct

    pub struct SomeStruct {

        //
        // 4 Variables
        //

        pub(set) var a: String

        pub var b: String

        access(contract) var c: String

        access(self) var d: String

        //
        // 3 Functions
        //

        pub fun publicFunc() {}

        access(contract) fun contractFunc() {}

        access(self) fun privateFunc() {}


        pub fun structFunc() {
            /**************/
            /*** AREA 1 ***/
            /**************/
        }

        init() {
            self.a = "a"
            self.b = "b"
            self.c = "c"
            self.d = "d"
        }
    }

    pub resource SomeResource {
        pub var e: Int

        pub fun resourceFunc() {
            /**************/
            /*** AREA 2 ***/
            /**************/
        }

        init() {
            self.e = 17
        }
    }

    pub fun createSomeResource(): @SomeResource {
        return <- create SomeResource()
    }

    pub fun questsAreFun() {
        /**************/
        /*** AREA 3 ****/
        /**************/
    }

    init() {
        self.testStruct = SomeStruct()
    }
}

```


variable A

    Read Scoped
        Area's 1, 2, 3, 4
    Write Scoped
        Area's 1, 2, 3, 4

Variable B

    Read Scoped
        Area's 1, 2, 3, 4
    Write Scoped
        Area 1

Variable C

    Read Scoped
        Area's 1, 2, 3
    Write Scoped
        Area 1

Variable D

    Read Scoped
        Area 1
    Write Scoped
        Area 1

publicFunc

    Access Scoped
        Area's 1, 2, 3, 4

privateFunc

    Access Scoped
        Area 1

contractFunc

    Access Scoped
        Area's 1, 2, 3

Right?

____________________________________________________________________________________________________________________________________________________________________

## Chapter 4

### day 1

**Explain what lives inside of an account.**

Accounts consist of any contract code deployed by your account, as well as a storage section that has both public and private paths.

    
**What is the difference between the /storage/, /public/, and /private/ paths?**


storage/ <----
This is main storage section of your accout where all your data is actually stored.
public/ <----
This is a public storage section that is available to everyone
private/ <----
This is a private storage section that is only available to the owner and specefic people the give access to.
    
**What does .save() do? What does .load() do? What does .borrow() do?**

.save()
This saves a resource into account storage
.load()
This loads a resrouce from account storage using the type and path specified.
.borrow()      
This create a reference to a resource that someone can borrow without removing the resource from your account storage.


**Explain why we couldn't save something to our account storage inside of a script.**

Scripts only allow you to read things from the blockchain, since saving someting would modify the blockchain it requires gas fees thus needing a transaction to complete it.


**Explain why I couldn't save something to your account.**

Only the account owner can access their account storage utilziing their AuthAccount.
Define a contract that returns a resource that has at least 1 field in it. Then, write 2 transactions:

```cadence
pub contract bChain {

    pub resource elem1 {
        pub let itemName: String
        pub let itemID: String
        pub var bChain: @[CustodyExhange]

        init(_itemName: String, _itemID: String) {
            self.itemName = _itemName
            self.itemID = _itemID
            self.bChain <- []
        }

        destroy() {
            destroy self.bChain
        }

        pub fun addCustodyExchange(custodyExhange: @CustodyExhange) {
            self.bChain.append(<- custodyExhange)
        }

        pub fun removeCustodyExhange(index: Int): @CustodyExhange {
            return <- self.bChain.remove(at: index)
        }
    }

    pub resource CustodyExhange {
        pub let exchangeID: String
        pub let custodiansName: String
        pub let dateOfExchange: String

        init(_exchangeID: String, _custodiansName: String, _dateOfExchange: String) {
            self.exchangeID = _exchangeID
            self.custodiansName = _custodiansName
            self.dateOfExchange = _dateOfExchange
        }
    }

    init() {
        
    }

    pub fun createelem1(_itemName: String, _itemID: String): @elem1 {
        return <- create elem1(_itemName: _itemName, _itemID: _itemID)
    }

}
```

1. A transaction that first saves the resource to account storage, then loads it out of account storage, logs a field inside the resource, and destroys it.

```cadence
import bChain from 0x01

transaction(_itemName: String, _itemID: String) {

    prepare(signer: AuthAccount) {
        let elem1 <- bChain.createelem1(_itemName: _itemName, _itemID: _itemID)
        signer.save(<- elem1, to: /storage/Myelem1)

        let loadedelem1 <- signer.load<@ChainOfCustody.elem1>(from: /storage/elem1) ?? panic("Nothing found at this path")
        log(loadedelem1.itemName)
        destroy loadedelem1
    }

    execute {

    }
}
```
2. A transaction that first saves the resource to account storage, then borrows a reference to it, and logs a field inside the resource.

``` cadence
import bChain from 0x01

transaction(_itemName: String, _itemID: String) {

    prepare(signer: AuthAccount) {
        let elem1 <- bChain.createelem1(_itemName: _itemName, _itemID: _itemID)
        signer.save(<- elem1, to: /storage/Myelem1)

        let loadedelem1 = signer.borrow<&ChainOfCustody.elem1>(from: /storage/Myelem1) ?? panic("Nothing found at this path")
        log(loadedelem1.itemName)
    }

    execute {

    }
}

```

### day2

**What does .link() do?**


.link() makes a link for accessibility to the place where the resources are /public /private make them available


**In your own words (no code), explain how we can use resource interfaces to only expose certain things to the /public/ path.**

Having defined variables for functions that we would like to give other people access to the resource interface, we will use them to access resources, accessing resources in the /public/ path.



![image](https://user-images.githubusercontent.com/106597629/173684382-458d0a65-46a3-4c64-9606-28e372b51251.png)
![image](https://user-images.githubusercontent.com/106597629/173684453-d5b2969b-f295-4502-8cb1-73b30f3fe37f.png)
![image](https://user-images.githubusercontent.com/106597629/173684617-3072afe1-24c1-4b16-9fe4-7bae089e27fb.png)


### day3

**Why did we add a Collection to this contract? List the two main reasons**

We have changed the collection to this contract, due to

If we had multiple NFTs, we would need to remember every single storage path we gave to each NFT, which is very inefficient and annoying.
No one can give us any NFTs because only the account owner can store NFTs in /storage/ directly, so no one can create NFTs for us.
          
**What do you have to do if you have resources "nested" inside of another resource? ("Nested resources")**

If you have resources "embedded" on another resource, you will appropriately proclaim a prohibition prohibition, which unconsciously destroys the "nested" repertoires with the support of the elimination of the paramount word.

**Brainstorm some extra things we may want to add to this contract. Think about what might be problematic with this contract and how we could fix it.**

If we want to read information about our NFTs inside our Collection, right now we need to take it from the Collection in order to do so. This is good?

No, we don't want everyone to be able to create NFTs. Sometimes we need to be able to mint only certain addresses, for example in a whitelist/allowlist scenario. So, we need to add a resource that mints NFT. Thus, only the address that owns this resource can create an NFT.

Removing our NFTs from our Collection to read something about it is not good, because we only want to have one "container" for all of our NFTs so that they can be stored in it for ease of access and functionality. In order to read our NFTs without taking them out of the collection, we need to add a .borrow() function to our NFT contract because the .borrow() function allows us to view the data in /storage/.

### day4

Because we had a LOT to talk about during this Chapter, I want you to do the following:
Take our NFT contract so far and add comments to every single resource or function explaining what it's doing in your own words. Something like this:


```cadence

pub contract CryptoPoops {
pub var totalSupply: UInt64

// This NFT resource contains the and ID field and several meta data fields

pub resource NFT {
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

// This resource interface defines the publicly accessible methods for our NFT Collection 

pub resource interface CollectionPublic {
    pub fun deposit(token: @NFT)
    pub fun getIDs(): [UInt64]
    pub fun borrowNFT(id: UInt64): &NFT
}

// This is our NFT Collection, it implements the public collection interface and stores our NFTs allowing for deposits, withdrawals and borrowing of the NFT.

pub resource Collection: CollectionPublic {
    pub var ownedNFTs: @{UInt64: NFT}

    // This functions is used to deposit NFTs into the collection.

    pub fun deposit(token: @NFT) {
    self.ownedNFTs[token.id] <-! token
    }

    //This function is used to withdraw NFTs from the collection.

    pub fun withdraw(withdrawID: UInt64): @NFT {
    let nft <- self.ownedNFTs.remove(key: withdrawID) 
            ?? panic("This NFT does not exist in this Collection.")
    return <- nft
    }

    //Returns all NFTs IDs of owned NFTs.

    pub fun getIDs(): [UInt64] {
    return self.ownedNFTs.keys
    }

    //Used for borrowing the NFT and reading its metadata without removing it from the collection.

    pub fun borrowNFT(id: UInt64): &NFT {
    return &self.ownedNFTs[id] as &NFT
    }

    // called when the collection is created and created an empty dictionary of owned NFTs.

    init() {
    self.ownedNFTs <- {}
    }
    
    // explictly destorys the nested dictionary of resources when the collection is destroyed.

    destroy() {
    destroy self.ownedNFTs
    }
}

// Creates an empty collection and returns it to the transaction calling it.

pub fun createEmptyCollection(): @Collection {
    return <- create Collection()
}

// this is Minter resource which is the only place with the code to create NFTs or addtional minters.

pub resource Minter {
    // Creates the NFTs and returns it to the transaction calling the function.

    pub fun createNFT(name: String, favouriteFood: String, luckyNumber: Int): @NFT {
    return <- create NFT(_name: name, _favouriteFood: favouriteFood, _luckyNumber: luckyNumber)
    }

    // creates a new Minter resource allowing for someone else to mint NFTs.

    pub fun createMinter(): @Minter {
    return <- create Minter()
    }

}

// called when the contract is deployed setting the supply variable to 0 and saving a Minter resource to the account storage.

init() {
    self.totalSupply = 0
    self.account.save(<- create Minter(), to: /storage/Minter)
}
}

```
____________________________________________________________________________________________________________________________________________________________________

## day5
### chapter 1


**Describe what an event is, and why it might be useful to a client. **

An event is an event that notifies all participants in the blockchain network, for example mint nft, so clients can update thier code accordingly, like the live claim feed on floats.city that shows every time a FLOAT is minted and claimed by an address and clients can avoid constantly checking the smart contract to check if an event occurred, which is inefficient and annoying

**Deploy a contract with an event in it, and emit the event somewhere else in the contract indicating that it happened. **
![image](https://user-images.githubusercontent.com/106597629/173758666-3014ca25-f549-4cc3-b7cf-8bcc2f130360.png)

**Using the contract in step 2), add some pre conditions and post conditions to your contract to get used to writing them out**

![image](https://user-images.githubusercontent.com/106597629/173759853-5d44d678-fbd5-4349-a504-318c7ca713ea.png)

**For each of the functions below (numberOne, numberTwo, numberThree), follow the instructions.**

![image](https://user-images.githubusercontent.com/106597629/173760547-bfcbd333-0de4-45c0-bf9e-a9880178a63c.png)



_THE OLD ANSWER:_
numberOne: No, the function will not log the name "Jacob"
numberTwo: Yes, the function will return a value.
numberThree: Yes, the function will log the updated number. After it's run, the value of self.number will be 2.

_THE NEW ANSWER:_ 
numberOne: Yes, the function will log the name "Jacob" 
numberTwo: Yes, the function will return a value.
numberThree: No, the function won't run because the pre-condition of 5 isn't met.

### day2

**Explain why standards can be beneficial to the Flow ecosystem.**

The standards can be useful for the FLOW ecosystem as they communicate to us the understanding that the smart contract we are considering should be an "NFT contract" without having to read all of its code line by line. It also helps women, in this way, as a DApp in the market, to understand what they are going for and do not need to implement different features for each NFT contract. It's also useful for discussion because they have an NFT contract scheme that you can look at to make sure they include what's needed (and therefore they're not really bad NFT contracts).


**What is YOUR favourite food?**

pizza

**Please fix this code (Hint: There are two things wrong):**

```cadence

pub contract Test {
  pub var number: Int
  
  pub fun updateNumber(newNumber: Int) {
    newNumber = 5 //Mistake #1
  }

  pub resource interface IStuff {
    pub var favouriteActivity: String
  }

  pub resource Stuff: ITest.IStuff { //Mistake #2  
    pub var favouriteActivity: String

    init() {
      self.favouriteActivity = "Playing League of Legends."
    }
  }

  init() {
    self.number = 0
  }
}

```

```cadence

pub contract Test: ITest {
    pub var number: Int
    
    pub fun updateNumber(newNumber: Int) {
        self.number = newNumber
    }

    pub resource interface IStuff {
        pub var favouriteActivity: String
    }

    pub resource Stuff: IStuff {
        pub var favouriteActivity: String

        init() {
        self.favouriteActivity = "Playing League of Legends."
        }
    }

    init() {
        self.number = 0
    }
}

```


### day3

**What does "force casting" with as! do? Why is it useful in our Collection? **

Reduction to strength allows us to move from a more common type to increased excitability. This is useful because we are storing or embedding our NFT type, not the generic NFT type. This of course has a wider application for all types of interfaces.

**What does auth do? When do we use it? **

auth is how we use "coercion" for resource references. We use authorization sequence per generic type and then apply it using as

**This last quest will be your most difficult yet. Take this contract:

and add a function called borrowAuthNFT just like we did in the section called "The Problem" above. Then, find a way to make it publically accessible to other people so they can read our NFT's metadata. Then, run a script to display the NFTs metadata for a certain id.

You will have to write all the transactions to set up the accounts, mint the NFTs, and then the scripts to read the NFT's metadata. We have done most of this in the chapters up to this point, so you can look for help there :)**

```cadende

import NonFungibleToken from 0x02
pub contract CryptoPoops: NonFungibleToken {
    pub var totalSupply: UInt64

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

```
make transaction collection for 2 acc

```cadence
import CryptoPoops from 0x01

transaction() {

    prepare(signer: AuthAccount) {
        let newCollection <- CryptoPoops.createEmptyCollection()
        signer.save(<- newCollection, to: /storage/MyCollection)

        signer.link<&CryptoPoops.Collection{CryptoPoops.CollectionPublic}>(/public/MyCollection, target: /storage/MyCollection)
    }
}

```
trans to nint NFT and tranfer for to acc


```cadence
import CryptoPoops from 0x01

transaction(recipient: Address) {

    prepare(signer: AuthAccount) {
        let minter = signer.borrow<&CryptoPoops.Minter>(from: /storage/Minter) ?? panic("This signer is not the one who deployed the contract.")

        let recipientsCollection = getAccount(recipient).getCapability(/public/MyCollection).borrow<&CryptoPoops.Collection{CryptoPoops.CollectionPublic}>() ?? panic("the user does not have a collection")

        let nft <- minter.createNFT(name: "Object of Unkown Origin", favouriteFood: "Apples", luckyNumber: 7)

        recipientsCollection.deposit(token: <- nft)
    }
}
```
this is script for Get ID

```cadence
import CryptoPoops from 0x01

pub fun main(address: Address): [UInt64] {
    let recipientsCollection = getAccount(address).getCapability(/public/MyCollection).borrow<&CryptoPoops.Collection{CryptoPoops.CollectionPublic}>() ?? panic("the user does not have a collection")

    return recipientsCollection.getIDs()
}
```

check borrowed
```cadence
import CryptoPoops from 0x01

pub fun main(address: Address): String {
    let recipientsCollection = getAccount(address).getCapability(/public/MyCollection).borrow<&CryptoPoops.Collection{CryptoPoops.CollectionPublic}>() ?? panic("the user does not have a collection")

    let recipientsNFT = recipientsCollection.borrowAuthNFT(id: 3)
    return "NFT Says: My name is ".concat(recipientsNFT.name).concat(", my favourite food is ").concat(recipientsNFT.favouriteFood).concat(", and my lucky number is ").concat(recipientsNFT.luckyNumber.toString())
}
```
