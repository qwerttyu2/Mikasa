import discord
from discord.ext.commands import Bot
from discord.ext import commands
bot = discord.Client()
bot_prefix = "!"
import random

bot = commands.Bot(command_prefix = bot_prefix)

@bot.event
async def on_ready():
    print("Merhaba ben geldim")
    print("ismim {}".format(bot.user.name))
    print(str(len(set(bot.get_all_members())))+ " tane kullaniciya erisiyorum")
    await bot.change_presence(game=discord.Game(name='Silkroad Online'))


@bot.command(pass_context = True)
async def kimsin(ctx):
    await bot.say("ismim Mikasa senin ismin nedir?")
@bot.command(pass_context = True)
async def y(ctx):
    await bot.say("Yaratıcım Ceyhun onu çok seviyorum")
@bot.command(pass_context =True)
async def hatun(ctx):
    url1 = ["https://cdn.shopify.com/s/files/1/0733/8367/products/image_e1c64c43-3e03-4228-a99b-bf6ba21595f7_large.jpg?v=1509674266",
            "https://i.ytimg.com/vi/LqoShsSnrjc/maxresdefault.jpg",
            "https://www.greatestphysiques.com/wp-content/uploads/2017/02/Yanita-Yancheva-Profile-684x1024.jpg",
            "https://fashionunited.be/fr/images/201604/Exx-VVictoriaSecretet-1.jpg",
            "https://suburbanturmoil.com/wp-content/uploads/2014/03/2014-victorias-secret-catalog3.jpg",
            "https://www.skinnyvscurvy.com/wp-content/uploads/2016/02/barbara-palvin-2016-photo-sports-illustrated-x160011_tk5_1230-rawwmfinal1920.jpg",
            "http://w4.wallls.com/uploads/original/201711/28/wallls.com_178292.jpg",
            "https://m.media-amazon.com/images/M/MV5BMjA4NmRiOTItZGQ4YS00YTVjLTlkMzAtY2QyNDc0YTkxNzc2XkEyXkFqcGdeQXVyNDUzOTQ5MjY@._V1_SY1000_CR0,0,666,1000_AL_.jpg",
            "https://i.ytimg.com/vi/EJ_3U5TVBe0/maxresdefault.jpg",
            "https://i2-prod.mirror.co.uk/incoming/article803780.ece/ALTERNATES/s615b/SLIDER%20IMAGE%20Victoria's%20Secret%20Angels%20launch%20'most%20comfortable%20push-up%20bra%20yet'.jpg",]
    embed = discord.Embed()
    embed.set_image(url = random.choice(url1))
    await bot.say(embed=embed)

@bot.command(pass_context = True)
async def soyle(ctx):
    satir = ""
    msg = ctx.message.content.split("1")
    await bot.delete_message(ctx.message)
    for i in msg:
        satir += i
    await bot.send_message(ctx.message.channel, satir[6:])





bot.run("NDg3MTc4NzAwNTA1MzUwMTU0.DnKVIg.dP7JmdUaRp2CbL66HfcOoOrV-yY")

