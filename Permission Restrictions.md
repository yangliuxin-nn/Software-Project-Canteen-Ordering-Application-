# Permission Restrictions
## Permission map initialization
This creates a map which stores key(access_name)-value(groupPrefix) pairs. This pre-defined map serves as a group model.
## checkPermission method
### Step 1
pass in the access_name
### Step 2
groupPrefix (apply map and pass in the key(access_name) to get the groupPrefix)
### Step 3
getAccounts (returns a linkedlist which store all account_id in this groupPrefix)
### Step 4
check whether the passed-in parameter: account_id is in the accounts linkedlist (checkPermission method)

## addGroup method
This method will add new memebrs into a group. This can only add a detailed group which is stored in the group model map.
### Step 1
pass in the groupSuffix parameter
### Step 2
concatenate the groupPrefix + groupSuffix to attain the group_name (group_name = groupPrefix + groupSuffix)
### Step 3
insert into access_group (which is a table storing all groups and their members) values (group_name, int[] account_id);

## deleteGroup method
This method will delete the group and all its members.
### Step 1
pass in the groupSuffix parameter
### Step 2
concatenate the groupPrefix + groupSuffix to attain the groupName (groupName = groupPrefix + groupSuffix)
### Step 3
delete from access_group (which is a table storing all groups and their members) where group_name = groupName

## deleteAccount method
This method will delete a member in a group.
### Step 1
pass in the groupSuffix parameter
### Step 2
concatenate the groupPrefix + groupSuffix to attain the groupName (groupName = groupPrefix + groupSuffix)
### Step 3
delete from access_group (which is a table storing all groups and their members) where group_name = groupName and account_id = account
