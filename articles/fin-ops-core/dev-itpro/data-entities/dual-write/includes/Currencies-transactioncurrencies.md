## <a name="currencies-to-transactioncurrencies"></a>Valute per transactioncurrencies

Questo modello sincronizza i dati tra le app Finance and Operations e Common Data Service.

Filtro origine: ((CURRENCYCODE != "999"))

Campo di Finance and Operations | Tipo di mappa | Altro campo di Dynamics 365 | Valore predefinito
---|---|---|---
CURRENCYCODE | = | isocurrencycode | 
NAME | = | currencyname | 
SYMBOL | = | currencysymbol | 
nessuno | >> | exchangerate | 1
