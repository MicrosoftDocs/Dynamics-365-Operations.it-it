---
title: Disponibilità delle scorte in doppia scrittura
description: Questo argomento fornisce informazioni su come controllare la disponibilità delle scorte in doppia scrittura.
author: yijialuan
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: riluan
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-05-26
ms.openlocfilehash: a7bfe998d2d787203a507a831c171fc43b03fedc
ms.sourcegitcommit: cc9921295f26804259cc9ec5137788ec9f2a4c6f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2021
ms.locfileid: "4839551"
---
# <a name="inventory-availability-in-dual-write"></a>Disponibilità delle scorte in doppia scrittura

[!include [banner](../../includes/banner.md)]

Utilizzando la disponibilità delle scorte, puoi verificare le scorte prima di aggiungere un prodotto alla pagina **Offerte**, **Ordini** o **Fatture** in Microsoft Dynamics 365 Sales. Ad esempio, la verifica delle scorte e la determinazione di una data di evasione sono attività chiave nel processo [prospect-to-cash](dual-write-prospect-to-cash.md).

Se non si dispone di scorte sufficienti, è possibile stimare una data di consegna in base a entrate e uscite da magazzino previste. È anche possibile verificare le informazioni available-to-promise (ATP) del prodotto, che indicano la quantità ATP nell'intervallo temporale predefinito.

## <a name="on-hand-inventory"></a>Scorte disponibili

In Dynamics 365 Sales, nell'intestazione delle pagine **Offerte**, **Ordini** e **Fatture**, viene aggiunto un nuovo pulsante **Scorte disponibili**. Quando selezioni questo pulsante, viene visualizzata una finestra di dialogo in cui è possibile specificare la società e il prodotto per i quali si desidera verificare le scorte disponibili. Questa finestra di dialogo mostra le stesse informazioni di [Scorte disponibili](../../../../supply-chain/inventory/tasks/check-availability-stock.md).

La finestra di dialogo restituisce le informazioni di inventario da Dynamics 365 Supply Chain Management. Queste informazioni includono le seguenti quantità:

- Quantità disponibile
- Quantità disponibile prenotata
- Quantità disponibile utilizzabile
- Quantità ordinata
- Quantità in ordinazione
- Quantità ordinata prenotata
- Quantità totale disponibile

## <a name="atp-information"></a>Informazioni ATP

Nelle Sales, è stato aggiunto alle voci un nuovo pulsante **Informazioni ATP** nelle pagine **Offerte**, **Ordini** e **Fatture**. Quando selezioni questo pulsante, viene visualizzata una finestra di dialogo in cui è possibile specificare la società, il prodotto, il sito magazzino, il magazzino scorte e la quantità dell'ordine. Questa finestra di dialogo ha le stesse impostazioni descritte in [Promesse ordine](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).

La finestra di dialogo restituisce le informazioni ATP da Supply Chain Management. Queste informazioni includono le seguenti quantità:

- Quantità ATP
- Quantità entrata
- Quantità uscita
- Quantità disponibile

## <a name="how-it-works"></a>Funzionamento

Quando selezioni il pulsante **Scorte disponibili** nella pagina **Offerte**, **Ordini** o **Fatture**, viene effettuata una chiamata live a doppia scrittura all'API **Scorte disponibili**. L'API calcola le scorte disponibili per il prodotto specificato. Il risultato viene memorizzato nelle tabelle **InventCDSInventoryOnHandRequestEntity** e **InventCDSInventoryOnHandEntryEntity**, quindi viene scritto in Dataverse con doppia scrittura. Per utilizzare questa funzionalità, è necessario eseguire i seguenti mapping di doppia scrittura. Salta la sincronizzazione iniziale quando esegui i mapping.

- Voci di scorte disponibili CDS (msdyn_inventoryonhandentries)
- Richieste di disponibilità di scorte CDS (msdyn_inventoryonhandrequests)

## <a name="templates"></a>Modelli
I seguenti modelli sono disponibili per l'esposizione dei dati sulle scorte disponibili.

App di Finance and Operations | App di interazione con i clienti | descrizione 
---|---|---
[Movimenti scorte disponibili inventario CDS](#145) | msdyn_inventoryonhandentries |
[Richieste scorte disponibili inventario CDS](#147) | msdyn_inventoryonhandrequests |

[!include [banner](../../includes/dual-write-symbols.md)]

###  <a name="cds-inventory-on-hand-entries-msdyn_inventoryonhandentries"></a><a name="145"></a>Voci di scorte disponibili CDS (msdyn_inventoryonhandentries)

Questo modello sincronizza i dati tra le app Finance and Operations e Dataverse.

Campo di Finance and Operations | Tipo di mappa | Campo Interazione con i clienti | Valore predefinito
---|---|---|---
`REQUESTID` | = | `msdyn_request.msdyn_requestid` |
`INVENTORYSITEID` | = | `msdyn_inventorysite.msdyn_siteid` |
`INVENTORYWAREHOUSEID` | = | `msdyn_inventorywarehouse.msdyn_warehouseidentifier` |
`AVAILABLEONHANDQUANTITY` | > | `msdyn_availableonhandquantity` |
`AVAILABLEORDEREDQUANTITY` | > | `msdyn_availableorderedquantity` |
`ONHANDQUANTITY` | > | `msdyn_onhandquantity` |
`ONORDERQUANTITY` | > | `msdyn_onorderquantity` |
`ORDEREDQUANTITY` | > | `msdyn_orderedquantity` |
`RESERVEDONHANDQUANTITY` | > | `msdyn_reservedonhandquantity` |
`RESERVEDORDEREDQUANTITY` | > | `msdyn_reservedorderedquantity` |
`TOTALAVAILABLEQUANTITY` | > | `msdyn_totalavailablequantity` |
`ATPDATE` | = | `msdyn_atpdate` |
`ATPQUANTITY` | > | `msdyn_atpquantity` |
`PROJECTEDISSUEQUANTITY` | > | `msdyn_projectedissuequantity` |
`PROJECTEDONHANDQUANTITY` | > | `msdyn_projectedonhandquantity` |
`PROJECTEDRECEIPTQUANTITY` | > | `msdyn_projectedreceiptquantity` |
`ORDERQUANTITY` | > | `msdyn_orderquantity` |
`UNAVAILABLEONHANDQUANTITY` | > | `msdyn_unavailableonhandquantity` |

###  <a name="cds-inventory-on-hand-requests-msdyn_inventoryonhandrequests"></a><a name="147"></a>Richieste di disponibilità di scorte CDS (msdyn_inventoryonhandrequests)

Questo modello sincronizza i dati tra le app Finance and Operations e Dataverse.

Campo di Finance and Operations | Tipo di mappa | Campo Interazione con i clienti | Valore predefinito
---|---|---|---
`REQUESTID` | = | `msdyn_requestid` |
`PRODUCTNUMBER` | < | `msdyn_product.msdyn_productnumber` |
`ISATPCALCULATION` | << | `msdyn_isatpcalculation` |
`ORDERQUANTITY` | < | `msdyn_orderquantity` |
`INVENTORYSITEID` | < | `msdyn_inventorysite.msdyn_siteid` |
`INVENTORYWAREHOUSEID` | < | `msdyn_inventorywarehouse.msdyn_warehouseidentifier` |
`REFERENCENUMBER` | < | `msdyn_referencenumber` |
`LINECREATIONSEQUENCENUMBER` | < | `msdyn_linecreationsequencenumber` |






[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]