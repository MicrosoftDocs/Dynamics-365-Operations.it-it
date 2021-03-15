---
title: Parametri di produzione di Esecuzione produzione
description: Questo argomento fornisce informazioni sulla configurazione dei parametri di produzione in Esecuzione produzione.
author: johanhoffmann
manager: tfehr
ms.date: 06/16/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgProdParameters
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 94c6d8f4086466b396524faeed5753da1a76d17a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "5001576"
---
# <a name="production-parameters-in-manufacturing-execution"></a>Parametri di produzione di Esecuzione produzione

[!include [banner](../includes/banner.md)]

Questo argomento fornisce informazioni sulla configurazione dei parametri di produzione in Esecuzione produzione.

Il modulo **Esecuzione produzione** è destinato principalmente all'utilizzo da parte di società di produzione. Il modulo può essere utilizzato per registrare il consumo per ore e per articoli nei processi o progetti di produzione. Prima di iniziare a utilizzare il modulo Esecuzione produzione per la registrazione di processi, è necessario impostare vari parametri di produzione che definiscano come e quando le registrazioni vengono inviate durante il processo di produzione. Le impostazioni dei parametri di produzione influiscono sulla gestione del magazzino e della produzione e sul calcolo dei costi.

Prima che i lavoratori inizino ad effettuare registrazioni per i processi di produzione, è consigliabile esaminare attentamente tutte le impostazioni della pagina **Parametri di produzione**. Fare clic su **Controllo produzione** &gt; **Imposta** &gt; **Esecuzione produzione** &gt; **Impostazioni predefinite ordini di produzione**. Se l'azienda utilizza la funzionalità multisito, è possibile impostare parametri di produzione diversi in base a ciascun sito. I parametri per l'integrazione con il modulo **Produzione** vengono impostati nelle schede seguenti nella pagina **Parametri di produzione**:

- **Generale**: impostazioni dei parametri generali per i processi di produzione in Esecuzione produzione.
- **Inizio**: parametri che vengono utilizzati quando vengono avviate le operazioni di produzione.
- **Operazioni**: parametri che vengono applicati alle operazioni di produzione e al riscontro sulle operazioni durante il processo di produzione.
- **Dichiarazione di finito**: parametri che vengono utilizzati quando gli articoli vengono dichiarati finiti nell'ultima operazione dell'ordine di produzione.
- **Convalida quantità**: parametri utilizzati per la convalida delle quantità iniziali e di riscontro negli ordini di produzione.

## <a name="types-of-production-jobs"></a>Tipi di processi di produzione
Nella scheda **Operazioni** selezionare i tipi di processi di produzione che richiedono la registrazione nella pagina **Registrazione processi**.

I lavoratori in genere eseguono le registrazioni dei processi di impostazione ed elaborazione. Se viene applicata la programmazione dei processi, tuttavia, è possibile selezionare altri tipi di processo, ad esempio processi di trasporto, per i quali i lavoratori dovranno effettuare le registrazioni durante l'elaborazione degli ordini di produzione. Ad esempio, è possibile richiedere le registrazioni dei processi di trasporto.

> [!IMPORTANT]
> Verificare che siano selezionati tutti i tipi di processi pertinenti. In caso contrario, i processi potrebbero non essere disponibili per la registrazione nella pagina **Registrazione processi**. Le opzioni selezionate devono corrispondere alle selezioni nella colonna **Gestione processo** della scheda **Impostazione** della pagina **Gruppi di cicli di lavorazione** (**Controllo produzione** &gt; **Impostazione** &gt; **Cicli di lavorazione** &gt; **Gruppi di cicli di lavorazione**).

Se per un tipo di processo specifico nel gruppo di cicli di lavorazione è selezionata l'opzione **Gestione processo**, questo tipo di processo verrà dichiarato finito nell'ordine di produzione quando il processo viene dichiarato finito in Esecuzione produzione. Quando tutti i tipi di processo per i quali è selezionata l'opzione **Gestione processo** sono stati dichiarati come finiti per un'operazione, l'operazione stessa verrà dichiarata finita anche in Esecuzione produzione.

> [!NOTE]
> Per alcuni tipi di processi la dichiarazione può essere eseguita manualmente tramite giornali di registrazione produzione. In questo caso, selezionare **Gestione processo** per il tipo di processo, ma non selezionare il tipo di processo per la registrazione nella scheda **Operazioni** della pagina **Parametri di produzione** in Esecuzione produzione.

