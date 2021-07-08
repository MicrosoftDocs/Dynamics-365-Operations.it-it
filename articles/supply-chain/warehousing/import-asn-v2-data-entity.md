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
# <a name="import-inbound-asns-through-the-v2-data-entity"></a><span data-ttu-id="93940-103">Importare gli ASN in entrata tramite l'entità di dati V2</span><span class="sxs-lookup"><span data-stu-id="93940-103">Import inbound ASNs through the V2 data entity</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="93940-104">Gli gli Advanced Shipping Notice (ASN) ti informano sulle consegne dei fornitori.</span><span class="sxs-lookup"><span data-stu-id="93940-104">Advanced shipping notices (ASNs) notify you about vendor deliveries.</span></span> <span data-ttu-id="93940-105">Aiutano il mittente a descrivere il contenuto di una spedizione e ulteriori informazioni, come gli articoli e l'imballaggio.</span><span class="sxs-lookup"><span data-stu-id="93940-105">They help the sender describe the contents of a shipment and additional information about it, such as the items and packaging.</span></span>

<span data-ttu-id="93940-106">Gli ASN possono aiutare i magazzinieri a sapere cosa sta arrivando e quando.</span><span class="sxs-lookup"><span data-stu-id="93940-106">ASNs can help warehouse workers learn what is arriving when.</span></span> <span data-ttu-id="93940-107">Pertanto, possono prepararsi.</span><span class="sxs-lookup"><span data-stu-id="93940-107">Therefore, they can prepare.</span></span> <span data-ttu-id="93940-108">Inoltre, gli addetti al magazzino possono utilizzare gli ASN per abbinare i dettagli di una spedizione all'ordine fornitore correlato creato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="93940-108">In addition, warehouse workers can use ASNs to match the details of a shipment to the related purchase order that was previously created.</span></span>

<span data-ttu-id="93940-109">Questo argomento presenta una raccolta di scenari che mostrano, attraverso esempi, come utilizzare i file ASN.</span><span class="sxs-lookup"><span data-stu-id="93940-109">This topic presents a collection of scenarios that show, through examples, how to work with ASN files.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="93940-110">L'importazione di *ASN in entrata* si applica solo agli articoli abilitati per la gestione avanzata del magazzino (WMS).</span><span class="sxs-lookup"><span data-stu-id="93940-110">*Inbound ASN* import applies only to items that are enabled for advanced warehouse management (WMS).</span></span> <span data-ttu-id="93940-111">Prima di ricevere un ASN, è necessario registrare nel sistema un ordine relativo al fornitore che invia tale ASN.</span><span class="sxs-lookup"><span data-stu-id="93940-111">Before you receive an ASN, a purchase order must be registered in the system against the vendor who is sending that ASN.</span></span>

## <a name="inbound-asn-v2-entity"></a><span data-ttu-id="93940-112">Entità ASN V2 in entrata</span><span class="sxs-lookup"><span data-stu-id="93940-112">Inbound ASN V2 entity</span></span>

<span data-ttu-id="93940-113">Importi gli ASN in entrata usando l'entità di dati composita *ASN V2 in entrata*.</span><span class="sxs-lookup"><span data-stu-id="93940-113">You import inbound ASNs by using the *Inbound ASN V2* composite data entity.</span></span> <span data-ttu-id="93940-114">*ASN V2 in entrata* si avvale delle seguenti entità:</span><span class="sxs-lookup"><span data-stu-id="93940-114">*Inbound ASN V2* takes advantage of the following entities:</span></span>

- <span data-ttu-id="93940-115">Intestazione carico in entrata</span><span class="sxs-lookup"><span data-stu-id="93940-115">Inbound load header</span></span>
- <span data-ttu-id="93940-116">Intestazione spedizione in entrata</span><span class="sxs-lookup"><span data-stu-id="93940-116">Inbound shipment header</span></span>
- <span data-ttu-id="93940-117">Strutture di imballaggio carico in entrata</span><span class="sxs-lookup"><span data-stu-id="93940-117">Inbound load packing structures</span></span>
- <span data-ttu-id="93940-118">Casse struttura di imballaggio carico in entrata</span><span class="sxs-lookup"><span data-stu-id="93940-118">Inbound load packing structure cases</span></span>
- <span data-ttu-id="93940-119">Righe casse di struttura di imballaggio carico in entrata</span><span class="sxs-lookup"><span data-stu-id="93940-119">Inbound load packing structure case lines</span></span>
- <span data-ttu-id="93940-120">Righe struttura di imballaggio carico in entrata</span><span class="sxs-lookup"><span data-stu-id="93940-120">Inbound load packing structure lines</span></span>

<span data-ttu-id="93940-121">L'entità di dati composita *ASN V2 in entrata* è destinata a scenari di integrazione asincrona in cui vengono utilizzate importazioni basate su file XML.</span><span class="sxs-lookup"><span data-stu-id="93940-121">The *Inbound ASN V2* composite data entity is intended for asynchronous integration scenarios where XML file–based imports are used.</span></span>

## <a name="xml-format-for-importing-asns"></a><span data-ttu-id="93940-122">Formato XML per l'importazione di ASN</span><span class="sxs-lookup"><span data-stu-id="93940-122">XML format for importing ASNs</span></span>

