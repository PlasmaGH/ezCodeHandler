# ezCodeHandler : VERSION 1
A simple to use Twitter/media code module with **Function Integration** and **Code Expiration (using Unix-Time)**.

---

## To process a redemption request:

```
local processMessage = codeModule.redeemCode(player:Player, codeValue:string)
```

It is recommended to tell the client the value returned from the "`redeemCode`" function.
`"return processMessage"`
