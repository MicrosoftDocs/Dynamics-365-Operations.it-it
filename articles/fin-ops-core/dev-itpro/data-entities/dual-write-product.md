---
title: Esperienza prodotto unificata
description: In questo argomento viene descritta l'integrazione dei dati del prodotto tra le app Finance and Operations e Common Data Service.
author: t-benebo
manager: AnnBe
ms.date: 09/3/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 9dc26e0e50c0b77555d09e4a50b846c80b1d5760
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2019
ms.locfileid: "2249330"
---
# <a name="unified-product-experience"></a>Esperienza prodotto unificata

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

Quando un ecosistema aziendale è costituito da applicazioni Dynamics 365, come Finance, Supply Chain Management e Sales, è naturale per i clienti utilizzare queste applicazioni per acquisire dati di prodotto. Questo perché tali app forniscono una robusta infrastruttura di prodotto completata da sofisticati concetti di valutazione e dati di magazzino disponibile accurati. I clienti che utilizzano un sistema esterno di gestione del ciclo di vita del prodotto per l'acquisizione dei dati di prodotto possono dirigere i prodotti dalle app Finance and Operations ad altre app Dynamics 365. L'esperienza di prodotto unificata importa il modello di dati di prodotto integrato in Common Data Service, di modo che tutti gli utenti delle applicazioni inclusi gli utenti di Power Platform possano usufruire dei dati di prodotto avanzati delle app Finance and Operations.

Di seguito è riportato il modello di dati di prodotto di Sales.

![Modello di dati per prodotti Sales](media/dual-write-product-4.jpg)

Di seguito è riportato il modello di dati di prodotto delle app Finance and Operations.

![Modello di dati per prodotti in Finance and Operations](media/dual-write-products-5.jpg)

Questi due modelli di dati di prodotto sono stati integrati in Common Data Service come mostrato di seguito.

![Modello di dati per prodotti nelle app Dynamics 365](media/dual-write-products-6.jpg)

Le mappe di entità di doppia scrittura per i prodotti sono state progettate per un flusso di dati esclusivamente unidirezionale e rappresentano un'esperienza quasi in tempo reale dalle app Finance and Operations a Common Data Service. Tuttavia, l'infrastruttura di prodotto è stata aperta per renderla bidirezionale, se necessario. I clienti possono personalizzarla, a proprio rischio, in quanto Microsoft non consiglia questo approccio.

## <a name="templates"></a>Modelli

Le informazioni di prodotto contengono tutte le informazioni sul prodotto e sulla relativa definizione, come le dimensioni prodotto o le dimensioni di tracciabilità e di immagazzinamento. Come mostrato nella tabella seguente, una raccolta di mappe di entità viene creata per sincronizzare i prodotti e le informazioni correlate.

Finance and Operations | Altre app Dynamics 365
-----------------------|--------------------------------
Prodotti rilasciati V2 | msdyn\_sharedproductdetails
Prodotti specifici CDS rilasciati | Prodotto
Codice a barre identificatore di numeri prodotto | msdyn\_productbarcodes
Impostazioni ordine predefinite | msdyn\_productdefaultordersettings
Impostazioni ordine predefinite specifiche del prodotto | msdyn_productspecificdefaultordersettings
Gruppi di dimensioni prodotto | msdyn\_productdimensiongroups
Gruppi di dimensioni di immagazzinamento | msdyn\_productstoragedimensiongroups
Gruppi di dimensioni di tracciabilità | msdyn\_producttrackingdimensiongroups
Colori | msdyn\_productcolors
Dimensioni | msdyn\_productsizes
Stili | msdyn\_productsytles
Configurazioni | msdyn\_productconfigurations
Colori rappresentazione generale prodotto | msdyn_sharedproductcolors
Dimensioni rappresentazione generale prodotto | msdyn_sharedproductsizes
Stili rappresentazione generale prodotto | msdyn_sharedproductstyles
Configurazioni rappresentazione generale prodotto | msdyn_sharedproductconfigurations
Tutti i prodotti | msdyn_globalproducts
Unità | uoms
Conversioni unità | msdyn_ unitofmeasureconversions
Conversione di unità di misura specifiche del prodotto | msdyn_productspecificunitofmeasureconversion
Siti | msdyn\_operationalsites
Magazzini | msdyn\_inventwarehouses

[!include [symbols](../includes/dual-write-symbols.md)]

## <a name="integration-of-products"></a>Integrazione di prodotti

In questo modello, il prodotto è rappresentato dalla combinazione di due entità in Common Data Service: **Prodotto** e **msdyn\_sharedproductdetails**. Mentre la prima entità contiene la definizione di un prodotto (identificatore univoco per il prodotto, il nome del prodotto e la descrizione), la seconda entità contiene i campi archiviati a livello del prodotto. La combinazione di queste due entità viene utilizzata per definire il prodotto in base al concetto di unità di stockkeeping. Ogni prodotto rilasciato avrà le relative informazioni nelle entità menzionate (Prodotto e Dettagli prodotto condivisi). Per tenere traccia di tutti i prodotti (rilasciati e non rilasciati) si utilizza l'entità **Prodotti globali**. 

Poiché il prodotto è rappresentato come unità di stockkeeping, i concetti di prodotti specifici, rappresentazioni generali prodotto e varianti prodotto possono essere acquisiti in Common Data Service nel seguente modo:

- I **prodotti con prodotto di sottotipo** sono prodotti auto-definiti. Nessuna dimensione deve essere definita per questi prodotti. Un esempio è un registro specifico. Per tali prodotti, viene creato un record nell'entità **Prodotto** e un record nell'entità **msdyn\_sharedproductdetails**. Non viene creato nessun record di famiglia di prodotti.
- Le **rappresentazioni generali prodotto** sono utilizzate come prodotti generici che contengono la definizione e le regole che determinano il comportamento nei processi aziendali. In base a queste definizioni, è possibile generare i prodotti specifici noti come varianti prodotto. Ad esempio, Maglietta è la rappresentazione generale prodotto e può avere le dimensioni Colore e Dimensione. È possibile rilasciare varianti che hanno differenti combinazioni di queste dimensioni, come una maglietta blu di taglia S o una maglietta verde di taglia M. Nell'integrazione, un record per variante viene creato nella tabella dei prodotti. Tale record contiene informazioni specifiche della variante, come le differenti dimensioni. Le informazioni generiche per il prodotto sono archiviate nell'entità **msdyn\_sharedproductdetails** (queste informazioni generiche si trovano nella rappresentazione generale prodotto). Inoltre, un record di famiglia di prodotti viene creato per rappresentazione generale prodotto. Le informazioni relative alla rappresentazione generale prodotto vengono sincronizzate con Common Data Service non appena viene creata la rappresentazione generale prodotto rilasciata (ma prima del rilascio delle varianti).
- I **prodotti specifici** fanno riferimento a tutti i prodotti di sottotipo e a tutte le varianti prodotto. 

