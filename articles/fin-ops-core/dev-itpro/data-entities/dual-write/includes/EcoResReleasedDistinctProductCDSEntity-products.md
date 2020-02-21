## <a name="cds-released-distinct-products-to-products"></a>Prodotti specifici rilasciati da CDS per products

Questo modello sincronizza i dati tra le app Finance and Operations e Common Data Service.

Campo di Finance and Operations | Tipo di mappa | Altro campo di Dynamics 365 | Valore predefinito
---|---|---|---
PRODUCTNUMBER | >> | msdyn_productnumber | 
PRODUCTNAME | >> | name | 
PRODUCTDESCRIPTION | >> | description | 
ITEMNUMBER | >> | msdyn_itemnumber | 
CURRENCYCODE | >> | transactioncurrencyid.isocurrencycode | 
SALESUNITSYMBOL | >> | defaultuomid.msdyn_symbol | 
SALESPRICE | >> | price | 
UNITCOST | >> | currentcost | 
PRODUCTTYPE | >> | producttypecode | 
SALESUNITDECIMALPRECISION | >> | quantitydecimal | 0
ISCATCHWEIGHTPRODUCT | >> | msdyn_iscatchweight | 
PRODUCTCOLORID | >> | msdyn_productcolor.msdyn_productcolorname | 
PRODUCTCONFIGURATIONID | >> | msdyn_productconfiguration.msdyn_productconfiguration | 
PRODUCTSIZEID | >> | msdyn_productsize.msdyn_productsize | 
PRODUCTSTYLEID | >> | msdyn_productstyle.msdyn_productstyle | 
