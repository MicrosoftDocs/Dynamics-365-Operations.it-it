---
title: API dei prezzi di Commerce
description: Questo articolo descrive varie API dei prezzi fornite dal motore di determinazione dei prezzi di Microsoft Dynamics 365 Commerce.
author: boycez
ms.date: 08/10/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: boycez
ms.search.validFrom: 2022-07-15
ms.openlocfilehash: d694c44f6987fbf2a360869d2fb2a2fbaf0d2e4d
ms.sourcegitcommit: 924dbcdc6b03f6a7ae3a07378ec405fd15c7e359
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2022
ms.locfileid: "9294118"
---
# <a name="commerce-pricing-apis"></a>API dei prezzi di Commerce

[!include [banner](../includes/banner.md)]

Questo articolo descrive varie API dei prezzi fornite dal motore di determinazione dei prezzi di Microsoft Dynamics 365 Commerce.

Il motore di determinazione dei prezzi di Dynamics 365 Commerce fornisce le seguenti API di Retail Server che possono essere utilizzate da applicazioni esterne per supportare vari scenari di prezzi:

- **GetActivePrices**: questa API ottiene il prezzo calcolato di un prodotto, inclusi semplici sconti.
- **CalculateSalesDocument**: questa API calcola i prezzi e gli sconti per i prodotti a determinate quantità se vengono acquistati insieme.
- **GetAvailablePromotions**: questa API ottiene sconti applicabili per i prodotti nel carrello. 
- **AddCoupons**: questa API aggiunge buoni sconto a un carrello.
- **RemoveCoupons**: questa API rimuove buoni sconto da un carrello.

Per ulteriori informazioni su come utilizzare le API di Retail Server in applicazioni esterne, vedi [Utilizzare le API di Retail Server in applicazioni esterne](dev-itpro/consume-retail-server-api.md).

## <a name="getactiveprices"></a>GetActivePrices

L'API *GetActivePrices* è stata introdotta nella versione 10.0.4 di Commerce. Questa API ottiene il prezzo calcolato di un prodotto, inclusi semplici sconti. Non calcola sconti plurimi e presume che la quantità di ogni prodotto in una richiesta API sia pari a 1. Questa API può anche utilizzare un elenco di prodotti come input ed eseguire query sul prezzo di singoli prodotti in blocco.

L'API *GetActivePrices* supporta i ruoli **Dipendente**, **Cliente**, **Anonimo** e **Applicazione** di Commerce.

Il caso d'uso principale per l'API *GetActivePrices* è la pagina dei dettagli del prodotto (PDP), in cui i rivenditori intendono presentare il miglior prezzo di un prodotto, inclusi eventuali sconti effettivi.

La tabella seguente mostra i parametri di input per l'API *GetActivePrices*.

| Name                                    | Nome secondario | Tipo | Obbligatorio/Facoltativo | Description |
|-----------------------------------------|----------|------|-------------------|-------------|
| projectDomain                           | | ProjectionDomain | Obbligatorio | |
|                                         | ChannelId | long | Obbligatorio | |
|                                         | CatalogId | long | Obbligatorio | |
| productIds                              | | IEnumerable\<long\> | Obbligatorio | L'elenco dei prodotti per cui calcolare i prezzi. |
| activeDate                              | | DateTimeOffset | Obbligatorio | La data in cui vengono calcolati i prezzi. |
| customerId                              | | stringa | Facoltativo | Numero del conto cliente. |
| affiliationLoyaltyTiers                 | | IEnumerable\<AffiliationLoyaltyTier\> | Facoltativo | I livelli di rapporto e fedeltà. |
|                                         | AffiliationId | long | Obbligatorio | L'ID rapporto. |
|                                         | LoyaltyTierId | long | Facoltativo | L'ID livello fedeltà. |
| includeSimpleDiscountsInContextualPrice | | bool | Facoltativo | Imposta questo parametro su **true** per includere semplici sconti nel calcolo del prezzo. Il valore predefinito è **false**. |
| includeVariantPriceRange                | | bool | Facoltativo | Imposta questo parametro su **true** per ottenere i prezzi minimo e massimo tra tutte le varianti di un prodotto master. Il valore predefinito è **false**. |
| includeAttainablePricesAndDiscounts     | | bool | Facoltativo | Imposta questo parametro su **true** per ottenere prezzi e sconti raggiungibili. Il valore predefinito è **false**. |