![Modello di dati per prodotti](media/dual-write-product.png)

Con la funzionalità di doppia scrittura attivata, le app di Finance and Operations sono sincronizzate in altre app Dynamics 365 nello stato **Bozza**. Queste vengono aggiunte al primo listino prezzi con la stessa valuta. In altre parole, sono aggiunte al primo listino prezzi in un'app Dynamics 365 che corrisponde alla valuta della persona giuridica in cui il prodotto viene rilasciato in un'app Finance and Operations. 

Per sincronizzare il prodotto con stato **Attivo** di modo che sia possibile utilizzarlo direttamente, ad esempio, nelle offerte di ordine cliente, è necessario selezionare **Creare prodotti in stato attivo = Sì** in **Sistema > Amministrazione > Amministrazione sistema > Impostazioni di sistema > Impostazioni > Sales**. 

### <a name="cds-released-distinct-products-to-product"></a>Prodotti specifici rilasciati da CDS a Prodotto

L'entità **Prodotto** contiene i campi che definiscono il prodotto. Include singoli prodotti (prodotti con prodotto di sottotipo) e varianti prodotto. Nella seguente tabella sono riportati i mapping.

Campo di origine | Tipo di mappa | Campo di destinazione
---|---|---
PRODUCTNUMBER | >> | productnumber
PRODUCTNAME | >> | name
PRODUCTDESCRIPTION | >> | descrizione
ITEMNUMBER | >> | msdyn_itemnumber
CURRENCYCODE | >> | transactioncurrencyid.isocurrencycode
SALESUNITSYMBOL | >> | defaultuomid.msdyn_symbol
SALESPRICE | >> | prezzo
UNITCOST | >> | currentcost
PRODUCTTYPE | >> | producttypecode
SALESUNITDECIMALPRECISION | >> | quantitydecimal
ISCATCHWEIGHTPRODUCT | >> | msdyn_iscatchweight
PRODUCTCOLORID | >> | msdyn_productcolor.msdyn_productcolorname
PRODUCTCONFIGURATIONID | >> | msdyn_productconfiguration.msdyn_productconfiguration
PRODUCTSIZEID | >> | msdyn_productsize.msdyn_productsize
PRODUCTSTYLEID | >> | msdyn_productstyle.msdyn_productstyle

### <a name="released-products-v2-to-msdyn_sharedproductdetails"></a>Prodotti V2 rilasciati a msdyn\_sharedproductdetails

L'entità **msdyn\_sharedproductdetails** contiene i campi delle app Finance and Operations che definiscono il prodotto e che contengono le informazioni finanziarie e di gestione del prodotto. Nella seguente tabella sono riportati i mapping.

