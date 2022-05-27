---
title: Rivalutazione valuta estera - Banca
description: In questo argomento viene fornita una panoramica del processo di rivalutazione valuta estera della banca. Include informazioni su impostazione, esecuzione del processo, calcolo per il processo e storno delle transazioni di rivalutazione.
author: kweekley
ms.date: 05/16/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankCurrencyRevalHistory
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2019-03-08
ms.dyn365.ops.version: 10
ms.openlocfilehash: a8ce792fdc0c6b441deaead32db04ee0246becc9
ms.sourcegitcommit: 04e6c1c9400e1b582180cf3e0e4767434e736c26
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2022
ms.locfileid: "8711205"
---
# <a name="bank-foreign-currency-revaluation"></a>Rivalutazione valuta estera - Banca

[!include [banner](../includes/banner.md)]


In questo argomento viene fornita una panoramica del processo di rivalutazione valuta estera della banca. Descrive come impostare ed eseguire il processo e fornisce informazioni sul calcolo per il processo nonché come stornare le transazioni di rivalutazione, se lo storno è obbligatorio.

Nell'ambito di una fine periodo le convenzioni di contabilità richiedono che i saldi dei conti bancari in valuta estera vengano rivalutati utilizzando diversi tipi di tassi di cambio (corrente, storico, medio e così via). La funzionalità di rivalutazione valuta estera della banca può essere utilizzata per rivalutare uno o più conti bancari. La funzionalità è anche una funzionalità globale. Di conseguenza, da una singola pagina, è possibile rivalutare le banche per tutte le persone giuridiche a cui si ha accesso.

> [!NOTE]
> Quando si esegue il processo di rivalutazione, il saldo in ogni conto bancario registrato in una valuta estera verrà rivalutato. Le transazioni relative alla perdita o al profitto non realizzato create durante il processo di rivalutazione vengono generate dal sistema. È possibile che vengano create due transazioni, una per la valuta di contabilizzazione e una per la valuta di dichiarazione, se questa è pertinente. Ogni voce contabile verrà registrata nella perdita o nel profitto non realizzato e nel conto principale che viene rivalutato.

## <a name="prepare-to-run-foreign-currency-revaluation"></a>Preparare l'esecuzione della rivalutazione valuta estera

Prima di effettuare il processo di rivalutazione, è richiesta l'impostazione che segue.

- Nella pagina **Contabilità generale** specificare il tipo di tasso di cambio. Se un tipo di tasso di cambio non è definito nel conto principale, il tipo di tasso di cambio viene utilizzato durante la rivalutazione valuta estera.
- Nella pagina **Contabilità generale** specificare i profitti realizzati, le perdite realizzate, i profitti non realizzati e le perdite non realizzate per la rivalutazione valuta. I conti di profitti realizzati e perdite realizzate vengono utilizzati quando le transazioni contabilità fornitori e contabilità clienti vengono liquidate. I conti di profitti non realizzati e perdite non realizzate vengono utilizzati per rivalutare le transazioni aperte e i conti principali della contabilità generale.
- Nella pagina **Conti rivalutazione valuta** selezionare conti di rivalutazione valuta diversi per ogni valuta e società. Se non vengono definiti, vengono utilizzati i conti della pagina **Contabilità generale**.

## <a name="enable-foreign-currency-revaluation"></a>Abilitare la rivalutazione valuta estera

È necessario attivare la funzionalità di rivalutazione valuta estera della banca per poter elaborare le rivalutazioni valuta estera.

1. Andare a **Gestione cassa e banche \> Impostazioni \> Parametri di gestione cassa e banche**.
2. Nella scheda **Generale**, sotto **Rivalutazione valuta estera**, impostare l'opzione **Abilita rivalutazione della banca** su **Sì** per attivare la funzionalità per la persona giuridica corrente. 
3. Nella scheda **Sequenze numeriche**, aggiungere una sequenza numerica per la rivalutazione valuta estera.
4. Aggiornare il browser per visualizzare **Rivalutazione valuta estera** nella sezione **Attività periodiche** della pagina.

È necessario attivare la funzionalità per ogni persona giuridica che utilizzerà la rivalutazione valuta estera. Se si è assegnati al ruolo di amministratore di sistema o di responsabile delle funzionalità, è possibile eliminare questo passaggio abilitando la funzionalità denominata **Abilita rivalutazione della banca senza un parametro** nell'area di lavoro **Gestione funzionalità**.

> [!NOTE]
> Se la propria persona giuridica utilizza un codice paese russo, polacco o ungherese, è già possibile effettuare la rivalutazione valuta estera della banca. Non sarà possibile utilizzare la rivalutazione valuta estera utilizzata da altri paesi.

## <a name="process-foreign-currency-revaluation"></a>Elaborare una rivalutazione valuta estera

