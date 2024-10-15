1. Review the initialization pattern, if **`initializer`** is used in the parent contract instead of **`onlyInitializing`** the transaction will always revert.
2. Check overflow when price is calulated, if the amount is to high can be can provocate it.
3. Ensure that **`__ReentrancyGuard_init`** is called in upgradeable contracts; otherwise, **`_status`** will remain at its default value of 0 instead of 1 (**`NOT_ENTERED`**), rendering the reentrancy protection ineffective.
