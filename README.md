# Token
This is a solidity application where I am developing a token  program. Following user input, this program will provide the Total supply and the remaining amount as output. This code uses the basic concepts of a solidity, such as if-else conditions and function, etc.

# Description
This is straightforward Solidity programming code. This program is a simple contract written in Solidity, a programming language for Ethereum smart contracts. Two functions, two strings —one storing the name of the Token and the second storing the abbreviation of the Token, and two variables —one of which is of the uint type and the other is the mapping variable. The address is mapped to the uint type using the mapping variable. There are two functions: the mint function, which increase the balances and totalsupply, and the burn function, which is the reverse of the mint function but also includes an if-else statement.

# Getting Start
You should first launch the Remix online IDE, which is the solidity compiler, at https://remix.ethereum.org/ to begin working with this programming language. You must now create a file in which to write code when the IDE starts. To do this, click on the new file option that appears in the left-hand sidebar. Give the file the name you like, then save it with an extension.sol. Take aryan-token.sol, for instance.

```
// SPDX-License-Identifier: MIT
pragma solidity 0.8.7;

contract token{
    string public name = "Aryan";
    string public abbreviation = "AR";
    uint public totalsupply;

    mapping(address => uint) public balance;

    function mint(address _addr, uint _value) public {
        totalsupply += _value;       
        balance[_addr] += _value;     
    }

    function burn(address _addr, uint _value) public returns  (string memory ) {
        if (balance[_addr] >= _value) {
            balance[_addr] -= _value;     
            totalsupply -= _value; 
            }
        else {
            return ("Not Enough Balance");
        }}
        }
```
Select the "Solidity Compiler" tab from the sidebar on the left to begin compiling the code. Click "Compile aryan-token.sol" after ensuring that the "Compiler" option is set to "0.8.7".
You can use the contract after the code has been compiled. Six buttons—two orange and four blue—will be shown when the contract is deployed. The variables are represented by the Blue ones and the function by the orange ones.

When you click  name, "Aryan" will appear. "AR" appears when you click on the abbreviation. 
Now, from the account that is shown above the deploy button, you can choose address. Select an address from there, then copy it to the clipboard.

After doing that, simply paste the address into the mint function and enter any random number, like 500. Now, just verify the entire supply once more after doing that. The value has risen from 0 to 500. Apply the burn function in the same way, and the overall supply will drop.
You may now work with state variables and functions, run the burn function with various values, and see how variables like total supply react.

# Explanation
I started by creating the "token" contract. I created two string-type public variables in the contract called name and abbreviation, and I assigned the values "Aryan" and "AR", respectively.
I then made a public variable of type uint called totalsupply, whose default value is 0.
 (address => uint) is the mapping variable I made. This indicates that uint is the mapping for the address.

The next function is a mint function, which takes two parameters: addr (address) and value. Value is added to the address's balance and total supply inside a mint function.

Finally, the function burn is developed, and it works in opposition to the function mint. The function uses an if-else condition in which the value is deducted from both the total supply and the balances of address if the balance of address is more than or equal to the given value.

# License
This project is licensed under the MIT License - see the LICENSE.md file for details
