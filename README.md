# hyperliquid-python
Python SDK (sync and async) for Hyperliquid with Rest and WS capabilities.

You can check Hyperliquid's docs here: [Docs](https://ccxt.com)


You can check the SDK docs here: [SDK](https://docs.ccxt.com/#/exchanges/hyperliquid)

*This package derives from CCXT and allows you to call pretty much every endpoint by either using the unified CCXT API or calling the endpoints directly*

## Installation

```
pip install hyperliquid
```

## Usage

### Sync

```Python
from hyperliquid import HyperliquidSync

def main():
    instance = HyperliquidSync({})
    ob =  instance.fetch_order_book("BTC/USDC:USDC")
    print(ob)
    #
    # balance = instance.fetch_balance()
    # order = instance.create_order("BTC/USDC:USDC", "limit", "buy", 1, 100000)
```

### Async

```Python
import asyncio
from hyperliquid import HyperliquidAsync

async def main():
    instance = HyperliquidAsync({})
    ob =  await instance.fetch_order_book("BTC/USDC:USDC")
    print(ob)
    #
    # balance = await instance.fetch_balance()
    # order = await instance.create_order("BTC/USDC:USDC", "limit", "buy", 1, 100000)

asyncio.run(main())
```

### Websockets

```Python
from hyperliquid import HyperliquidWs

async def main():
    instance = HyperliquidWs({})
    while True:
        ob = await instance.watch_order_book("BTC/USDC:USDC")
        print(ob)
        # orders = await instance.watch_orders("BTC/USDC:USDC")
```

