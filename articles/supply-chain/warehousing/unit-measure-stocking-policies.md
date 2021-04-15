---
title: Politiche di immagazzinamento e di unità di misura
description: Questo articolo descrive come si utilizzano le unità predefinite, le sequenze unità e le conversioni di unità nei processi di magazzino.
author: perlynne
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductDetails, EcoResProductDetailsExtended, EcoResStorageDimensionGroup, InventItemOrderSetup, UnitOfMeasureConversion, WHSRFMenuItem, WHSUOMSeqGroupTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 29611
ms.assetid: 4b5ca875-9a06-416d-9ac0-cc3ab8f7338e
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dc99a6b03dace15f479e60e9f91e0d53cc0987cf
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5811487"
---
# <a name="unit-of-measure-and-stocking-policies"></a>Politiche di immagazzinamento e di unità di misura

[!include [banner](../includes/banner.md)]

Questo articolo descrive come si utilizzano le unità predefinite, le sequenze unità e le conversioni di unità nei processi di magazzino.

I gruppi di sequenze unità definiscono la sequenza di unità che può essere utilizzata nelle operazioni di magazzino. Vengono creati nella  pagina **Gruppi di sequenze unità**. La sequenza illustra la relazione delle diverse unità. Ad esempio, archiviare i pallet che contengono le caselle contenenti i diversi pezzi di articoli. In questo caso, è necessario immettere le tre diverse unità e l'ordine logico dei livelli. Gruppi di sequenze di unità consentono di definire i criteri per il raggruppamento di dei numeri di targa e unità predefinite che devono essere utilizzate per vari il magazzino elabora. Questo articolo viene applicato alla soluzione organizzazione immagazzinamento avanzata disponibile in gestione magazzino che la soluzione più organizzazione di immagazzinamento base disponibile in gestione articoli.

## <a name="unit-sequence-groups-for-released-products"></a>Gruppi di sequenze unità per i prodotti rilasciati
Se si desidera utilizzare i prodotti rilasciati nei processi di lavoro di magazzino, un gruppo di sequenze di unità deve essere assegnato. Se la convalida un prodotto associato a un gruppo di dimensioni di immagazzinamento e **Processi di gestione magazzino di utilizzo** l'opzione per il gruppo di dimensioni di immagazzinamento è impostati su **Sì**, verrà visualizzato un messaggio di errore se un ID gruppo di sequenze di unità non è definita per il prodotto. Se il gruppo di sequenze di unità utilizzato contiene più righe (e quindi più unità), è necessario impostare una conversione unità tra unità.  Completare questa impostazione nella pagina **Conversioni unità**. La più piccola unità di un gruppo di sequenze associato a un articolo deve corrispondere all'unità di magazzino definita per il prodotto corrispondente. L'unità di magazzino è l'unità di misura utilizzata per i calcoli di base delle scorte disponibili. È inoltre possibile impostare le conversioni unità di misura per le varianti prodotto delle rappresentazioni generali prodotto mediante l'opzione **Abilitare le conversioni unità di misura**.

## <a name="license-plate-grouping"></a>Raggruppamento targa
È possibile specificare se le entrate minori o maggiori di un pallet vengono raggruppate in un'unica targa o suddivise in una targa separata per ogni unità. Per impostare questo comportamento, utilizzare l'opzione **Raggruppamento di targa di immatricolazione** nella scheda **Dettagli riga** della pagina **Gruppi di sequenze di unità**. Se si desidera utilizzare il **raggruppamento targa** quando il lavoro viene elaborato con un dispositivo mobile, è necessario selezionare l'opzione Raggruppamento targa nella voce di menu del **dispositivo mobile**. Ad esempio, si utilizza un dispositivo mobile per registrare un articolo associato a un gruppo di sequenze di unità contenente due righe. La prima riga viene per pezzi e l'opzione **Raggruppamento di targa di immatricolazione** è impostata su **Sì**. La seconda riga viene per pezzi e l'opzione **Raggruppamento di targa di immatricolazione** è impostata su **No**. In questo caso, il sistema può automaticamente facilitare la divisione e la creazione dei numeri di targa per 100 pezzi.

## <a name="units-for-cycle-counting"></a>Unità per conteggio ciclo
Per definire le unità devono essere utilizzate come parte di processi di conteggio del ciclo di lavorazione, selezionare l'opzione **Unità di utilizzo del ciclo di conteggio** nella pagina **Gruppi di sequenze di unità**. È possibile selezionare fino a quattro unità nel gruppo di sequenze. Se si selezionano più di quattro unità, non verranno visualizzate nel dispositivo mobile.

## <a name="default-units-for-mobile-device-receiving-processes"></a>Unità predefinite per processi di ricezione dispositivo mobile
Per impostare le unità predefinite che devono essere utilizzate per i processi di ricevimento per dispositivi mobili, abilitare le opzioni **Unità predefinita per acquisto e trasferimento** e **Unità predefinita per produzione** sulla pagina **Gruppi di sequenze di unità**. Ad esempio, è possibile specificare che, per impostazione predefinita, il sistema deve utilizzare le quantità del pallet alle scorte disponibili dell'ordine fornitore vengono ricevute tramite un dispositivo mobile, ma che l'unità di conservazione deve essere pezzi. Per ottenere la conversione per il numero di pezzi ogni pallet che contiene, è necessario definire una conversione unità, ad esempio 100 pc = 1 PL.

## <a name="default-order-settings"></a>Impostazioni ordine predefinite
Come parte della creazione dei prodotti rilasciati, è necessario selezionare le unità predefinite per gli acquisti, vendite e magazzino elaborare i vari ordini. È possibile impostare le unità e le quantità predefinite per i vari documenti di origine utilizzando le pagine **Impostazioni ordine predefinite** e **Impostazioni ordine specifiche del sito**. È possibile accedere alle pagine dalla pagina **Prodotti rilasciati**.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]