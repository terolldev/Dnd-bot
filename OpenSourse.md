## Abzval GUI (balance command)

```py
class Bal(disnake.ui.View):
    def __init__(self, money: int, bit: int, coin: int, exp: int, prem: int, ver: int): # if your bot does not have a system of premium users, then remove the argument and the 6 button
        super().__init__()
        self.add_item(disnake.ui.Button(label=f"{int(money):,}", style=disnake.ButtonStyle.green, disabled=True)) # button balance dollar
        self.add_item(disnake.ui.Button(label=f"{int(bit):,}", style=disnake.ButtonStyle.primary, disabled=True)) # button balance bit-coin
        self.add_item(disnake.ui.Button(label=f"{int(coin):,}", style=disnake.ButtonStyle.success, disabled=True)) # button balance COIN
        self.add_item(disnake.ui.Button(label=f"{int(exp):,}", style=disnake.ButtonStyle.grey, disabled=True, row=2)) # button exp
        self.add_item(disnake.ui.Button(label=f"{int(exp/100):,}", style=disnake.ButtonStyle.grey, disabled=True, row=2)) # button lvl
        if prem == 1:
            self.add_item(disnake.ui.Button(label=f"Premium User", style=disnake.ButtonStyle.red, disabled=True, row=1)) # button
            if ver == 1:
                self.add_item(disnake.ui.Button(label=f" ", custom_id="HERE WRITE ID BUTTON VERIFY", style=disnake.ButtonStyle.green, disabled=False, row=2)) # button verify

                # same with verification
        if ver == 1:
            self.add_item(disnake.ui.Button(label=f" ", custom_id="HERE WRITE ID BUTTON VERIFY", style=disnake.ButtonStyle.green, disabled=False, row=2)) # button verify

            #same with verification


@bot.slash_command(description="tea")
async def sample(self, inter):
    await inter.response.send_message(embed=disnake.Embed(description="Profile: \nDate create account in bd: {long_date} | [{short_date}]\n\n\n```cs\nYou rank: {here_place_rank_user}\n```",
    color=disnake.Colour.random()), view=Bal())
```

### What display balance?
 - You need to create methods for finding the balance of participants.
   - After that, just insert the variables into the Bal() class
### What is inside?
 - Inside, added number separation as in version abzval `1.8.1`