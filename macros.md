# Hunter Macros for WoW Classic

I have found tons of macros online but often even though they are "advertised" as for WoW Classic they did not work.
Here is my list of working macros for WoW Classic.

#### Freezing Trap
```
#showtooltip Freezing Trap
/stopattack
/use [combat] Feign Death
/petpassive
/petfollow 
/stopcasting
/use Freezing Trap
```

#### Frost Trap
```
#showtooltip Frost Trap
/stopattack
/use [combat] Feign Death
/petpassive
/petfollow 
/stopcasting
/use Frost Trap
```

#### Immolation Trap
```
#showtooltip Immolation Trap
/use [combat] Feign Death
/stopcasting
/use Immolation Trap
```

#### Raptor Strike
I like to have both raptor and mongose out so I can see CD on them. But u can have it as single button.
```
#showtooltip Raptor Strike
/cast Mongoose Bite
/cast Raptor Strike
```

#### Moogoose Bite
I like to have both raptor and mongose out so I can see CD on them. But u can have it as single button.
```
#showtooltip
/cast Mongoose Bite
/cast Raptor Strike
```

#### Eagle Eye
With this u can get unlimited EE cos u can cast it inside the EE :)
```
#showtooltip
/cast !eagle Eye
```

#### Feed
Just swap the name of the food for the one u have
```
#showtooltip
/cast Feed Pet
/use [pet]  Roasted Quail
```

#### Aimed shot & furious howl
This is useful when u have WOLF. You could remove the nocombat to have the howl everytime you cast the AS but 
the problem is that AS has lower CD than FH which will spam you with "CD" warning. As far as I know there is no script to check
if the spell is on CD than to cast it.
```
#showtooltip Aimed Shot
/cast [nocombat] Furious Howl
/cast Aimed Shot
```

#### Revive 
Why? Cos that !#$!% costs so much many you have to always drink before & stand for ress... 
```
#showtooltip Revive Pet
/stand
/cast Revive Pet
```


#### Trinket number 1
So u can BIND your trinkets
```
#showtooltip
/use 13
```

#### Trinket number 2
So u can BIND your trinkets
```
#showtooltip
/use 14
```

#### Sell All Grey items in invetory
Grey items in your invetory are 100% worthless, they can't be used for anything.
Just come to the vendor and click on the macro button - awesome!
```
/run local c,i,n,v=0;for b=0,4 do for s=1,GetContainerNumSlots(b)do i={GetContainerItemInfo(b,s)}n=i[7]if n and string.find(n,"9d9d9d")then v={GetItemInfo(n)}q=i[2]c=c+v[11]*q;UseContainerItem(b,s)print(n,q)end;end;end;print(GetCoinText(c))
```
