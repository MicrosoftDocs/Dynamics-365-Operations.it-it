---
title: Importare gli ASN in entrata tramite l'entità di dati V2
description: Questo argomento spiega come gestire l'importazione degli Advanced Shipping Notice (ASN) in entrata tramite l'entità di dati ASN V2 in entrata.
author: GalynaFedorova
ms.date: 05/31/2021
ms.topic: article
ms.search.form: WHSInboundASNV2Entity, WHSInboundASNEntity
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-06-04
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 470cc0c39f211a5d0f106c4c6e193867388e2b53
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2021
ms.locfileid: "6249123"
---
# <a name="import-inbound-asns-through-the-v2-data-entity"></a>Importare gli ASN in entrata tramite l'entità di dati V2

[!include [banner](../../includes/banner.md)]

Gli gli Advanced Shipping Notice (ASN) ti informano sulle consegne dei fornitori. Aiutano il mittente a descrivere il contenuto di una spedizione e ulteriori informazioni, come gli articoli e l'imballaggio.

Gli ASN possono aiutare i magazzinieri a sapere cosa sta arrivando e quando. Pertanto, possono prepararsi. Inoltre, gli addetti al magazzino possono utilizzare gli ASN per abbinare i dettagli di una spedizione all'ordine fornitore correlato creato in precedenza.

Questo argomento presenta una raccolta di scenari che mostrano, attraverso esempi, come utilizzare i file ASN.

> [!IMPORTANT]
> L'importazione di *ASN in entrata* si applica solo agli articoli abilitati per la gestione avanzata del magazzino (WMS). Prima di ricevere un ASN, è necessario registrare nel sistema un ordine relativo al fornitore che invia tale ASN.

## <a name="inbound-asn-v2-entity"></a>Entità ASN V2 in entrata

Importi gli ASN in entrata usando l'entità di dati composita *ASN V2 in entrata*. *ASN V2 in entrata* si avvale delle seguenti entità:

- Intestazione carico in entrata
- Intestazione spedizione in entrata
- Strutture di imballaggio carico in entrata
- Casse struttura di imballaggio carico in entrata
- Righe casse di struttura di imballaggio carico in entrata
- Righe struttura di imballaggio carico in entrata

L'entità di dati composita *ASN V2 in entrata* è destinata a scenari di integrazione asincrona in cui vengono utilizzate importazioni basate su file XML.

## <a name="xml-format-for-importing-asns"></a>Formato XML per l'importazione di ASN

Microsoft Dynamics 365 Supply Chain Management supporta il seguente formato XML per l'importazione di ASN. Ciascun nodo nel file XML rappresenta un attributo di una singola entità.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Document>
    <WHSInboundLoadHeaderEntity>
        <WHSInboundShipmentHeaderEntity>
            <WHSInboundLoadPackingStructureEntity>
                <WHSInboundLoadPackingStructureCaseEntity>
                    <WHSInboundPackingStructureCaseLineV2Entity>
                    </WHSInboundPackingStructureCaseLineV2Entity>
                </WHSInboundLoadPackingStructureCaseEntity>
                <WHSInboundLoadPackingStructureLineV2Entity>
                </WHSInboundLoadPackingStructureLineV2Entity>
            </WHSInboundLoadPackingStructureEntity>
        </WHSInboundShipmentHeaderEntity>
    </WHSInboundLoadHeaderEntity>
</Document>
```

## <a name="examples"></a>Esempi

Le seguenti sottosezioni forniscono esempi di file di importazione XML ASN per le spedizioni dei fornitori.

### <a name="example-1"></a>Esempio 1

L'esempio seguente mostra un file XML per l'importazione di spedizioni dei fornitori per un ordine fornitore quando non sono inclusi i dettagli del caso.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Document>
    <WHSInboundLoadHeaderEntity TRACTORNUMBER="0000101">
        <WHSInboundShipmentHeaderEntity VENDORSHIPMENTID="VendASN_01" VENDORADDRESSCOUNTRYREGIONID = "USA" VENDORADDRESSSTREET = "123 Coffee Street" VENDORADDRESSSTATEID = "WA" VENDORADDRESSCITY = "Redmond" VENDORADDRESSZIPCODE = "98052">
            <WHSInboundLoadPackingStructureEntity LICENSEPLATENUMBER="LP_ASN_001">
                <WHSInboundLoadPackingStructureLineV2Entity PURCHASEORDERNUMBER="00000176" ITEMNUMBER="A0001" QUANTITY="1" UNITSYMBOL="ea" />
            </WHSInboundLoadPackingStructureEntity>
        </WHSInboundShipmentHeaderEntity>
    </WHSInboundLoadHeaderEntity>
</Document>
```

### <a name="example-2"></a>Esempio 2