**Corpo della richiesta di esempio**

```json
{
    "projectDomain": 
    {
        "ChannelId": 5637144592,
        "CatalogId": 0
    },
    "productIds": 
    [
        68719489871
    ],
    "activeDate": "2022-06-20T14:40:05.873+08:00",
    "includeSimpleDiscountsInContextualPrice": true,
    "includeVariantPriceRange": false
}
```

**Corpo della risposta di esempio**

```json
{
    "value": 
    [
        {
            "ProductId": 68719489871,
            "ListingId": 68719489871,
            "BasePrice": 0,
            "TradeAgreementPrice": 0,
            "AdjustedPrice": 0,
            "MaxVariantPrice": 0,
            "MinVariantPrice": 0,
            "CustomerContextualPrice": 0,
            "DiscountAmount": 0,
            "CurrencyCode": "USD",
            "ItemId": "82000",
            "InventoryDimensionId": null,
            "UnitOfMeasure": "ea",
            "ValidFrom": "2022-06-20T01:40:05.873-05:00",
            "ProductLookupId": 0,
            "ChannelId": 5637144592,
            "CatalogId": 0,
            "SalesAgreementPrice": 0,
            "PriceSourceTypeValue": 1,
            "DiscountLines": [],
            "AttainablePriceLines": [],
        }
    ]
}
```

## <a name="calculatesalesdocument"></a>CalculateSalesDocument

L'API *CalculateSalesDocument* è stata introdotta nella versione 10.0.25 di Commerce. Questa API calcola i prezzi e gli sconti per i prodotti a determinate quantità se vengono acquistati insieme in un ordine. Il calcolo dei prezzi con l'API *CalculateSalesDocument* prende in considerazione sia gli sconti a riga singola che sconti plurimi.

Il caso d'uso principale per l'API *CalculateSalesDocument* è il calcolo dei prezzi in scenari in cui il contesto del carrello completo non persiste (come offerte di vendita). Anche gli scenari nel POS e nell'e-commerce di Commerce possono trarre vantaggio da questo caso d'uso. Un prezzo totale inferiore quando gli articoli del carrello vengono calcolati come insieme (ad esempio, per aggregazioni discrete, prodotti collegati o consigliati o prodotti che sono già stati aggiunti al carrello) potrebbe indurre i clienti ad aggiungere prodotti al carrello.

Il modello di dati sia per la richiesta che per la risposta dell'API *CalculateSalesDocument* è **Cart**. Tuttavia, nel contesto di questa API, il modello di dati è denominato **SalesDocument**. Poiché la maggior parte delle proprietà è facoltativa e solo alcune di esse influiscono sul calcolo dei prezzi, nella tabella seguente vengono mostrati solo i campi relativi ai prezzi. Non è consigliabile includere altri campi nella richiesta API.

L'ambito dell'API *CalculateSalesDocument* è solo il calcolo di prezzi e sconti. IVA e spese non sono incluse.

La tabella seguente mostra i parametri di input nell'oggetto denominato **salesDocument**.