Campo di origine | Tipo di mappa | Campo di destinazione
---|---|---
PRODUCTNUMBER | > | msdyn_globalproduct.msdyn_productnumber
INTRASTATCHARGEPERCENTAGE | > | msdyn_intrastatchargepercentage
ITEMNUMBER | >> | msdyn_itemnumber
APPROXIMATESALESTAXPERCENTAGE | > | msdyn_approximatesalestaxpercentage
BESTBEFOREPERIODDAYS | > | msdyn_bestbeforeperioddays
CARRYINGCOSTABCCODE | >> | msdyn_carryingcostabccode
CONSTANTSCRAPQUANTITY | > | msdyn_constantscrapquantity
COSTCHARGESQUANTITY | > | msdyn_costchargesquantity
DEFAULTRECEIVINGQUANTITY | > | msdyn_defaultreceivingquantity
FIXEDPURCHASEPRICECHARGES | > | msdyn_fixedpurchasepricecharges
FIXEDSALESPRICECHARGES | > | msdyn_fixedsalespricecharges
GROSSDEPTH | > | msdyn_grossdepth
GROSSPRODUCTHEIGHT | > | msdyn_grossproductheight
GROSSPRODUCTWIDTH | > | msdyn_grossproductwidth
INVENTORYUNITSYMBOL | > | msdyn_inventoryunitsymbol.msdyn_symbol
ISDISCOUNTPOSREGISTRATIONPROHIBITED | >> | msdyn_isdiscountposregistrationprohibited
ISEXEMPTFROMAUTOMATICNOTIFICATIONANDCANCELLATION | >> | msdyn_exemptautomaticnotificationcancel
ISINSTALLMENTELIGIBLE | >> | msdyn_isinstallmenteligible
ISINTERCOMPANYPURCHASEUSAGEBLOCKED | >> | msdyn_isintercompanypurchaseusageblocked
ISINTERCOMPANYSALESUSAGEBLOCKED | >> | msdyn_isintercompanysalesusageblocked
ISMANUALDISCOUNTPOSREGISTRATIONPROHIBITED | >> | msdyn_ismanualdiscposregistrationprohibited
ISPHANTOM | >> | msdyn_isphantom
ISPOSREGISTRATIONBLOCKED | >> | msdyn_isposregistrationblocked
ISPOSREGISTRATIONQUANTITYNEGATIVE | >> | msdyn_isposregistrationquantitynegative
ISPURCHASEPRICEAUTOMATICALLYUPDATED | >> | msdyn_ispurchasepriceautomaticallyupdated
ISPURCHASEPRICEINCLUDINGCHARGES | >> | msdyn_ispurchasepriceincludingcharges
ISSALESWITHHOLDINGTAXCALCULATED | >> | msdyn_issaleswithholdingtaxcalculated
ISRESTRICTEDFORCOUPONS | >> | msdyn_isrestrictedforcoupons
ISSALESPRICEADJUSTMENTALLOWED | >> | msdyn_issalespriceadjustmentallowed
ISSALESPRICEINCLUDINGCHARGES | >> | msdyn_issalespriceincludingcharges
ISSCALEPRODUCT | >> | msdyn_isscaleproduct
ISSHIPALONEENABLED | >> | msdyn_isshipaloneenabled
ISUNITCOSTPRODUCTVARIANTSPECIFIC | >> | msdyn_isunitcostproductvariantspecific
ISVARIANTSHELFLABELSPRINTINGENABLED | >> | msdyn_isvariantshelflabelsprintingenabled
ISZEROPRICEPOSREGISTRATIONALLOWED | >> | msdyn_iszeropriceposregistrationallowed
KEYINPRICEREQUIREMENTSATPOSREGISTER | >> | msdyn_keyinpricerequirementsatposregister
KEYINQUANTITYREQUIREMENTSATPOSREGISTER | >> | msdyn_keyinquantityrequirementsatposregister
MARGINABCCODE | >> | msdyn_marginabccode
MAXIMUMPICKQUANTITY | > | msdyn_maximumpickquantity
MUSTKEYINCOMMENTATPOSREGISTER | >> | msdyn_mustkeyincommentatposregister
NECESSARYPRODUCTIONWORKINGTIMESCHEDULINGPROPERTYID | > | msdyn_necessaryproductionworkingtimeschedulingp
NETPRODUCTWEIGHT | > | msdyn_netproductweight
PACKINGDUTYQUANTITY | > | msdyn_packingdutyquantity
POSREGISTRATIONACTIVATIONDATE | > | msdyn_posregistrationactivationdate
POSREGISTRATIONBLOCKEDDATE | > | msdyn_posregistrationblockeddate
POSREGISTRATIONPLANNEDBLOCKEDDATE | > | msdyn_posregistrationplannedblockeddate
POTENCYBASEATTIBUTETARGETVALUE | > | msdyn_potencybaseattibutetargetvalue
POTENCYBASEATTRIBUTEVALUEENTRYEVENT | >> | msdyn_potencybaseattributevalueentryevent
PRODUCTTYPE | >> | msdyn_producttype
PRODUCTIONCONSUMPTIONDENSITYCONVERSIONFACTOR | > | msdyn_productionconsumptiondensityconversion
PRODUCTIONCONSUMPTIONDEPTHCONVERSIONFACTOR | > | msdyn_productionconsumptiondepthconversion
PRODUCTIONCONSUMPTIONHEIGHTCONVERSIONFACTOR | > | msdyn_productionconsumptionheightconversion
PRODUCTIONCONSUMPTIONWIDTHCONVERSIONFACTOR | > | msdyn_productionconsumptionwidthconversion
PRODUCTVOLUME | > | msdyn_productvolume
PURCHASECHARGESQUANTITY | > | msdyn_purchasechargesquantity
PURCHASEOVERDELIVERYPERCENTAGE | > | msdyn_purchaseoverdeliverypercentage
PURCHASEPRICE | > | msdyn_purchaseprice
PURCHASEPRICEDATE | > | msdyn_purchasepricedate
PURCHASEPRICINGPRECISION | > | msdyn_purchasepricingprecision
PURCHASEUNDERDELIVERYPERCENTAGE | > | msdyn_purchaseunderdeliverypercentage
RAWMATERIALPICKINGPRINCIPLE | >> | msdyn_rawmaterialpickingprinciple
SALESCHARGESQUANTITY | > | msdyn_saleschargesquantity
SALESOVERDELIVERYPERCENTAGE | > | msdyn_salesoverdeliverypercentage
SALESPRICE | > | msdyn_salesprice
SALESPRICECALCULATIONCHARGESPERCENTAGE | > | msdyn_salespricecalculationchargespercentage
SALESPRICECALCULATIONCONTRIBUTIONRATIO | > | msdyn_salespricecalculationcontributionratio
SALESPRICECALCULATIONMODEL | >> | msdyn_salespricecalculationmodel
SALESPRICEDATE | > | msdyn_salespricedate
SALESPRICINGPRECISION | > | msdyn_salespricingprecision
SALESUNDERDELIVERYPERCENTAGE | > | msdyn_salesunderdeliverypercentage
SALESUNITSYMBOL | > | msdyn_salesunitsymbol.msdyn_symbol
SCALEINDICATOR | >> | msdyn_scaleindicator
SELLSTARTDATE | > | msdyn_sellstartdate
SHELFADVICEPERIODDAYS | > | msdyn_shelfadviceperioddays
SHELFLIFEPERIODDAYS | > | msdyn_shelflifeperioddays
SHIPSTARTDATE | > | msdyn_shipstartdate
TAREPRODUCTWEIGHT | > | msdyn_tareproductweight
TRANSFERORDEROVERDELIVERYPERCENTAGE | > | msdyn_transferorderoverdeliverypercentage
TRANSFERORDERUNDERDELIVERYPERCENTAGE | > | msdyn_transferorderunderdeliverypercentage
UNITCOST | > | msdyn_unitcost
UNITCOSTDATE | > | msdyn_unitcostdate
UNITCOSTQUANTITY | > | msdyn_unitcostquantity
VARIABLESCRAPPERCENTAGE | > | msdyn_variablescrappercentage
WAREHOUSEMOBILEDEVICEDESCRIPTIONLINE1 | > | msdyn_warehousemobiledevicedescriptionline1
WAREHOUSEMOBILEDEVICEDESCRIPTIONLINE2 | > | msdyn_warehousemobiledevicedescriptionline2
WILLINVENTORYISSUEAUTOMATICALLYREPORTASFINISHED | >> | msdyn_willinventoryissueautoreportasfinished
WILLINVENTORYRECEIPTIGNOREFLUSHINGPRINCIPLE | >> | msdyn_willinventoryreceiptignoreflushing
WILLPICKINGWORKBENCHAPPLYBOXINGLOGIC | >> | msdyn_willpickingworkbenchapplyboxinglogic
WILLTOTALPURCHASEDISCOUNTCALCULATIONINCLUDEPRODUCT | >> | msdyn_willtotalpurchdiscountcalcincludeproduct
WILLTOTALSALESDISCOUNTCALCULATIONINCLUDEPRODUCT | >> | msdyn_willtotalsalesdiscountcalcincludeproduct
WILLWORKCENTERPICKINGALLOWNEGATIVEINVENTORY | >> | msdyn_willworkcenterpickingallownegativeinvent
YIELDPERCENTAGE | > | msdyn_yieldpercentage
ISUNITCOSTAUTOMATICALLYUPDATED | >> | msdyn_isunitcostautomaticallyupdated
PURCHASEUNITSYMBOL | > | msdyn_purchaseunitsymbol.msdyn_symbol
PURCHASEPRICEQUANTITY | > | msdyn_purchasepricequantity
ISUNITCOSTINCLUDINGCHARGES | >> | msdyn_isunitcostincludingcharges
FIXEDCOSTCHARGES | >> | msdyn_fixedcostcharges
MINIMUMCATCHWEIGHTQUANTITY | >> | msdyn_minimumcatchweightquantity
MAXIMUMCATCHWEIGHTQUANTITY | >> | msdyn_maximumcatchweightquantity
ALTERNATIVEITEMNUMBER | >> | msdyn_alternativeitemnumber.msdyn_itemnumber
BOMUNITSYMBOL | >> | msdyn_bomunitsymbol.msdyn_symbol
CATCHWEIGHTUNITSYMBOL | >> | msdyn_catchweightunitsymbol.msdyn_symbol
COMPARISONPRICEBASEUNITSYMBOL | >> | msdyn_comparisonpricebaseunitsymbol.msdyn_symbol
PRIMARYVENDORACCOUNTNUMBER | >> | msdyn_vendorid.msdyn_vendoraccountnumber
ISCATCHWEIGHTPRODUCT | >> | msdyn_iscatchweight
PRODUCTDIMENSIONGROUPNAME | >> | msdyn_productdimensiongroupid.msdyn_groupname

