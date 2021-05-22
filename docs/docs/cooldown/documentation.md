This is the detailed code documentation for Cooldown.

## Global Methods

```lua
Cooldown.new()
```

**Description** <div>
Creates and returns a new Cooldown object.

**Parameters**

| Name | Type | Default | Description |
| --- | --- | --- | --- |
| length | number | 1 | The length in seconds for this Cooldown object. |

**Returns**

| Name | Type | Description |
| --- | --- | --- |
| Cooldown | table | A new Cooldown object. |

---

## Cooldown Object

```lua
Cooldown:DoTask()
```

**Description** <div>
Completes a task based off a cooldown.

**Parameters**

| Name | Type | Default | Description |
| --- | --- | --- | --- |
| key | any | | The key to use when managing a certain cooldown. |
| callback | function | | The function called, also known as the task. See the below for the arguments of the callback. |

**Callback Arguments**

| Name | Type | Description |
| --- | --- | --- |
| onCooldown | bool | A boolean representing if the specified key is on cooldown or not. |
| timeLeft | number | The amount of time in seconds the cooldown key has remaining. |

---

```lua
Cooldown:GetStatus()
```

**Description** <div>
Gets cooldown information about a certain key.

**Parameters**

| Name | Type | Default | Description |
| --- | --- | --- | --- |
| key | any | | The key to retrieve cooldown information about. |

**Returns**

| Name | Type | Description |
| --- | --- | --- |
| onCooldown | bool | A boolean representing if the specified key is on cooldown or not. |
| lastUsed | number | The tick when the cooldown was last successful. |

---

```lua
Cooldown:Cleanup()
```

**Description** <div>
Cleans up any completed cooldowns. This is mostly useful for garbage collecting cooldowns where an instance would act as the key.