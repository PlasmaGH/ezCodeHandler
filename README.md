# ezCodeHandler : VERSION 1
A simple to use Twitter/media code module with **Function Integration** and **Code Expiration (using Unix-Time)**.

---

## To process a redemption request:

```
local processMessage = codeModule.redeemCode(player:Player, codeValue:string)
```

It is recommended to tell the client the value returned from the "`redeemCode`" function.
`"return processMessage"`

---

## Expire Settings ⏰

The expire variable use Unix time (Unix Epoch)
For best experience, I recommend setting expire dates using a website, such as: https://unixtime.org/.

> This setting can be completely overwrote by setting the variable "`Can_Expire`" to `false`

---

## Code Rewards 💲

There are two variables in the source version of the module "Coins" and "Gems". These variables are to show the functionality of the module, and can be removed or added on to. **Check the function "awardPlayer" to configure these settings.**

This module also supports custom integration for functions.
Whenever a code is redeemed by a player, the function under the code data "`codeFunction`" will be called, the first and only vanilla variable here is the player object who redeemed the code. You can use this function to do whatever, even award them gold or gems without the variable.

## Customization 🎨

> ### Errors:
There are many ways to customize this module, let's start with errors.

```
local errors = {
	["Missing"] = "Code does not exist", -- Code = nil
	["Expired"] = "Code is expired.", -- Code is expired
	["Success"] = [[Successfully redeemed "%s".]], -- Code redeemed successfully.
	["Flooded"] = "You are sending too many requests.", -- User is flooding requests.
	["Previously_Redeemed"] = "You already redeemed this code.", -- The user already redeemed this code.
	["DataStoreFail"] = "DataStore-Malfunctioned | [Try Again]", -- Error relating CodeStoreCache.
};
```

Currently, these are the default returned errors. These can be changed without throwing an error!

---

> ### Cooldown 🧊

To prevent spamming, this variable should be above 5.
If the player exceeds the cooldown, the "Flooded" error will be returned.