## <a name="all-product-to-msdyn_global-products"></a>Tutti i prodotti a prodotti msdyn_global

L'entità Tutti i prodotti contiene tutti i prodotti disponibili nelle app Finance and Operations, ovvero i prodotti rilasciati e quelli non rilasciati. Questi prodotti sono disponibili in Common Data Service mediante i mapping seguenti:

Campo di origine | Tipo di mappa | Campo di destinazione
---|---|---
PRODUCTNAME | >> | msdyn_productname
PRODUCTNUMBER | >> | msdyn_productnumber

## <a name="product-dimensions"></a>Dimensioni prodotto 

Le dimensioni prodotto sono caratteristiche che identificano una variante prodotto. Le quattro dimensioni prodotto (colore, dimensione, stile e configurazione) vengono inoltre mappati a Common Data Service per definire le varianti prodotto. Nella figura seguente è illustrato il modello di dati per la dimensione prodotto Colore. Lo stesso modello viene applicato a Dimensioni, Stili e Configurazioni. 

![Modello di dati per prodotti](media/dual-write-product-2.PNG)

### <a name="colors"></a>Colori

I colori possibili sono disponibili in Common Data Service mediante i seguenti mapping.

Campo di origine | Tipo di mappa | Campo di destinazione
---|---|---
COLORID | \>\> | msdyn\_productcolorname

### <a name="sizes"></a>Dimensioni

Le dimensioni possibili sono disponibili in Common Data Service mediante i seguenti mapping.

Campo di origine | Tipo di mappa | Campo di destinazione
---|---|---
SIZEID | \>\> | msdyn\_productsize

### <a name="styles"></a>Stili

Gli stili possibili sono disponibili in Common Data Service mediante i seguenti mapping.

Campo di origine | Tipo di mappa | Campo di destinazione
---|---|---
STYLEID | \>\> | msdyn\_productstyle

### <a name="configurations"></a>Configurazioni

Le configurazioni possibili sono disponibili in Common Data Service mediante i seguenti mapping.

Campo di origine | Tipo di mappa | Campo di destinazione
---|---|---
CONFIGURATIONID | \>\> | msdyn\_name

Quando un prodotto ha dimensioni prodotto differenti (ad esempio una rappresentazione generale prodotto ha Colore e Prodotto come dimensioni prodotto, ovvero ogni variante prodotto) è definito come combinazione di tali dimensioni prodotto. Ad esempio, il numero prodotto B0001 è una maglietta nera di taglia XS e il numero prodotto B0002 è una maglietta nera di taglia S. In questo caso, le combinazioni esistenti delle dimensioni prodotto sono definite. Ad esempio, la maglietta dell'esempio precedente può essere nera e di taglia XS, S, M o L, ma non può essere nera e di taglia XL. In altre parole, le dimensioni prodotto che una rappresentazione generale prodotto può avere sono specificate e le varianti possono essere rilasciate in base a tali valori.

Per tenere traccia delle dimensioni prodotto che una rappresentazione generale prodotto può utilizzare, le seguenti entità vengono create e mappate in Common Data Service per ogni dimensione prodotto. Per ulteriori informazioni, vedere [Panoramica delle informazioni sul prodotto](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/pim/product-information).

### <a name="shared-product-color"></a>Colore prodotto condiviso

L'entità **Colore prodotto condiviso** indica i colori che una specifica rappresentazione generale prodotto può avere. Questo concetto viene migrato a Common Data Service per assicurare la coerenza dei dati. Nella seguente tabella sono riportati i mapping.

Campo di origine | Tipo di mappa | Campo di destinazione
---|---|---
PRODUCTCOLORID | \>\> | msdyn\_productcolorid.msdyn\_productcolorname
PRODUCTMASTERNUMBER | \>\> | msdyn\_sharedproductdetailid.msdyn\_itemnumber
REPLENISHMENTWEIGHT | \>\> | msdyn\_replenishmentweight
DISPLAYSEQUENCENUMBER | \>\> | msdyn\_retaildisplayorder

### <a name="shared-product-size"></a>Dimensione prodotto condivisa

L'entità **Dimensione prodotto condivisa** indica le dimensioni che una rappresentazione generale prodotto può avere. Questo concetto viene migrato a Common Data Service per assicurare la coerenza dei dati. Nella seguente tabella sono riportati i mapping.

Campo di origine | Tipo di mappa | Campo di destinazione
---|---|---
PRODUCTMASTERNUMBER | \>\> | msdyn\_sharedproductdetailid.msdyn\_itemnumber
PRODUCTSIZEID | \>\> | msdyn\_productsizeid.msdyn\_productsize
REPLENISHMENTWEIGHT | \>\> | msdyn\_replenishmentweight
DISPLAYSEQUENCENUMBER | \>\> | msdyn\_displaysequencenumber

### <a name="shared-product-style"></a>Stile prodotto condiviso

L'entità **Stile prodotto condiviso** indica gli stili che una specifica rappresentazione generale prodotto può avere. Questo concetto viene migrato a Common Data Service per assicurare la coerenza dei dati. Nella seguente tabella sono riportati i mapping.

Campo di origine | Tipo di mappa | Campo di destinazione
---|---|---
PRODUCTMASTERNUMBER | \>\> | msdyn\_sharedproductdetailsid.msdyn\_itemnumber
PRODUCTSTYLEID | \>\> | msdyn\_productstyleintegration
PRODUCTSTYLEID | \>\> | msdyn\_productstyleid.msdyn\_productstyle
REPLENISHMENTWEIGHT | \>\> | msdyn\_replenishmentweight
DISPLAYSEQUENCENUMBER | \>\> | msdyn\_displaysequencenumber

### <a name="shared-product-configuration"></a>Configurazione prodotto condivisa