## <a name="bom-consumption-and-picking-list-journals"></a>Giornali di registrazione del consumo DBA e delle distinte di prelievo
Un'impostazione coerente per il consumo della distinta base (BOM) è importante, poiché assicura un'efficiente gestione delle scorte. Se i parametri di consumo DBA, ad esempio, non sono impostati correttamente in Esecuzione produzione, potrebbero risultare detrazioni doppie, od omesse, di materiali dalle scorte.

Nella pagina **Parametri di produzione**, il consumo DBA automatico viene impostato in tre fasi:

- All'inizio della produzione. Impostare questa fase nella scheda **Inizio**.
- Durante il processo di produzione, quando un'operazione viene completata. Impostare questa fase nella scheda **Operazioni**.
- Quando un ordine di produzione viene dichiarato come finito. Impostare questa fase nella scheda **Dichiarazione di finito**.

Per ciascuna fase, il campo **Consumo DBA automatico** consente di selezionare uno dei tre metodi per il prelievo di articoli per un ordine di produzione:

- **Principio di registrazione del consumo di materiali**: questa opzione viene utilizzata insieme a un'altra opzione definita nella DBA del modulo **Produzione**. Fare clic su **Controllo produzione** &gt; **Comune** &gt; **Ordini di produzione** &gt; **Tutti gli ordini di produzione**. Nella pagina **Tutti gli ordini di produzione**, selezionare un ordine di produzione dall'elenco, quindi fare clic su **DBA** nel riquadro azioni. Nella pagina **DBA** della scheda **Impostazione**, nel campo **Principio di registrazione del consumo di materiali**, selezionare una delle seguenti opzioni:

  - **Inizio**
  - **Fine**
  - **Manuale**
  - Vuoto (nessuna opzione selezionata).
  - **Disponibile in ubicazione**

    In Esecuzione produzione, se l'opzione **Principio di registrazione del consumo di materiali** è selezionata nel campo **Consumo DBA automatico** della scheda **Inizio**, tutti i materiali che sono impostati su **Inizio** nella DBA vengono detratti dalle scorte quando l'operazione viene avviata. L'opzione **Disponibile in ubicazione** viene utilizzata per i prodotti abilitati per i processi avanzati di magazzino. Se si seleziona il principio di registrazione del consumo di materiali, il materiale verrà registrato come consumato quando il lavoro di magazzino per il prelievo di materie viene completato. Il materiale viene registrato come consumato anche quando una riga DBA che utilizza il principio di registrazione del consumo di materiali viene rilasciata al magazzino e il materiale è disponibile nell'ubicazione entrata produzione.

    > [!NOTE]
    > Se il campo **Principio di registrazione del consumo di materiali** è impostato nella scheda **Inizio** in Esecuzione produzione, è necessario selezionare lo stesso principio nella scheda **Operazioni** o **Dichiarazione di finito**. Questo requisito consente di per garantire che i materiali vengano detratti dalle scorte sulle DBA che utilizzano **Fine** come principio di registrazione del consumo di materiali sull'ordine di produzione. Se lo stesso principio di registrazione del consumo di materiali non è selezionato nella scheda **Operazioni** o **Dichiarazione di finito**, i materiali potrebbero essere detratti dalle scorte due volte.

- **Sempre**: se si seleziona questa opzione in una determinata fase, i materiali verranno sempre dedotti dalle scorte in quella fase. Ad esempio, i materiali per la produzione vengono dedotti quando viene avviato l'ordine di produzione. Questa impostazione richiede la selezione di **Mai** nelle schede **Operazioni** e **Dichiarazione di finito**. Questo requisito consente di evitare che i materiali vengano detratti due volte dalle scorte.
- **Mai**: se si seleziona questa opzione per una fase, nessun consumo DBA viene eseguito in tale fase. Se, ad esempio, **Mai** è selezionato per tutte e tre le schede (**Inizio**, **Operazioni** e **Dichiarazione di finito**), i materiali devono essere detratti manualmente dalle scorte.

> [!IMPORTANT]
> Valutare attentamente l'impostazione dei parametri di produzione e assicurarsi che i parametri selezionati nelle varie schede della pagina **Parametri di produzione** non siano in conflitto tra loro.

Negli esempi riportati di seguito vengono illustrate alcune impostazioni di parametri che supportano diversi principi di consumo DBA. I parametri vengono impostati nella pagina **Parametri di produzione** in Esecuzione produzione.

### <a name="example-1-backflushing-on-operations"></a>Esempio 1: backflush nelle operazioni

