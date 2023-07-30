// SPDX-License-Identifier: MIT
pragma solidity ^0.8.18;

contract ArrayDeletion {
uint[] public items;

    constructor(uint[] memory _items) {
        items = _items;
    }

    function deleteItem(uint index) public {
        require(index < items.length, "Index out of bounds");

        // Shift all items to the left
        for (uint i = index; i < items.length - 1; i++) {
            items[i] = items[i + 1];
        }

        // Delete the last element
        items.pop();
    }

    function getItems() public view returns(uint[] memory) {
        return items;
    }

}
