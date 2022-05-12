---
title: Mostrare i saldi ferie nell'interfaccia di esecuzione dell'area di produzione
description: Questo argomento fornisce uno scenario di esempio che mostra come configurare Microsoft Dynamics 365 Supply Chain Management in modo che utilizzi le statistiche sulle retribuzioni per fornire ai lavoratori una panoramica del saldo delle ferie per l'anno in corso.
author: johanhoffmann
ms.date: 04/22/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-04-22
ms.dyn365.ops.version: 10.0.XX
ms.openlocfilehash: a97858c72b0be50609cee552bd0635e2d68ea478
ms.sourcegitcommit: d715e44b92b84b1703f5915d15d403ccf17c6606
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645347"
---
# <a name="show-vacation-balances-in-the-production-floor-execution-interface"></a>Mostrare i saldi ferie nell'interfaccia di esecuzione dell'area di produzione

[!include [banner](../includes/banner.md)]

Questo argomento fornisce uno scenario di esempio che mostra come configurare Microsoft Dynamics 365 Supply Chain Management in modo che utilizzi le statistiche sulle retribuzioni per fornire a ogni lavoratore una panoramica del saldo delle ferie per l'anno in corso. I lavoratori potranno vedere il loro saldo ferie nella finestra di dialogo **Registrazioni quotidiane** nell'interfaccia di esecuzione dell'area di produzione.

Questo scenario utilizza la legge danese sulle ferie, in cui l'anno di ferie va dal 1 settembre al 31 agosto. In questo scenario, la tua azienda ha assunto un nuovo lavoratore e gli concederà un saldo di 10 giorni di ferie per il resto dell'anno di ferie corrente.

## <a name="turn-on-the-required-features"></a>Attivare le funzionalità richieste

Per eseguire questo scenario, è necessario abilitare la visualizzazione *"Registrazione quotidiane" per l'interfaccia di esecuzione dell'area di produzione* in [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md). Per informazioni su come abilitare questa e altre funzionalità per l'interfaccia di esecuzione dell'area di produzione, vedi [Configurare l'interfaccia di esecuzione dell'area di produzione](production-floor-execution-configure.md).

## <a name="make-sample-data-available"></a>Rendi disponibili i dati di esempio

Per elaborare lo scenario utilizzando i record e i valori di esempio specificati qui, devi utilizzare un sistema in cui sono installati i [dati dimostrativi](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) standard. È inoltre necessario selezionare la persona giuridica **USMF** prima di iniziare.

## <a name="create-a-new-pay-type"></a>Creare un nuovo tipo di retribuzione

Inizia creando un nuovo *tipo di retribuzione* che terrà traccia dei giorni di ferie guadagnati dai lavoratori (indicati anche come *saldo ferie*). In genere, i tipi di retribuzione vengono utilizzati per calcolare la retribuzione dei lavoratori. Tuttavia, il tipo di retribuzione che crei qui verrà utilizzato per calcolare un saldo.

1. Vai a **Orario e presenze \> Impostazioni \> Retribuzioni \> Tipi di retribuzione**.
1. Nel riquadro azioni seleziona **Nuova** per aggiungere una riga alla griglia.
1. Nella nuova riga, imposta i seguenti valori:

    - **Tipo di retribuzione:** *5151-1*
    - **Descrizione:** *Contatore per i giorni di ferie dei lavoratori*
    - **Includi nell'esportazione:** *No*

## <a name="update-the-pay-agreement"></a>Aggiornare l'accordo salariale

In questa sezione, modificherai un *accordo salariale* esistente aggiungendo il nuovo tipo di retribuzione e impostando le regole che definiscono il modo in cui il saldo ferie di ciascun lavoratore viene rettificato al momento della registrazione dei giorni di ferie.

1. Vai a **Orario e presenze \> Impostazioni \> Retribuzioni \> Accordi salariali**.
1. Seleziona l'accordo salariale in cui desideri impostare i criteri di ferie. Se stai lavorando con dati di esempio USMF standard, c'è un solo accordo salariale, *Man*.
1. Assicurati che l'accordo salariale selezionato sia valido per la data corrente. Se stai lavorando con dati di esempio USMF standard, il campo **Data di fine** dell'accordo salariale *Man* potrebbe essere impostato su una data passata. Modifica il valore in modo che sia un anno o due nel futuro, come richiesto.
1. Nel riquadro azioni fai clic su **Righe contratto**.
1. Sulla pagina **Righe accordo salariale** nella Scheda dettaglio **Panoramica**, imposta i seguenti valori sulla barra degli strumenti:

    - Nel primo elenco a discesa seleziona **Lunedì**.
    - Nel secondo elenco a discesa seleziona **Assenza**.

