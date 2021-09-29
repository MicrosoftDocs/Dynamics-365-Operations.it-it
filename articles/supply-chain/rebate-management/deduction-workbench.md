---
title: Gestire le detrazioni usando il workbench detrazioni
description: In questo argomento viene descritto come utilizzare il workbench detrazioni per elaborare i pagamenti cliente che includano le detrazioni.
author: sherry-zheng
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: bf98529176fbed368708ea925f542a70f2936037
ms.sourcegitcommit: ecd4c148287892dcd45656f273401315adb2805e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2021
ms.locfileid: "7500404"
---
# <a name="manage-deductions-using-the-deduction-workbench"></a>Gestire le detrazioni usando il workbench detrazioni

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto come utilizzare il workbench detrazioni per elaborare i pagamenti cliente che includano le detrazioni.

A un cliente a cui è dovuto uno sconto può decidere di non aspettare un pagamento dello sconto. Invece, il cliente può inviare un pagamento che include una detrazione per l'importo dello sconto. Per gestire questo tipo di transazione, è possibile utilizzare il workbench detrazioni per far corrispondere le detrazioni alle transazioni di credito aperte, per suddividere, negare e ammortizzate le detrazioni.

> [!NOTE]
> Il workbench detrazioni ha fatto parte delle funzionalità di vendita e marketing in Microsoft Dynamics 365 Supply Chain Management per molto tempo. Tuttavia, ora è stato migliorato in modo che funzioni anche con il più recente modulo **Gestione degli sconti**. Questo argomento descrive come utilizzare sia le funzioni precedenti che le funzioni di gestione degli sconti del workbench detrazioni. Tuttavia, se non hai [attivato il modulo **Gestione degli sconti** per il tuo sistema](rebate-management-enable.md), alcune delle funzionalità descritte qui non saranno disponibili.

## <a name="prerequisites"></a>Prerequisiti

### <a name="set-up-the-old-deduction-management-system"></a>Impostare il vecchio sistema di gestione delle detrazioni

Puoi utilizzare il workbench detrazioni insieme alle vecchie funzionalità di gestione delle detrazioni di Supply Chain Management, anche se non usi il modulo **Gestione degli sconti**. Tuttavia, è necessario prima preparare il sistema come descritto in questa sezione.

Prima di poter utilizzare il workbench detrazioni devi completare le attività di impostazione che vengono descritte in [Impostare Gestione detrazione](/dynamicsax-2012/appuser-itpro/set-up-deduction-management). È inoltre possibile impostare un certo tipo di accordo sugli sconti impostati per il cliente: uno sconto cliente, come descritto in [Impostazione e gestione di sconti clienti](/dynamicsax-2012/appuser-itpro/setting-up-and-maintaining-customer-rebates) o uno sconto commerciale.

Se stai applicando una detrazione a uno sconto cliente, devi completare queste attività:

- [Imposta i tuoi sconti cliente](/dynamicsax-2012/appuser-itpro/setting-up-and-maintaining-customer-rebates).
- Approva ed elabora lo sconto, in modo da poter utilizzare il workbench detrazioni.

Se stai applicando una detrazione a uno sconto commerciale, devi completare queste attività:

- Imposta gli sconti nota di accredito.
- Applica gli sconti nota di accredito.

### <a name="configure-accounts-receivable-and-deductions"></a><a name="accounts-receivable-deductions"></a>Configurare la contabilità clienti e le detrazioni

Il sistema registra tutti gli eventi di detrazione in un giornale di registrazione attestazioni. Pertanto, il sistema deve includere un giornale che può essere utilizzato per questo scopo. Se non disponi già di un giornale di registrazione attestazioni, configuralo ora. Questo giornale è necessario per creare detrazioni direttamente nel workbench detrazioni, liquidazione cliente o pagina cliente.

Per impostare un nuovo giornale di registrazione attestazioni effettua le operazioni indicate di seguito.

1. Passare a **Contabilità generale \> Impostazione giornale di registrazione \> Nomi giornale di registrazione**.
1. Seleziona **Nuovo** e imposta i seguenti campi per il nome del nuovo giornale di registrazione:

    - **Nome** - Immetti un nome univoco per il giornale di registrazione attestazioni.
    - **Descrizione** – Immetti una breve descrizione del nuovo giornale di registrazione.
    - **Tipo di giornale di registrazione** – Seleziona *Giornaliero*.
    - **Serie giustificativi** – Assegna una sequenza numerica esistente. In alternativa, crea una nuova sequenza numerica con ambito aziendale e assegnala al nuovo nome del giornale.

1. Andare a **Contabilità clienti \> Impostazioni \> Parametri contabilità clienti**.
1. Nella scheda **Detrazioni** nella scheda dettaglio **Generale** imposta il campo **Nome giornale di registrazione attestazioni** sul nome del giornale appena creato.
1. Nella scheda dettaglio **Ordine di reso**, imposta i seguenti campi:

    - **Crea ordine di reso** – Imposta questa opzione per specificare cosa deve fare il sistema quando viene approvata un'attestazione basata sulla quantità:

        - *Sì* – Crea un ordine di reso.
        - *No* – Crea un ordine cliente negativo.

    - **Creazione senza fattura allegata** – Seleziona un valore per specificare cosa deve fare il sistema quando viene approvata un'attestazione basata sulla quantità ma non è allegata alcuna fattura:

        - *Accetta* – Crea un ordine di reso.
        - *Avviso* – Crea un ordine di reso, ma mostra il seguente messaggio di avviso: "L'attestazione non è allegata a una fattura".
        - *Errore* – Non crea un ordine di reso e mostra il seguente messaggio di errore: "L'attestazione non è allegata a una fattura. L'aggiornamento è stato annullato."

    - **Crea ordine di reso prima dell'approvazione della detrazione** – Imposta questa opzione su *Sì* se è possibile creare ordini di reso prima dell'approvazione dell'attestazione. Questa impostazione si applica solo alle richieste basate sulla quantità in cui l'opzione **Crea ordine di reso** è impostata su *Sì*.

### <a name="configure-general-ledger-parameters"></a>Configurare i parametri di contabilità generale

