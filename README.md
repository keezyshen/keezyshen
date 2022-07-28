- 👋 Hi, I’m @keezyshen

I am now using ccxrpro, with the endpoint of watch_balance, when I have dumped all the positions at the same time, (for example : nearusdt and uniusdt
)but it's just fectched the balance of nearusdt (sure, it's zero) but there's no balance inof about uniusdt. 

the data returned from watch_balance as follows: 
{'info': {'e': 'ACCOUNT_UPDATE', 'T': 1659018683218, 'E': 1659018683228, 'a': {'B': [{'a': 'USDT', 'wb': '11849.72056194', 'cw': '11849.72056194',
'bc': '0'}], 'P': [{'s': 'NEARUSDT', 'pa': '0', 'ep': '0.0000', 'cr': '0', 'up': '0', 'mt': 'isolated', 'iw': '0', 'ps': 'BOTH', 'ma': 'USDT'},
{'s': 'NEARUSDT', 'pa': '0', 'ep': '0.0000', 'cr': '116.37600000', 'up': '0', 'mt': 'isolated', 'iw': '0', 'ps': 'LONG', 'ma': 'USDT'},
{'s': 'NEARUSDT', 'pa': '0', 'ep': '0.0000', 'cr': '503.78699999', 'up': '0', 'mt': 'isolated', 'iw': '0', 'ps': 'SHORT', 'ma': 'USDT'}], 
'm': 'ORDER'}}, 'USDT': {'free': None, 'used': None, 'total': 11849.72056194}, 'timestamp': None, 'datetime': None, 'free': {'USDT': None}, 
'used': {'USDT': None}, 'total': {'USDT': 11849.72056194}}

Question is I can not obtain the real balance data of uninear again, how can I fix this problem?

	while True :
		try : 
			balance = await exchange.watch_balance({'type' : 'future'}) 
		except ccxt.NetworkError as e:
			await asyncio.sleep(1)
			continue 
		except Exception as e:
		 	print(type(e).__name__, str(e))
		 	raise Exception(str(e))
      
     print(balance)
     
     #processing the balance code below....
     
   many thanks.
   
 Wesley S 

