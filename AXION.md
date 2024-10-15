1. Review the initialization pattern, if **`initializer`** is used in the parent contract instead of **`onlyInitializing`** the transaction will always revert.
2. Check overflow when price is calulated, if the amount is to high can be can provocate it.
3. Ensure that **`__ReentrancyGuard_init`** is called in upgradeable contracts; otherwise, **`_status`** will remain at its default value of 0 instead of 1 (**`NOT_ENTERED`**), rendering the reentrancy protection ineffective.
4. If a token is meant to be burned after withdrawing liquidity (LP) from a pool, and **`totalSupply()`** is used. This would allow them to attempt to burn more tokens than the pool actually holds and will reverts.
5. Review the interfaces carefully, as **`IERC20Upgradeable`** expects functions like **`approve`** to return a bool, whereas some tokens, like USDT, do not return any value at all.
