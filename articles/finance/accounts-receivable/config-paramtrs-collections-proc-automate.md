---
title: Configurare i parametri per l'automazione del processo di riscossione
description: Questo argomento descrive i parametri che influiscono sui processi di riscossione automatizzata e fornisce indicazioni per impostarli in modo che il processo automatizzato rifletta le intenzioni e le aspettative.
author: JodiChristiansen
ms.date: 08/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustomerCollectionManagerWorkspace
audience: Application User, IT Pro
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-08-26
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 3055e10375f1b0be936e3ed0344cdf33dc7bc7e9
ms.sourcegitcommit: 3f6cbf4fcbe0458b1515c98a1276b5d875c7eda7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2021
ms.locfileid: "7487076"
---
# <a name="configure-parameters-for-collection-process-automation"></a>Configurare i parametri per l'automazione del processo di riscossione

[!include [banner](../includes/banner.md)]

Questo argomento descrive i parametri che influiscono sui processi di riscossione automatizzata e fornisce indicazioni per impostarli in modo che il processo automatizzato rifletta le intenzioni e le aspettative. Per informazioni su come automatizzare i processi di riscossione, vedi [Automazione del processo di riscossione](collections-process-automate.md).

## <a name="general"></a>Generali
Inserisci un numero in **Percentuale di clienti per attività batch** per determinare il numero di attività batch per processo di automazione. Imposta **Invia lettere di sollecito automaticamente** su **Sì** quindi il tipo di azione lettera di sollecito pubblica la lettera durante l'automazione. Imposta **Crea attività per automazioni** su **Sì** per creare e chiudere attività per tipi di azione non attività per visualizzare tutti i passaggi automatizzati eseguiti su un account. Definisci il numero di giorni in cui la cronologia di riscossione è memorizzata in **Giorni per conservare la cronologia dell'automazione del processo di riscossione**. Quando una fattura raggiunge l'ultimo passaggio del processo di riscossione, non verrà utilizzata per creare futuri tipi di azioni di automazione del processo se **Escludi la fattura dopo aver attivato l'ultimo passaggio del processo** è impostato su **Sì**. La fattura più vecchia successiva determina il passaggio di automazione del processo successivo per garantire che le azioni di automazione del processo di riscossione continuino. 

## <a name="payment-predictions"></a>Previsioni di pagamento
A partire dalla versione 10.0.21, le previsioni di pagamento dei clienti, disponibili in Finance Insights, indicano se una fattura verrà pagata in tempo, in ritardo o molto in ritardo. Puoi configurare ciascuna di queste categorie in Finance Insights. Se si prevede che le fatture verranno pagate in ritardo, è importante avviare il processo di riscossione prima della scadenza della fattura. Tali previsioni possono essere utilizzate per creare attività di riscossione quando vengono eseguite le automazioni del processo di riscossione. Imposta **Abilita previsioni di pagamento** su **Sì** per utilizzare le previsioni di pagamento dei clienti per creare attività di riscossione in base alla probabilità che la fattura venga pagata in ritardo. 

Per ulteriori informazioni sulle previsioni di pagamento dei clienti e su Finance Insights, vedi [Previsioni di pagamento dei clienti](payment-insights-overview.md).

Quando viene eseguito il modello di previsione del pagamento del cliente, assegna una percentuale alla previsione della fattura pagata in tempo, in ritardo o molto in ritardo. Puoi utilizzare queste informazioni per avviare automaticamente le attività di riscossione utilizzando l'automazione del processo di riscossione nei casi in cui è previsto un pagamento ritardato. Puoi visualizzare queste percentuali nelle pagine **Previsioni di pagamento per cliente** o **Previsioni di pagamento per transazione** sotto **Credito e riscossioni > Riscossioni**. 

Se la previsione di pagamento media per una fattura del cliente è inferiore alla percentuale di benchmark, non viene creata alcuna attività. Se la previsione della fattura è maggiore o uguale alla percentuale di benchmark, viene creata una attività per cliente. Per **Previsione: in ritardo**, immetti la **Percentuale di benchmark** di quando l'automazione del processo di riscossione deve creare attività di riscossione. Questo è un valore aggregato sia per ritardo che per molto ritardo. Seleziona un **Modello di documento aziendale** da utilizzare per l'attività creata o creane uno nuovo. Questo identifica **Tipo**, **Scopo**, e **Giorni fino alla chiusura dell'attività**. Inserisci le **Note** che saranno la descrizione predefinita quando viene creata l'attività. Per **Previsione: molto in ritardo**, immetti la **Percentuale di benchmark** di quando l'automazione del processo di riscossione deve creare attività di riscossione per cliente che si prevede paghi molto in ritardo. Seleziona un **Modello di documento aziendale** da utilizzare per l'attività creata. Questo identifica **Tipo**, **Scopo**, e **Giorni fino alla chiusura dell'attività**. Inserisci le **Note** che saranno la descrizione predefinita quando viene creata l'attività. 

### <a name="example"></a>Esempio
Se la percentuale di benchmark del ritardo è impostata al 60%. Quando vengono eseguite le previsioni del pagamento del cliente per ogni fattura, il sistema assegna una percentuale alla previsione della fattura pagata in tempo, in ritardo o molto in ritardo. Se la previsione di pagamento che la fattura verrà pagata in ritardo è pari o inferiore al 59%, non verrà creata alcuna attività di riscossione per la fattura dal processo di riscossione automatizzato. Se la previsione di pagamento del cliente per una fattura è maggiore o uguale al 60%, viene creata un'attività di riscossione durante l'automazione del processo di riscossione. 

> [!NOTE]
> La previsione molto in ritardo viene valutata prima della previsione in ritardo perché molto in ritardo include fatture che si prevede vengano pagate in ritardo. Il processo di riscossione genera un'attività solo se la fattura rientra nei parametri di benchmark sia in ritardo che molto in ritardo. In tal caso, il sistema utilizza l'attività e il documento aziendale molto in ritardo perché viene data priorità a molto in ritardo. Eventuali altre azioni già generate non verranno generate una seconda volta.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
