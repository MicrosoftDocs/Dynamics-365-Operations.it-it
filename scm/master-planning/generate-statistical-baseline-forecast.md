---
title: Generare una previsione di base statistica
description: In questo articolo vengono fornite informazioni sui parametri e i filtri utilizzati nel calcolo di previsione della domanda.
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 72683
ms.assetid: 42190463-2a64-4f63-b653-10cac3df0692
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: c0c918b94fe96d123bb6c25c42fe168a026cd8a9
ms.lasthandoff: 03/31/2017


---

# <a name="generate-a-statistical-baseline-forecast"></a>Generare una previsione di base statistica

In questo articolo vengono fornite informazioni sui parametri e i filtri utilizzati nel calcolo di previsione della domanda. 

Quando si crea una previsione di base, è necessario specificare i parametri e i filtri utilizzati nel calcolo. Ad esempio, è possibile creare una previsione di base che stima la richiesta in base ai dati della transazione relativi all'anno precedente per una società specifica, per il mese successivo e per un gruppo di articoli selezionato. 

Per generare una previsione della domanda, passare ** la previsione &gt; della domanda di previsioni &gt; di pianificazione &gt; generale vengono generati la previsione di base statistica **. 

L'intervallo di previsione può essere selezionato al momento della generazione della previsione. I valori disponibili sono: Giorno, Settimana e Mese. 

Il numero di intervalli per la generazione della previsione viene impostato nel campo** Orizzonte previsione**. 

Se la strategia di previsione è impostata su **Copia domanda storica**, la fine dell'orizzonte storico viene ignorata. Il sistema copia il numero di intervalli specificato in ** orizzonte di previsione ** sistema alla richiesta di previsione, a partire dalla data impostata ** alla data ** nel campo in ** orizzonte storico **. Copiando la domanda storica da una determinata data in avanti, i responsabili di pianificazione della produzione possono creare il piano per il trimestre successivo in due modi:

-   Copiando la domanda dello stesso trimestre dell'anno precedente.
-   Copiando la domanda del trimestre precedente.

Per evitare confusione nei piani di produzione, è possibile bloccare un certo numero di intervalli di previsione. Questo numero viene impostato nel campo **Intervallo temporale blocco**. Nella pagina **Previsione della domanda modificata **le celle corrispondenti agli intervalli bloccati vengono disabilitate, per fornire un'indicazione visiva che i valori non devono essere modificati. 

La data di inizio per la previsione della domanda di base non deve corrispondere alla data corrente o a una data in futuro. Per impostare una data di inizio diversa, utilizzare il campo **Data di inizio previsione di base - Da**. Ad esempio, a giugno, gli utenti possono generare una previsione per l'anno successivo. Poiché gli intervalli di previsione tra la fine della richiesta storica e l'inizio di base mancano, le previsioni potrebbero non essere precise. Se si utilizza Microsoft Dynamics 365 per l'utilizzo di previsione della domanda operazioni, sono disponibili quattro i risultati colmare in intervalli mancanti. È possibile scegliere il metodo che si desidera impostando il parametro MANCANTE di SOSTITUZIONE\_VALORE\_** parametri di previsione della domanda ** nella pagina. 

** Il riferimento previste la data di inizio ** - ** alla data ** campo deve essere impostato sull'inizio di un intervallo di previsione, ad esempio, negli Stati Uniti, domenica se l'intervallo di previsione è la settimana. Il sistema regola automaticamente ** data di inizio di previsione di riferimento ** - ** alla data ** sistema in modo che corrisponda all'inizio di un intervallo di previsione. 

** Il riferimento previste la data di inizio ** - ** alla data ** campo può essere impostato su una data nel passato. Ovvero è possibile generare una previsione della domanda nel passato. Questa opzione è utile, poiché consente agli utenti di adattare i parametri del servizio di previsione in modo che la previsione statistica generata nel passato corrisponda alla richiesta storica effettiva. Gli utenti possono quindi continuare a utilizzare le impostazioni dei parametri per generare una previsione di base statistica per il futuro. 

Le rettifiche manuali effettuate nelle iterazioni precedenti di previsione della domanda possono essere applicati automaticamente alla nuova previsione di base se è selezionata la casella di controllo **Trasferisci correzioni manuali alla previsione della domanda**. Se la casella di controllo è deselezionata, le correzioni manuali non vengono aggiunte alla previsione di base, ma non verranno eliminate. Le correzioni manuali effettuate in una previsione possono essere eliminate solo durante l'importazione della previsione, deselezionando la casella di controllo **Salva le rettifiche manuali apportate alla previsione della domanda di base**. Le correzioni manuali vengono salvate nella fase di autorizzazione. Di conseguenza, se un utente verranno apportate rettifiche manuali alla previsione, ma non consente la previsione a Dynamics 365 per le operazioni, le modifiche vengono persi. Per ulteriori informazioni sulle rettifiche manuali e come vengono eseguiti, vedere il autorizzando [rettificato programmato authorize-adjusted-forecast.md] (). 

Una creazione di una previsione della domanda può avere un nome e dei commenti per facilitare gli utenti a identificare la previsione generata. Questi valori sono visibili nello storico della generazione di previsione nella pagina **Storico generazione previsione di base statistica**. 

Il gruppo di pianificazione interaziendale, le chiavi di allocazione articolo e altri filtri possono essere applicati quando si genera la previsione. Questi possono essere utilizzati per migliorare le prestazioni o per dividere i dati in blocchi gestibili. Tuttavia, si noti che una previsione della domanda non viene generata per i membri di qualsiasi chiave di allocazione articolo non associata a un gruppo di pianificazione interaziendale, anche se la chiave di allocazione articolo è selezionata nella query. 

**Suggerimento**: talvolta gli utenti potrebbero ricevere degli errori durante la generazione di una previsione della domanda o quando la generazione di previsione viene completata senza il registro della sessione. Questo può verificarsi a causa di dati rimanenti nella query precedentemente utilizzata per la generazione di previsione. Per risolvere questo problema, fare clic su **Seleziona** per aprire la pagina **Query**, fare clic su **Reimposta** e quindi rigenerare la previsione di base. 

Se la previsione non viene generata per un ampio set di articoli, ma, ad esempio, per un articolo o una chiave di allocazione articolo alla volta, per migliorare le prestazioni, è possibile selezionare ** modalità di risposta alla richiesta di l ** la casella di controllo ** pianificazione generale - sull'impostazione di previsione della domanda ** - ** parametri di previsione della domanda - apprendimento automatico azzurrato ** scheda.

<a name="see-also"></a>Vedere anche
--------

[Demand forecasting setup](demand-forecasting-setup.md)

[Making manual adjustments to the baseline forecast](manual-adjustments-baseline-forecast.md)

[Authorizing the adjusted forecast](authorize-adjusted-forecast.md)