L'entità **Configurazione prodotto condivisa** indica le configurazioni che una specifica rappresentazione generale prodotto può avere. Questo concetto viene migrato a Common Data Service per assicurare la coerenza dei dati. Nella seguente tabella sono riportati i mapping.

Campo di origine | Tipo di mappa | Campo di destinazione
---|---|---
CONTAINERUNITSYMBOL | \>\> | msdyn\_containerunitsymbol
PRODUCTCONFIGURATIONID | \>\> | msdyn\_productconfigurationid.msdyn\_productconfiguration
PRODUCTMASTERNUMBER | \>\> | msdyn\_sharedproductdetailid.msdyn\_itemnumber
REPLENISHMENTWEIGHT | \>\> | msdyn\_replenishmentweight
DISPLAYSEQUENCENUMBER | \>\> | msdyn\_displaysequencenumber

## <a name="product-number-identifier-bar-codes"></a>Codici a barre identificatori di numeri prodotto

I codici a barre sono utilizzati per identificare in modo univoco i prodotti. I mapping seguenti sono utilizzati per rendere questi codici a barre disponibili in Common Data Service.

Campo di origine | Tipo di mappa | Campo di destinazione
---|---|---
PRODUCTNUMBER | \> | msdyn\_productnumberid.productnumber
BARCODE | \> | msdyn\_name
BARCODE | \> | msdyn\_barcode
PRODUCTQUANTITY | \> | msdyn\_productquantity
PRODUCTDESCRIPTION | \> | msdyn\_productdescription
BARCODESETUPID | \> | msdyn\_barcodesetupid
PRODUCTQUANTITYUNITSYMBOL | \> | msdyn\_unitofmeasureid.name
ISDEFAULTSCANNEDBARCODE | \>\> | msdyn\_isdefaultscannedbarcode
ISDEFAULTPRINTEDBARCODE | \>\> | msdyn\_isdefaultprintedbarcode
ISDEFAULTDISPLAYEDBARCODE | \>\> | msdyn\_isdefaultdisplayedbarcode

## <a name="default-order-settings-and-product-specific-default-order-settings"></a>Impostazioni ordine predefinite e impostazioni ordine predefinite specifiche del prodotto

Le impostazioni ordine predefinite definiscono il sito e il magazzino in cui gli articoli saranno prelevati o archiviati, le quantità minima, massima, multipla e standard che verrà utilizzata per il commercio o la gestione degli articoli, i lead time, il flag di interruzione e il metodo delle promesse ordine. Questo informazioni saranno disponibili in CDS mediante le impostazioni ordine predefinite e le impostazioni ordine predefinite specifiche del prodotto. Per ulteriori informazioni sulla funzionalità, vedere la [pagina Impostazioni ordine predefinite](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/production-control/default-order-settings).

### <a name="default-order-settings"></a>Impostazioni ordine predefinite

I mapping seguenti sono utilizzati per rendere le impostazioni ordine predefinite disponibili in Common Data Service.

Campo di origine | Tipo di mappa | Campo di destinazione
---|---|---
INVENTWAREHOUSEID | = | msdyn_inventorywarehouse.msdyn_warehouseidentifier
INVENTORYSITEID | = | msdyn_inventorysite.msdyn_siteid
INVENTORYATPDELAYEDDEMANDOFFSETDAYS | = | msdyn_inventoryatpdelayeddemandoffsetdays
INVENTORYATPDELAYEDSUPPLYOFFSETDAYS | = | msdyn_inventoryatpdelayedsupplyoffsetdays
ITEMNUMBER | = | msdyn_itemnumber.msdyn_itemnumber
INVENTORYATPBACKWARDDEMANDTIMEFENCEDAYS | = | msdyn_inventoryatpbackwarddemandtimefencedays
INVENTORYATPBACKWARDSUPPLYTIMEFENCEDAYS | = | msdyn_inventoryatpbackwardsupplytimefencedays
INVENTORYATPTIMEFENCEDAYS | = | msdyn_inventoryatptimefencedays
MAXIMUMINVENTORYORDERQUANTITY | = | msdyn_maximuminventoryorderquantity
MAXIMUMPROCUREMENTORDERQUANTITY | = | msdyn_maximumprocurementorderquantity
MAXIMUMSALESORDERQUANTITY | = | msdyn_maximumsalesorderquantity
MINIMUMINVENTORYORDERQUANTITY | = | msdyn_minimuminventoryorderquantity
MINIMUMPROCUREMENTORDERQUANTITY | = | msdyn_minimumprocurementorderquantity
MINIMUMSALESORDERQUANTITY | = | msdyn_minimumsalesorderquantity
STANDARDINVENTORYORDERQUANTITY | = | msdyn_standardinventoryorderquantity
STANDARDPROCUREMENTORDERQUANTITY | = | msdyn_standardprocurementorderquantity
STANDARDSALESORDERQUANTITY | = | msdyn_standardsalesorderquantity
INVENTORYLEADTIMEDAYS | = | msdyn_inventoryleadtimedays
INVENTORYQUANTITYMULTIPLES | = | msdyn_inventoryquantitymultiples
PROCUREMENTQUANTITYMULTIPLES | = | msdyn_procurementquantitymultiples
SALESQUANTITYMULTIPLES | = | msdyn_salesquantitymultiples
PROCUREMENTSITEID | = | msdyn_procurementsite.msdyn_siteid
PROCUREMENTLEADTIMEDAYS | = | msdyn_procurementleadtimedays
SALESSITEID | = | msdyn_salessite.msdyn_siteid
SALESATPDELAYEDDEMANDOFFSETDAYS | = | msdyn_salesatpdelayeddemandoffsetdays
SALESATPDELAYEDSUPPLYOFFSETDAYS | = | msdyn_salesatpdelayedsupplyoffsetdays
SALESATPBACKWARDDEMANDTIMEFENCEDAYS | = | msdyn_salesatpbackwarddemandtimefencedays
SALESATPBACKWARDSUPPLYTIMEFENCEDAYS | = | msdyn_salesatpbackwardsupplytimefencedays
SALESATPTIMEFENCEDAYS | = | msdyn_salesatptimefencedays
SALESLEADTIMEDAYS | = | msdyn_salesleadtimedays
PROCUREMENTWAREHOUSEID | = | msdyn_procurementwarehouse.msdyn_warehouseidentifier
SALESWAREHOUSEID | = | msdyn_saleswarehouse.msdyn_warehouseidentifier
AREINVENTORYORDERPROMISINGDEFAULTSOVERRIDDEN | >< | msdyn_areinventoryorderdefaultsoverridden
INVENTORYORDERPROMISINGMETHOD | >< | msdyn_inventoryorderpromisingmethod
ISINVENTORYATPINCLUDINGPLANNEDORDERS | >< | msdyn_isinventoryatpincludingplannedorders
ISINVENTORYUSINGWORKINGDAYS | >< | msdyn_isinventoryusingworkingdays
ISINVENTORYSITEMANDATORY | >< | msdyn_isinventorysitemandatory
ISINVENTORYPROCESSINGSTOPPED | >< | msdyn_isinventoryprocessingstopped
ISPROCUREMENTUSINGWORKINGDAYS | >< | msdyn_isprocurementusingworkingdays
ISPROCUREMENTSITEMANDATORY | >< | msdyn_isprocurementsitemandatory
ISPROCUREMENTPROCESSINGSTOPPED | >< | msdyn_isprocurementprocessingstopped
ARESALESORDERPROMISINGDEFAULTSOVERRIDDEN | >< | msdyn_aresalesorderdefaultsoverridden
SALESORDERPROMISINGMETHOD | >< | msdyn_salesorderpromisingmethod
ISSALESATPINCLUDINGPLANNEDORDERS | >< | msdyn_issalesatpincludingplannedorders
ISSALESSITEMANDATORY | >< | msdyn_issalessitemandatory
ISSALESLEADTIMEOVERRIDDEN | >< | msdyn_issalesleadtimeoverridden
ISSALESPROCESSINGSTOPPED | >< | msdyn_issalesprocessingstopped
ISINVENTORYWAREHOUSEMANDATORY | >< | msdyn_isinventorywarehousemandatory
ISPROCUREMENTWAREHOUSEMANDATORY | >< | msdyn_isprocurementwarehousemandatory
ISSALESWAREHOUSEMANDATORY | >< | msdyn_issaleswarehousemandatory

