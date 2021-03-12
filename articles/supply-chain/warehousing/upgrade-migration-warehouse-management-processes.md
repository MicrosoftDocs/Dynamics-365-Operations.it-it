---
title: Aggiornare la gestione magazzino da Microsoft Dynamics AX 2012 a Supply Chain Management
description: Questo argomento fornisce una panoramica delle opzioni di migrazione della gestione di prodotti e magazzino.
author: perlynne
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventLocationWHSProcessEnablement, WHSLocationProfile, InventTableStorageDimensionGroupChange, InventUpdateBlockedItem, WHSParameters, WHSReservationHierarchy, WHSUOMSeqGroupTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1714054
ms.assetid: 79a1a3b9-3a36-4162-8839-ec39b5e26602
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 45d9809d4bbf1b5a68c3f799ce5d51f9709d276b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4970283"
---
# <a name="upgrade-warehouse-management-from-microsoft-dynamics-ax-2012-to-supply-chain-management"></a>Aggiornare la gestione magazzino da Microsoft Dynamics AX 2012 a Supply Chain Management 


[!include [banner](../includes/banner.md)]

Questo argomento fornisce una panoramica del processo di aggiornamento da Microsoft Dynamics AX 2012 R3, che esegue il modulo WMSII, a Supply Chain Management.

Supply Chain Management non supporta più il modulo legacy **WMSII** di Microsoft Dynamics AX 2012. In alternativa, è possibile utilizzare il modulo **Gestione magazzino**. Nel modulo WMSII, le dimensioni inventariali ID pallet e Ubicazione possono essere selezionate per l'inventario finanziario, tuttavia, la dimensione inventariale ID pallet non può essere utilizzata per l'inventario finanziario in Supply Chain Management.

Durante un aggiornamento, tutti i prodotti associati a un gruppo di dimensioni di immagazzinamento che utilizza la dimensione inventariale ID pallet vengono identificati, contrassegnati come bloccati e non elaborati per l'aggiornamento.

## <a name="upgrading-to-supply-chain-management-when-ax-2012-r3-wmsii-is-used"></a>Aggiornamento a Supply Chain Management quando viene utilizzato AX 2012 R3 WMSII
Dopo l'aggiornamento, è possibile utilizzare un set di opzioni di migrazione nel modulo **Modifica del gruppo di dimensioni di immagazzinamento per articoli** per sbloccare i prodotti bloccati durante l'aggiornamento e quindi elaborare le transazioni per quei prodotti.

### <a name="enabling-items-in-supply-chain-management"></a>Abilitazione degli articoli in Supply Chain Management 
Questa modifica è necessaria poiché in Supply Chain Management il tracciamento degli articoli fa parte dei processi di gestione del magazzino. Per questi processi, tutti i magazzini e le relative ubicazioni devono essere associati a un profilo di ubicazione. Se si desidera utilizzare i processi di gestione del magazzino, è necessario configurare quanto segue:
-   I magazzini esistenti devono essere abilitati per l'utilizzo dei processi di gestione del magazzino. 
-   I prodotti rilasciati esistenti devono essere associati a un gruppo di dimensioni di immagazzinamento che utilizza processi di gestione del magazzino. 

Se i gruppi di dimensioni di immagazzinamento di origine utilizzano la dimensione inventariale ID pallet, le ubicazioni degli inventari esistenti che hanno utilizzato la dimensione inventariale ID pallet devono essere associate a un profilo di ubicazione in cui il parametro **Usa rilevamento targa** è selezionato. Se i magazzini esistenti non devono essere abilitati per l'utilizzo dei processi di gestione magazzino, è possibile modificare i gruppi di dimensioni di immagazzinamento dell'inventario esistente in gruppi che gestiscono solo le dimensioni inventariali Sito, Magazzino e Ubicazione. 

> [!NOTE] 
>  È possibile modificare il gruppo di dimensioni di immagazzinamento per gli articoli anche se sono presenti transazioni di magazzino aperte.

## <a name="find-products-that-were-blocked-because-of-pallet-id"></a>Trovare prodotti che sono stati bloccati a causa dell'ID pallet
Per visualizzare l'elenco di prodotti rilasciati che sono stati bloccati durante l'aggiornamento e che non possono essere elaborati, fare clic su **Gestione inventario** &gt; **Impostazioni** &gt; **Magazzino** &gt; **Articoli bloccati per gli aggiornamenti di inventario**.

## <a name="change-storage-dimension-group-for-blocked-products"></a>Cambiare il gruppo di dimensioni di immagazzinamento per i prodotti bloccati 
 
Per essere utilizzati nell'ambito di un processo di gestione magazzino, un articolo deve essere associato a un gruppo di dimensioni di immagazzinamento in cui la dimensione inventariale Ubicazione è attiva e il parametro **Usa processi di gestione magazzino** è selezionato. Quando questa impostazione è selezionata, le dimensioni inventariali Sito, Magazzino, Stato inventario, Ubicazione e Targa diventano attive.

