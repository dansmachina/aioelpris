# aiodkelpris

An aio library to retrieve Denmark's current electricity price. It gets the information from the [Energi Data Service API](https://www.energidataservice.dk/tso-electricity/Elspotprices).

## Basic example

```python

import asyncio

import aiohttp

from aiodkelpris import DKElPris
from aiodkelpris.core.models import Price

async def test():
    async with aiohttp.ClientSession() as session:
        pris = DKElPris(session=session, price_area="DK1")
        price: Price = await pris.get_current_price()
        print(price)
        return price

asyncio.run(test())

```
