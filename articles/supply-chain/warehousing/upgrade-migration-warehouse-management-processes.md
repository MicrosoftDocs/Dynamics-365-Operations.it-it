---
title: Migrare la gestione di prodotti e magazzino da AX 2012 a Finance and Operations
description: Questo argomento fornisce una panoramica delle opzioni di migrazione della gestione di prodotti e magazzino.
author: perlynne
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventLocationWHSProcessEnablement, WHSLocationProfile, InventTableStorageDimensionGroupChange, InventUpdateBlockedItem, WHSParameters, WHSReservationHierarchy, WHSUOMSeqGroupTable
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 1714054
ms.assetid: 79a1a3b9-3a36-4162-8839-ec39b5e26602
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 72d4ff5e1311005d3bf43a13e28208cd9b3d1457
ms.openlocfilehash: 4d94a5b2cc0e9ea144fbefc97cc27a2920016358
ms.contentlocale: it-it
ms.lasthandoff: 03/08/2018

---

# <a name="migrate-products-and-warehouse-management-from-ax-2012-to-finance-and-operations"></a>Migrare la gestione di prodotti e magazzino da AX 2012 a Finance and Operations

[!include[banner](../includes/banner.md)]

Questo argomento fornisce una panoramica delle opzioni di migrazione della gestione di prodotti e magazzino in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.

<a name="introduction"></a>Introduzione
------------

Durante l'aggiornamento a Finance and Operations, i prodotti vengono bloccati se sono associati a un gruppo di dimensioni di immagazzinamento che ha impostazioni che non corrispondono ai requisiti per le impostazioni di un gruppo di dimensioni di immagazzinamento in Finance and Operations. Tuttavia, dopo l'aggiornamento, è possibile utilizzare un set di opzioni di migrazione nel processo di **Modifica del gruppo di dimensioni di immagazzinamento per articoli** per sbloccare i prodotti bloccati durante l'aggiornamento. È quindi possibile elaborare le transazioni per quei prodotti. Alcuni degli articoli potrebbero essere già associati a gruppi di dimensioni di immagazzinamento laddove le dimensioni di immagazzinamento Sito, Magazzino e Ubicazione sono attive e monitorate fisicamente. In questo caso, è possibile utilizzare il processo di **Modifica del gruppo di dimensioni di immagazzinamento per articoli** per consentire l'utilizzo di quegli articoli nei processi di gestione del magazzino. Questa funzionalità è utile se si desidera utilizzare la funzionalità di gestione magazzino per gli articoli esistenti.

## <a name="upgrading-to-finance-and-operations-when-ax-2012-r3-wmsii-is-used"></a>Aggiornamento a Finance and Operations, quando si utilizza il modulo WMSII di AX 2012 R3
Finance and Operations non supporta più il modulo legacy **WMSII** di Microsoft Dynamics AX 2012. In alternativa, è possibile utilizzare il nuovo modulo **Gestione magazzino**. Nelle versioni precedenti, le dimensioni inventariali ID pallet e Ubicazione possono essere selezionate per le scorte finanziarie. Tuttavia, nell'ambito del processo di aggiornamento, la dimensione inventariale ID pallet non può più essere attivata per l'inventario finanziario. Tutti i prodotti associati a un gruppo di dimensioni di immagazzinamento che utilizza la dimensione inventariale ID pallet verranno bloccati e non verranno elaborati.

### <a name="enabling-items-in-finance-and-operations"></a>Attivazione di articoli in Finance and Operations

In Finance and Operations, gli articoli che vengono utilizzati nell'ambito dei processi di gestione magazzino devono essere associati a un gruppo di dimensioni di immagazzinamento in cui il parametro **Usa processi di gestione magazzino** è selezionato. Quando questa impostazione è selezionata, le dimensioni inventariali Sito, Magazzino, Stato inventario, Ubicazione e Targa diventano attive. È possibile modificare a questo tipo di gruppo di dimensioni di immagazzinamento solo per gli articoli che sono già associati a gruppi di dimensioni di immagazzinamento in cui la dimensione inventariale Ubicazione è attiva.

### <a name="items-that-are-blocked-for-inventory-updates"></a>Articoli che sono bloccati per aggiornamenti di inventario

Per visualizzare l'elenco di prodotti rilasciati che sono stati bloccati durante l'aggiornamento e che non possono essere elaborati, fare clic su **Gestione inventario** &gt; **Impostazioni** &gt; **Magazzino** &gt; **Articoli bloccati per gli aggiornamenti di inventario**.

### <a name="reapplying-blocked-products"></a>Riapplicazione di prodotti bloccati

Per sbloccare i prodotti che sono stati bloccati durante l'aggiornamento, è necessario selezionare un nuovo gruppo di dimensioni di immagazzinamento per i prodotti. Tenere presente che è possibile modificare il gruppo di dimensioni di immagazzinamento anche se sono presenti transazioni di magazzino aperte. Per utilizzare gli articoli che sono stati bloccati durante l'aggiornamento, sono disponibili due opzioni:

-   Modificare il gruppo di dimensioni di immagazzinamento per l'articolo in un gruppo di dimensioni di immagazzinamento che utilizza solo dimensioni inventariali Sito, Magazzino e Ubicazione. A seguito di questa modifica, la dimensione inventariale ID pallet non viene più utilizzata.
-   Modificare il gruppo di dimensioni di immagazzinamento per l'articolo in un gruppo di dimensioni di immagazzinamento che utilizza i processi di gestione del magazzino. A seguito di questa modifica, la dimensione inventariale Targa viene ora utilizzata.

### <a name="migration-processes"></a>Processi di migrazione

In Finance and Operations, il tracciamento degli articoli fa parte dei processi di gestione del magazzino. Per questi processi, tutti i magazzini e le relative ubicazioni devono essere associati a un profilo di ubicazione. Concettualmente, se si desidera utilizzare i processi di gestione del magazzino, è necessario gestire due processi:

-   I magazzini esistenti devono essere abilitati per l'utilizzo dei processi di gestione del magazzino.
-   I prodotti rilasciati esistenti devono essere associati a un nuovo gruppo di dimensioni di immagazzinamento che utilizza processi di gestione del magazzino.

Se i gruppi di dimensioni di immagazzinamento di origine utilizzano la dimensione inventariale ID pallet, le ubicazioni degli inventari esistenti che hanno utilizzato la dimensione inventariale ID pallet devono essere associate a un profilo di ubicazione in cui il parametro **Usa rilevamento targa** è selezionato. Se i magazzini esistenti non devono essere abilitati per l'utilizzo dei processi di gestione magazzino, è possibile modificare i gruppi di dimensioni di immagazzinamento dell'inventario esistente in gruppi che gestiscono solo le dimensioni inventariali Sito, Magazzino e Ubicazione.

### <a name="using-the-warehouse-management-processes"></a>Utilizzo dei processi di gestione del magazzino

Prima di poter utilizzare i prodotti rilasciati nel modulo **Gestione magazzino**, i prodotti devono utilizzare un gruppo di dimensioni di immagazzinamento in cui il parametro **Usa processi di gestione magazzino** è selezionato.

#### <a name="enable-warehouses-to-use-warehouse-management-processes"></a>Consentire ai magazzini di utilizzare i processi di gestione magazzino

1.  Creare almeno un nuovo profilo di ubicazione.
2.  Fare clic su **Gestione magazzino** &gt; **Impostazioni** &gt; **Consenti processi di gestione magazzino** &gt; **Consenti impostazione magazzino**.
3.  Nella pagina **Consenti impostazione magazzino** aggiungere i magazzini che devono essere attivati. È possibile completare questo passaggio direttamente nella pagina o tramite l'integrazione con Microsoft Office.
4.  Assegnare un profilo di ubicazione a tutte le ubicazioni. È possibile completare facilmente questo passaggio utilizzando l'integrazione con Microsoft Office o direttamente dalla pagina. È possibile esportare e importare i dati o utilizzare l'elaborazione delle entità di dati in [Gestione dati](../../dev-itpro/data-entities/data-entities.md).
5.  Convalidare le modifiche. Durante il processo di convalida si verificano alcune convalide di integrità dei dati. Nell'ambito di un processo di aggiornamento di dimensioni più ampie, è possibile che si debba correggere eventuali problemi nell'implementazione di origine. In questo caso sarà necessario eseguire un ulteriore aggiornamento dei dati.
6.  Elaborare le modifiche.

#### <a name="change-the-storage-dimension-group-for-items-so-that-it-uses-warehouse-management-processes"></a>Modificare il gruppo di dimensioni di immagazzinamento per gli articoli in modo che il gruppo utilizzi i processi di gestione magazzino

1.  Creare un nuovo valore **Stato inventario** e assegnarlo come valore **ID stato inventario predefinito** nelle impostazioni **Parametri di gestione magazzino**.
2.  Creare un nuovo gruppo di dimensioni di immagazzinamento in cui il parametro **Usa processi di gestione magazzino** è selezionato.
3.  Nella pagina **Gerarchia prenotazioni** definire una nuova gerarchia di prenotazioni in base ai gruppi di dimensioni di tracciabilità e di immagazzinamento dell'articolo.
4.  Creare uno o più gruppi di sequenze di unità che include almeno le stesse unità utilizzate per le unità di magazzino degli articoli.
5.  Fare clic su **Gestione magazzino** &gt; **Impostazioni** &gt; **Consenti processi di gestione magazzino** &gt; **Modifica gruppo di dimensioni di immagazzinamento per articoli**.
6.  Nella pagina **Modifica gruppo di dimensioni di immagazzinamento per articoli** aggiungere i numeri articolo, i gruppi di dimensioni di immagazzinamento e i gruppi di sequenze di unità. È possibile completare questo passaggio direttamente nella pagina, utilizzando l'integrazione di Microsoft Office oppure il processo delle entità di dati in [Gestione dati](../../dev-itpro/data-entities/data-entities.md).
7.  Convalidare le modifiche. Durante il processo di convalida si verificano alcune convalide di integrità dei dati. Nell'ambito di un processo di aggiornamento di dimensioni più ampie, è possibile che si debba correggere eventuali problemi nell'implementazione di origine. In questo caso sarà necessario eseguire un ulteriore aggiornamento dei dati.
8.  Elaborare le modifiche. L'aggiornamento di tutte le dimensioni inventariali può richiedere qualche minuto. È possibile monitorare lo stato utilizzando le attività dei processi batch.



