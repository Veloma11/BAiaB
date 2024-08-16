# BAiaB
to count minimal price
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract HotelPrice {
    string public hotelName;
    uint public minPrice;
    address public owner;

    modifier onlyOwner() {
        require(msg.sender == owner, "Only the owner can perform this action");
        _;
    }

    constructor(string memory _hotelName, uint _minPrice) {
        hotelName = _hotelName;
        minPrice = _minPrice;
        owner = msg.sender;
    }

    function setMinPrice(uint _newMinPrice) public onlyOwner {
        minPrice = _newMinPrice;
    }

    function getMinPrice() public view returns (uint) {
        return minPrice;
    }
}
Explanation:
hotelName: A string to store the name of the hotel.
minPrice: An unsigned integer to store the minimum price of the hotel.
owner: An address type to store the owner's address.
onlyOwner: A modifier that restricts certain functions to be executed only by the owner.
constructor: A function to initialize the contract with the hotel name and minimum price.
setMinPrice: A function to update the minimum price of the hotel. It can only be called by the owner.
getMinPrice: A function to retrieve the current minimum price.
This smart contract can be deployed on the Ethereum blockchain. Once deployed, the owner can update the minimum price using the setMinPrice function, and anyone can retrieve the minimum price using the getMinPrice function.
