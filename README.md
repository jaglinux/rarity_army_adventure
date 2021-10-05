# rarity_army_adventure
Building army on top of rarity game by Andre Cronje.
Task is to create army of all summoners and use it to adventure in a group.

## Steps to add summoners to army
## 1. Approve rarity_army_adventure contract to summoner.  
  3 Go the main contract of rarity game, 0xce761D788DF608BD21bdd59d6f4B54b2e27F25Bb  
   Under Write contract, approve(to, tokenId) --> 'to' is the contract deployed address of rarity_army_adventure <yet to deploy the contract>  
                                                  tokenId is your summoner id.  
   Repeat above step for all the summoners belonging to each EOA.  

### 2. Register summoner in rarity_army_adventure contract
   Go the rarity_army_adventure, <contract address (TBD)>  
   Under Write contract, register_to_army(uint256[]) --> add all summoners id in an array to register.  
   This creates a mapping to your address to array of summoners id.  
   Note that the summoners id should be approved to use this contract as mentioned in step1.  
   
## Command to order adventure once a day
### 3. Go the rarity_army_adventure, <contract address (TBD)>
  Under Write contract, command_adventure_all() --> this will order all summoners belonging to EOA to adventure.  
  Even if one summoner fails to adventure (due to 1 day limit), then the transaction will fail.  
  Repeat for all EOA which has summoners attached to it. (commander --> summoners[])  
 
 ## Add or remove summoners
 command_adventure_all()  
 deregister_from_army()  