1. Nel riquadro azioni seleziona **Nuova** per aggiungere una riga alla griglia.
1. Sulla nuova riga, imposta il campo **Tipo di retribuzione** sul tipo di retribuzione che hai creato per questo scenario (*5151-1*). Lascia tutti gli altri campi impostati sui valori predefiniti.
1. Mentre la nuova riga è ancora selezionata, nella Scheda dettaglio **Generale**, imposta i seguenti valori:

    - **Codice assenza:** *Ferie*
    - **Utilizza quantità fissa:** *Sì*
    - **Costante:** *-1*

1. Nel riquadro azioni, seleziona **Copia giorno**.
1. Nella finestra di dialogo **Copia giorno** imposta i valori seguenti:

    - **Martedì**, **Mercoledì**, **Giovedì**, e **Venerdì:** *Sì*
    - **Sostituisci:** *Sì*
    - **Assenza:** *Sì*

1. Seleziona **OK**.

## <a name="create-a-payroll-statistic-group"></a>Creare un gruppo di statistiche retributive

I *Gruppi di statistiche retributive* vengono utilizzati per impostare statistiche per le registrazioni dei lavoratori durante un periodo. In questo scenario, utilizzerai un gruppo di statistiche sulle retribuzioni per calcolare il numero di giorni di ferie guadagnati dai lavoratori durante un periodo di ferie. In Danimarca, il periodo di ferie va dal 1 settembre al 31 agosto.

1. Vai a **Orario e presenze \> Impostazioni \> Retribuzioni \> Gruppi statistiche retributive**.
1. Nel riquadro azioni seleziona **Nuova** per aggiungere una riga alla griglia.
1. Nella nuova riga, imposta i seguenti valori:

    - **Gruppo statistiche retributive:** *FER*
    - **Descrizione:** *Saldo ferie*
    - **Trasferimento:** *No*

1. Mentre la nuova riga è ancora selezionata, seleziona **Impostazioni** nel riquadro azioni.
1. Nella pagina **Impostazioni**, nel riquadro azioni seleziona **Nuovo** per aggiungere una riga alla griglia.
1. Nella nuova riga, imposta il campo **Tipo di retribuzione** su *5151-1*.
1. Seleziona e tieni premuto (o fai clic con il pulsante destro del mouse) il campo campo **Codice periodo**, quindi seleziona **Visualizza dettagli**. Ora puoi impostare il codice periodo che assegnerai a questo campo in seguito.
1. Nella pagina **Tipi di periodo**, nel riquadro azioni seleziona **Nuovo** per aggiungere una riga alla griglia.
1. Nella nuova riga, imposta i seguenti valori:

    - **Tipi di periodo:** *VacYear*
    - **Descrizione:** *Anno ferie*
    - **Frequenza:** *Anni*

1. Mentre la nuova riga è ancora selezionata, seleziona **Genera periodi** nel riquadro azioni.
1. Nella finestra di dialogo **Genera periodi**, imposta i seguenti valori:

    - **Specifica data di inizio del periodo:** *1 settembre 2021*
    - **Durata del periodo:** *5*

1. Seleziona **OK**.
1. Chiudi la pagina **Tipi di periodo** per tornare alla pagina **Gruppi di statistiche retributive**.
1. Imposta il campo **Codice periodo** sul tipo di periodo che hai appena creato (*VacYear*).

## <a name="create-a-statistical-balance-setup"></a>Creare un'impostazione saldo statistico

In questa sezione creerai un'*impostazione saldo statistico* che è collegata al gruppo di statistiche retributive creato nella sezione precedente. Successivamente, collegherai questa impostazione saldo statistico alla visualizzazione **Registrazioni quotidiane** nell'interfaccia di esecuzione dell'area di produzione. La visualizzazione **Registrazioni quotidiane** sarà quindi in grado di mostrare i saldi ferie per il tipo di retribuzione assegnato al gruppo di statistiche retributive associato.

1. Vai a **Orario e presenze \> Impostazioni \> Retribuzioni \> Impostazione saldo statistico**.
1. Nel riquadro azioni seleziona **Nuova** per aggiungere una riga alla griglia.
1. Nella nuova riga, imposta i seguenti valori:

    - **Gruppo statistiche retributive:** *FER*
    - **Nome esterno:** *Saldo ferie*
    - **Flessibilità:** *No*

## <a name="create-a-manual-premium"></a>Creare un premio manuale

I *Premi manuali* sono in genere utilizzati per garantire ai lavoratori una retribuzione aggiuntiva per un lavoro extra. In questo scenario, creerai un premio manuale che puoi utilizzare per impostare il saldo ferie iniziale per ogni lavoratore.

1. Vai a **Orario e presenze \> Impostazioni \> Retribuzioni \> Premi manuali**.
1. Nel riquadro azioni selezionare **Nuovo** per aggiungere un record.
1. Nel nuovo record, imposta i seguenti valori:

    - **Premi:** *FER*
    - **Descrizione:** *Rettifiche al saldo ferie dei lavoratori*
    - **Tipo di retribuzione:** *5151-1*

