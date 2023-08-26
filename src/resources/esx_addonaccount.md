# esx_addonaccount

GitHub Repo: https://github.com/esx-framework/esx_addonaccount \
Version: [26. July 2023](https://github.com/esx-framework/esx_addonaccount/commit/00b93c323702c3eaae58a927b4c6b097ea90ddbd)

## Client
    - NO EVENTS

## Server

### getSharedAccount / Export: GetSharedAccount
Get a shared account of a job.

#### Parameters
- account name
  - type: string

#### Return value
returns type account.

Example:
```lua
TriggerEvent('esx_addonaccount:getSharedAccount', 'society_realestateagent', function(account)
    account.addMoney(500)
end)
```

### getAccount
Get the account of a client.

Example:
```lua
TriggerEvent('esx_addonaccount:getAccount', 'property_black_money', 'steam:0123456789', function(account)
    account.removeMoney(500)
end)
```

## Export: AddSharedAccount
Add/Register a new shared account in the database.

### Parameters
#### society
Type: ``` string // 'society_police' ```\
The name of the society the shared account belongs to.

#### amount
Type: ```int```\
The start amount of the AddonAccount.

## Type AddonAccount
**When editing the values you need to run the _save()_ function after.**

### Values
#### name
The name of the AddonAccount. 

**Example:**
    
    'society_default_name'

#### owner
The user license of the owner or null for shared AddonAccounts.

#### money
The value of the AddonAccount. \
Is of type int.

### functions

#### addMoney(``amount``)
Adds the ``amount`` on top of the existing money.

#### removeMoney(``amount``)
Removes the ``amount`` from the existing money.\
**CAN GO NEGATIVE**

#### setMoney(``amount``)
Set the money value to ``amount``.

#### save()
Saves all changes and updates it in the database.