Dopo il completamento dell'impostazione, utilizzare la pagina **Rivalutazione valuta estera** in Gestione cassa e banche per rivalutare i saldi di uno o più conti bancari per tutte le persone giuridiche. È possibile eseguire il processo in tempo reale oppure programmarlo per l'esecuzione mediante un batch.

La pagina **Rivalutazione valuta estera** mostra lo storico di ogni processo di rivalutazione. Indica quando è stato eseguito il processo e i criteri definiti e fornisce un collegamento al giustificativo creato per la rivalutazione. Mostra inoltre se è stato eseguito lo storno di una rivalutazione precedente. Per eseguire il processo di rivalutazione, selezionare **Rivalutazione valuta estera** nel Riquadro azioni per aprire la finestra di dialogo **Rivalutazione valuta estera - Banca**.

Il campo **Data rivalutazione** definisce la date limite per il calcolo del saldo in valuta estera che verrà rivalutato. La somma di tutte le transazioni bancarie effettuate fino a tale data viene rivalutata.

Il campo **Data tasso di cambio** definisce la data del tasso di cambio che sarà utilizzato per rivalutare i saldi in valuta. Ad esempio, è possibile rivalutare i saldi al 31 gennaio ma utilizzare il tasso di cambio definito per il 1° febbraio.

Il processo di rivalutazione può essere eseguito per una o più persone giuridiche. La ricerca mostra solo le persone giuridiche a cui si ha accesso. Selezionare le persone giuridiche di cui si desidera selezionare i conti bancari idonei per la rivalutazione valuta estera. Tutti i conti bancari di quelle persone giuridiche verranno visualizzati nella griglia.

Impostare l'opzione **Visualizza anteprima prima della registrazione** su **Sì** se si desidera esaminare i risultati della rivalutazione prima di registrarla. La rivalutazione valuta estera contiene include un'anteprima che può essere registrata. Non è necessario eseguire nuovamente il processo di rivalutazione. È possibile esportare i risultati nell'anteprima in Microsoft Excel per mantenere uno storico di come sono stati calcolati gli importi. Non è possibile utilizzare l'elaborazione batch se si desidera visualizzare l'anteprima dei risultati della rivalutazione.

Selezionare **OK** per elaborare la rivalutazione valuta estera. Viene creato un record in per tenere traccia dello storico di ogni esecuzione. Un record separato viene creato per ogni persona giuridica e livello di registrazione.

## <a name="calculate-unrealized-gainloss"></a>Calcolare perdita o profitto non realizzato

In Gestione cassa e banche, la valuta della banca viene considerata come la valuta di base e non viene rivalutata. Il saldo del conto bancario nella valuta di contabilizzazione viene rivalutato utilizzando i tassi di cambio tra la valuta della banca e la valuta di contabilizzazione nel cambio **Data tasso di cambio**. Il saldo del conto bancario nella valuta di contabilizzazione viene rivalutato utilizzando i tassi di cambio tra la valuta della banca e la valuta di contabilizzazione nel campo **Data tasso di cambio**.

Una transazione viene creata per la differenza tra il saldo del conto bancario e il nuovo saldo calcolato per la valuta di contabilizzazione. Un'altra transazione viene creata per la differenza tra il saldo del conto bancario e il nuovo saldo calcolato per la valuta di dichiarazione. Le voci per queste transazioni vengono contrassegnate come riconciliate. 

Nessuna voce verrà effettuata per la valuta di contabilizzazione se la valuta della banca corrisponde alla valuta di contabilizzazione. Analogamente, nessuna voce viene effettuata per la valuta di dichiarazione se la valuta della banca corrisponde alla valuta di dichiarazione.

La transazione di rivalutazione valuta estera viene inoltre suddivisa tra le dimensioni presenti nelle transazioni bancarie. La suddivisione si basa sul saldo di ciascuna dimensione. Ad esempio, il saldo bancario totale è 10.000, ma il saldo per la Business Unit 001 è 4.000, mentre il saldo per la Business Unit 002 è 6.000. In questo caso, il 40% dell'importo di rivalutazione viene registrato nel conto rivalutazione della Business Unit 001 e il 60% viene registrato nel conto rivalutazione della Business Unit 002. Se la struttura dei conti non include una Business Unit, l'intero importo viene registrato nel conto rivalutazione.

## <a name="reverse-foreign-currency-revaluation"></a>Storna rivalutazione valuta estera

Se si deve stornare la transazione di rivalutazione, selezionare il pulsante **Transazione di storno** nel Riquadro azione della pagina **Rivalutazione valuta estera**. Un nuovo record cronologico di rivalutazione valuta estera viene creato per mantenere un audit trail storico di quando la rivalutazione si è verificata o è stata stornata.

Per stornare più rivalutazioni, è necessario stornare dapprima quella più recente. Continuare quindi a stornare le rivalutazioni meno recenti in base alla data. È possibile quindi elaborare le nuove rivalutazioni per i periodi stornati.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
