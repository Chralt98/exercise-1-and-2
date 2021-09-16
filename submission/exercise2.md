# Exercise 2:

1. Design kitties pallet 
2. Requirements:
    
    a. Kitty must have a 128 bit DNA, which is randomly generated

    b. Kitty must have one owner

    c. A user can have zero or more kitties
 
### pallet-kitties

Config:
- Event: From<Event<Self>> + IsType<<Self as frame_system::Config>::Event>
- KittyRandomness: Randomness<H128, Self::BlockNumber>

Calls:
- fn create_kitty

Types:
- struct Kitty
    - owner: AccountId
    - id: u64
    - dna: Hash

Storages:
- MapOwnerWithIndexToKitty: StorageMap (AccountId, u64) => Optional<Kitty>
- NextKittyId: u64

Events:
- KittyCreated
    - kitty_id: u64
    - owner: AccountId
    - kitty: Kitty

Implementations:
- GetRandomHash: AccountId => Hash

Additional comments or pseudo code: -