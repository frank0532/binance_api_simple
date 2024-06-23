# binance_api_simple
This project tries to keep clear and simple to deploy / call Binance API functions by python, some of which have been done, and now welcome to any contribution for other parts.

## The basic usages
* initiate.  
`bn_api = BinanceAPI(api_key='your own api here', secret_key='your own secret here', account_type='spot')`

* get history klines data.  
`klines = bn_api.history_klines(symbol='BTCUSDT', interval='1d', start_time_utc='2020-06-18 00:00:00')`  

* create websocket.  
`ws = bn_api.generate_websocket(type_ws='account')`
* book 4-hours klines stream for 'BTCUSDT', 'ETHUSDT', 'SOLUSDT' and 'LINKUSDT'.  
`bn_api.subscribe_websocket(ws, ['BTCUSDT', 'ETHUSDT', 'SOLUSDT', 'LINKUSDT'], sub_type="kline_4h")`

* send a new real-trade order to Binance: buy 0.1 'BTCUSDT' at market realtime price on Binance.  
`bn_api.new_order(symbol='BTCUSDT', side='BUY', type_order="MARKET", quantity='0.1')`
