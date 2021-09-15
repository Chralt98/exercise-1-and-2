# Exercise 2:

1. Design kitties pallet 
2. Requirements:
    
    a. Kitty must have a 128 bit DNA, which is randomly generated
    b. Kitty must have one owner
    c. A user can have zero or more kitties
 
# pallet-kitties

Calls:
- fn create_kitty
Types:
- struct Kitty
    - owner: AccountId
    - price: Balance
    - dna: Hash
Storages:
- KittyOfOwner: double_map AccountId, u32 => Option<Kitty>
- NextKittyId: u32
Events:
- KittyCreated
    - owner: AccountId
    - kitty_id: u32
    - kitty: Kitty
    