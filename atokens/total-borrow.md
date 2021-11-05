# Total Borrow

Total Borrows is the amount of underlying currently loaned out by the market, and the amount upon which interest is accumulated to suppliers of the market.

**SErc20 / SEther**

```text
function totalBorrowsCurrent() returns (uint)
```

* `RETURN`: The total amount of borrowed underlying, with interest.

**Solidity**

```text
SErc20 aToken = SToken(0x3FDA...);
uint borrows = aToken.totalBorrowsCurrent();
```

**Web3 1.0**

```javascript
const aToken = SEther.at(0x3FDB...);
const borrows = (await aToken.methods.totalBorrowsCurrent().call());
```

