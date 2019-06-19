---
title: Impostare l'integrazione fiscale per canali di vendita al dettaglio
description: In questo argomento vengono fornite indicazioni per l'impostazione della funzionalità di integrazione fiscale per canali di vendita al dettaglio.
author: josaw
manager: annbe
ms.date: 02/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailFunctionalityProfile, RetailFormLayout, RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: v-kikozl
ms.search.validFrom: 2018-11-1
ms.dyn365.ops.version: 8.1.1
ms.openlocfilehash: fda94e77480b9d9455fc0e214e43772ab2921f2d
ms.sourcegitcommit: ffc37f7c2a63bada3055f37856a30424040bc9a3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/16/2019
ms.locfileid: "1577902"
---
# <a name="set-up-the-fiscal-integration-for-retail-channels"></a>Impostare l'integrazione fiscale per canali di vendita al dettaglio

[!include [banner](../includes/banner.md)]

## <a name="introduction"></a>Introduzione

In questo argomento vengono fornite indicazioni per l'impostazione della funzionalità di integrazione fiscale per canali di vendita al dettaglio. Per ulteriori informazioni sull'integrazione fiscale, vedere [Panoramica dell'integrazione fiscale per i canali di vendita al dettaglio](fiscal-integration-for-retail-channel.md).

Il processo di impostazione dell'integrazione fiscale include le seguenti attività:

1. Configurare connettori fiscali che rappresentano dispositivi o servizi fiscali utilizzati a scopo di registrazione fiscale, ad esempio le stampanti fiscali.
2. Configurare fornitori di documenti che generano documenti fiscali che verranno registrati nei dispositivi o servizi fiscali mediante connettori fiscali.
3. Configurare il processo di registrazione fiscale che definisce una sequenza di fasi di registrazione fiscale nonché i connettori fiscali e i fornitori di documenti fiscali utilizzati per ogni fase.
4. Assegnare il processo di registrazione fiscale ai profili funzionalità POS.
5. Assegnare profili tecnici di connettore a profili hardware.

## <a name="set-up-a-fiscal-registration-process"></a>Configurare un processo di registrazione fiscale

Prima di utilizzare la funzionalità di integrazione fiscale, è necessario configurare le impostazioni descritte di seguito.

1. Aggiornare i parametri di vendita al dettaglio.

    1. Nella pagina **Parametri condivisi di vendita al dettaglio**, nella scheda **Generale**, impostare l'opzione **Abilita integrazione fiscale** su **Sì**. Nella scheda **Sequenze numeriche**, definire le sequenze numeriche per i seguenti riferimenti:

        - Numero del profilo tecnico fiscale
        - Numero del gruppo di connettori fiscali
        - Numero del processo di registrazione

    2. Nella pagina **Parametri di vendita al dettaglio** definire la sequenza numerica per il numero di profilo funzionale fiscale.

    > [!NOTE]
    > Le sequenze numeriche sono facoltative. I numeri per tutte le entità di integrazione fiscale possono essere generati a partire da sequenze numeriche o manualmente.

2. Caricare le configurazioni di connettori fiscali e di fornitori di documenti fiscali.

    Un fornitore di documenti fiscali è responsabile della generazione di documenti fiscali che rappresentano eventi e transazioni di vendite al dettaglio registrati nel POS in un formato utilizzato anche per l'interazione con un dispositivo o servizio fiscale. Ad esempio, un fornitore di documenti fiscali potrebbe generare una rappresentazione di una ricevuta fiscale in un formato XML.

    Un connettore fiscale è responsabile della comunicazione con un dispositivo o servizio fiscale. Ad esempio, un connettore fiscale potrebbe inviare una ricevuta fiscale che un fornitore di documenti fiscali ha creato in un formato XML per una stampante fiscale. Per ulteriori informazioni sui componenti di integrazione fiscale, vedere [Processo di registrazione fiscale ed esempi di integrazione fiscale per dispositivi fiscali](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices).

    1. Nella pagina **Connettori fiscali** (**Vendita al dettaglio \> Impostazione canale \> Integrazione fiscale \> Connettori fiscali**), caricare una configurazione XML per ogni dispositivo o servizio che si prevede di utilizzare per scopi di integrazione fiscale.

        > [!TIP]
        > Se si seleziona **Visualizza**, è possibile visualizzare tutti i profili funzionali e tecnici relativi al connettore fiscale corrente.

    2. Nella pagina **Fornitori di documenti fiscali** (**Vendita al dettaglio \> Impostazione canale \> Integrazione fiscale \> Fornitori di documenti fiscali**), caricare una configurazione XML per ogni dispositivo o servizio che si prevede di utilizzare.

        > [!TIP]
        > Se si seleziona **Visualizza**, è possibile visualizzare tutti i profili funzionali relativi al fornitore di documenti fiscali corrente.

    Per esempi di configurazioni di connettori fiscali e fornitori di documenti fiscali, vedere [Esempi di integrazione fiscale in Retail SDK](fiscal-integration-for-retail-channel.md#fiscal-integration-samples-in-the-retail-sdk).

    > [!NOTE]
    > Il mapping dei dati viene considerato parte di un fornitore di documenti fiscali. Per impostare mapping di dati differenti per lo stesso connettore (ad esempio le normative specifiche di stato), è necessario creare diversi fornitori di documenti fiscali.

3. Creare profili funzionali e tecnici di connettore.

    1. Nella pagina **Profili funzionali del connettore** (**Vendita al dettaglio \> Impostazione canale \> Integrazione fiscale \> Profili funzionali del connettore**), creare un profilo funzionale di connettore per ogni combinazione di connettore fiscale e di fornitore di documenti fiscali relativo a quel connettore fiscale.

        1. Selezionare un nome di connettore.
        2. Selezionare un fornitore di documenti.

        È possibile modificare i parametri di mapping dei dati in un profilo funzionale di connettore. Per ripristinare i parametri predefiniti definiti in una configurazione di fornitore di documenti fiscali, selezionare **Aggiorna**.

        **Esempi**

        |   | Formatta | Esempio |
        |---|--------|---------|
        | **Impostazioni aliquote IVA** | value : VATrate | 1 : 2000, 2 : 1800 |
        | **Mapping codici IVA** | VATcode : value | vat20 : 1, vat18 : 2 |
        | **Mapping tipi di metodo di pagamento** | TenderType : value | Cash : 1, Card : 2 |

        > [!NOTE]
        > I profili funzionali di connettore sono specifici della società. Se si prevede di utilizzare la stessa combinazione di connettore fiscale e di fornitore di documenti fiscali in differenti società, è necessario creare un profilo funzionale di connettore per ogni società.

    2. Nella pagina **Profili tecnici del connettore** (**Vendita al dettaglio \> Impostazione canale \> Integrazione fiscale \> Profili tecnici del connettore**) creare un profilo tecnico di connettore per ogni connettore fiscale.

        1. Selezionare un nome di connettore.
        2. Selezionare un tipo di connettore. Per i dispositivi collegati a una stazione hardware, selezionare **Locale**.

            > [!NOTE]
            > Solo i connettori locali sono attualmente supportati.

        I parametri nelle schede **Dispositivo** e **Impostazioni** in un profilo tecnico di connettore possono essere modificati. Per ripristinare i parametri predefiniti definiti in una configurazione di connettore fiscale, selezionare **Aggiorna**. Durante il caricamento di una nuova versione di una configurazione XML, viene visualizzato un messaggio indicante che il connettore fiscale o il fornitore di documenti fiscali corrente è già in uso. Questa procedura non sovrascrive le modifiche manuali effettuate precedentemente in profili funzionali di connettore e profili tecnici di connettore. Per applicare il set di parametri predefinito da una nuova configurazione, nella pagina **Profili funzionali del connettore** o **Profili tecnici del connettore**, selezionare **Aggiorna**.

4. Creare gruppi di connettori fiscali.

    Un gruppo di connettori fiscali combina profili funzionali di connettori fiscali che eseguono funzioni identiche e sono utilizzati nella stessa fase di un processo di registrazione fiscale. Ad esempio, se è possibile utilizzare diversi modelli di stampante fiscale in un punto vendita al dettaglio, i connettori fiscali per quelle stampanti fiscali possono essere combinati in un gruppo di connettori fiscali.

    1. Nella pagina **Gruppo di connettori fiscali** (**Vendita al dettaglio \> Impostazione canale \> Integrazione fiscale \> Gruppi di connettori fiscali**), creare un nuovo gruppo di connettori fiscali.
    2. Aggiungere profili funzionali al gruppo di connettori. Nella scheda **Profili funzionali**, selezionare **Aggiungi** e selezionare un numero di profilo. Ogni connettore fiscale In un gruppo di connettori può avere un solo profilo funzionale.
    3. Per sospendere l'utilizzo del profilo funzionale, impostare l'opzione **Disabilita** su **Sì**. Questa modifica viene applicata solo al gruppo di connettori corrente. È possibile continuare a utilizzare lo stesso profilo funzionale in altri gruppi di connettori.

5. Creare un processo di registrazione fiscale

    Un processo di registrazione fiscale è definito dalla sequenza dei passaggi di registrazione e dal gruppo di connettori utilizzato in ogni passaggio.

    1. Nella pagina **Processo di registrazione fiscale** (**Vendita al dettaglio \> Impostazione canale \> Integrazione fiscale \> Processi di registrazione fiscale**), creare un nuovo record per ogni processo univoco di registrazione fiscale.
    2. Aggiungere i passaggi di registrazione al processo:

        1. Selezionare **Aggiungi**.
        2. Selezionare un tipo di connettore fiscale.
        3. Nel campo **Numero gruppo**, selezionare un gruppo di connettori fiscali appropriato.

6. Assegnare entità del processo di registrazione fiscale a profili POS.

    1. Nella pagina **Profili funzionalità POS** (**Vendita al dettaglio \> Impostazione canale \> Impostazioni POS \> Profili POS \> Profili funzionalità**), assegnare il processo di registrazione fiscale a un profilo funzionalità POS. Selezionare **Modifica**, quindi nella scheda **Processo di registrazione fiscale**, nel campo **Numero processo**, selezionare un processo.
    2. Nella pagina **Profilo hardware POS** (**Vendita al dettaglio \> Impostazione canale \> Impostazioni POS \> Profili POS \> Profili hardware**), assegnare profili tecnici di connettore a un profilo hardware. Selezionare **Modifica**, aggiungere una riga nella scheda **Periferiche fiscali**, quindi nel campo **Numero profilo**, selezionare un profilo tecnico di connettore.

    > [!NOTE]
    > È possibile aggiungere più profili tecnici a uno stesso profilo hardware. Tuttavia, un profilo hardware o un profilo funzionalità POS deve avere una sola intersezione con qualsiasi gruppo di connettori fiscali.

    Il flusso di registrazione fiscale viene definito dal processo di registrazione fiscale nonché da alcuni parametri dei componenti di integrazione fiscale: l'estensione di Commerce Runtime per il fornitore di documenti fiscali e l'estensione stazione hardware per il connettore fiscale.

    - La sottoscrizione di eventi e transazioni alla registrazione fiscale è predefinita nel fornitore di documenti fiscali.
    - Il fornitore di documenti fiscali è anche responsabile dell'identificazione del connettore fiscale utilizzato per la registrazione fiscale. Il fornitore abbina i profili funzionali di connettore inclusi nel gruppo di connettori fiscali specificato per il passaggio corrente del processo di registrazione fiscale al profilo tecnico di connettore assegnato al profilo hardware della stazione hardware a cui il POS è associato.
    - Il fornitore di documenti fiscali utilizza le impostazioni di mapping dei dati nella configurazione di fornitore di documenti fiscali per trasformare i dati di eventi/transazioni come imposte e pagamenti durante la generazione di un documento fiscale.
    - Quando il fornitore di documenti fiscali genera un documento fiscale, il connettore fiscale può inviarlo al dispositivo fiscale così com'è oppure analizzarlo e trasformarlo in una sequenza di comandi dell'API del dispositivo, a seconda di come la comunicazione viene gestita.

7. Nella pagina **Processo di registrazione fiscale** (**Vendita al dettaglio \> Impostazione canale \> Integrazione fiscale \> Processi di registrazione fiscale**), selezionare **Convalida** per convalidare il processo di registrazione fiscale.

    Si consiglia di eseguire questo tipo di convalida nei seguenti casi:

    - Dopo aver completato tutte le impostazioni per un nuovo processo di registrazione, tra cui l'assegnazione di processi di registrazione a profili di funzionalità POS e a profili hardware.
    - Dopo aver apportato modifiche a un processo di registrazione fiscale esistente e tali modifiche possono comportare la selezione di un connettore fiscale differente al runtime (ad esempio, se si modifica il gruppo di connettori per un passaggio del processo di registrazione fiscale, si abilita un profilo funzionale di connettore in un gruppo di connettori o si aggiunge un nuovo profilo funzionale di connettore a un gruppo di connettori).
    - Dopo aver apportato modifiche all'assegnazione dei profili tecnici di connettore ai profili hardware.

8. Nella pagina **Programmazione distribuzione**, eseguire i processi **1090** e **1070** per trasferire i dati ai database del canale.

## <a name="set-up-fiscal-texts-for-discounts"></a>Impostare testi fiscali per sconti

In alcuni casi, è necessario stampare un testo speciale su una ricevuta fiscale se viene applicato uno sconto. È possibile impostare testi fiscali per sconti nella pagina **Gruppo di connettori fiscali** (**Vendita al dettaglio \> Impostazione canale \> Integrazione fiscale \> Gruppi di connettori fiscali**).

- Per gli sconti manuali applicati dal POS, è necessario impostare un testo fiscale per il codice informativo o il gruppo di codici informativi specificato come codice informativo **Sconto prodotti** nel profilo funzionalità POS.

    1. Nella pagina **Gruppo di connettori fiscali**, selezionare **Testo per ricevuta fiscale**.
    2. Nella scheda **Codici informativi** selezionare **Aggiungi** e quindi un codice informativo o un gruppo di codici informativi.
    3. In **Numero codice informativo**, selezionare un valore.
    4. Nel campo **Numero sottocodice**, selezionare un valore se un sottocodice è necessario per il codice informativo selezionato.
    5. Nel campo **Testo per ricevuta fiscale**, specificare un testo fiscale che deve essere stampato su una ricevuta fiscale.
    6. Impostare **Stampa input utente su ricevuta fiscale** su **Sì** per sostituire il testo su una ricevuta fiscale con informazioni che un utente immette manualmente dal POS. Questa opzione si applica solo ai codici informativi il cui tipo di input è **Testo**.

    > [!NOTE]
    > È possibile specificare un testo fiscale per diversi codici informativi per supportare gli scenari in cui sono utilizzati gruppi di codici informativi, codici informativi collegati e codici informativi attivati. In questi scenari, la ricevuta fiscale conterrà i testi fiscali di tutti i codici informativi collegati alla riga di transazione a cui lo sconto è stato applicato.

- Per gli sconti specifici del canale, è necessario definire un testo fiscale per l'ID sconto.

    1. Nella pagina **Gruppo di connettori fiscali**, selezionare **Testo per ricevuta fiscale**.
    2. Nella scheda **Sconti** selezionare **Aggiungi** e un ID sconto.
    3. Nel campo **Testo per ricevuta fiscale**, specificare un testo fiscale che deve essere stampato su una ricevuta fiscale.

    > [!NOTE]
    > Se più sconti sono applicati alla stessa riga di transazione, la ricevuta fiscale conterrà i testi fiscali di tutti gli sconti collegati a tale riga di transazione.

## <a name="set-error-handling-settings"></a>Configurare le impostazioni di gestione degli errori

Le opzioni di gestione degli errori disponibili nell'integrazione fiscale sono impostate nel processo di registrazione fiscale. Per ulteriori informazioni sulla gestione degli errori nell'integrazione fiscale, vedere [Gestione errori](fiscal-integration-for-retail-channel.md#error-handling).

1. Nella pagina **Processo di registrazione fiscale** (**Vendita al dettaglio \> Impostazione canale \> Integrazione fiscale \> Processi di registrazione fiscale**), è possibile impostare i seguenti parametri per ogni passaggio del processo di registrazione fiscale:

    - **Consenti di ignorare** - Questo parametro abilita l'opzione **Ignora** nella finestra di dialogo per la gestione degli errori.
    - **Consenti di contrassegnare come registrato** - Questo parametro abilita l'opzione **Contrassegna come registrato** nella finestra di dialogo per la gestione degli errori.
    - **Continua in caso di errore** - Se questo parametro è abilitato, il processo di registrazione fiscale può continuare sul registratore di cassa POS se la registrazione fiscale di una transazione o di un evento non riesce. In caso contrario, per eseguire la registrazione della transazione o dell'evento successivo, l'operatore dovrà riprovare la registrazione fiscale non riuscita, ignorarla o contrassegnare la transazione o l'evento come registrato. Per ulteriori informazioni, vedere [Registrazione fiscale facoltativa](fiscal-integration-for-retail-channel.md#optional-fiscal-registration).

    > [!NOTE]
    > Se il parametro **Continua in caso di errore** è abilitato, i parametri **Consenti di ignorare** e **Consenti di contrassegnare come registrato** vengono disabilitati automaticamente.

2. Le opzioni **Contrassegna come registrato** e **Ignora** nella finestra di dialogo per la gestione degli errori richiedono l'autorizzazione **Consenti di ignorare la registrazione o di contrassegnare come registrato**. Di conseguenza, nella pagina **Gruppi di autorizzazione** (**Vendita al dettaglio \> Dipendenti \> Gruppi di autorizzazioni**), abilitare l'autorizzazione **Consenti di ignorare la registrazione o di contrassegnare come registrato**.
3. Le opzioni **Contrassegna come registrato** e **Ignora** consentono agli operatori di immettere informazioni aggiuntive quando la registrazione fiscale ha esito negativo. Per rendere questa funzionalità disponibile, è necessario specificare i codici informativi **Contrassegna come registrato** e **Ignora** in un gruppo di connettori fiscali. Le informazioni immesse dagli operatori sono salvate come transazione codice informativo collegata alla transazione fiscale. Per ulteriori informazioni sui codici informativi, vedere [Codici informativi e gruppi di codici informativi](../info-codes-retail.md).

    > [!NOTE]
    > La funzione di attivazione **Prodotto** non è supportata per i codici informativi utilizzati per **Ignora** e **Contrassegna come registrato** nei gruppi di connettori fiscali.

    - Nella pagina **Gruppo di connettori fiscali**, nella scheda **Codici informativi**, selezionare i codici informativi o i gruppi di codici informativi nei campi **Ignora** e **Contrassegna come registrato**.

    > [!NOTE]
    > Un documento fiscale e un documento non fiscale possono essere generati per qualsiasi passaggio di un processo di registrazione fiscale. Un'estensione di fornitore di documenti fiscali identifica ogni tipo di transazione o evento come correlato a documenti fiscali o non fiscali. La funzionalità di gestione degli errori è utilizzabile solo con documenti fiscali.
    >
    > - **Documento fiscale** - Un documento obbligatorio che deve essere registrato correttamente (ad esempio, una ricevuta fiscale).
    > - **Documento non fiscale** - Un documento supplementare per la transazione o l'evento (ad esempio, una distinta di gift card).

4. Se l'operatore deve poter continuare a elaborare l'operazione corrente (ad esempio, la creazione o la finalizzazione di una transazione) dopo un errore di verifica integrità, è necessario abilitare l'autorizzazione **Consenti di ignorare errore di verifica integrità** nella pagina **Gruppi di autorizzazione** (**Vendita al dettaglio \> Dipendenti \> Gruppi di autorizzazione**). Per ulteriori informazioni sulla procedura di verifica integrità, vedere [Verifica integrità della registrazione fiscale](fiscal-integration-for-retail-channel.md#fiscal-registration-health-check).

## <a name="set-up-fiscal-xz-reports-from-the-pos"></a>Configurare report X/Z fiscali dal POS

Per abilitare report X/Z fiscali per l'esecuzione dal POS, è necessario aggiungere nuovi pulsanti a un layout POS.

- Nella pagina **Griglie dei pulsanti**, seguire le istruzioni in [Aggiungere un pulsante di operazione al layout POS in Retail Headquarters](../dev-itpro/add-pos-operations.md#add-a-custom-operation-button-to-the-pos-layout-in-retail-headquarters) per installare il designer e aggiornare un layout POS.

    1. Selezionare il layout da aggiornare. 
    2. Aggiungere un nuovo pulsante e impostare la proprietà del pulsante **Stampa X fiscale**.
    3. Aggiungere un nuovo pulsante e impostare la proprietà del pulsante **Stampa Z fiscale**.
    4. Nella pagina **Programmazione della distribuzione**, eseguire il processo **1090** per trasferire le modifiche al database del canale.

## <a name="enable-manual-execution-of-postponed-fiscal-registration"></a>Abilitare l'esecuzione manuale della registrazione fiscale posticipata

Per abilitare l'esecuzione manuale di una registrazione fiscale posticipata, è necessario aggiungere un nuovo pulsante a un layout POS.

- Nella pagina **Griglie dei pulsanti**, seguire le istruzioni in [Aggiungere un pulsante di operazione al layout POS in Retail Headquarters](../dev-itpro/add-pos-operations.md#add-a-custom-operation-button-to-the-pos-layout-in-retail-headquarters) per installare il designer e aggiornare un layout POS.

    1. Selezionare il layout da aggiornare.
    2. Aggiungere un nuovo pulsante e impostare la proprietà del pulsante **Processo di registrazione fiscale completo**.
    3. Nella pagina **Programmazione della distribuzione**, eseguire il processo **1090** per trasferire le modifiche al database del canale.
