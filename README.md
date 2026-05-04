// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract SimpleVault {
    address public owner;
    constructor() { owner = msg.sender; }
    receive() external payable {} // Дозволяє приймати ETH
    function withdraw() external {
        require(msg.sender == owner, "Not owner");
        payable(owner).transfer(address(this).balance);.3
    }
}
