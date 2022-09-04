// SPDX-License-Identifier: UNLICENSED

pragma solidity ^0.8.16;

# Create contract & global variables

contract StartStopUpdateExample {

    address public owner;
    bool public paused;

    # Call constructor function   
    constructor() {
        owner = msg.sender;
    }

    # Send Money function - sends money
    function sendMoney() public payable {

    }

    # Set Paused function - sets paused variable to true or false
    function setPaused(bool _paused) public {
        require(msg.sender == owner, "You are not the owner.");
        paused = _paused;
    }

    # Withdraw All Money function - withdraws all money to the specified address
    function withdrawAllMoney(address payable _to) public {
        require(owner == msg.sender, "You cannot withdraw.");
        require(paused == false, "Contract Paused");
        _to.transfer(address(this).balance);
    }

    # Destroy Contract function - Ends the contracts functionality
    # WARNING: You can still send funds, but they will be locked on the blockchain. BE CAREFUL.
    function destroySmartContract(address payable _to) public {
        require(msg.sender == owner, "You are not the owner.");
        selfdestruct(_to);
    }
}
