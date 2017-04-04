---
title: Materiali di imballaggio e commissioni
description: "Gli addebiti relativi al materiale di imballaggio vengono pagati a una società di riciclaggio a determinati intervalli. Per ciascun materiale di cui si compone un&quot;unità di imballaggio viene pagato un importo per unità di peso. Questi addebiti vengono calcolati e inclusi in un report, tuttavia non vengono registrate transazioni contabili, in quanto gli addebiti relativi al materiale di imballaggio non sono considerati come imposte da pagare a un ufficio tributario."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventPackagingGroup, InventPackagingMaterialCode, InventPackagingMaterialFee, InventPackagingMaterialTrans, InventPackagingMaterialTransPurch, InventPackagingUnit
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 2194
ms.assetid: 040b65dc-43c9-4256-b69f-b2d6e736fbe9
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: 7c0bc5b5d86956336012096c11d0d7621abab1f9
ms.lasthandoff: 03/31/2017


---

# <a name="packing-materials-and-fees"></a>Materiali di imballaggio e commissioni

Gli addebiti relativi al materiale di imballaggio vengono pagati a una società di riciclaggio a determinati intervalli. Per ciascun materiale di cui si compone un'unità di imballaggio viene pagato un importo per unità di peso. Questi addebiti vengono calcolati e inclusi in un report, tuttavia non vengono registrate transazioni contabili, in quanto gli addebiti relativi al materiale di imballaggio non sono considerati come imposte da pagare a un ufficio tributario.

I pesi e gli addebiti relativi al materiale di imballaggio vengono calcolati per le righe degli ordini fornitore e cliente.

È possibile definire una o più unità di imballaggio per un articolo, un gruppo di articoli di imballaggio o tutti gli articoli. Un'unità di imballaggio si compone di materiali di imballaggio e dei relativi pesi, oltre che del numero di articoli inclusi nell'unità. Un codice materiale di imballaggio viene assegnato a ciascun tipo di materiale di imballaggio definito. In base al codice materiale di imballaggio, è possibile specificare un prezzo per un periodo specifico. Gli addebiti relativi al materiale di imballaggio vengono calcolati in base a tali informazioni.

| **Nota **                                                                                                                                             |
|------------------------------------------------------------------------------------------------------------------------------------------------------|
| Anche se la società non effettua pagamenti per addebiti relativi al materiale di imballaggio, è possibile utilizzare questa funzionalità per calcolare statistiche relative ai pesi per il materiale di imballaggio. |

## <a name="setup-requirements-for-packing-material-fees"></a>Requisiti di impostazione per gli addebiti per il materiale di imballaggio
Prima di calcolare i pesi o gli addebiti relativi al materiale di imballaggio, o entrambi, creare la seguente anagrafica:

-   Gruppi di imballaggio: consente di creare gruppi di imballaggio da assegnare agli articoli.
-   Codici materiale di imballaggio: consente di creare codici materiale di imballaggio per ogni tipo di materiale di imballaggio definito.
-   Unità di imballaggio: specificare un'unità di imballaggio per un articolo, un gruppo di imballaggio o per tutti gli articoli. Per ogni unità di imballaggio, definire i materiali di imballaggio da includere, assegnare i pesi e, nel campo Fattore unità di imballaggio, immettere il fattore di conversione dall'unità di magazzino.
-   Addebiti materiale di imballaggio: specificare gli addebiti per il materiale di imballaggio per il codice del materiale di imballaggio. Per ciascun tipo di materiale definire il periodo di validità, il prezzo per materiale, la valuta e l'unità.

## <a name="packing-units-on-sales-order-lines"></a>Unità di imballaggio nelle righe ordine cliente
Quando si crea una riga ordine cliente, viene effettuata una verifica per accertare se sono state specificate le unità di imballaggio per l'articolo. Se le unità di imballaggio sono specificate, il sistema aggiorna la riga ordine cliente con l'unità di imballaggio e la quantità di unità di imballaggio specificate. Questa quantità viene basata sulla quantità ordinata divisa per il numero di articoli nell'unità di imballaggio selezionata. Se non è stata specificata un'unità di imballaggio, è possibile immettere manualmente un'unità e una quantità di unità di imballaggio nella riga ordine cliente. È inoltre possibile modificare l'unità di imballaggio e la quantità di unità di imballaggio quando si registra la riga ordine cliente. Questo aspetto è importante se la riga ordine cliente viene consegnata o fatturata solo parzialmente. Quando si fattura l'ordine cliente, le transazioni per materiale di imballaggio vengono create. Le transazioni per materiale di imballaggio contengono i pesi del materiale di imballaggio della riga di vendita. È anche possibile modificare le transazioni dopo la fatturazione e quindi creare nuove transazioni.

## <a name="packing-units-on-purchase-order-lines"></a>Unità di imballaggio nelle righe ordine fornitore
Le transazioni per materiale di imballaggio per una riga ordine fornitore non vengono create dal sistema. È necessario creare manualmente le transazioni per le righe ordine fornitore fatturate nella pagina **Transazioni materiale di imballaggio**.

## <a name="set-up-customer-packagingmaterialfee-license-numbers"></a>Numero di licenza packagingmaterialfee di impostazione dei clienti
Se gli addebiti per il materiale di imballaggio sono a carico dei clienti, specificare i relativi numeri di licenza nella pagina **Clienti**. Quando si assegna un numero di licenza a un cliente, gli addebiti per il materiale di imballaggio vengono calcolati automaticamente al momento della fatturazione degli ordini cliente. Dopo la fatturazione la casella di controllo **Calcola addebito** viene deselezionata nella pagina **Transazioni materiale di imballaggio**, in quanto non è necessario calcolare e stampare un report. È possibile stampare i pesi del materiale di imballaggio sulla fattura e informare i clienti che gli addebiti relativi sono a loro carico. 

Se gli addebiti per il materiale di imballaggio sono a carico della società, non specificare i numeri di licenza dei clienti. Dopo la fatturazione, la casella di controllo **Calcolare la commissione** è selezionata nella pagina **Transazioni materiale di imballaggio**. Ciò significa che gli addebiti vengono calcolati al momento della creazione di un report. È possibile stampare i pesi sulla fattura e indicare che gli addebiti relativi sono a carico della società.

## <a name="print-packaging-material-weights-on-invoices"></a>Stampare i pesi del materiale di imballaggio sulle fatture
È possibile stampare i pesi del materiale di imballaggio sulla fattura e indicare a chi sono imputabili gli addebiti per tale materiale. I pesi vengono riepilogati per codice di imballaggio.
 