| Name             | Nome secondario | Tipo | Obbligatorio/Facoltativo | Description |
|------------------|----------|------|-------------------|-------------|
| ID               | | stringa | Obbligatorio | L'identificatore del documento di vendita. |
| CartLines        | | IList\<CartLine\> | Facoltativo | L'elenco delle righe per cui calcolare prezzi e sconti. |
|                  | ID prodotto | long | Richiesto nell'ambito di CartLine | L'ID record prodotto. |
|                  | ItemId | stringa | Facoltativo | L'Identificatore dell'articolo. Se viene fornito un valore, deve corrispondere al valore del parametro **ProductId**. |
|                  | InventoryDimensionId | stringa | Facoltativo | L'identificatore della dimensione inventariale. Se viene fornito un valore, la combinazione dei valori **ItemId** e **InventoryDimensionId** deve corrispondere al valore del parametro **ProductId**. |
|                  | Quantity | decimale | Richiesto nell'ambito di CartLine | La quantità del prodotto. |
|                  | UnitOfMeasureSymbol | stringa | Facoltativo | L'unità del prodotto. Per impostazione predefinita, se non viene fornito un valore, l'API utilizza l'unità di vendita del prodotto. |
| CustomerId       | | stringa | Facoltativo | Numero del conto cliente. |
| LoyaltyCardId    | | stringa | Facoltativo | L'identificatore della carta fedeltà. Qualsiasi conto cliente associato alla carta fedeltà deve corrispondere al valore del parametro **CustomerId** (se fornito). La carta fedeltà non verrà presa in considerazione se non viene trovata o se lo stato è **Bloccata**. |
| AffiliationLines | | IList\<AffiliationLoyaltyTier\> | Facoltativo | Le righe del livello di fedeltà del rapporto. Se vengono specificati i valori **CustomerId** e/o **LoyaltyCardId**, le righe del livello di fedeltà del rapporto corrispondenti verranno unite alle righe nel valore **AffiliationLines**. |
|                  | AffiliationId | long | Richiesto nell'ambito di AffiliationLoyaltyTier | L'ID record rapporto. |
|                  | LoyaltyTierId | long | Richiesto nell'ambito di AffiliationLoyaltyTier | L'ID record livello di fedeltà. |
|                  | AffiliationTypeValue | int | Richiesto nell'ambito di AffiliationLoyaltyTier | Un valore che indica se il tipo della riga del rapporto è **Generale** (**0**) o **Fedeltà** (**1**). Se questo parametro è impostato su **0**, l'API usa il valore **AffiliationId** come identificatore e ignora il valore **LoyaltyTierId**. Se è impostato su **1**, l'API usa il valore **LoyaltyTierId** come identificatore e ignora il valore **AffiliationId**. |
|                  | ReasonCodeLines | Collezione\<ReasonCodeLine\> | Richiesto nell'ambito di AffiliationLoyaltyTier | Le righe del codice motivo. Questo parametro non ha effetto sul calcolo del prezzo ma è obbligatorio come parte dell'oggetto **AffiliationLoyaltyTier**. |
|                  | CustomerId | stringa | Richiesto nell'ambito di AffiliationLoyaltyTier | Numero del conto cliente. |
| Buoni sconto          | | IList\<Coupon\> | Facoltativo | I buoni sconto non applicabili (inattivi, scaduti o non trovati) non verranno presi in considerazione nel calcolo del prezzo. |
|                  | Codice | stringa | Richiesto nell'ambito di Coupon | Il codice buono sconto. |
|                  | CodeId | stringa | Facoltativo | L'identificatore del codice buono sconto. Se viene fornito un valore, deve corrispondere al valore del parametro **Code**. |
|                  | DiscountOfferId | stringa | Facoltativo | L'Identificatore dello sconto. Se viene fornito un valore, deve corrispondere al valore del parametro **Code**. |

**Corpo della richiesta di esempio**

```json
{
    "salesDocument": 
    {
        "Id": "CalculateSalesDocument",
        "CartLines": 
        [
            {
                "ProductId": 68719491408,
                "ItemId": "91003",
                "InventoryDimensionId": "",
                "Quantity": 1,
                "UnitOfMeasureSymbol": "ea"
            },
            {
                "ProductId": 68719493014,
                "Quantity": 2,
                "UnitOfMeasureSymbol": "ea"
            }
        ],
        "CustomerId": "3003",
        "AffiliationLines": 
        [
            {
                "AffiliationId": 68719476742,
                "LoyaltyTierId": 0,
                "AffiliationTypeValue": 0,
                "ReasonCodeLines": [],
                "CustomerId": null
            }
        ],
        "LoyaltyCardId": "55103",
        "Coupons": 
        [
            {
                "CodeId": "CODE-0005",
                "Code": "CPN0004",
                "DiscountOfferId": "ST100077"
            }
        ]
    }
}
```

L'intero oggetto carrello viene restituito come corpo della risposta. Per controllare prezzi e sconti, dovresti concentrarti sui campi nella tabella seguente.