### <a name="product-specific-default-order-settings"></a>Impostazioni ordine predefinite specifiche del prodotto

I mapping seguenti sono utilizzati per rendere le impostazioni ordine predefinite specifiche del prodotto disponibili in Common Data Service.

Campo di origine | Tipo di mappa | Campo di destinazione
---|---|---
INVENTORYWAREHOUSEID | = | msdyn_inventorywarehouse.msdyn_warehouseidentifier
INVENTORYSITEID | = | msdyn_inventorysite.msdyn_siteid
INVENTORYATPDELAYEDDEMANDOFFSETDAYS | = | msdyn_inventoryatpdelayeddemandoffsetdays
INVENTORYATPDELAYEDSUPPLYOFFSETDAYS | = | msdyn_inventoryatpdelayedsupplyoffsetdays
ITEMNUMBER | = | msdyn_itemnumber.msdyn_itemnumber
INVENTORYATPBACKWARDDEMANDTIMEFENCEDAYS | = | msdyn_inventoryatpbackwarddemandtimefencedays
INVENTORYATPBACKWARDSUPPLYTIMEFENCEDAYS | = | msdyn_inventoryatpbackwardsupplytimefencedays
INVENTORYATPTIMEFENCEDAYS | = | msdyn_inventoryatptimefencedays
MAXIMUMINVENTORYORDERQUANTITY | = | msdyn_maximuminventoryorderquantity
MAXIMUMPROCUREMENTORDERQUANTITY | = | msdyn_maximumprocurementorderquantity
MAXIMUMSALESORDERQUANTITY | = | msdyn_maximumsalesorderquantity
MINIMUMINVENTORYORDERQUANTITY | = | msdyn_minimuminventoryorderquantity
MINIMUMPROCUREMENTORDERQUANTITY | = | msdyn_minimumprocurementorderquantity
MINIMUMSALESORDERQUANTITY | = | msdyn_minimumsalesorderquantity
STANDARDINVENTORYORDERQUANTITY | = | msdyn_standardinventoryorderquantity
STANDARDPROCUREMENTORDERQUANTITY | = | msdyn_standardprocurementorderquantity
STANDARDSALESORDERQUANTITY | = | msdyn_standardsalesorderquantity
INVENTORYLEADTIMEDAYS | = | msdyn_inventoryleadtimedays
INVENTORYQUANTITYMULTIPLES | = | msdyn_inventoryquantitymultiples
PROCUREMENTQUANTITYMULTIPLES | = | msdyn_procurementquantitymultiples
SALESQUANTITYMULTIPLES | = | msdyn_salesquantitymultiples
PROCUREMENTSITEID | = | msdyn_procurementsite.msdyn_siteid
PROCUREMENTLEADTIMEDAYS | = | msdyn_procurementleadtimedays
SALESSITEID | = | msdyn_salessite.msdyn_siteid
SALESATPDELAYEDDEMANDOFFSETDAYS | = | msdyn_salesatpdelayeddemandoffsetdays
SALESATPDELAYEDSUPPLYOFFSETDAYS | = | msdyn_salesatpdelayedsupplyoffsetdays
SALESATPBACKWARDDEMANDTIMEFENCEDAYS | = | msdyn_salesatpbackwarddemandtimefencedays
SALESATPBACKWARDSUPPLYTIMEFENCEDAYS | = | msdyn_salesatpbackwardsupplytimefencedays
SALESATPTIMEFENCEDAYS | = | msdyn_salesatptimefencedays
SALESLEADTIMEDAYS | = | msdyn_salesleadtimedays
PROCUREMENTWAREHOUSEID | = | msdyn_procurementwarehouse.msdyn_warehouseidentifier
SALESWAREHOUSEID | = | msdyn_saleswarehouse.msdyn_warehouseidentifier
AREINVENTORYDEFAULTORDERSETTINGSOVERRIDDEN | >< | msdyn_areinventoryorderdefaultsoverridden
INVENTORYORDERPROMISINGMETHOD | >< | msdyn_inventoryorderpromisingmethod
ISINVENTORYATPINCLUDINGPLANNEDORDERS | >< | msdyn_isinventoryatpincludingplannedorders
ISINVENTORYUSINGWORKINGDAYS | >< | msdyn_isinventoryusingworkingdays
ISINVENTORYSITEMANDATORY | >< | msdyn_isinventorysitemandatory
ISINVENTORYPROCESSINGSTOPPED | >< | msdyn_isinventoryprocessingstopped
ISPROCUREMENTUSINGWORKINGDAYS | >< | msdyn_isprocurementusingworkingdays
ISPROCUREMENTSITEMANDATORY | >< | msdyn_isprocurementsitemandatory
ISPROCUREMENTPROCESSINGSTOPPED | >< | msdyn_isprocurementprocessingstopped
ARESALESDEFAULTORDERSETTINGSOVERRIDDEN | >< | msdyn_aresalesorderdefaultsoverridden
SALESORDERPROMISINGMETHOD | >< | msdyn_salesorderpromisingmethod
ISSALESATPINCLUDINGPLANNEDORDERS | >< | msdyn_issalesatpincludingplannedorders
ISSALESSITEMANDATORY | >< | msdyn_issalessitemandatory
ISSALESLEADTIMEOVERRIDDEN | >< | msdyn_issalesleadtimeoverridden
ISSALESPROCESSINGSTOPPED | >< | msdyn_issalesprocessingstopped
ISINVENTORYWAREHOUSEMANDATORY | >< | msdyn_isinventorywarehousemandatory
ISPROCUREMENTWAREHOUSEMANDATORY | >< | msdyn_isprocurementwarehousemandatory
ISSALESWAREHOUSEMANDATORY | >< | msdyn_issaleswarehousemandatory
OPERATIONALSITEID | = | msdyn_operationalsite.msdyn_siteid
PRODUCTCOLORID | = | msdyn_productcolor.msdyn_productcolorname
PRODUCTCONFIGURATIONID | = | msdyn_productconfiguration.msdyn_productconfiguration
PRODUCTSIZEID | = | msdyn_productsize.msdyn_productsize
PRODUCTSTYLEID | = | msdyn_productstyle.msdyn_productstyle