## <a name="set-a-workers-initial-vacation-balance-and-adjust-it-by-one-day"></a>Impostare il saldo ferie iniziale di un lavoratore e rettificarlo di un giorno

Gli amministratori delle retribuzioni utilizzano la pagina **Approva** per rivedere e approvare le registrazioni giornaliere dei lavoratori. In questo scenario, assumerai il ruolo di amministratore in modo da poter impostare il saldo ferie iniziale per un lavoratore e registrare i giorni di ferie che il lavoratore prende.

1. Vai a **Orario e presenze \> Rivedi e approva \> Approva**.
1. Nella finestra di dialogo **Approva**, imposta i seguenti campi:

    - **Gruppo di approvazione** – Seleziona il gruppo di approvazione a cui appartieni. Se stai lavorando con dati di esempio USMF standard, c'è un solo gruppo di approvazione, *AdmMan*.
    - **Visualizza l'intero gruppo, 1 giorno** – Seleziona l'opzione, quindi imposta il campo sulla data corrente.

1. Seleziona **OK**.
1. La pagina **Approva** mostra un elenco di record che corrispondono ai tuoi criteri. Seleziona il lavoratore che desideri approvare. Se stai lavorando con dati di esempio USMF standard, seleziona il lavoratore *000496* (*Christina Portra*).
1. Concedi al lavoratore selezionato 10 giorni di ferie:

    1. Mentre il lavoratore è ancora selezionato, seleziona **Righe premio** nel riquadro azioni.
    1. Nella pagina **Righe premio**, nel riquadro azioni selezionare **Nuovo** per aggiungere una riga alla griglia.
    1. Nella nuova riga, imposta i seguenti valori:

        - **Premi:** *FER*
        - **Quantità:** *10*

    1. Chiudi la pagina **Righe premio**.

1. Sulla pagina **Approva** registra il fatto che il lavoratore ha usufruito di uno dei propri giorni di ferie alla data corrente:

    1. Mentre il lavoratore è ancora selzionato, nella parte inferiore della pagina, nella scheda **Panoramica**, seleziona **Nuovo** sulla barra degli strumenti per aggiungere una riga alla griglia.
    1. Nella nuova riga, imposta i seguenti valori:

        - **Tipo di registrazione giornale:** *Assenza*
        - **Riferimento:** *Ferie*

    1. Nella parte superiore della pagina, seleziona **Trasferisci** sulla barra degli strumenti per applicare il saldo ferie e calcolare la detrazione.

## <a name="configure-the-production-floor-execution-interface-so-that-it-includes-the-my-day-dialog-box"></a>Configurare l'interfaccia di esecuzione dell'area di produzione in modo che includa la finestra di dialogo Registrazioni quotidiane

In questa sezione, aggiungerai un pulsante **Registrazioni quotidiane** all'interfaccia di esecuzione dell'area di produzione. I lavoratori possono quindi utilizzare questo pulsante per aprire la finestra di dialogo **Registrazioni quotidiane**.

1. Andare a **Controllo produzione \> Imposta \> Esecuzione produzione \> Configura esecuzione area di produzione**.
1. Seleziona una configurazione, ad esempio *Predefinita*.
1. Nel riquadro azioni seleziona **Schede di progettazione**.
1. Sulla pagina **Schede di progettazione** nel riquadro elenco, seleziona *Tutti i processi* per visualizzare le impostazioni per quella scheda. Il campo **Visualizzazione principale** ora mostra un valore di *Tutti i lavori*.
1. Nel riquadro azioni, seleziona **Modifica**.
1. Sulla Scheda dettaglio **Barra degli strumenti secondaria**, nella colonna **Azioni disponibili** seleziona **Registrazioni quotidiane**. Quindi seleziona il pulsante freccia destra per spostarlo nella colonna **Azioni selezionate**.

## <a name="check-your-balance-in-the-production-floor-execution-interface"></a>Controllare il saldo nell'interfaccia di esecuzione dell'area di produzione

In questa sezione, accederai all'interfaccia di esecuzione dell'area di produzione come lavoratore di cui hai impostato il periodo di ferie in precedenza. Quindi aprirai la finestra di dialogo **Registrazioni quotidiane** per visualizzare il saldo delle ferie.

1. Vai in **Controllo produzione \> Impostazioni \> Esecuzione produzione \> Esecuzione area di produzione**.
1. Se ti viene chiesto di selezionare una configurazione, seleziona la configurazione che hai impostato in precedenza in questo scenario (*Predefinita*).
1. Accedi come l'utente configurato in precedenza in questo scenario. Se stai lavorando con dati di esempio USMF standard, dovresti essere in grado di accedere inserendo *123* nel campo **ID badge**. Questo ID badge corrisponde a Christina Portra.
1. Seleziona **Registrazioni quotidiane** sulla barra degli strumenti a sinistra.
1. Ispeziona la sezione **Saldi** della finestra di dialogo. Questa sezione ora mostra che hai un saldo di nove giorni di ferie.