| Name           | Nome secondario | Tipo | Description |
|----------------|----------|------|--------------|
| NetPrice       | | decimale | Il prezzo netto dell'intero documento di vendita prima che vengano applicati gli sconti. |
| DiscountAmount | | decimale | L'importo totale delle sconto dell'intero documento di vendita. |
| TotalAmount    | | decimale | L'importo totale dell'intero documento di vendita. |
| CartLines      | | IList\<CartLine\> | Le righe calcolate che includono dettagli su prezzo e sconti. |
|                | Prezzo | decimale | Il prezzo unitario del prodotto. |
|                | NetPrice | decimale | Il prezzo netto della riga prima che vengano applicati gli sconti (= *Prezzo* &times; *Quantità*). |
|                | DiscountAmount | decimale | L'importo dello sconto. |
|                | TotalAmount | decimale | Il risultato finale del prezzo totale della riga. |
|                | PriceLines | IList\<PriceLine\> | I dettagli sul prezzo, inclusa l'origine del prezzo (prezzo base, rettifica del prezzo o accordo commerciale) e l'importo. |
|                | DiscountLines | IList\<DiscountLine\> | I dettagli dello sconto. |

## <a name="getavailablepromotions"></a>GetAvailablePromotions 

Dato un carrello che ha diverse righe di carrello, l'API *GetAvailablePromotions* restituisce tutti gli sconti applicabili per le righe del carrello. 

Il caso d'uso principale per l'API *GetAvailablePromotions* è la pagina del carrello, in cui i rivenditori intendono presentare gli sconti applicati o i buoni sconto disponibili per il carrello corrente.

La tabella seguente mostra i parametri di input per l'API *GetAvailablePromotions*.

| Name        | Tipo | Obbligatorio/Facoltativo | Description |
|-------------|------|-------------------|-------------|
| chiave         | stringa | Obbligatorio | L'ID carrello. |
| cartLineIds | IEnumerable\<string\> | Facoltativo | Imposta questo parametro per restituire sconti solo per le righe del carrello selezionate. |

**Corpo della risposta di esempio**

```json
{
    "value": 
    [
        {
            "LineId": "f495ffa507bc4f63a47a409cd8713dd7",
            "Promotion": {
                "OfferId": "ST100012",
                "OfferName": "Loyalty 5% off over $100",
                "PeriodicDiscountTypeValue": 4,
                "IsDiscountCodeRequired": false,
                "ValidationPeriodId": null,
                "AdditionalRestrictions": null,
                "Description": "All loyalty members get 5% with transaction total above $10 unless some exclusive or best price discounts are already applied on the transaction",
                "ValidFromDate": "2022-06-20T06:52:56.2460219Z",
                "ValidToDate": "2022-06-20T06:52:56.2460224Z",
                "CouponCodes": [],
                "ValidationPeriod": null
            }
        }
    ]
}
```

## <a name="addcoupons"></a>AddCoupons

L'API *AddCoupons* supporta l'aggiunta di un elenco di buoni sconto a un carrello. Restituisce l'oggetto carrello dopo l'aggiunta di buoni sconto.

La tabella seguente mostra i parametri di input per l'API *AddCoupons*.

| Name                 | Tipo | Obbligatorio/Facoltativo | Description |
|----------------------|------|-------------------|-------------|
| chiave                  | stringa | Obbligatorio | L'ID carrello. |
| couponCodes          | IEnumerable\<string\> | Obbligatorio | I codici buoni sconto da aggiungere al carrello. |
| isLegacyDiscountCode | bool | Facoltativo | Imposta questo parametro su **true** per indicare che il buono sconto è un codice sconto legacy. Il valore predefinito è **false**. |

## <a name="removecoupons"></a>RemoveCoupons

L'API *RemoveCoupons* supporta la rimozione di un elenco di buoni sconto da un carrello. Restituisce l'oggetto carrello dopo la rimozione di buoni sconto.

La tabella seguente mostra i parametri di input per l'API *RemoveCoupons*.

| Name        | Tipo | Obbligatorio/Facoltativo | Description |
|-------------|------|-------------------|-------------|
| chiave         | stringa | Obbligatorio | L'ID carrello. |
| couponCodes | IEnumerable\<string\> | Obbligatorio | I codici buoni sconto da rimuovere dal carrello. |

[!INCLUDE[footer-include](../includes/footer-banner.md)]
