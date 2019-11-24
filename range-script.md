### Weak Auras - Hunter Range script

It's impossible to tell the RANGE in yd using wow API. However u can check if any spell is in range.
You can also check range of interactions: https://wowwiki.fandom.com/wiki/API_CheckInteractDistance

Original code taken from https://wago.io/f6uD_aQRN
However it's improved with Scatter shot range (20yd) to display more information in the Medium range.

The main logic code:
```lua
function()
    local unit = "target"
    local rangeDisplay
    if UnitExists(unit) and UnitIsVisible(unit) then
        if IsSpellInRange("Wing Clip",unit) == 1 then
            rangeDisplay = "Melee"
        elseif IsSpellInRange("Auto Shot",unit) == 1 then
            if CheckInteractDistance(unit, 4) then
                if IsSpellInRange("Scatter Shot", unit) == 1 then
                    rangeDisplay = "Medium < 20"
                else
                    rangeDisplay = "In Range 20-28"                    
                end
            else 
                rangeDisplay = "Long Range 28-41"
            end
        elseif CheckInteractDistance(unit, 2) then
            rangeDisplay = "Deadzone"
        else
            rangeDisplay = "Out of Range"
        end
        
    end
    
    return rangeDisplay
end
```
But u need whole script with other settings so copy this string and import in WeakAuaras:
```
!DJvFtTnUt4VlmZVzGzkG8RX53C9psdHd6LAOXH(YmmorylhRwJDoBzO0)WF2VvswjoHet46D9Ldyc2wRwT6zF2hVk(A(J99U13lK)hCjUKfNLFXCgnlTaEaZ3lOSGLD7yYxGRJktd4dT)bvVUAQ83KSaCs10YukRA6lRMUhdNpJW27rwKJtNroHwmpb)WYbPrvtVcM7GVqlyf7ZDZbvtXPHYhFEX7Of0BsiQryXK0LZUPxoVWBojj580r8fA)9EpnDw10(j0579I6j)si(02Mpu)UsCk2rVHKqi794zqskiBAL7vYYQM6fNXEERm3x9JjbF(8ugjhhWGOGHtdKB(xun18GNYfTbiEbyg4xvKjZz7ASTlOuiT82QP)w1uD0EpTN4O33Y6DEA1uXoJVEhQ7S3U6QDi0a63RBnU3bN84iEygNrQIzNdn1AbM2ymOyCTYs0p45tXpHGd)Aw62y5phxDrjieKfvVr3Kd3i6(6np8IRYjSY801LrKgl(137HlIIkim)tn7AARPzBzHm0Dm0r(rhAAcQBPbG62Lz0uqlR)a3Xdg1uF7Q5HygX3Ru9)8eFVygBEX))4JVhpl7iA2Xr2LNmb)2rUhRbomqju6bPGCMuXKcPb5vrWLfXIRH7y50zZi5CZDfcV1pqC5dZjQybw5cYeEY0)vW1PK7i8ag0MZG1P8gX9ELrr0V47nPFpVXt8g3Be4LWYCmpI89GGREANrWjS4Lt8YCIyIExoy4WLlzdP9hb9RPrRu43So9MgTpoThJHd(8(7XtBKCU6Z6gUFAgt5moDCPN2kFwXjy5LnOOBRavzDeEfgTGcbF47LIVLu)wVcHYzy9DcGRW37YH9(4GrtaW(3hmEs)Z65(7dobWqE14caxIOtKzuGwWkl4zrkNbi2qqEICdK(glS4SbdV80RgYxMY0LmcoJXvVvwsRuHDl7VBBmvbXg3zBGa9m6n4NEk2)ODwSr66U(ELTqF3OSPItVuBSo3ftdHChJEljCJmoJwzCBKa0MOttHS2ik)sL(B2ExJL4hpfy7n40k5qsqw79mRv6Vf9JwLGKAEY0XgjBM)yiB)3sv6psZUpDFTUqVohSlhW4jovWFNZe0oP(7sdTpDz1)c6Q)ikA8cPfFsqQVJW7O9bzxO3rgln7nzGaV7HAizNOaGMItEh01jVOXvx0fm9wznuJ2wRR9sHJaSSitv7rcYsHwHahElMMU7wVO93DZErJrfqDEoh9UrSvdGSdzsEgtgXUiFV7uBgnbuoImRUh86MQHo5NueJdZU)d1NhGBz9IvEdt8nziSsE5)lO(2GSKSCPF4)Pl(0q8Pj)t10IY4z8tZPFTA6BlXHq4IRMoE11UFdNHeodjCgAnNjT(JQi9qn1Zjjr1NuP3vJVW3tGbe53dJ7fUdAemYgjDfOR4HB8GoYhUyLq12(jqPKg9Ws7w4wp6xbQKMJAQFy9PENu5d0BfjVycDwmVhcKkA5jXKmS4RwIRohKGlkehQbUr0I9N5QxQNKaLfj85adfi(MPktyufXxozoNfA)kH358vYaEfRA4vx9UDm5MdBJ1CgNktZZHmeSA5cgKee57RYC4cyFLgkkM8E1WbUN0yiHmveoGCDVWWlslU(9e8N7bS2IR5Fhi4RhlTS4AV)SeNtMCAzsY7JPCjbwwWs(RMbshksHtEmQ8Mmwr10ZktfAXcTzHMiVptyFtbskuNerNvFYYC4SkW7obQNGEFpneEfiKSqQS1PClKBkV(JgmWfWy(sfpYAoffm88ZGr(I6eZhA2XUJMULrxhhhKULT6iZjZJLRqZQd0rDn7I06AJ64yAOz2OybgYbz0vxZY2XwhW)f0DEzoLTsTQuVSrtaUhcaYD4CkMZR865QoeYJp0mpMwAzrC2987tkjYLB1Zo5QVvJrpQTx4UwnEL2wG7AZyjZnMNoxUfKJRGYoMAADSn7GSCC0nKsfhTa)SqDDQbwTo6wlHDbWIoYXuhPzyQ5y3X0SdF1MNNnNKZEqLYynol5pdaU2UblgR8tnSy3KCPWfDdnJfqJMcxmqDr6DTnCaITEl4IX3xCX4Bfx0BYwSQXfJ1OgcCXXQzrQcxSm00nT1G)J0BJVy(9fxmB3yJNr18tbINA3fOmoiBKHTPjsO1zjyyNY5voDDmS072fyD61JyaJyPH0DSTbofcbWnFKgIBBbeT(LfextLZ4BvLZAnfnbT1uNJ016FQ3FyutTfd48mPTS6wpunl2OnQ6(B49i47PFKM1rCeacptDo64)x
```

![Range](https://i.imgur.com/BhTmBoN.png)
![Range](https://i.imgur.com/uQCjC3e.png)
![Range](https://i.imgur.com/Epj0tpa.png)
![Range](https://i.imgur.com/1bngA9C.png)

Tested with WA: 2.15.2

