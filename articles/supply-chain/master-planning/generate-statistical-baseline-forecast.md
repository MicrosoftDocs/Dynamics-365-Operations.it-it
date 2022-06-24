---
title: Generare una previsione di base statistica
description: In questo articolo vengono fornite informazioni sui parametri e i filtri utilizzati nel calcolo di previsione della domanda.
author: t-benebo
ms.date: 07/08/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72683
ms.assetid: 42190463-2a64-4f63-b653-10cac3df0692
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c45d763a1f3d199c91f3cf6181c22f4b8130fabc
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8844940"
---
# <a name="generate-a-statistical-baseline-forecast"></a>Generare una previsione di base statistica

[!include [banner](../includes/banner.md)]

In questo articolo vengono fornite informazioni sui parametri e i filtri utilizzati nel calcolo di previsione della domanda. 

Quando si crea una previsione di base, è necessario specificare i parametri e i filtri utilizzati nel calcolo. Ad esempio, è possibile creare una previsione di base che stima la richiesta in base ai dati della transazione relativi all'anno precedente per una società specifica, per il mese successivo e per un gruppo di articoli selezionato. 

Per generare una previsione di base statistica, andare a **Pianificazione generale &gt;  Previsioni &gt; Previsione della domanda &gt; Genera previsione di base statistica**. 

L'intervallo di previsione può essere selezionato al momento della generazione della previsione. I valori disponibili sono: Giorno, Settimana e Mese. 

Il numero di intervalli per la generazione della previsione viene impostato nel campo **Orizzonte previsione**. 

Se la strategia di previsione è impostata su **Copia domanda storica**, la fine dell'orizzonte storico viene ignorata. Il sistema copia il numero di intervalli specificato nel campo **Orizzonte di previsione** nella previsione della domanda, a partire dalla data impostata nel campo **Dal** in **Orizzonte storico**. Copiando la domanda storica da una determinata data in avanti, i responsabili di pianificazione della produzione possono creare il piano per il trimestre successivo in due modi:

-   Copiando la domanda dello stesso trimestre dell'anno precedente.
-   Copiando la domanda del trimestre precedente.

Per evitare confusione nei piani di produzione, è possibile bloccare un certo numero di intervalli di previsione. Questo numero viene impostato nel campo **Intervallo temporale blocco**. Nella pagina **Previsione della domanda modificata** le celle corrispondenti agli intervalli bloccati vengono disabilitate, per fornire un'indicazione visiva che i valori non devono essere modificati. 

La data di inizio per la previsione della domanda di base non deve corrispondere alla data corrente o a una data in futuro. Per impostare una data di inizio diversa, utilizzare il campo **Data di inizio previsione di base - Da**. Ad esempio, a giugno, gli utenti possono generare una previsione per l'anno successivo. Poiché gli intervalli di previsione tra la fine della richiesta storica e l'inizio di base mancano, le previsioni potrebbero non essere precise. Se si utilizza il servizio di previsione della domanda, sono disponibili quattro modalità in cui è possibile compilare le interruzioni mancanti. È possibile selezionare il metodo di registrazione desiderato impostando il parametro MISSING\_VALUE\_SUBSTITUTION nella pagina **Parametri di previsione della domanda**. 

> [!NOTE]
> La sostituzione dei valori mancanti viene eseguita solo per le interruzioni nei dati tra le date di inizio e fine dei dati storici. Non specificherà i dati prima o dopo l'ultimo punto dati fisico, in quanto funge solo da estrapolazione tra i punti dati esistenti effettivi. 

Il campo **Data di inizio previsione di base** - **Dal** deve essere impostato all'inizio di un intervallo di previsione, ad esempio negli Stati Uniti questo giorno corrisponderà alla domenica se l'intervallo di previsione è settimanale. Il sistema regola automaticamente il campo **Data di inizio previsione di base**  - **Dal** in modo che corrisponda all'inizio di un intervallo di previsione. 

Il campo **Data di inizio previsione di base** - **Dal** può essere impostato su una data nel passato. Ovvero è possibile generare una previsione della domanda nel passato. Questa opzione è utile, poiché consente agli utenti di modificare i parametri del servizio di previsione in modo che la previsione statistica generata nel passato corrisponda alla richiesta storica effettiva. Gli utenti possono quindi continuare a utilizzare le impostazioni dei parametri per generare una previsione di base statistica per il futuro. 

Le rettifiche manuali effettuate nelle iterazioni precedenti di previsione della domanda possono essere applicati automaticamente alla nuova previsione di base se è selezionata la casella di controllo **Trasferisci correzioni manuali alla previsione della domanda**. Se la casella di controllo è deselezionata, le correzioni manuali non vengono aggiunte alla previsione di base, ma non verranno eliminate. Le correzioni manuali effettuate in una previsione possono essere eliminate solo durante l'importazione della previsione, deselezionando la casella di controllo **Salva le rettifiche manuali apportate alla previsione della domanda di base**. Le correzioni manuali vengono salvate nella fase di autorizzazione. Di conseguenza, se un utente apporta rettifiche manuali alla previsione, ma non autorizza la previsione in Supply Chain Management, le modifiche vanno perse. Per ulteriori informazioni sulle rettifiche manuali e sul loro utilizzo, vedere [Autorizzare una previsione rettificata](authorize-adjusted-forecast.md). 

Una creazione di una previsione della domanda può avere un nome e dei commenti per facilitare gli utenti a identificare la previsione generata. Questi valori sono visibili nello storico della generazione di previsione nella pagina **Storico generazione previsione di base statistica**. 

Il gruppo di pianificazione interaziendale, le chiavi di allocazione articolo e altri filtri possono essere applicati quando si genera la previsione. Questi possono essere utilizzati per migliorare le prestazioni o per dividere i dati in blocchi gestibili. Tuttavia, si noti che una previsione della domanda non viene generata per i membri di qualsiasi chiave di allocazione articolo non associata a un gruppo di pianificazione interaziendale, anche se la chiave di allocazione articolo è selezionata nella query. 

> [!TIP]
> Talvolta gli utenti potrebbero ricevere degli errori durante la generazione di una previsione della domanda o quando la generazione di previsione viene completata senza il registro della sessione. Questo può verificarsi a causa di dati rimanenti nella query precedentemente utilizzata per la generazione di previsione. Per risolvere questo problema, fare clic su **Seleziona** per aprire la pagina **Query**, selezionare **Reimposta** e quindi rigenerare la previsione di base. 

Se la previsione non viene generata per un grande set di articoli, ma ad esempio, per un articolo o una chiave di allocazione articolo per volta, per ottenere migliori prestazioni, è possibile selezionare la casella di controllo **Utilizza modalità di richiesta-risposta** nella scheda **Pianificazione generale - Impostazioni - Previsione della domanda** -  **Parametri di previsione della domanda - Azure Machine Learning**.

> [!NOTE]
> Una previsione potenzialmente piana può essere dovuta ai dati storici che devono essere relativi a un intervallo storico più lungo (un minimo di 3 periodi di tempo per selezionare gli schemi, ad esempio 3 anni con previsione mensile). Per ottenere un migliore risultato, è possibile provare a modificare la granularità dell'intervallo di tempo o aumentare tale intervallo.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Impostazione della previsione della domanda](demand-forecasting-setup.md)

- [Implementare correzioni manuali nella previsione di base](manual-adjustments-baseline-forecast.md)

- [Autorizzare una previsione corretta](authorize-adjusted-forecast.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]