## <a name="unit-of-measure-and-unit-of-measure-conversions"></a>Unità di misura e conversioni di unità di misura

Le unità di misura e le relative conversioni saranno disponibili in Common Data Service mediante il modello di dati visualizzato nel diagramma.

![Modello di dati per prodotti](media/dual-write-product-3.PNG)

Il concetto di unità di misura è integrato tra le app Finance and Operations e altre app Dynamics 365. Per ogni classe di unità di misura in un'app Finance and Operations, viene creato un gruppo di unità in un'app Dynamics 365, che contiene le unità appartenenti alla classe di unità di misura. Un'unità di base predefinita viene inoltre creata per ogni gruppo di unità. 

### <a name="unit-of-measure"></a>Unità di misura

I mapping seguenti sono utilizzati per rendere le unità di misura nelle app Finance and Operations disponibili in Common Data Service.

Campo di origine | Tipo di mappa | Campo di destinazione
---|---|---
UNITSYMBOL | >> | msdyn_symbol
UNITCLASS | >> | msdyn_externalunitclassname
DECIMALPRECISION | >> | msdyn_decimalprecision
ISBASEUNIT | >> | msdyn_isbaseunit
ISSYSTEMUNIT | >> | msdyn_issystemunit
SYSTEMOFUNITS | >> | msdyn_systemofunits
UNITSYMBOL | >> | name
UNITDESCRIPTION | >> | msdyn_description

### <a name="unit-of-measure-conversions"></a>Conversioni di unità di misura

I mapping seguenti sono utilizzati per rendere le conversioni di unità di misura nelle app Finance and Operations disponibili in Common Data Service.

Campo di origine | Tipo di mappa | Campo di destinazione
---|---|---
DENOMINATOR | = | msdyn_denominator
NUMERATOR | = | msdyn_numerator
FACTOR | = | msdyn_factor
INNEROFFSET | = | msdyn_inneroffset
OUTEROFFSET | = | msdyn_outeroffset
ROUNDING | >< | msdyn_rounding
TOUNITSYMBOL | = | msdyn_tounit.msdyn_symbol
FROMUNITSYMBOL | = | msdyn_fromunit.msdyn_symbol

### <a name="product-specific-unit-of-measure-conversions"></a>Conversioni di unità di misura specifiche del prodotto

I mapping seguenti sono utilizzati per rendere le conversioni di unità di misura specifiche del prodotto nelle app Finance and Operations disponibili in Common Data Service.

Campo di origine | Tipo di mappa | Campo di destinazione
---|---|---
DENOMINATOR | = | msdyn_denominator
NUMERATOR | = | msdyn_numerator
FACTOR | = | msdyn_factor
FROMUNITSYMBOL | = | msdyn_fromunit.msdyn_symbol
TOUNITSYMBOL | = | msdyn_tounit.msdyn_symbol
PRODUCTNUMBER | = | msdyn_globalproduct.msdyn_productnumber
INNEROFFSET | = | msdyn_inneroffset
OUTEROFFSET | = | msdyn_outeroffset
ROUNDING | >< | msdyn_rounding

## <a name="product-policies-dimension-tracking-and-storage-groups"></a>Criteri di prodotto: gruppi di dimensioni, tracciabilità e archiviazioni

I criteri di prodotto sono set di criteri utilizzati per definire i prodotti e le relative caratteristiche in magazzino. Il gruppo di dimensioni prodotto, di dimensioni di tracciabilità e di dimensioni di immagazzinamento sono disponibili come criteri di prodotto. 

### <a name="product-dimension-group"></a>Gruppo di dimensioni prodotto

Il gruppo di dimensioni prodotto determina le dimensioni prodotto che definiscono il prodotto. I quattro gruppi possibili di dimensioni prodotto sono: colore, configurazione, dimensione e stile. I gruppi di dimensioni prodotto sono disponibili in Common Data Service mediante i mapping seguenti. 

Campo di origine | Tipo di mappa | Campo di destinazione
---|---|---
WILLSALESPRICESEARCHUSEPRODUCTSTYLE | >< | msdyn_willsalespricesearchuseproductstyle
WILLPURCHASEPRICESEARCHUSEPRODUCTSIZE | >< | msdyn_willpurchasepricesearchuseproductsize
WILLSALESPRICESEARCHUSEPRODUCTCONFIGURATION | >< | msdyn_willsalespricesearchuseprodconfig
WILLSALESPRICESEARCHUSEPRODUCTCOLOR | >< | msdyn_willsalespricesearchuseproductcolor
WILLPURCHASEPRICESEARCHUSEPRODUCTSTYLE | >< | msdyn_willpurchasepricesearchuseproductstyle
WILLPURCHASEPRICESEARCHUSEPRODUCTCONFIGURATION | >< | msdyn_willpurchpricesearchuseprodconfig
WILLPURCHASEPRICESEARCHUSEPRODUCTCOLOR | >< | msdyn_willpurchpricesearchuseproductcolor
ISPRODUCTSTYLEACTIVE | >< | msdyn_isproductstyleactive
ISPRODUCTSIZEACTIVE | >< | msdyn_isproductsizeactive
ISPRODUCTCONFIGURATIONACTIVE | >< | msdyn_isproductconfigurationactive
ISPRODUCTCOLORACTIVE | >< | msdyn_isproductcoloractive
GROUPNAME | = | msdyn_groupname
GROUPDESCRIPTION | = | msdyn_groupdescription
PRODUCTVARIANTNOMENCLATURENAME | = | msdyn_productvariantnomenclaturename
WILLSALESPRICESEARCHUSEPRODUCTSIZE | >< | msdyn_willsalespricesearchuseproductsize

