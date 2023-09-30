# newpeople.py
#this says hello to the new peoples in the gruop
import discord


class MyClient(discord.Client):
    async def on_ready(self):
        print(f'Logged in as {self.user} (ID: {self.user.id})')
        print("hoşgeldin",{self.user})

    async def on_member_join(self, member):
        guild = member.guild
        if guild.system_channel is not None:
            to_send = f'hoşgeldin {member.mention},  {guild.name}ye!'
            await guild.system_channel.send(to_send)


intents = discord.Intents.default()
intents.members = True

client = MyClient(intents=intents)
client.run('MTE1MjYyODc1NDE1MDA3NjU0Nw.GseRTl.5Vc9bp8Pa_y9p_MxYnNrKcHohpePnuNGkazBoa')