L'esempio seguente mostra un file XML per l'importazione di spedizioni dei fornitori per un ordine fornitore quando sono inclusi i dettagli del caso.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Document>
    <WHSInboundLoadHeaderEntity ESTIMATEDARRIVALDATETIME="2021-04-25T11:00:00+00:00">
        <WHSInboundShipmentHeaderEntity VENDORSHIPMENTID="MVR_SNN_0004">
            <WHSInboundLoadPackingStructureEntity LICENSEPLATENUMBER="MVR_SNN_0004" PACKEDTOTALQUANTITY="2.00">
                <WHSInboundLoadPackingStructureCaseEntity PARENTPACKINGSTRUCTURELICENSEPLATENUMBER="MVR_SNN_0004" LICENSEPLATENUMBER="MVR_SNN_0004A" PACKEDTOTALQUANTITY="2.00" />
                <WHSInboundLoadPackingStructureLineV2Entity PURCHASEORDERNUMBER="00000175" ITEMNUMBER="A0001" PURCHASEORDERLINENUMBER="1" QUANTITY="2.00" UNITSYMBOL="ea" />
            </WHSInboundLoadPackingStructureEntity>
        </WHSInboundShipmentHeaderEntity>
    </WHSInboundLoadHeaderEntity>
</Document>
```

### <a name="example-3"></a>Esempio 3

L'esempio seguente mostra un file XML per l'importazione di spedizioni dei fornitori per più ordini fornitore quando sono inclusi i dettagli del caso.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Document>
    <WHSInboundLoadHeaderEntity TRACTORNUMBER="0000101">
        <WHSInboundShipmentHeaderEntity VENDORSHIPMENTID="VendASN_01" VENDORADDRESSCOUNTRYREGIONID = "USA" VendorAddressStreet = "123 Coffee Street" VENDORADDRESSSTATEID = "WA" VENDORADDRESSCITY = "Redmond" VENDORADDRESSZIPCODE = "98052">
            <WHSInboundLoadPackingStructureEntity LICENSEPLATENUMBER="LP_ASN_001">
                <WHSInboundLoadPackingStructureLineV2Entity PURCHASEORDERNUMBER="00000176" ITEMNUMBER="A0001" QUANTITY="100" UNITSYMBOL="ea" />
            </WHSInboundLoadPackingStructureEntity>
        </WHSInboundShipmentHeaderEntity>
        <WHSInboundShipmentHeaderEntity VENDORSHIPMENTID="VendASN_02" VENDORADDRESSCOUNTRYREGIONID = "USA" VendorAddressStreet = "123 Coffee Street" VENDORADDRESSSTATEID = "WA" VENDORADDRESSCITY = "Redmond" VENDORADDRESSZIPCODE = "98052">
            <WHSInboundLoadPackingStructureEntity LICENSEPLATENUMBER="LP_ASN_001">
                <WHSInboundLoadPackingStructureLineV2Entity PURCHASEORDERNUMBER="00000177" ITEMNUMBER="A0001" QUANTITY="200" UNITSYMBOL="ea" />
                <WHSInboundLoadPackingStructureLineV2Entity PURCHASEORDERNUMBER="00000177" ITEMNUMBER="P0004" QUANTITY="300" UNITSYMBOL="ea" ITEMBATCHNUMBER="BN0001" />
            </WHSInboundLoadPackingStructureEntity>
            <WHSInboundLoadPackingStructureEntity LICENSEPLATENUMBER="LP_ASN_002">
                <WHSInboundLoadPackingStructureCaseEntity LICENSEPLATENUMBER="LP_ASN_002_C01">
                    <WHSInboundLoadPackingStructureCaseLineV2Entity PURCHASEORDERNUMBER="00000177" ITEMNUMBER="A0001" QUANTITY="400" UNITSYMBOL="ea" />
                </WHSInboundLoadPackingStructureCaseEntity>
            </WHSInboundLoadPackingStructureEntity>
        </WHSInboundShipmentHeaderEntity>
    </WHSInboundLoadHeaderEntity>
</Document>
```

## <a name="inspect-the-results-of-importing-an-asn-file"></a>Ispezionare i risultati dell'importazione di un file ASN

Segui questi passaggi per controllare i risultati dell'importazione di un file ASN.

1. Passare a **Gestione magazzino \> Carichi \> Tutti i carichi**.
1. Trova e apri un carico che è stato creato come parte di un'importazione ASN.
1. Nella Scheda dettaglio **Carico** dovresti vedere i valori basati sul file XML.
1. Nella Scheda dettaglio **Righe di carico** dovresti vedere i numeri dell'ordine fornitore e i dettagli degli articoli basati sul file XML.
1. Nel riquadro azioni, nella scheda **Spedisci e ricevi**, nel gruppo **Ricevi** seleziona **Struttura di imballaggio** per rivedere la struttura di imballaggio del carico.
1. Nella Scheda dettaglio **Pallet** dovresti vedere le targhe basate sul file XML.
1. Nella Scheda dettaglio **Casi** dovresti vedere i casi basati sul file XML.
1. Nella Scheda dettaglio **Articoli** dovresti vedere gli articoli e le quantità basati sul file XML.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