Per sbloccare i prodotti che sono stati bloccati durante l'aggiornamento, è necessario selezionare un nuovo gruppo di dimensioni di immagazzinamento per i prodotti. Tenere presente che è possibile modificare il gruppo di dimensioni di immagazzinamento anche se sono presenti transazioni di magazzino aperte. Per utilizzare gli articoli che sono stati bloccati durante l'aggiornamento, sono disponibili due opzioni:

-   Modificare il gruppo di dimensioni di immagazzinamento per l'articolo in un gruppo di dimensioni di immagazzinamento che utilizza solo dimensioni inventariali Sito, Magazzino e Ubicazione. A seguito di questa modifica, la dimensione inventariale ID pallet non viene più utilizzata.
-   Modificare il gruppo di dimensioni di immagazzinamento per l'articolo in un gruppo di dimensioni di immagazzinamento che utilizza i processi di gestione del magazzino. A seguito di questa modifica, la dimensione inventariale Targa viene ora utilizzata.

## <a name="configure-warehouse-management-processes"></a>Configurare i processi di gestione magazzino
Prima di poter utilizzare i prodotti rilasciati nel modulo **Gestione magazzino**, i prodotti devono utilizzare un gruppo di dimensioni di immagazzinamento in cui il parametro **Usa processi di gestione magazzino** è selezionato.

### <a name="enable-warehouses-to-use-warehouse-management-processes"></a>Consentire ai magazzini di utilizzare i processi di gestione magazzino

1.  Creare almeno un nuovo profilo di ubicazione.
2.  Fare clic su **Gestione magazzino** &gt; **Impostazioni** &gt; **Consenti processi di gestione magazzino** &gt; **Consenti impostazione magazzino**.
3.  Nella pagina **Consenti impostazione magazzino** aggiungere i magazzini che devono essere attivati. È possibile completare questo passaggio direttamente nella pagina o tramite l'integrazione con Microsoft Office.
4.  Assegnare un profilo di ubicazione a tutte le ubicazioni. È possibile completare facilmente questo passaggio utilizzando l'integrazione con Microsoft Office o direttamente dalla pagina. È possibile esportare e importare i dati o utilizzare l'elaborazione delle entità di dati in [Gestione dati](../../dev-itpro/data-entities/data-entities.md).
5.  Convalidare le modifiche. Durante il processo di convalida si verificano alcune convalide di integrità dei dati. Nell'ambito di un processo di aggiornamento di dimensioni più ampie, è possibile che si debba correggere eventuali problemi nell'implementazione di origine. In questo caso sarà necessario eseguire un ulteriore aggiornamento dei dati.
6.  Elaborare le modifiche.

### <a name="change-the-storage-dimension-group-for-items-so-that-it-uses-warehouse-management-processes"></a>Modificare il gruppo di dimensioni di immagazzinamento per gli articoli in modo che il gruppo utilizzi i processi di gestione magazzino

1.  Creare un nuovo valore **Stato inventario** e assegnarlo come valore **ID stato inventario predefinito** nelle impostazioni **Parametri di gestione magazzino**.
2.  Creare un nuovo gruppo di dimensioni di immagazzinamento in cui il parametro **Usa processi di gestione magazzino** è selezionato.
3.  Nella pagina **Gerarchia prenotazioni** definire una nuova gerarchia di prenotazioni in base ai gruppi di dimensioni di tracciabilità e di immagazzinamento dell'articolo.
4.  Creare uno o più gruppi di sequenze di unità che include almeno le stesse unità utilizzate per le unità di magazzino degli articoli.
5.  Fare clic su **Gestione magazzino** &gt; **Impostazioni** &gt; **Consenti processi di gestione magazzino** &gt; **Modifica gruppo di dimensioni di immagazzinamento per articoli**.
6.  Nella pagina **Modifica gruppo di dimensioni di immagazzinamento per articoli** aggiungere i numeri articolo, i gruppi di dimensioni di immagazzinamento e i gruppi di sequenze di unità. È possibile completare questo passaggio direttamente nella pagina, utilizzando l'integrazione di Microsoft Office oppure il processo delle entità di dati in [Gestione dati](../../dev-itpro/data-entities/data-entities.md).
7.  Convalidare le modifiche. Durante il processo di convalida si verificano alcune convalide di integrità dei dati. Nell'ambito di un processo di aggiornamento di dimensioni più ampie, è possibile che si debba correggere eventuali problemi nell'implementazione di origine. In questo caso sarà necessario eseguire un ulteriore aggiornamento dei dati.
8.  Elaborare le modifiche. L'aggiornamento di tutte le dimensioni inventariali può richiedere qualche minuto. È possibile monitorare lo stato utilizzando le attività dei processi batch.
