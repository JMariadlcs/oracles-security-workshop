# Oracle Workshop 

This repository contains a Foundry-based workshop project focused on **integrating and interacting with decentralized oracles**. The goal is to explore how to use Chainlink and Pyth oracles in Solidity smart contracts, both with and without additional safety checks.

---

## 📂 Project Structure

The project includes four main Solidity contracts:

| Contract Name             | Description                                                          |
|---------------------------|----------------------------------------------------------------------|
| `ChainlinkOracle.sol`     | Implements basic interaction with Chainlink oracle to fetch prices, **without any safety checks**. |
| `PythOracle.sol`          | Implements basic interaction with Pyth oracle to fetch prices, **without any safety checks**.     |
| `ChainlinkOracleChecks.sol` | Extends Chainlink oracle usage by adding **price validity and freshness checks** to ensure safety. |
| `PythOracleChecks.sol`    | Extends Pyth oracle usage by adding **price validity and freshness checks** for safer price reads. |

---

## 📄 Contract Details

### ChainlinkOracle.sol
- Simple price feed consumer for Chainlink.  
- Calls Chainlink AggregatorV3Interface `latestRoundData()` directly.  
- No validation or freshness checks.

### ChainlinkOracleChecks.sol
- Wraps Chainlink oracle calls with checks:  
  - Ensures price > 0  
  - Checks the timestamp for freshness  
  - Validates round IDs to prevent stale data

### PythOracle.sol
- Basic integration with Pyth Oracle contract.  
- Calls `getPrice()` without extra validations.  
- Suitable for learning data fetching.

### PythOracleChecks.sol
- Adds validation layers on top of `PythOracle.sol`:  
  - Checks for price validity  
  - Validates timestamps and confidence intervals

---

## 📚 Additional Resources

- [Chainlink Docs](https://docs.chain.link/docs)  
- [Pyth Network Docs](https://docs.pyth.network/)  
- [Foundry Book](https://book.getfoundry.sh/)  
- [Solidity Docs](https://docs.soliditylang.org/)

