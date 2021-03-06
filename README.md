# dispike

***
[![codecov](https://codecov.io/gh/ms7m/dispike/branch/master/graph/badge.svg?token=E5AXLZDP9O)](https://codecov.io/gh/ms7m/dispike) ![Test Dispike](https://github.com/ms7m/dispike/workflows/Test%20Dispike/badge.svg?branch=master) ![PyPi Link](https://img.shields.io/badge/Available%20on%20PyPi-Dispike-blue?logo=pypi&link=%22https://pypi.org/project/dispike%22) ![PyPiVersion](https://img.shields.io/badge/dynamic/json?color=blue&label=PyPi%20Version&query=%24.info.version&url=https%3A%2F%2Fpypi.org%2Fpypi%2Fdispike%2Fjson) ![Docs](https://img.shields.io/badge/Docs-Available-lightgrey?link=https://dispike.ms7m.me/) [![FOSSA Status](https://app.fossa.com/api/projects/git%2Bgithub.com%2Fms7m%2Fdispike.svg?type=shield)](https://app.fossa.com/projects/git%2Bgithub.com%2Fms7m%2Fdispike?ref=badge_shield)


***



an *extremely-extremely* early WIP library for easily creating REST-based webhook bots for discord using the new Slash Commands feature. 

Powered by FastAPI.


***


## Install

```
pip install dispike
```

## Learn more
- Read documentation [here](https://dispike.ms7m.me)
- See example bot [here](https://github.com/ms7m/dispike-example-bot)

## Example Code

```python

from dispike import Dispike
bot = Dispike(..)

@bot.interaction.on("stock"):
async def handle_stock_request(stockticker: str, ctx: IncomingDiscordInteraction) -> DiscordResponse:
  get_price = function(stockticker...)
  
  embed=discord.Embed()
  embed.add_field(name="Stock Price for {stockticker}.", value="Current price is {get_price}", inline=True)
  embed.set_footer(text="Request received by {ctx.member.user.username}")
  return DiscordResponse(embed=embed)
```



## Caveats

- ~~Does not handle registring new commands.~~
- ~~Does not handle anything other then string responses. (However you are free to return any valid dict in your handler.)~~
- ~~Not on PyPi~~
- Does not speak over the discord gateway. You'll need a server to handle requests and responses.
- Python 3.6+
- ~~Handling followup messages.~~



# Development

Help is wanted in mantaining this library. Please try to direct PRs to the ``dev`` branch, and use black formatting (if possible).

![Test Dispike](https://github.com/ms7m/dispike/workflows/Test%20Dispike/badge.svg?branch=dev)


## License
[![FOSSA Status](https://app.fossa.com/api/projects/git%2Bgithub.com%2Fms7m%2Fdispike.svg?type=large)](https://app.fossa.com/projects/git%2Bgithub.com%2Fms7m%2Fdispike?ref=badge_large)