### <a name="product-tracking-dimension-group"></a>Gruppo di dimensioni di tracciabilità prodotto

Il gruppo di dimensioni di tracciabilità prodotto rappresenta il metodo utilizzato per tenere traccia del prodotto in magazzino. Questi gruppi sono disponibili in Common Data Service mediante i mapping seguenti. 

Campo di origine | Tipo di mappa | Campo di destinazione
---|---|---
SERIALNUMBERCAPTURINGOPERATION | >< | msdyn_serialnumbercapturingoperation
GROUPNAME | = | msdyn_groupname
GROUPDESCRIPTION | = | msdyn_groupdescription
ISSERIALNUMBERENABLEDFORPRODUCTIONCONSUMPTIONPROCESS | >< | msdyn_issnenabledforpcprocess
ISSERIALNUMBERCONTROLENABLED | >< | msdyn_isserialnumbercontrolenabled
ISSERIALNUMBERENABLEDFORSALESPROCESS | >< | msdyn_isserialnumberenabledforsalesprocess
ISSERIALNUMBERACTIVE | >< | msdyn_isserialnumberactive
ISSALESPRICEBYSERIALNUMBER | >< | msdyn_issalespricebyserialnumber
ISSALESPRICEBYBATCHNUMBER | >< | msdyn_issalespricebybatchnumber
ISPURCHASEPRICEBYSERIALNUMBER | >< | msdyn_ispurchasepricebyserialnumber
ISPURCHASEPRICEBYBATCHNUMBER | >< | msdyn_ispurchasepricebybatchnumber
ISPRIMARYSTOCKINGENABLEDFORSERIALNUMBER | >< | msdyn_isprimarystockingenabledforsn
ISPRIMARYSTOCKINGENABLEDFORBATCHNUMBER | >< | msdyn_isprimarystockingenabledforbn
ISPHYSICALINVENTORYENABLEDFORSERIALNUMBER | >< | msdyn_isphysicalinventoryenabledforsn
ISPHYSICALINVENTORYENABLEDFORBATCHNUMBER | >< | msdyn_isphysicalinventoryenabledforbn
ISFINANCIALINVENTORYENABLEDFORSERIALNUMBER | >< | msdyn_isfinancialinventoryenabledforsn
ISFINANCIALINVENTORYENABLEDFORBATCHNUMBER | >< | msdyn_isfinancialinventoryenabledforbn
ISCOVERAGEPLANENABLEDFORSERIALNUMBER | >< | msdyn_iscoverageplanenabledforserialnumber
ISCOVERAGEPLANENABLEDFORBATCHNUMBER | >< | msdyn_iscoverageplanenabledforbatchnumber
ISBLANKRECEIPTALLOWEDFORSERIALNUMBER | >< | msdyn_isblankreceiptallowedforserialnumber
ISBLANKRECEIPTALLOWEDFORBATCHNUMBER | >< | msdyn_isblankreceiptallowedforbatchnumber
ISBLANKISSUEALLOWEDFORSERIALNUMBER | >< | msdyn_isblankissueallowedforserialnumber
ISBLANKISSUEALLOWEDFORBATCHNUMBER | >< | msdyn_isblankissueallowedforbatchnumber
ISBATCHNUMBERACTIVE | >< | msdyn_isbatchnumberactive
ISINVENTORYOWNERACTIVE | >< | msdyn_isinventoryowneractive

### <a name="product-storage-dimension-group"></a>Gruppo di dimensioni di immagazzinamento prodotto

Il gruppo di dimensioni di immagazzinamento prodotto rappresenta il metodo utilizzato per definire l'ubicazione del prodotto in magazzino. Questi gruppi sono disponibili in Common Data Service mediante i mapping seguenti. 

Campo di origine | Tipo di mappa | Campo di destinazione
---|---|---
WILLSALESPRICESEARCHUSEWAREHOUSE | >< | msdyn_willsalespricesearchusewarehouse
WILLSALESPRICESEARCHUSESITE | >< | msdyn_willsalespricesearchusesite
WILLSALESPRICESEARCHUSEINVENTORYSTATUS | >< | msdyn_willsalespricesearchuseinventorystatus
WILLPURCHASEPRICESEARCHUSEWAREHOUSE | >< | msdyn_willpurchasepricesearchusewarehouse
WILLPURCHASEPRICESEARCHUSESITE | >< | msdyn_willpurchasepricesearchusesite
WILLPURCHASEPRICESEARCHUSEINVENTORYSTATUS | >< | msdyn_willpurchpricesearchuseinventstatus
WILLCOVERAGEPLANNINGUSEWAREHOUSE | >< | msdyn_willcoverageplanusewarehouse
WILLCOVERAGEPLANNINGUSELOCATION | >< | msdyn_iscoverageplanenabledforlocation
WILLCOVERAGEPLANNINGUSEINVENTORYSTATUS | >< | msdyn_willcoverageplanuseinventorystatus
AREADVANCEDWAREHOUSEMANAGEMENTPROCESSESENABLED | >< | msdyn_areadvancedwmprocessesenabled
ISWAREHOUSEPRIMARYSTORAGEDIMENSION | >< | msdyn_iswarehouseprimarystoragedimension
ISWAREHOUSEMANDATORY | >< | msdyn_iswarehousemandatory
ISPHYSICALINVENTORYENABLEDFORWAREHOUSE | >< | msdyn_isphysicalinventoryenabledforwarehouse
ISPHYSICALINVENTORYENABLEDFORLOCATION | >< | msdyn_isphysicalinventoryenabledforlocation
ISLOCATIONACTIVE | >< | msdyn_islocationactive
ISFINANCIALINVENTORYENABLEDFORWAREHOUSE | >< | msdyn_isfinancialinventoryenabledforwarehouse
GROUPNAME | = | msdyn_groupname
GROUPDESCRIPTION | = | msdyn_groupdescription
ISBLANKRECEIPTALLOWEDFORLOCATION | >< | msdyn_isblankreceiptallowedforlocation
ISBLANKISSUEALLOWEDFORLOCATION | >< | msdyn_isblankissueallowedforlocation