<span data-ttu-id="93940-123">Microsoft Dynamics 365 Supply Chain Management supporta il seguente formato XML per l'importazione di ASN.</span><span class="sxs-lookup"><span data-stu-id="93940-123">Microsoft Dynamics 365 Supply Chain Management supports the following XML format for importing ASNs.</span></span> <span data-ttu-id="93940-124">Ciascun nodo nel file XML rappresenta un attributo di una singola entità.</span><span class="sxs-lookup"><span data-stu-id="93940-124">Each node in the XML file represents an attribute from an individual entity.</span></span>

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

## <a name="examples"></a><span data-ttu-id="93940-125">Esempi</span><span class="sxs-lookup"><span data-stu-id="93940-125">Examples</span></span>

<span data-ttu-id="93940-126">Le seguenti sottosezioni forniscono esempi di file di importazione XML ASN per le spedizioni dei fornitori.</span><span class="sxs-lookup"><span data-stu-id="93940-126">The following subsections provide examples of ASN XML import files for vendor shipments.</span></span>

### <a name="example-1"></a><span data-ttu-id="93940-127">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="93940-127">Example 1</span></span>

<span data-ttu-id="93940-128">L'esempio seguente mostra un file XML per l'importazione di spedizioni dei fornitori per un ordine fornitore quando non sono inclusi i dettagli del caso.</span><span class="sxs-lookup"><span data-stu-id="93940-128">The following example shows an XML file for importing vendor shipments for one purchase order when no case details are included.</span></span>

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

### <a name="example-2"></a><span data-ttu-id="93940-129">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="93940-129">Example 2</span></span>

<span data-ttu-id="93940-130">L'esempio seguente mostra un file XML per l'importazione di spedizioni dei fornitori per un ordine fornitore quando sono inclusi i dettagli del caso.</span><span class="sxs-lookup"><span data-stu-id="93940-130">The following example shows an XML file for importing vendor shipments for one purchase order when case details are included.</span></span>

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

### <a name="example-3"></a><span data-ttu-id="93940-131">Esempio 3</span><span class="sxs-lookup"><span data-stu-id="93940-131">Example 3</span></span>

<span data-ttu-id="93940-132">L'esempio seguente mostra un file XML per l'importazione di spedizioni dei fornitori per più ordini fornitore quando sono inclusi i dettagli del caso.</span><span class="sxs-lookup"><span data-stu-id="93940-132">The following example shows an XML file for importing vendor shipments for multiple purchase orders when case details are included.</span></span>

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

## <a name="inspect-the-results-of-importing-an-asn-file"></a><span data-ttu-id="93940-133">Ispezionare i risultati dell'importazione di un file ASN</span><span class="sxs-lookup"><span data-stu-id="93940-133">Inspect the results of importing an ASN file</span></span>

<span data-ttu-id="93940-134">Segui questi passaggi per controllare i risultati dell'importazione di un file ASN.</span><span class="sxs-lookup"><span data-stu-id="93940-134">Follow these steps to inspect the results of importing an ASN file.</span></span>

1. <span data-ttu-id="93940-135">Passare a **Gestione magazzino \> Carichi \> Tutti i carichi**.</span><span class="sxs-lookup"><span data-stu-id="93940-135">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="93940-136">Trova e apri un carico che è stato creato come parte di un'importazione ASN.</span><span class="sxs-lookup"><span data-stu-id="93940-136">Find and open a load that was created as part of an ASN import.</span></span>
1. <span data-ttu-id="93940-137">Nella Scheda dettaglio **Carico** dovresti vedere i valori basati sul file XML.</span><span class="sxs-lookup"><span data-stu-id="93940-137">On the **Load** FastTab, you should see values that are based on the XML file.</span></span>
1. <span data-ttu-id="93940-138">Nella Scheda dettaglio **Righe di carico** dovresti vedere i numeri dell'ordine fornitore e i dettagli degli articoli basati sul file XML.</span><span class="sxs-lookup"><span data-stu-id="93940-138">On the **Load lines** FastTab, you should see purchase order numbers and item details that are based on the XML file.</span></span>
1. <span data-ttu-id="93940-139">Nel riquadro azioni, nella scheda **Spedisci e ricevi**, nel gruppo **Ricevi** seleziona **Struttura di imballaggio** per rivedere la struttura di imballaggio del carico.</span><span class="sxs-lookup"><span data-stu-id="93940-139">On the Action Pane, on the **Ship and receive** tab, in the **Receive** group, select **Packing structure** to review the packing structure of the load.</span></span>
1. <span data-ttu-id="93940-140">Nella Scheda dettaglio **Pallet** dovresti vedere le targhe basate sul file XML.</span><span class="sxs-lookup"><span data-stu-id="93940-140">On the **Pallets** FastTab, you should see license plates that are based on the XML file.</span></span>
1. <span data-ttu-id="93940-141">Nella Scheda dettaglio **Casi** dovresti vedere i casi basati sul file XML.</span><span class="sxs-lookup"><span data-stu-id="93940-141">On the **Cases** FastTab, you should see cases that are based on the XML file.</span></span>
1. <span data-ttu-id="93940-142">Nella Scheda dettaglio **Articoli** dovresti vedere gli articoli e le quantità basati sul file XML.</span><span class="sxs-lookup"><span data-stu-id="93940-142">On the **Items** FastTab, you should see items and quantities that are based on the XML file.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
