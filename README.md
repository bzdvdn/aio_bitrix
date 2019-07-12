
# Requirements

* Python (3.6, 3.7)
* aiohttp==3.4.4

# Installation

Install using `pip`...

    pip install aio-bitrix




# Usage

```python
from aio_bitrix import Bitrix
import asyncio
loop = asyncio.get_event_loop()
bitrix = Bitrix(access_token='access_token', refresh_token='refresh_token', client_id='', client_secret='')
deals = loop.run_until_complete(
    bitrix.bitrix_call('crm.deal.list')
 ) # return paginated deal result

#  multi call bitrix
method_list = [
    {
        "name": "crm.deal.list",
        "params": {}
    },
    {
        "name": "crm.lead.list",
        "params": {}
    }
]
multi_result = loop.run_until_complete(
    bitrix.get_multi_value(method_list)
) # return {"crm.deal.list": [], "crm.lead.list": []}

```
