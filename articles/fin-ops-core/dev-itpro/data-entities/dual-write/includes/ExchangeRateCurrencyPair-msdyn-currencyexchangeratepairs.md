## <a name="exchange-rate-currency-pair-to-msdyn_currencyexchangeratepairs"></a>Coppia di valute tasso di cambio per msdyn_currencyexchangeratepairs

Questo modello sincronizza i dati tra le app Finance and Operations e Common Data Service.

Campo di Finance and Operations | Tipo di mappa | Altro campo di Dynamics 365 | Valore predefinito
---|---|---|---
EXCHANGERATEDISPLAYFACTOR | >< | msdyn_displayfactor | 
EXCHANGERATETYPENAME | = | msdyn_currencyexchangeratetypeid.msdyn_name | 
FROMCURRENCYCODE | = | msdyn_fromtransactioncurrencyid.isocurrencycode | 
TOCURRENCYCODE | = | msdyn_totransactioncurrencyid.isocurrencycode | 
