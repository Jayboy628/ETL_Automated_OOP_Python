# OOP - "Automate ETL process using Python and AWS"

![contract](Images/data_python.png)

## My Background

My name is Shaunjay Brown and I have years of experience in Business Intelligence and Data Analysis. Data extraction is one of my many functions in BI and I mainly used SSIS and SQL to Extract Transform and Load. However, I find that SSIS is better suited for large functions like data migration because SSIS has a high overhead cost with maintenance, performance and more importantly time consuming.
I am very excited for my new love for python and using pandas with python allows me to quickly profile the data and quickly decide what I need for my reports.
I am going to illustrate a production ready ETL pipeline in python using Pandas tool to write python code and Visual studio to refactorize the code into an object oriented code.

## Project Background

The Deutsche Börse Public Dataset (PDS) project makes near-time data derived from Deutsche Börse's trading systems available to the public for free. This is the first time that such detailed financial market data has been shared freely and continually from the source provider.

This data is provided on a minute-by-minute basis and aggregated from the Xetra and Eurex engines, which comprise a variety of equities, funds and derivative securities. The PDS contains details for on a per security level, detailing trading activity by minute including the high, low, first and last prices within the time period.

## Content

- Quick and Dirty.

- Functional Approach.

- Object Oriented Approach.

## Files

- [`AssociateProfitSplitter.sol`](Starter-Code/AssociateProfitSplitter.sol) -- Level 1 starter code.

- [`TieredProfitSplitter.sol`](Starter-Code/TieredProfitSplitter.sol) -- Level 2 starter code.

- [`DeferredEquityPlan.sol`](Starter-Code/DeferredEquityPlan.sol) -- Level 3 starter code.

## Task Background

This assignment has three levels of difficulty, with each contract increasing in complexity and capability. Although it is highly recommended you complete all three contracts, you are only required to solve one of the three contracts. Recommended to start with Level 1, then move forward as you complete the challenges. You can build all three with the skills you already have!

- **Level One** is an `AssociateProfitSplitter` contract. This will accept Ether into the contract and divide the Ether evenly among the associate level employees. This will allow the Human Resources department to pay employees quickly and efficiently.

- **Level Two** is a `TieredProfitSplitter` that will distribute different percentages of incoming Ether to employees at different tiers/levels. For example, the CEO gets paid 60%, CTO 25%, and Bob gets 15%.

- **Level Three** is a `DeferredEquityPlan` that models traditional company stock plans. This contract will automatically manage 1000 shares with an annual distribution of 250 over 4 years for a single employee.

Navigate to the [Remix IDE](https://remix.ethereum.org) and create a new contract called `AssociateProfitSplitter.sol` using the starter code for level one above.

While developing and testing your contract, use the [Ganache](https://www.trufflesuite.com/ganache) development chain, and point MetaMask to `localhost:8545`, or replace the port with what you have set in your workspace.

### Step one: Quick and Dirty

At the top of your contract, you will need to define the following `public` variables:

- `employee_one` -- The `address` of the first employee. Make sure to set this to `payable`.

- `employee_two` -- Another `address payable` that represents the second employee.

- `employee_three` -- The third `address payable` that represents the third employee.

Create a constructor function that accepts:

- `address payable _one`

- `address payable _two`

- `address payable _three`

Within the constructor, set the employee addresses to equal the parameter values. This will allow you to avoid hardcoding the employee addresses.

Next, create the following functions:

- `balance` -- This function should be set to `public view returns(uint)`, and must return the contract's current balance. Since we should always be sending Ether to the beneficiaries, this function should always return `0`. If it does not, the `deposit` function is not handling the remainders properly and should be fixed. This will serve as a test function of sorts.

- `deposit` -- This function should set to `public payable` check, ensuring that only the owner can call the function.

  - In this function, perform the following steps:

    - Set a `uint amount` to equal `msg.value / 3;` in order to calculate the split value of the Ether.

    - Transfer the `amount` to `employee_one`.

    - Repeat the steps for `employee_two` and `employee_three`.

    - Since `uint` only contains positive whole numbers, and Solidity does not fully support float/decimals, we must deal with a potential remainder at the end of this function since `amount` will discard the remainder during division.

    - We may either have `1` or `2` wei leftover, so transfer the `msg.value - amount * 3` back to `msg.sender`. This will re-multiply the `amount` by 3, then subtract it from the `msg.value` to account for any leftover wei, and send it back to Human Resources.

- Create a fallback function using `function() external payable`, and call the `deposit` function from within it. This will ensure that the logic in `deposit` executes if Ether is sent directly to the contract. This is important to prevent Ether from being locked in the contract since we don't have a `withdraw` function in this use-case.

In the `Deploy` tab in Remix, deploy the contract to your local Ganache chain by connecting to `Injected Web3` and ensuring MetaMask is pointed to `localhost:8545`.

You will need to fill in the constructor parameters with your designated `employee` addresses.

Test the `deposit` function by sending various values. Keep an eye on the `employee` balances as you send different amounts of Ether to the contract and ensure the logic is executing properly.

### Requirements

<details>
<summary>Tools and Package</summary>

- Python 3.9
- Jupyter Notebook
- Github
- Visual Studio
- padas, boto3, pyyaml, awscli, jupyter, pylint, moto, coverage, memory-profile

</details>

<details>
<summary>Best Practice Python</summary>

#### Best practices in developing Python code

- Design Princples
- Clean Coding
- Virtual Environments
- Configuration
- Logging
- Folder setup
- Unit Testing
- Exception Handling
- Lintig

© 2021 Trilogy Education Services, a 2U, Inc. brand. All Rights Reserved.
