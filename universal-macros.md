# Universal macros 

##### Delete items from invetory based on the name 
Replace `Coarse Thread` in the script
```
/run for b=0,4 do for s=1,36 do n=GetContainerItemLink(b,s);if n and string.find(n,"Coarse Thread") then PickupContainerItem(b,s);DeleteCursorItem();end;end;end;
```