Quando il sistema crea un giornale di registrazione attestazioni per una nuova detrazione, crea anche due nuove transazioni cliente: una per compensare l'importo dell'attestazione con la fattura originale e una per registrare il debito di un cliente per l'importo dell'attestazione (perché l'attestazione non è stata ancora approvata). Pertanto, è necessario configurare il sistema in modo che un singolo giustificativo possa avere più righe cliente.

Per consentire a un singolo giustificativo di avere più righe cliente, segui questi passaggi.

1. Passa a **Contabilità generale \> Impostazione contabilità generale \> Parametri di contabilità generale**.
1. Nella scheda **Contabilità generale** nella scheda dettaglio **Generale** imposta l'opzione **Consenti più transazioni in un giustificativo** su *Sì*.
1. Se ricevi un messaggio di avviso, seleziona **Chiudi** per accettare la modifica.

### <a name="create-deduction-reasons"></a><a name="deduction-reasons"></a>Creare motivi di detrazione

Il sistema richiede che gli utenti specifichino un motivo per ogni detrazione che immettono direttamente in workbench detrazioni, liquidazione cliente o pagina cliente. Il motivo determina come viene gestita la detrazione una volta approvata.

1. Vai a **Vendite e marketing \> Sconti commerciali \> Detrazioni \> Motivi di detrazione**.
1. Seleziona **Nuovo** per aggiungere una riga alla griglia e quindi imposta i seguenti campi:

    - **Motivo attestazione** - Immetti un nome univoco per il motivo.
    - **Descrizione** - Immetti una descrizione del motivo per fornire ulteriori informazioni su come deve essere utilizzato.
    - **Base attestazione** – Seleziona una base di attestazione per il motivo di attestazione:

        - *Basato sul prezzo* – Crea una nota di credito a testo libero all'approvazione.
        - *Basato sulla quantità* – Crea un ordine cliente negativo o un ordine di reso all'approvazione.

    - **Codice motivo reso** – Seleziona un codice motivo di reso da applicare come **Codice motivo reso** per l'ordine di reso.
    - **Tipo**: seleziona un tipo di detrazione. Il valore **Compensazione detrazione** per il tipo selezionato verrà utilizzato per impostare il campo **Compensazione detrazione** quando viene creata una detrazione o un'attestazione. I tipi di detrazione sono definiti nella pagina **Tipi di detrazione** (**Vendite e marketing \> Sconti commerciali \> Detrazioni \> Tipi di detrazione**).
    - **Conto di registrazione attestazioni** – Questo campo è disponibile solo quando il campo **Base attestazione** è impostato su *Basato sul prezzo*. Quando viene approvato un'attestazione basata sul prezzo, il sistema assegna il conto CoGe selezionato qui come **Conto principale** per la bozza della nota di credito a testo libero.

### <a name="set-up-the-settle-approved-deductions-periodic-task"></a>Impostare l'attività periodica di liquidazione delle detrazioni approvate

Per le detrazioni create utilizzando il comando **Nuova detrazione** nel workbench detrazioni, nella liquidazione del cliente o nella pagina del cliente, è possibile impostare l'attività periodica *Liquida detrazioni approvate* per abbinare automaticamente detrazioni e crediti che hanno valori e importi **ID detrazione** corrispondenti.

Per pianificare questa attività, vai a **Vendite e marketing \> Attività periodiche \> Liquida detrazioni approvate** e imposta le opzioni, i filtri e una pianificazione, proprio come per altri tipi di attività periodiche.

> [!NOTE]
> Se l'opzione **Liquidazione automatica** è impostata su *Sì* nella scheda **Liquidazione** della pagina **Parametri contabilità clienti** (**Contabilità clienti \> Impostazioni \> Parametri contabilità clienti**), l'attività periodica *Liquida detrazioni approvate* non viene eseguita perché il credito verrà automaticamente liquidato.

## <a name="create-a-deduction"></a>Creare una detrazione

### <a name="create-a-deduction-journal-entry-by-using-the-customer-payment-journal"></a>Creare una una scrittura contabile di detrazione utilizzando il giornale di registrazione pagamenti cliente

Per creare una scrittura contabile di detrazione completa i passaggi seguenti.

1. Vai a **Contabilità clienti \> Pagamenti \> Giornale di registrazione pagamenti cliente**.
1. Seleziona **Nuovo** per aggiungere una riga alla griglia.
1. Nel campo **Nome** per la nuova riga, seleziona il nome del giornale.
1. Nel riquadro azioni seleziona **Righe**.
1. Immetti la data, l'account della società e il numero di conto del cliente.
1. Nel campo **Fattura** seleziona la fattura a cui è associata la detrazione.
1. Nel campo **Credito** immetti l'importo pagato dal cliente.
1. Seleziona **OK** per confermare che l'importo è inferiore all'importo totale della transazione contrassegnata.
1. Seleziona il tipo di conto di contropartita e il conto di contropartita.
1. Sulla barra degli strumenti sopra la griglia, seleziona **Detrazioni**.
1. Nella pagina **Detrazione**, nel riquadro azioni seleziona **Nuovo** per aggiungere una riga alla griglia. Il campo **ID detrazione** per la nuova riga viene impostato automaticamente.
1. Nel campo **Tipo** seleziona il tipo di detrazione.
1. Nel campo **Importo** inserisci l'importo che viene mostrato nel campo **Saldo** sotto l'elenco delle detrazioni. Questo importo rappresenta l'importo che il cliente ha detratto dal pagamento.
1. Chiudi la pagina **Detrazione**. Viene nuovamente visualizzata la pagina **Pagamenti cliente** che ora mostra una nuova riga per la detrazione.
1. Nel riquadro azioni, seleziona **Convalida \> Convalida**. Viene visualizzato il seguente messaggio: "Il giornale di registrazione è corretto".
1. Nel riquadro Azioni selezionare **Registra**.

### <a name="create-a-deduction-by-using-the-deduction-workbench"></a>Creare una detrazione usando il workbench detrazioni

Per creare una nuova detrazione nel workbench detrazioni, effettua le operazioni seguenti.

1. Vai a **Vendite e marketing \> Sconti commerciali \> Detrazioni \> Workbench detrazioni**.
1. Nel riquadro azioni, seleziona **Gestisci \> Nuova detrazione**.

    Nella finestra di dialogo **Nuova detrazione** il campo **ID detrazione** è impostato in base alla sequenza numerica di **ID detrazione** definita nella pagina **Parametri di gestione sconti commerciali** (**Vendite e marketing \> Impostazioni \> Sconti commerciali \> Parametri di gestione sconti commerciali**).

1. Impostare i seguenti campi:

    - **Conto cliente** – Seleziona il conto cliente a cui si applica la detrazione.
    - **Numero attestazione esterna** – Immetti il riferimento dell'attestazione del cliente.
    - **Importo attestazione** – Immetti l'importo dell'attestazione comprensivo di IVA. Il valore deve essere positivo.
    - **Valuta** – Seleziona la valuta per la detrazione. Il valore predefinito è la valuta impostata per il conto cliente selezionato.
    - **Base attestazione** – Seleziona la base dell'attestazione. La base dell'attestazione determina il tipo di transazione di credito che viene creata dopo l'approvazione della detrazione o dell'attestazione.

        - *Basato sul prezzo* – Verrà creata una bozza di fattura a testo libero.
        - *Basato sulla quantità* – Verrà creato un ordine cliente negativo o un ordine di reso.

    - **Data attestazione** – Seleziona la data dell'attestazione. Il valore predefinito è la data corrente.
    - **Motivo attestazione** – Seleziona il codice motivo che si applica alla detrazione corrente. La base di attestazione selezionata influisce sulle opzioni applicabili. Per ulteriori informazioni su come creare e configurare i motivi dell'attestazione disponibili per la selezione qui, vedi la sezione [Creare motivi di detrazione](#deduction-reasons) precedente in questo argomento.
    - **Note** – Aggiungi eventuali note applicabili. Quando l'attestazione viene approvata, l'approvatore è in grado di modificare o aggiungere note.
    - **Crea un giornale di registrazione attestazioni** – Imposta questa opzione per specificare se creare il giornale di registrazione attestazioni al momento della creazione dell'attestazione o della detrazione:

        - *Sì* – Il sistema creerà e registrerà un giornale di registrazione generale utilizzando il giornale di registrazione attestazioni impostato nella pagina **Parametri contabilità clienti**. Per ulteriori informazioni, vedi la sezione [Configurare la contabilità clienti e le detrazioni](#accounts-receivable-deductions) precedente in questo argomento. Quando una fattura è allegata all'attestazione, il giornale di registrazione viene utilizzato per ridurre il saldo della fattura applicabile. Se l'attestazione viene successivamente respinta, il giornale di registrazione e le liquidazioni (se è stata allegata una fattura) verranno stornati.
        - *No* – Al momento non viene creato alcun giornale di registrazione attestazioni. Verrà creato quando l'attestazione sarà approvata. È ancora possibile allegare una fattura alla nuova attestazione, anche se non è stato creato un giornale di registrazione. Tuttavia, la liquidazione non può essere effettuata senza il giornale di registrazione attestazioni.

1. Selezionare **OK**.

    Viene creata una nuova detrazione. Se imposti l'opzione **Crea un giornale di registrazione attestazioni** su *Sì*, vengono registrate le seguenti transazioni:

    - **Due nuove transazioni cliente** – Una transazione compensa l'importo dell'attestazione con la fattura originale. L'altra transazione registra il debito del cliente per l'importo dell'attestazione, perché l'attestazione non è stata ancora approvata. La transazione della fattura originale e la transazione dell'attestazione di compensazione verranno automaticamente contrassegnate per la liquidazione quando si allega la fattura selezionando **Gestisci \> Allega fattura** nel riquadro azioni.
    - **Due transazioni di compensazione** – Queste transazioni sono registrate nel conto CoGe **Compensazione detrazione**.
    - **Giornale di registrazione attestazioni** – Per visualizzare il giornale di registrazione attestazioni per ogni detrazione mostrata nel workbench detrazioni, seleziona la scheda **Riferimenti**. Il giornale di registrazione attestazioni è mostrato nel campo **Numero batch giornale di registrazione**. È inoltre possibile visualizzare il giornale di registrazione attestazioni nella scheda **Eventi detrazione** dove il valore di **Tipo di aggiornamento** è *Corrispondenza*.

### <a name="create-a-deduction-from-a-customer-settlement"></a>Creare una detrazione da una liquidazione cliente

Il processo di creazione di una detrazione da una liquidazione cliente è simile al processo di creazione di una detrazione tramite il workbench detrazioni. Tuttavia, il cliente e la valuta della fattura vengono impostati automaticamente e la fattura viene allegata. Non devi selezionare **Gestisci \> Allega fattura** nel riquadro azioni quando crei un'attestazione o una detrazione tramite la pagina di liquidazione cliente.

1. Andare a **Contabilità clienti \> Clienti \> Tutti i clienti**.
1. Seleziona il cliente per cui creare una detrazione.
1. Nel riquadro azioni, nella scheda **Raccolta**, nel gruppo **Liquidazione** seleziona **Liquida transazioni**.
1. Nella finestra di dialogo **Impostazione transazioni** nella scheda **Panoramica** seleziona la fattura per cui creare la detrazione.
1. Sulla barra degli strumenti, seleziona **Detrazioni \> Nuova detrazione**.

    Nella finestra di dialogo **Nuova detrazione** il campo **ID detrazione** è impostato in base alla sequenza numerica di **ID detrazione** definita nella pagina **Parametri di gestione sconti commerciali** (**Vendite e marketing \> Impostazioni \> Sconti commerciali \> Parametri di gestione sconti commerciali**). Il campo **Conto cliente** viene impostato sul conto cliente a cui si applica la detrazione.

1. Impostare i seguenti campi:

    - **Numero attestazione esterna** – Immetti il riferimento dell'attestazione del cliente.
    - **Importo attestazione** – Immetti l'importo dell'attestazione comprensivo di IVA. Il valore deve essere positivo.
    - **Valuta** – Seleziona la valuta per la detrazione. Il valore predefinito è la valuta impostata per il conto cliente selezionato.
    - **Base attestazione** – Seleziona la base dell'attestazione. La base dell'attestazione determina il tipo di transazione di credito che viene creata dopo l'approvazione della detrazione o dell'attestazione.

        - *Basato sul prezzo* – Verrà creata una bozza di fattura a testo libero.
        - *Basato sulla quantità* – Verrà creato un ordine cliente negativo o un ordine di reso.

    - **Data attestazione** – Seleziona la data dell'attestazione. Il valore predefinito è la data corrente.
    - **Motivo attestazione** – Seleziona il codice motivo che si applica alla detrazione corrente. La base di attestazione selezionata influisce sulle opzioni applicabili. Per ulteriori informazioni su come creare e configurare i motivi dell'attestazione disponibili per la selezione qui, vedi la sezione [Creare motivi di detrazione](#deduction-reasons) precedente in questo argomento.
    - **Note** – Aggiungi eventuali note applicabili. Quando l'attestazione viene approvata, l'approvatore è in grado di modificare o aggiungere note.
    - **Crea un giornale di registrazione attestazioni** – Imposta questa opzione per specificare se creare il giornale di registrazione attestazioni al momento della creazione dell'attestazione o della detrazione:

        - *Sì* – Il sistema creerà e registrerà un giornale di registrazione generale utilizzando il giornale di registrazione attestazioni impostato nella pagina **Parametri contabilità clienti**. Per ulteriori informazioni, vedi la sezione [Configurare la contabilità clienti e le detrazioni](#accounts-receivable-deductions) precedente in questo argomento. Quando una fattura è allegata all'attestazione, il giornale di registrazione viene utilizzato per ridurre il saldo della fattura applicabile. Se l'attestazione viene successivamente respinta, il giornale di registrazione e le liquidazioni (se è stata allegata una fattura) verranno stornati.
        - *No* – Al momento non viene creato alcun giornale di registrazione attestazioni. Verrà creato quando l'attestazione sarà approvata. È ancora possibile allegare una fattura alla nuova attestazione, anche se non è stato creato un giornale di registrazione. Tuttavia, la liquidazione non può essere effettuata senza il giornale di registrazione attestazioni.

1. Selezionare **OK**.

    Viene creata una nuova detrazione. Se imposti l'opzione **Crea un giornale di registrazione attestazioni** su *Sì*, vengono registrate le seguenti transazioni:

    - **Due nuove transazioni cliente** – Una transazione compensa l'importo dell'attestazione con la fattura originale. L'altra transazione registra il debito del cliente per l'importo dell'attestazione, perché l'attestazione non è stata ancora approvata. La transazione della fattura originale e la transazione dell'attestazione di compensazione verranno automaticamente contrassegnate per la liquidazione quando si allega la fattura selezionando **Gestisci \> Allega fattura** nel riquadro azioni.
    - **Due transazioni di compensazione** – Queste transazioni sono registrate nel conto CoGe **Compensazione detrazione**.
    - **Giornale di registrazione attestazioni** – Per visualizzare il giornale di registrazione attestazioni per ogni detrazione mostrata nel workbench detrazioni, seleziona la scheda **Riferimenti**. Il giornale di registrazione attestazioni è mostrato nel campo **Numero batch giornale di registrazione**. È inoltre possibile visualizzare il giornale di registrazione attestazioni nella scheda **Eventi detrazione** dove il valore di **Tipo di aggiornamento** è *Corrispondenza*.

    Viene di nuovo visualizzata la pagina **Liquida transazioni** che ora mostra la fattura selezionata come contrassegnata. Il pulsante **Registra** è disponibile solo se si imposta l'opzione **Crea un giornale di registrazione attestazioni** su *Sì*. Se è disponibile, seleziona **Registra** per ridurre il saldo della fattura del valore di **Importo attestazione**.

### <a name="create-a-deduction-from-a-customer-page"></a>Creare una detrazione da una pagina cliente

Il processo di creazione di una detrazione da una pagina cliente è simile al processo di creazione di una detrazione tramite il workbench detrazioni. Tuttavia, il cliente viene impostato automaticamente.

1. Andare a **Contabilità clienti \> Clienti \> Tutti i clienti**.
1. Seleziona il cliente per cui creare una detrazione.
1. Nel riquadro azioni della scheda **Raccolta** del gruppo **Detrazioni**, seleziona **Crea detrazioni**.

    Nella finestra di dialogo **Nuova detrazione** il campo **ID detrazione** è impostato in base alla sequenza numerica di **ID detrazione** definita nella pagina **Parametri di gestione sconti commerciali** (**Vendite e marketing \> Impostazioni \> Sconti commerciali \> Parametri di gestione sconti commerciali**). Il campo **Conto cliente** viene impostato sul conto cliente a cui si applica la detrazione.

1. Impostare i seguenti campi:

    - **Numero attestazione esterna** – Immetti il riferimento dell'attestazione del cliente.
    - **Importo attestazione** – Immetti l'importo dell'attestazione comprensivo di IVA. Il valore deve essere positivo.
    - **Valuta** – Seleziona la valuta per la detrazione. Il valore predefinito è la valuta impostata per il conto cliente selezionato.
    - **Base attestazione** – Seleziona la base dell'attestazione. La base dell'attestazione determina il tipo di transazione di credito che viene creata dopo l'approvazione della detrazione o dell'attestazione.

        - *Basato sul prezzo* – Verrà creata una bozza di fattura a testo libero.
        - *Basato sulla quantità* – Verrà creato un ordine cliente negativo o un ordine di reso.

    - **Data attestazione** – Seleziona la data dell'attestazione. Il valore predefinito è la data corrente.
    - **Motivo attestazione** – Seleziona il codice motivo che si applica alla detrazione corrente. La base di attestazione selezionata influisce sulle opzioni applicabili. Per ulteriori informazioni su come creare e configurare i motivi dell'attestazione disponibili per la selezione qui, vedi la sezione [Creare motivi di detrazione](#deduction-reasons) precedente in questo argomento.
    - **Note** – Aggiungi eventuali note applicabili. Quando l'attestazione viene approvata, l'approvatore è in grado di modificare o aggiungere note.
    - **Crea un giornale di registrazione attestazioni** – Imposta questa opzione per specificare se creare il giornale di registrazione attestazioni al momento della creazione dell'attestazione o della detrazione:

        - *Sì* – Il sistema creerà e registrerà un giornale di registrazione generale utilizzando il giornale di registrazione attestazioni impostato nella pagina **Parametri contabilità clienti**. Per ulteriori informazioni, vedi la sezione [Configurare la contabilità clienti e le detrazioni](#accounts-receivable-deductions) precedente in questo argomento. Quando una fattura è allegata all'attestazione, il giornale di registrazione viene utilizzato per ridurre il saldo della fattura applicabile. Se l'attestazione viene successivamente respinta, il giornale di registrazione e le liquidazioni (se è stata allegata una fattura) verranno stornati.
        - *No* – Al momento non viene creato alcun giornale di registrazione attestazioni. Verrà creato quando l'attestazione sarà approvata. È ancora possibile allegare una fattura alla nuova attestazione, anche se non è stato creato un giornale di registrazione. Tuttavia, la liquidazione non può essere effettuata senza il giornale di registrazione attestazioni.

1. Selezionare **OK**.

    Viene creata una nuova detrazione. Se imposti l'opzione **Crea un giornale di registrazione attestazioni** su *Sì*, vengono registrate le seguenti transazioni:

    - **Due nuove transazioni cliente** – Una transazione compensa l'importo dell'attestazione con la fattura originale. L'altra transazione registra il debito del cliente per l'importo dell'attestazione, perché l'attestazione non è stata ancora approvata. La transazione della fattura originale e la transazione dell'attestazione di compensazione verranno automaticamente contrassegnate per la liquidazione quando si allega la fattura selezionando **Gestisci \> Allega fattura** nel riquadro azioni.
    - **Due transazioni di compensazione** – Queste transazioni sono registrate nel conto CoGe **Compensazione detrazione**.
    - **Giornale di registrazione attestazioni** – Per visualizzare il giornale di registrazione attestazioni per ogni detrazione mostrata nel workbench detrazioni, seleziona la scheda **Riferimenti**. Il giornale di registrazione attestazioni è mostrato nel campo **Numero batch giornale di registrazione**. È inoltre possibile visualizzare il giornale di registrazione attestazioni nella scheda **Eventi detrazione** dove il valore di **Tipo di aggiornamento** è *Corrispondenza*.

## <a name="create-a-credit-note-for-a-customer"></a>Creare una nota di accredito per un cliente

Se esiste uno sconto approvato per il cliente, puoi creare una nota di accredito sul conto cliente per rappresentare lo sconto, come necessario. Il credito verrà quindi visualizzato nel workbench detrazioni, in cui può essere associato a una detrazione.

Per creare una nota di accredito, completa i passaggi seguenti.

1. Vai a **Vendite e marketing \> Clienti \> Tutti i clienti**.
1. Selezionare il cliente.
1. Nel riquadro azioni, nella scheda **Raccolta**, nel gruppo **Liquidazione** seleziona **Liquida transazioni**.
1. Nella finestra di dialogo **Liquida transazioni** seleziona la transazione a cui è stato applicato lo sconto.
1. Sulla barra degli strumenti, nel menu **Funzioni** seleziona il tipo di programma di sconti applicabile.
1. Nella pagina **Sconto** nella schead **Panoramica** seleziona la casella di controllo **Contrassegna** accanto all'ID sconto pertinente.
1. Nel riquadro azioni, seleziona **Funzioni \> Crea nota di accredito**.

## <a name="process-a-deduction-on-the-deduction-workbench"></a>Elaborare una detrazione nel workbench detrazioni

Nel workbench di detrazione, è possibile far corrispondere le detrazioni alle transazioni di credito aperte, suddividere, negare e ammortizzate le detrazioni.

A seconda della modalità di elaborazione della detrazione, completa uno o più delle procedure indicate nelle seguenti sottosezioni. Se necessario, è possibile combinare le procedure. Ad esempio, puoi suddividere una detrazione in due parti e quindi far corrispondere una parte a un credito, ma lasciando la parte rimanente nel workbench da abbinare a un altro credito in seguito. Puoi inoltre far corrispondere una detrazione a un credito più piccolo rispetto all'importo della detrazione, quindi negare o annullare il saldo residuo della detrazione.

### <a name="match-a-deduction-to-a-credit"></a>Abbinare la detrazione a un credito

Per abbinare una detrazione a un credito, segui questi passaggi.

1. Vai a **Vendite e marketing \> Sconti commerciali \> Detrazioni \> Workbench detrazioni**.
1. Seleziona la casella di controllo **Contrassegna** per la detrazione da elaborare.
1. Nella sezione **Transazioni aperte** seleziona la casella di controllo **Contrassegna** per abbinare il credito alla detrazione. Se sono elencati più crediti, puoi selezionare più di un credito da far corrispondere alla detrazione. Se il sistema deve selezionare automaticamente i crediti che corrispondono all'importo della detrazione, nella barra degli strumenti seleziona un'opzione appropriata nel menu **Seleziona importo detrazione**.
1. Nel riquadro azioni seleziona **Gestisci \> Corrispondenza**. Il sistema fa corrispondere la detrazione al credito. Se rimane un saldo nella detrazione, viene mostrato nel campo **Importo residuo** della scheda **Detrazioni**.

    > [!NOTE]
    > Per le detrazioni create utilizzando il comando **Nuova detrazione** nel workbench detrazioni, nella liquidazione cliente o nella pagina cliente, il comando **Gestisci \> Corrispondenza** è disponibile solo se il campo **Stato attestazione** è impostato su *Accettato*. Questo comando può essere utilizzato per abbinare manualmente la transazione basata sul prezzo o sulla quantità al credito associato nella sezione **Transazioni aperte**. Questo credito viene creato sia quando viene approvata la detrazione (utilizzando il comando **Gestisci \> Approva detrazione**), o quando è allegato a un credito esistente come descritto nella sezione [Crediti creati al di fuori del processo di approvazione detrazione](#credits-outside-approval) più avanti in questo argomento. L'attività periodica *Liquida detrazioni approvate* (**Vendite e marketing \> Attività periodiche \> Liquida detrazioni approvate**) può essere utilizzata anche per abbinare automaticamente detrazioni e crediti che hanno **ID detrazione** e importi corrispondenti.

### <a name="split-a-deduction"></a>Dividere una detrazione

Per dividere una detrazione effettua le operazioni indicate di seguito.

1. Vai a **Vendite e marketing \> Sconti commerciali \> Detrazioni \> Workbench detrazioni**.
1. Seleziona la casella di controllo **Contrassegna** per la detrazione da elaborare.
1. Nel riquadro azioni seleziona **Gestisci \> Dividi**.
1. Nella finestra di dialogo **Dividi** nel campo **Dividi importo** immetti l'importo da dividere dalla detrazione principale. Selezionare **OK**.
1. Nella scheda **Detrazioni** un nuovo record verrà visualizzato per l'importo suddiviso. Il record originale di detrazione contiene il resto del saldo di detrazione. Ora puoi gestire separatamente le due parti dello sconto originale.
1. Seleziona il record di detrazione originale, quindi seleziona la scheda **Riferimenti**. Il campo **Dividi importo** mostra l'importo che è stato diviso dall'importo originale.

### <a name="attach-an-invoice-to-a-deduction"></a>Allegare una fattura a una detrazione

Puoi allegare una fattura a una detrazione se la detrazione è stata creata utilizzando il comando **Nuova detrazione** nel workbench detrazioni, nella liquidazione cliente o nella pagina cliente e se non è attualmente allegata alcuna fattura (ovvero, la colonna **Fattura** è vuota).

Per allegare una fattura a una detrazione, attieniti alla seguente procedura.

1. Vai a **Vendite e marketing \> Sconti commerciali \> Detrazioni \> Workbench detrazioni**.
1. Seleziona la casella di controllo **Contrassegna** per la detrazione da elaborare.
1. Nel riquadro azioni, seleziona **Gestisci \> Allega fattura**.
1. Nella finestra di dialogo **Allega fattura** seleziona una fattura, quindi seleziona **OK**.
1. Nella finestra di dialogo **Liquida transazioni** segui uno di questi passaggi, a seconda che sia stato registrato un giornale di registrazione attestazioni quando è stata creata la detrazione:

    - Se è stato registrato un giornale di registrazione attestazioni, la fattura selezionata e la transazione di credito cliente del giornale di registrazione attestazioni mostrano un segno di spunta nella colonna **Contrassegna**. Selezionare **Registra**. Il saldo residuo della fattura allegata viene ridotto dell'importo dell'attestazione.
    - Se non è stato registrato un giornale di registrazione attestazioni, nessuna transazione mostra un segno di spunta nella colonna **Contrassegna**. Poiché non è possibile compensare con un giornale di registrazione attestazioni finché la detrazione non viene approvata, seleziona **Annulla**.

### <a name="detach-an-invoice-from-a-deduction"></a>Scollegare una fattura da una detrazione

Puoi scollegare una fattura da una detrazione se la detrazione è stata creata utilizzando il comando **Nuova detrazione** nel workbench detrazioni, nella liquidazione cliente o nella pagina cliente e se una fattura è attualmente allegata (ovvero, la colonna **Fattura** mostra un numero di fattura), e se il campo **Stato attestazione** è impostato su *Aperto*. Potresti completare questa attività perché è stata allegata una fattura errata. La fattura viene rimossa dalla detrazione e il saldo residuo viene aggiornato se è stato ridotto quando è stata allegata la fattura.

Per scollegare una fattura completa i passaggi seguenti.

1. Vai a **Vendite e marketing \> Sconti commerciali \> Detrazioni \> Workbench detrazioni**.
1. Seleziona la casella di controllo **Contrassegna** per la detrazione da elaborare.
1. Nel riquadro azioni, seleziona **Gestisci \> Scollega fattura**.

### <a name="approve-a-deduction"></a>Approvare una detrazione

È possibile approvare le detrazioni create utilizzando il comando **Nuova detrazione** nel workbench detrazioni, nella liquidazione cliente o nella pagina cliente. Tuttavia, puoi approvare solo le detrazioni in cui il campo **Stato attestazione** è impostato su *Aperto*.

Per approvare una detrazione effettua le operazioni indicate di seguito.

1. Vai a **Vendite e marketing \> Sconti commerciali \> Detrazioni \> Workbench detrazioni**.
1. Seleziona la casella di controllo **Contrassegna** per la detrazione da elaborare.
1. Nel riquadro azioni, seleziona **Gestisci \> Approva detrazione**.
1. Nella finestra di dialogo **Approva detrazione** modifica o aggiungi le informazioni nel campo **Nota** come richiesto.
1. Se la detrazione è basata sul prezzo e non è stata allegata una fattura, seleziona una fascia IVA articolo. In genere, la fascia IVA articoli è impostata sulla fattura. Pertanto, il codice articolo imposta deve essere specificato quando non è allegato a una fattura.
1. Selezionare **OK**.

    A questo punto non è possibile apportare ulteriori modifiche alla detrazione. Se l'opzione **Crea un giornale di registrazione attestazioni** era impostata su *No* quando è stata creata la detrazione, il giornale di registrazione attestazioni viene creato e registrato quando la detrazione viene approvata. Dopo l'approvazione della detrazione, il credito viene creato e aperto automaticamente. Il tipo dipende dal valore **Base attestazione** della detrazione:

    - *Basato sul prezzo* – Se la detrazione è basata sul prezzo, viene creata una fattura a testo libero per il conto cliente. Puoi aggiungere una descrizione e registrare il credito. I seguenti campi vengono compilati dalla detrazione al momento della creazione della bozza:

        - **ID detrazione** – Questo campo viene aggiunto all'intestazione per consentire la tracciabilità della detrazione.
        - **Account principale** – Il valore è determinato dal valore **Conto di registrazione attestazioni** impostato per il motivo della detrazione assegnato alla detrazione.
        - **Fascia IVA articolo** – Il valore è determinato dalla fattura allegata o dal valore selezionato al momento dell'approvazione della detrazione.
        - **Prezzo unitario** – Il valore è il credito dell'importo attestazione della detrazione.
        - **Testo fattura** – Per impostazione predefinita, questo campo è impostato sul valore **Note** della detrazione.

    - *Basato sulla quantità* – Se la detrazione è basata sulla quantità, viene creato un ordine cliente aperto o un ordine di reso. L'impostazione **Crea ordine di reso** nella pagina **[Parametri contabilità clienti](#accounts-receivable-deductions)** determina se viene creato un ordine di vendita o un ordine di reso quando viene approvata la detrazione. Viene visualizzata la pagina **Copia ordini** e viene filtrata per mostrare le righe in cui il campo **Conto fattura** è impostato sul conto cliente della detrazione. Eseguire i passaggi indicati di seguito:

        1. Nella scheda dettaglio **Fatture** la sezione **Intestazioni** mostra le fatture di vendita in cui il valore **Conto fattura** corrisponde al conto cliente della detrazione. Seleziona una fattura di vendita applicabile.
        1. La sezione **Righe** mostra le righe della fattura di vendita selezionata. Seleziona la casella di controllo **Seleziona** per ogni riga che vuoi copiare. In alternativa, nella sezione **Intestazioni** seleziona la casella di controllo **Seleziona tutto** per l'ordine cliente per selezionare tutte le righe.
        1. Regola il valore **Quantità** per una o più righe come richiesto.

            Tutte le righe che hai selezionato finora sono elencate nella scheda dettagio **Righe o intestazioni selezionate da copiare**.

        1. Ripeti i due passaggi precedenti come richiesto fino a quando tutte le righe richieste non sono elencate nella scheda dettaglio **Righe o intestazioni selezionate da copiare**.
        1. Selezionare **OK**.

            Il nuovo ordine di reso viene aperto e i seguenti campi vengono impostati automaticamente:

            - **ID detrazione** – Questo campo viene aggiunto all'intestazione per consentire la tracciabilità della detrazione.
            - **Codice motivo reso** – Per impostazione predefinita, questo campo è impostato sul valore **Codice motivo reso** impostato per il motivo della detrazione assegnato alla detrazione.

Dopo che il credito è stato fatturato, appare nella sezione **Transazioni aperte** del workbench detrazioni per il valore **ID detrazione** applicabile e il campo **Tipo di detrazione** è impostato su *Altri crediti*. Il credito sarà disponibile per la liquidazione con la detrazione in una delle seguenti modalità:

- Lo liquidi manualmente selezionando **Gestisci \> Corrispondenza** nel riquadro azioni.
- Viene liquidato automaticamente dal processo periodico *Liquida attestazioni approvate* (**Vendite e marketing \> Attività periodiche \> Liquida attestazioni approvate**).
- Viene liquidato automaticamente perché l'opzione **Liquidazione automatica** nella scheda **Liquidazione** della pagina **Parametri contabilità clienti** è impostata su *Sì*.

Per visualizzare il credito che si crea al momento dell'approvazione della detrazione è possibile utilizzare anche il pulsante **Credito aperto** nella sezione **Transazioni aperte** del workbench detrazioni.

### <a name="create-a-return-order"></a>Creare un ordine di reso

È possibile creare un ordine di reso per le detrazioni create utilizzando il comando **Nuova detrazione** nel workbench detrazioni, nella liquidazione cliente o nella pagina cliente. Tuttavia, devono essere soddisfatte tutte le seguenti condizioni:

- Il campo **Base attestazione** è impostato su *Basato sulla quantità*.
- Il campo **Stato attestazione** è impostato su *Aperto*.
- L'opzione **Crea ordine di reso** nella scheda **Detrazioni** della pagina **[Parametri contabilità clienti](#accounts-receivable-deductions)** è impostata su *Sì*.
- L'opzione **Crea ordine di reso prima dell'approvazione della detrazione** nella scheda **Detrazioni** della pagina **[Parametri contabilità clienti](#accounts-receivable-deductions)** è impostata su *Sì*.

Segui questi passaggi per creare un ordine di reso.

1. Vai a **Vendite e marketing \> Sconti commerciali \> Detrazioni \> Workbench detrazioni**.
1. Seleziona la casella di controllo **Contrassegna** per la detrazione da elaborare.
1. Nel riquadro azioni seleziona **Gestisci \> Crea ordine di reso**.
1. Nella finestra di dialogo **Approva detrazione** modifica o aggiungi le informazioni nel campo **Note** come richiesto e seleziona **OK**.
1. Nella finestra di dialogo **Copia ordini**, nella scheda dettaglio **Fatture** la sezione **Intestazioni** mostra le fatture di vendita in cui il valore **Conto fattura** corrisponde al conto cliente della detrazione. Seleziona una fattura di vendita applicabile.
1. La sezione **Righe** mostra le righe della fattura di vendita selezionata. Seleziona la casella di controllo **Seleziona** per ogni riga da copiare. In alternativa, nella sezione **Intestazioni** seleziona la casella di controllo **Seleziona tutto** per l'ordine cliente per selezionare tutte le righe.
1. Regola il valore **Quantità** per una o più righe come richiesto.

    Tutte le righe che hai selezionato finora sono elencate nella scheda dettagio **Righe o intestazioni selezionate da copiare**.

1. Ripeti i due passaggi precedenti come richiesto fino a quando tutte le righe richieste non sono elencate nella scheda dettaglio **Righe o intestazioni selezionate da copiare**.
1. Selezionare **OK**.

    Il nuovo ordine di reso viene aperto e i seguenti campi vengono impostati automaticamente:

    - **ID detrazione** – Questo campo viene aggiunto all'intestazione per consentire la tracciabilità della detrazione.
    - **Codice motivo reso** – Per impostazione predefinita, questo campo è impostato sul valore **Codice motivo reso** impostato per il motivo della detrazione assegnato alla detrazione.

### <a name="deny-a-deduction"></a>Negare una detrazione

Per negare una detrazione effettua le operazioni indicate di seguito.

1. Vai a **Vendite e marketing \> Sconti commerciali \> Detrazioni \> Workbench detrazioni**.
1. Seleziona la casella di controllo **Contrassegna** per la detrazione da elaborare.
1. Nel riquadro azioni seleziona **Gestisci \> Nega**.
1. Nella finestra di dialogo **Nega** seleziona il codice motivo per il rifiuto, quindi seleziona **OK**.
1. Nel campo **Mostra** al di sotto del riquadro azioni seleziona *Chiuso*.

    La scheda **Detrazioni** mostra la detrazione negata e il campo **Importo residuo** per la detrazione è impostato su *0,00*.

    Per le detrazioni create utilizzando il comando **Nuova detrazione** nel workbench detrazioni, nella liquidazione cliente o nella pagina cliente, si verificano i seguenti eventi:

    - Nella scheda **Riferimenti** i campi nella sezione **Negato** sono aggiornati.
    - Se hai scelto di creare il giornale di registrazione attestazioni quando è stata creata la detrazione e se alla detrazione è stata allegata una fattura che ha ridotto il saldo della fattura, la fattura viene scollegata e il saldo residuo della fattura precedentemente allegata viene aumentato dell'importo dell'attestazione rifiutata.
    - Il campo **Stato** della detrazione è impostato su *Chiuso*.
    - Il campo **Stato attestazione** della detrazione è impostato su *Rifiutato*.

Per annullare un rifiuto effettua le operazioni indicate di seguito.

1. Nella scheda **Detrazioni** seleziona una detrazione negata.
1. Nel riquadro azioni, seleziona **Inverti rifiuto**.

    Per le detrazioni create utilizzando il comando **Nuova detrazione** nel workbench detrazioni, nella liquidazione cliente o nella pagina cliente, si verificano i seguenti eventi:

    - Nella scheda **Riferimenti** i campi nella sezione **Negato** sono aggiornati.
    - Il campo **Stato** della detrazione è impostato su *Aperto*.
    - Il campo **Stato attestazione** della detrazione è impostato su *Aperto*.

### <a name="write-off-a-deduction"></a>Annullare una detrazione

Per annullare una detrazione effettua le operazioni indicate di seguito.

1. Vai a **Vendite e marketing \> Sconti commerciali \> Detrazioni \> Workbench detrazioni**.
1. Seleziona la casella di controllo **Contrassegna** per la detrazione da elaborare.
1. Nel riquadro azioni seleziona **Gestisci \> Annulla**.
1. Nella finestra di dialogo **Annulla** seleziona il codice motivo per l'annullamento, quindi seleziona **OK**.
1. Nel campo **Mostra** seleziona *Chiuso*.

    La scheda **Detrazioni** mostra la detrazione annullata e il campo **Importo residuo** per la detrazione è impostato su *0,00*.

    Per le detrazioni create utilizzando il comando **Nuova detrazione** nel workbench detrazioni, nella liquidazione cliente o nella pagina cliente, si verificano i seguenti eventi:

    - Nella scheda **Riferimenti** i campi nella sezione **Eliminazione** sono aggiornati.
    - Se il giornale di registrazione attestazioni è stato creato quando è stata creata la detrazione, un giornale di registrazione attestazioni viene registrato nel codice motivo annullamento della detrazione. Puoi vedere questa voce nella scheda **Eventi detrazione** dove **Tipo di aggiornamento** ha il valore *Eliminazione*.
    - Il campo **Stato** della detrazione è impostato su *Chiuso*
    - Il campo **Stato attestazione** della detrazione è impostato su *Eliminazione*.

Per annullare un annullamento effettua le operazioni indicate di seguito.

1. Nella scheda **Detrazioni** seleziona una detrazione negata.
1. Nel riquadro azioni seleziona **Inverti annullamento**.

    Per le detrazioni create utilizzando il comando **Nuova detrazione** nel workbench detrazioni, nella liquidazione cliente o nella pagina cliente, si verificano i seguenti eventi:

    - Nella scheda **Riferimenti** i campi nella sezione **Eliminazione** sono aggiornati.
    - Se il giornale di registrazione attestazioni è stato creato quando è stata creata la detrazione, un giornale di registrazione attestazioni viene registrato nel codice motivo annullamento della detrazione. Puoi vedere questa voce nella scheda **Eventi detrazione** dove **Tipo di aggiornamento** ha il valore *Inverti annullamento*.
    - Il campo **Stato** della detrazione è impostato su *Aperto*.
    - Il campo **Stato attestazione** della detrazione è impostato su *Aperto*.

## <a name="credits-created-outside-the-approve-deduction-process"></a><a name="credits-outside-approval"></a>Crediti creati al di fuori del processo di approvazione detrazione

Questa sezione si applica solo alle detrazioni create utilizzando il comando **Nuova detrazione** nel workbench detrazioni, nella liquidazione cliente o nella pagina cliente.

Diversi utenti potrebbero aver già creato una fattura a testo libero, un ordine di reso o un ordine cliente negativo per la detrazione di un cliente al di fuori del processo **Approva detrazione**. Quando la detrazione esistente viene approvata nel workbench di detrazione, il sistema crea automaticamente una fattura a testo libero, un ordine di reso o un ordine cliente negativo. Questa sezione descrive come allegare i crediti esistenti a una detrazione prima che la detrazione venga approvata, per evitare crediti duplicati.

### <a name="attach-a-credit-to-deduction"></a>Allegare un credito alla detrazione

Questa sezione descrive come allegare un credito a una detrazione dal credito.

Dopo aver allegato un credito alla detrazione puoi visualizzarlo usando il pulsante **Credito aperto** nella barra degli strumenti nella sezione **Transazioni aperte** del workbench detrazioni.

Dopo che il credito è stato fatturato e la detrazione è stata approvata, il credito appare nella sezione **Transazioni aperte** del workbench detrazioni per il valore **ID detrazione** applicabile e il campo **Tipo di detrazione** è impostato su *Altri crediti*.

#### <a name="attach-a-free-text-invoice-to-a-deduction"></a>Allegare una fattura a testo libero a una detrazione

Per allegare una fattura a testo libero a una detrazione, attieniti alla seguente procedura.

1. Passa a **Contabilità clienti \> Fatture \> Tutte le fatture a testo libero**.
1. Seleziona la fattura applicabile.
1. Nel riquadro azioni, nella scheda **Fattura**, seleziona **Allega credito a detrazione**. Questo pulsante è disponibile solo il campo **ID detrazione** della fattura a testo libero è vuoto. Un campo vuoto indica che la fattura a testo libero non è già allegata a una detrazione.
1. Nella pagina **Allega credito a detrazione** puoi selezionare *una* detrazione. Solo le detrazioni *basate sul prezzo* aperte sono disponibili per la selezione.
1. Selezionare **OK**. Il campo **ID detrazione** è impostato sull'intestazione della fattura a testo libero.

#### <a name="attach-a-return-order-to-a-deduction"></a>Allegare un ordine di reso a una detrazione

Per allegare un ordine di reso a una detrazione, attieniti alla seguente procedura.

1. Vai a **Contabilità clienti \> Ordini \> Tutti gli ordini di reso**.
1. Seleziona il codice NAR ricevuto o aperto applicabile.
1. Nel riquadro azioni, nella scheda **Ordine di reso**, seleziona **Allega credito a detrazione**. Questo pulsante è disponibile solo il campo **ID detrazione** dell'ordine di reso è vuoto. Un campo vuoto indica che l'ordine di reso non è già allegato a una detrazione.
1. Nella pagina **Allega credito a detrazione** puoi selezionare *una* detrazione. Solo le detrazioni *basate sulla quantità* aperte sono disponibili per la selezione.
1. Selezionare **OK**. Il campo **ID detrazione** è impostato sull'intestazione dell'ordine di reso.

#### <a name="attach-a-sales-order-to-a-deduction"></a>Allegare un ordine cliente a una detrazione

Per allegare un ordine cliente a una detrazione, attieniti alla seguente procedura.

1. Vai a **Contabilità clienti \> Ordini \> Tutti gli ordini cliente**.
1. Seleziona l'ordine cliente aperto, consegnato o fatturato applicabile.
1. Nel riquadro azioni, nella scheda **Fattura**, seleziona **Allega credito a detrazione**. Questo pulsante è disponibile solo il campo **ID detrazione** dell'ordine cliente è vuoto. Un campo vuoto indica che l'ordine cliente non è già allegato a una detrazione.
1. Nella pagina **Allega detrazione** puoi selezionare *una* detrazione. Solo le detrazioni *basate sulla quantità* aperte sono disponibili per la selezione.
1. Selezionare **OK**. Il campo **ID detrazione** è impostato sull'intestazione dell'ordine cliente.

#### <a name="detach-a-deduction-from-a-credit"></a>Scollegare una detrazione da un credito

Se è stata allegata la detrazione errata, è possibile scollegarla dal credito. Tuttavia, devono essere soddisfatte tutte le seguenti condizioni:

- Alla detrazione è allegato un credito.
- Il campo **Stato attestazione** è impostato su *Aperto*.

Per scollegare una detrazione da un credito, segui uno di questi passaggi, a seconda del tipo di credito:

- **Fatture a testo libero:** nella pagina **Tutte le fatture a testo libero** seleziona una fattura. Quindi nel riquadro azioni, nella scheda **Fattura**, seleziona **Scollega credito da detrazione**.
- **Ordini di reso:** nella pagina **Tutti gli ordini di reso** seleziona un ordine. Quindi nel riquadro azioni, nella scheda **Ordine di reso**, seleziona **Scollega credito da detrazione**.
- **Ordini cliente:** nella pagina **Tutti gli ordini cliente** seleziona un ordine. Quindi nel riquadro azioni, nella scheda **Fattura**, seleziona **Scollega credito da detrazione**.

### <a name="attach-a-deduction-to-a-credit"></a>Allegare una detrazione a un credito

Questa sezione descrive come allegare una detrazione a un credito da una detrazione.

#### <a name="attach-a-deduction-to-a-free-text-return-order-or-sales-order-credit"></a>Allegare una detrazione a un credito di una fattura a testo libero, un ordine di reso o un ordine cliente

Per allegare una detrazione a un credito di una fattura a testo libero, un ordine di reso o un ordine cliente, segui questi passaggi.

1. Vai a **Vendite e marketing \> Sconti commerciali \> Detrazioni \> Workbench detrazioni**.
1. Seleziona la detrazione aperta applicabile.
1. Nel riquadro azioni, seleziona **Gestisci \> Allega detrazione a credito**. Questo pulsante è disponibile solo se il campo **Stato attestazione** è impostato su *Aperto*.
1. Nella pagina **Allega credito** puoi selezionare *un* credito. Il tipo di credito che viene mostrato dipende dal valore **Base attestazione** della detrazione:

    - *Basato sul prezzo* – La pagina mostra le fatture a testo libero per il conto cliente in cui il campo **ID detrazione** è vuoto. Le richieste di approvvigionamento cliente vengono visualizzate perché la fattura a testo libero potrebbe non essere registrata. Pertanto, potrebbe non avere un numero a cui è possibile fare riferimento.
    - *Basato sulla quantità* – Il tipo di credito che viene visualizzato dipende dall'impostazione dell'opzione **Crea ordine di reso** nella pagina **[Parametri contabilità clienti](#accounts-receivable-deductions)**:

        - *Sì* – La pagina mostra gli ordini di reso per il conto cliente in cui il campo **ID detrazione** è vuoto.
        - *No* – La pagina mostra gli ordini cliente per il conto cliente in cui il campo **ID detrazione** è vuoto.

1. Selezionare **OK**. Il campo **ID detrazione** è impostato sull'intestazione del credito.

Dopo aver allegato un credito alla detrazione puoi visualizzarlo usando il pulsante **Credito aperto** nella barra degli strumenti nella sezione **Transazioni aperte** del workbench detrazioni.

Dopo che il credito è stato fatturato e la detrazione è stata approvata, il credito appare nella sezione **Transazioni aperte** del workbench detrazioni per il valore **ID detrazione** applicabile e il campo **Tipo di detrazione** è impostato su *Altri crediti*.

#### <a name="detach-a-credit-from-the-deduction"></a>Scollegare un credito da una detrazione

Se è stato allegato un credito errato, è possibile scollegarlo dalla detrazione. Nel riquadro azioni, nel gruppo **Gestisci** seleziona **Scollega detrazione da credito**. Il valore **ID detrazione** viene rimosso dal credito.

Il pulsante **Scollega detrazione da credito** è disponibile solo se sono soddisfatte le seguenti condizioni:

- Alla detrazione è allegato un credito.
- Il campo **Stato attestazione** è impostato su *Aperto*.

## <a name="create-a-one-time-promotion"></a>Creare una promozione una tantum

È talvolta possibile non disporre di uno sconto approvato da abbinare a una detrazione. In questo caso, è possibile utilizzare la funzionalità di *promozione una tantum* per abbinare la detrazione a uno sconto commerciale associato al cliente. Con la funzionalità di *promozione una tantum* viene creato un nuovo sconto commerciale e un evento di merchandising con somma forfettaria. La funzionalità quindi abbina la somma forfettaria alla detrazione ed effettua le registrazioni necessarie per chiudere la detrazione.

Questa funzionalità è utile se si utilizzano gli sconti commerciali. Per ulteriori informazioni sugli sconti commerciali, vedi [Gestione degli sconti commerciali](../sales-marketing/trade-allowance.md).

Innanzitutto, è necessario impostare un modello da usare per creare il nuovo contratto di sconto commerciale. Per impostare un modello, effettua le operazioni seguenti.

1. Vai a **Vendite e marketing \> Sconti commerciali \> Modelli**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nei campi immetti le informazioni che devono essere visualizzate nei contratti creati dal modello.
1. Nella scheda dettaglio **Clienti** nel campo **Gerarchia** seleziona un livello di gerarchia.
1. Nell'elenco della gerarchia seleziona il cliente che ha una detrazione senza corrispondenza, quindi seleziona il pulsante freccia destra (**\>**). Il cliente viene aggiunto all'elenco **Clienti con accordi con sconto commerciale**.
1. Imposta i campi rimanenti come desideri, quindi chiudi la pagina.
1. Vai a **Vendite e marketing \> Impostazioni \> Sconto commerciale \> Parametri di gestione sconti commerciali**.
1. Nella scheda **Panoramica** nel campo **Modello promozione una tantum** seleziona il nome del modello da utilizzare per creare le promozioni una tantum.

Quindi puoi creare una promozione una tantum nel workbench detrazioni. Per creare una promozione una tantum effettua i passaggi seguenti.

1. Vai a **Vendite e marketing \> Sconti commerciali \> Detrazioni \> Workbench detrazioni**.
1. Seleziona la casella di controllo **Contrassegna** accanto alla detrazione da elaborare.
1. Nel riquadro azioni, seleziona **Gestisci \> Liquida detrazione come promozione una tantum**.
1. Nella finestra di dialogo **Promozione una tantum** segui questi passaggi per associare la detrazione a uno o più fondi:

    1. Seleziona **Nuovo**, quindi nel campo **ID fondo**, seleziona un ID fondo. Ripeti questo passaggio per aggiungere tutti i fondi necessari.
    1. Nel campo **Percentuale** accanto a ogni ID fondo, immetti la percentuale della detrazione da allocare al fondo. Gli importi immessi nei campi **Percentuale** devono ammontare al 100 per cento.

1. Selezionare **OK**. Il sistema crea un nuovo contratto con sconto commerciale con un evento di merchandising con somma forfettaria e abbina la somma forfettaria alla detrazione.

## <a name="do-a-mass-update-of-deductions"></a>Eseguire un aggiornamento di massa delle detrazioni

Se è necessario apportare la stessa modifica a più detrazioni, è possibile selezionare tali detrazioni ed eseguire un aggiornamento di massa dei relativi campi.

Segui i passaggi seguenti per eseguire un aggiornamento di massa.

1. Vai a **Vendite e marketing \> Sconti commerciali \> Detrazioni \> Workbench detrazioni**.
1. Nel campo **Mostra**, al di sotto del Riquadro azioni, seleziona il tipo di detrazioni da visualizzare.
1. Seleziona la casella di controllo accanto a ogni detrazione da aggiornare. Nel riquadro azioni, seleziona **Gestisci \> Aggiornamento di massa**.
1. La finestra di dialogo **Aggiornamento di massa** mostra le detrazioni selezionate. Aggiorna i campi come richiesto, quindi seleziona **OK** per accettare le modifiche.
