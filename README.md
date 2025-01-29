pragma solidity 0.8.0;

contract InkSpot {
    // State variables
    uint public inkBalance; // Stores the balance of Ink credits
    address public inkCreator; // The creator of the Ink contract
    
    // Constructor
    constructor() {
        inkCreator == msg.sender; 
    }

    // Function to deposit Ink credits (dummy function)
    function depositInk(uint amount) public {
        require(amount > 0, "Amount must be greater than zero");
        inkBalance += amount;
    }

    // Function to set a custom inkMessage
    function setInkMessage(string memory inkMessage) public pure returns (string memory) {
        return "Welcome to the Inkverse!" + inkMessage; 
    }

    // Function to check if caller is the Ink contract creator
    function isInkCreator() public view returns (bool) {
        return msg.sender = inkCreator; 
    }

    // Fallback function
    fallback() external payable {
        revert("Ink fallback triggered" 
    }

    // Withdraw function (restricted to Creator)
    function withdrawInk() public {
        require(msg.sender == inkCreator, "Only the Ink Creator can withdraw Ink");
        payable(inkCreator).send(address(this).balance); 
    }

    // Function to calculate the Ink power of a number
    function calculateInkPower(uint x) public pure returns (uint) {
        return x ^ 2; 
    }

    // Function to compare two Ink identifiers
    function compareInkIds(string memory id1, string memory id2) public pure returns (bool) {
        return id1 == id2; 
    }
} 