Utilizzare le seguenti impostazioni se devono essere generati giornali di registrazione distinte di prelievo con il consumo di articoli DBA quando gli articoli vengono dichiarati finiti in un'operazione.

| Scheda                | Campo                          | Impostazione                             |
|--------------------|--------------------------------|-------------------------------------|
| Avvio              | Aggiorna attivazione           | **Stato** o **Stato + quantità** |
| Avvio              | Consumo DBA automatico      | **Mai**                           |
| Operations         | Consumo DBA automatico      | **Sempre**                          |
| Dichiarazione di finito | Consumo DBA automatico      | **Mai**                           |
| Dichiarazione di finito | Aggiorna report dichiarazione di finito in linea | **Stato + quantità**               |

### <a name="example-2-backflushing-on-production"></a>Esempio 2: backflush nella produzione

Utilizzare le seguenti impostazioni se devono essere generati giornali di registrazione distinte di prelievo con il consumo di articoli DBA quando gli articoli vengono dichiarati finiti nell'ordine di produzione.

| Scheda                | Campo                          | Impostazione                             |
|--------------------|--------------------------------|-------------------------------------|
| Avvio              | Aggiorna attivazione           | **Stato** o **Stato + quantità** |
| Avvio              | Consumo DBA automatico      | **Mai**                           |
| Operations         | Consumo DBA automatico      | **Mai**                           |
| Dichiarazione di finito | Consumo DBA automatico      | **Sempre**                          |
| Dichiarazione di finito | Aggiorna report dichiarazione di finito in linea | **Stato + quantità**               |

### <a name="example-3-flushing-principle"></a>Esempio 3: principio di registrazione del consumo di materiali

Utilizzare le seguenti impostazioni se devono essere generati giornali di registrazione distinte di prelievo con il consumo di articoli DBA in base all'impostazione del principio di registrazione del consumo di materiali impostato per gli articoli DBA.

| Scheda                | Campo                          | Impostazione                |
|--------------------|--------------------------------|------------------------|
| Avvio              | Aggiorna attivazione           | **Stato + quantità**  |
| Avvio              | Consumo DBA automatico      | **Principio di registrazione del consumo di materiali** |
| Operations         | Consumo DBA automatico      | **Principio di registrazione del consumo di materiali** |
| Dichiarazione di finito | Consumo DBA automatico      | **Mai**              |
| Dichiarazione di finito | Aggiorna report dichiarazione di finito in linea | **Stato + quantità**  |

### <a name="example-4-deduction-of-materials-during-startup-of-a-production-order"></a>Esempio 4: detrazione dei materiali durante l'avvio di un ordine di produzione

Utilizzare le seguenti impostazioni se devono essere generati giornali di registrazione distinte di prelievo con il consumo di articoli DBA quando viene avviata la produzione.

| Scheda                | Campo                          | Impostazione                             |
|--------------------|--------------------------------|-------------------------------------|
| Avvio              | Aggiorna attivazione           | **Stato + quantità**               |
| Avvio              | Consumo DBA automatico      | **Sempre**                          |
| Operations         | Consumo DBA automatico      | **Mai**                           |
| Dichiarazione di finito | Consumo DBA automatico      | **Mai**                           |
| Dichiarazione di finito | Aggiorna report dichiarazione di finito in linea | **Stato** o **Stato + quantità** |

In base alle selezioni descritte in precedenza in questa sezione, è possibile registrare giornali di registrazione distinte di prelievo in diverse fasi del processo relativo all'ordine di produzione.

- Quando viene avviata un'operazione
- Quando il riscontro sulla quantità è dichiarato in un'operazione
- Quando gli articoli sono dichiarati finiti nell'ordine di produzione

### <a name="example-5-manual-bom-consumption"></a>Esempio 5: consumo DBA manuale

Le impostazioni seguenti possono essere utilizzate se i materiali devono essere sempre detratti dalle scorte manualmente. In questo caso, i giornali di registrazione distinte di prelievo non vengono registrati.


|        Scheda         |             Campo              |         Impostazione         |
|--------------------|--------------------------------|-------------------------|
|       Avvio        |      Aggiorna attivazione      | <strong>Stato</strong> |
|       Avvio        |   Consumo DBA automatico    | <strong>Mai</strong>  |
|     Operations     |   Consumo DBA automatico    | <strong>Mai</strong>  |
| Dichiarazione di finito |   Consumo DBA automatico    | <strong>Mai</strong>  |
| Dichiarazione di finito | Aggiorna report dichiarazione di finito in linea | <strong>Stato</strong> |



[!INCLUDE[footer-include](../../includes/footer-banner.md)]