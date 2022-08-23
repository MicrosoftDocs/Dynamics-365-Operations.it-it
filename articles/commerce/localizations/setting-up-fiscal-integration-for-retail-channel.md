---
title: Impostare l'integrazione fiscale per canali di commercio
description: In questo articolo vengono fornite indicazioni per l'impostazione della funzionalità di integrazione fiscale per canali di commercio.
author: EvgenyPopovMBS
ms.date: 04/28/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 9fd801395f2ba04c703734a1de7998d6a53b6462
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9276134"
---
# <a name="set-up-the-fiscal-integration-for-commerce-channels"></a>Impostare l'integrazione fiscale per canali di commercio

[!include [banner](../includes/banner.md)]

In questo articolo vengono fornite indicazioni per l'impostazione della funzionalità di integrazione fiscale per canali di commercio. Per ulteriori informazioni sull'integrazione fiscale, vedere [Panoramica dell'integrazione fiscale per i canali di commercio](fiscal-integration-for-retail-channel.md).

## <a name="enable-features-in-commerce-headquarters"></a>Abilitare le funzionalità in Commerce headquarters

Per abilitare le funzionalità relative alla funzionalità di integrazione fiscale per i canali di Commerce, attieniti alla seguente procedura.

1. In Commerce Headquarters andare a **Amministrazione sistema \> Aree di lavoro \> Gestione funzionalità**.
1. Trova e abilita le seguenti funzionalità:

    - **Integrazione fiscale diretta da registri POS** – Questa funzione estende il framework di integrazione fiscale aggiungendo la capacità di creare connettori fiscali che verranno eseguiti nel punto vendita (POS). Questo tipo di connettore comunica con un dispositivo o un servizio fiscale che fornisce un'API (Application Programming Interface) HTTP e non richiede una macchina fisica dedicata nel negozio. Ad esempio, questa funzionalità consente l'integrazione fiscale per i dispositivi mobili senza richiedere una stazione hardware condivisa.
    - **Sostituzioni profilo tecnico fiscale di integrazione fiscale** – Questa funzionalità consente di ampliare la configurazione dell'integrazione fiscale e aggiunge la possibilità di verificare i parametri di connessione nella pagina delle impostazioni di un registro POS. Quando questa funzione è abilitata, puoi sostituire i parametri di un profilo tecnico.
    - **Stato della registrazione fiscale dei registri POS** – Quando questa funzione è abilitata, è possibile disabilitare il processo di registrazione fiscale per specifici registri POS. Se la registrazione fiscale è disabilitata per un registro POS, le transazioni di vendita non possono essere completate su quel registro.
    - **Backup archiviazione locale di integrazione fiscale** – Questa funzione estende le capacità di gestione degli errori del framework di integrazione fiscale. Consente inoltre il backup automatico dei dati di registrazione fiscale in caso di perdita dei dati, in modo che i dati nella memoria locale vengano ripristinati all'attivazione di un dispositivo.

## <a name="set-up-commerce-parameters"></a>Configurare parametri di commercio

Per impostare i parametri di Commerce, effettua le seguenti operazioni.

1. Nella pagina **Parametri condivisi di commercio**, nella scheda **Generale**, impostare l'opzione **Abilita integrazione fiscale** su **Sì**.
1. Nella scheda **Sequenze numeriche**, definire le sequenze numeriche per i seguenti riferimenti:

    - Numero del profilo tecnico fiscale
    - Numero del gruppo di connettori fiscali
    - Numero del processo di registrazione

1. Nella pagina **Parametri di commercio** definire la sequenza numerica per il numero di profilo funzionale fiscale.

> [!NOTE]
> Le sequenze numeriche sono facoltative. I numeri per tutte le entità di integrazione fiscale possono essere generati a partire da sequenze numeriche o manualmente.

## <a name="set-up-a-fiscal-registration-process"></a>Configurare un processo di registrazione fiscale

Il processo di impostazione dell'integrazione fiscale include le seguenti attività:

- Configurare connettori fiscali che rappresentano dispositivi o servizi fiscali utilizzati a scopo di registrazione fiscale, ad esempio le stampanti fiscali.
- Configurare fornitori di documenti che generano documenti fiscali che verranno registrati nei dispositivi o servizi fiscali mediante connettori fiscali.
- Configurare il processo di registrazione fiscale che definisce una sequenza di fasi di registrazione fiscale nonché i connettori fiscali e i fornitori di documenti fiscali utilizzati per ogni fase.
- Assegna il processo di registrazione fiscale ai profili funzionalità POS.
- Assegnare profili tecnici di connettore a profili hardware.
- Assegnare profili tecnici di connettore a profili hardware POS o funzionalità.

### <a name="upload-configurations-of-fiscal-document-providers"></a>Caricare le configurazioni di fornitori di documenti fiscali

Un fornitore di documenti fiscali è responsabile della generazione di documenti fiscali che rappresentano eventi e transazioni registrati nel POS in un formato utilizzato anche per l'interazione con un dispositivo o servizio fiscale. Ad esempio, un fornitore di documenti fiscali potrebbe generare una rappresentazione di una ricevuta fiscale in un formato XML.

Per caricare le configurazioni di fornitori di documenti fiscali segui questi passaggi.

1. In Commerce headquarters, vai alla pagina **Provider di documenti fiscali** (**Retail e Commerce \> Impostazione canale \> Integrazione fiscale \> Provider di documenti fiscali**).
1. Carica una configurazione XML per ogni dispositivo o servizio che intendi utilizzare.

> [!TIP]
> Se si seleziona **Visualizza**, è possibile visualizzare tutti i profili funzionali relativi al fornitore di documenti fiscali corrente.

> [!NOTE]
> Il mapping dei dati viene considerato parte di un fornitore di documenti fiscali. Per impostare mapping di dati differenti per lo stesso connettore (ad esempio le normative specifiche di stato), è necessario creare diversi fornitori di documenti fiscali.

### <a name="upload-configurations-of-fiscal-connectors"></a>Caricare le configurazioni dei connettori fiscali

Un connettore fiscale è responsabile della comunicazione con un dispositivo o servizio fiscale. Ad esempio, un connettore fiscale potrebbe inviare una ricevuta fiscale che un fornitore di documenti fiscali ha creato in un formato XML per una stampante fiscale. Per ulteriori informazioni sui componenti di integrazione fiscale, vedere [Processo di registrazione fiscale ed esempi di integrazione fiscale per dispositivi fiscali e servizi](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services).

Per caricare le configurazioni di connettori fiscali segui questi passaggi.

1. In Commerce headquarters, vai alla pagina **Connettori fiscali** (**Retail e Commerce \> Impostazione canale \> Integrazione fiscale \> Connettori fiscali**).
1. Carica una configurazione XML per ogni dispositivo o servizio che intendi utilizzare per scopi di integrazione fiscale.

> [!TIP]
> Se si seleziona **Visualizza**, è possibile visualizzare tutti i profili funzionali e tecnici relativi al connettore fiscale corrente.

Per esempi di configurazioni di connettori fiscali e fornitori di documenti fiscali, vedi [Esempi di integrazione fiscale nell'SDK Commerce](fiscal-integration-for-retail-channel.md#fiscal-integration-samples-in-the-commerce-sdk).

### <a name="create-connector-functional-profiles"></a>Creare profili funzionali del connettore

Per creare profili funzionali del connettore, completa i passaggi seguenti.

1. In Commerce headquarters, vai alla pagina **Profili funzionali del connettore** (**Retail e Commerce \> Impostazione canale \> Integrazione fiscale \> Profili funzionali del connettore**).
1. Per ogni combinazione di connettore fiscale e di provider di documenti fiscali correlata a questo connettore fiscale, crea un profilo funzionale di connettore seguendo questi passaggi.

    1. Selezionare un nome di connettore.
    1. Selezionare un fornitore di documenti.

#### <a name="change-data-mapping-parameters-in-a-connector-functional-profile"></a>Modificare i parametri di mapping dei dati in un profilo funzionale di connettore

È possibile modificare i parametri di mapping dei dati in un profilo funzionale di connettore. La tabella seguente fornisce alcuni esempi di parametri di mapping dei dati in un profilo funzionale del connettore.

| Parametro | Formattazione | Esempio |
|-----------|--------|---------|
| Impostazioni aliquote IVA | value : VATrate | 1 : 2000, 2 : 1800 |
| Mapping codici IVA | VATcode : value | vat20 : 1, vat18 : 2 |
| Mapping tipi di metodo di pagamento | TenderType : value | Cash : 1, Card : 2 |

Per ripristinare i parametri predefiniti definiti in una configurazione di fornitore di documenti fiscali, seleziona **Aggiorna** nella pagina **Profili funzionali del connettore**.

> [!NOTE]
> I profili funzionali di connettore sono specifici della società. Se si prevede di utilizzare la stessa combinazione di connettore fiscale e di fornitore di documenti fiscali per differenti società, è necessario creare un profilo funzionale di connettore per ogni società.

### <a name="create-connector-technical-profiles"></a>Creare profili tecnici del connettore

Per creare profili tecnici del connettore, completa i passaggi seguenti.

1. In Commerce headquarters, vai alla pagina **Profili tecnici connettori** (**Retail e Commerce \> Impostazione canale \> Integrazione fiscale \> Profili tecnici connettori**).
1. Crea un profilo tecnico del connettore per ogni connettore fiscale attenendoti alla seguente procedura:

    1. Selezionare un nome di connettore.
    1. Seleziona un tipo di connettore:

        - Per dispositivi o servizi connessi a una stazione hardware o presenti nella rete locale, seleziona **Locale**.
        - Per i servizi esterni, seleziona **Esterno**.
        - Per i connettori interni in Commerce Runtime (CRT), seleziona **Interno**. 

    1. Seleziona una posizione del connettore:

        - Se il connettore si trova sulla stazione hardware, seleziona **Stazione hardware**.
        - Se il connettore si trova sul registro POS, seleziona **Registro**.

I parametri nelle schede **Dispositivo** e **Impostazioni** in un profilo tecnico di connettore possono essere modificati. Per ripristinare i parametri predefiniti definiti in una configurazione di connettore fiscale, selezionare **Aggiorna**. Durante il caricamento di una nuova versione di una configurazione XML, viene visualizzato un messaggio indicante che il connettore fiscale o il fornitore di documenti fiscali corrente è già in uso. Questa procedura non sovrascrive le modifiche manuali effettuate precedentemente in profili funzionali di connettore e profili tecnici di connettore. Per applicare il set di parametri predefinito da una nuova configurazione, nella pagina **Profili funzionali del connettore** o **Profili tecnici del connettore**, seleziona **Aggiorna**.

Se devi configurare parametri specifici per un singolo registratore o punto vendita POS, attieniti alla seguente procedura.

1. Seleziona la voce di menu **Sostituzione**.
1. Nella pagina **Sostituzione**, crea un nuovo record.
1. Seleziona un punto vendita o registratore POS. È possibile sostituire i parametri del profilo tecnico selezionato per un singolo registratore POS o tutti i registratori POS in un singolo punto vendita.
1. Nella scheda **Dispositivo**, immetti i parametri per il registratore o punto vendita POS selezionato.

### <a name="create-fiscal-connector-groups"></a>Creare gruppi di connettori fiscali

Un gruppo di connettori fiscali combina profili funzionali di connettori fiscali che eseguono funzioni identiche e sono utilizzati nella stessa fase di un processo di registrazione fiscale. Ad esempio, se è possibile utilizzare diversi modelli di stampante fiscale in un punto vendita, i connettori fiscali per quelle stampanti fiscali possono essere combinati in un gruppo di connettori fiscali.

Per creare un gruppo di connettori fiscali, completare i passaggi seguenti.

1. Vai alla pagina **Gruppo di connettori fiscali** (**Retail e Commerce \> Impostazione canale \> Integrazione fiscale \> Gruppi di connettori fiscali**).
1. Crea un nuovo gruppi di connettori fiscali.
1. Aggiungere profili funzionali al gruppo di connettori. Nella scheda **Profili funzionali**, selezionare **Aggiungi** e selezionare un numero di profilo. Ogni connettore fiscale in un gruppo di connettori può avere un solo profilo funzionale.
1. Per sospendere l'utilizzo del profilo funzionale, impostare l'opzione **Disabilita** su **Sì**. Questa modifica viene applicata solo al gruppo di connettori corrente. È possibile continuare a utilizzare lo stesso profilo funzionale in altri gruppi di connettori.

### <a name="create-a-fiscal-registration-process"></a>Creare un processo di registrazione fiscale

Un processo di registrazione fiscale è definito dalla sequenza dei passaggi di registrazione e dal gruppo di connettori utilizzato in ogni passaggio.

Per creare un processo di registrazione fiscale, attieniti alla procedura seguente.

1. In Commerce headquarters, vai alla pagina **Processo di registrazione fiscale** (**Retail e Commerce \> Impostazione canale \> Integrazione fiscale \> Processi di registrazione fiscale**).
1. Crea un nuovo record per ogni processo di registrazione fiscale univoco.
1. Aggiungi i passaggi di registrazione al processo seguendo questi passaggi:

    1. Seleziona **Aggiungi**.
    1. Selezionare un tipo di connettore fiscale.
    1. Nel campo **Numero gruppo**, selezionare un gruppo di connettori fiscali appropriato.

### <a name="assign-entities-of-the-fiscal-registration-process-to-pos-profiles"></a>Assegnare entità del processo di registrazione fiscale a profili POS

Per assegnare entità del processo di registrazione fiscale a profili POS, segui questi passaggi.

1. In Commerce headquarters, vai alla pagina **Profili funzionalità POS** (**Retail e Commerce \> Impostazione canale \> Impostazioni POS \> Profili POS \> Profili funzionalità**). 
1. Assegna il processo di registrazione fiscale a un profili funzionalità POS.
1. Selezionare **Modifica**, quindi nella scheda **Processo di registrazione fiscale**, nel campo **Numero processo**, selezionare un processo.
1. Nella scheda **Servizi fiscali**, selezionare i profili tecnici del connettore con la posizione del connettore **Registratore di cassa**.
1. Vai alla pagina **Profilo hardware POS** (**Retail e Commerce \> Impostazione canale \> Impostazioni POS \> Profili POS \> Profili hardware**).
1. Assegna profili tecnici di connettore a un profilo hardware. 
1. Seleziona **Modifica**, quindi nella scheda **Periferiche fiscali**, aggiungi una riga. 
1. Nel campo **Numero profilo**, seleziona un profilo tecnico del connettore.
1. Nella scheda **Periferiche fiscalii**, selezionare i profili tecnici del connettore con la posizione del connettore **Stazione hardware**.

> [!NOTE]
> È possibile aggiungere più profili tecnici a uno stesso profilo hardware. Tuttavia, un profilo hardware o un profilo funzionalità POS deve avere una sola intersezione con qualsiasi gruppo di connettori fiscali.

Il flusso di registrazione fiscale viene definito dal processo di registrazione fiscale nonché da alcuni parametri dei componenti di integrazione fiscale: l'estensione di CRT per il fornitore di documenti fiscali e l'estensione stazione hardware per il connettore fiscale.

- La sottoscrizione di eventi e transazioni alla registrazione fiscale è predefinita nel fornitore di documenti fiscali.
- Il fornitore di documenti fiscali è anche responsabile dell'identificazione del connettore fiscale utilizzato per la registrazione fiscale. Il fornitore abbina i profili funzionali di connettore inclusi nel gruppo di connettori fiscali specificato per il passaggio corrente del processo di registrazione fiscale al profilo tecnico di connettore assegnato al profilo hardware della stazione hardware a cui il POS è associato.
- Il fornitore di documenti fiscali utilizza le impostazioni di mapping dei dati nella configurazione di fornitore di documenti fiscali per trasformare i dati di eventi/transazioni come imposte e pagamenti durante la generazione di un documento fiscale.
- Quando il fornitore di documenti fiscali genera un documento fiscale, il connettore fiscale può inviarlo al dispositivo fiscale così com'è oppure analizzarlo e trasformarlo in una sequenza di comandi dell'API del dispositivo, a seconda di come la comunicazione viene gestita.

### <a name="set-up-registers-with-fiscal-registration-restrictions"></a>Configurare registri con vincoli di registrazione fiscale

Puoi selezionare registri dove la registrazione fiscale è proibita, ad esempio nei casi in cui devii fornire solo operazioni non fiscali, come la ricerca nel catalogo prodotti, la ricerca di clienti o la creazione di bozze di transazione su questi dispositivi.

Per configurare registri con vincoli di registrazione fiscale, segui questi passaggi.

1. In Commerce Headquarters, vai a **Retail e Commerce \> Impostazione canale \> Integrazione fiscale \> Processi di registrazione fiscale**.
1. Seleziona il processo richiesto.
1. Seleziona la scheda **Registri POS con vincoli di processo fiscale**.
1. Aggiungi i registri con vincoli di processo fiscale in base alle esigenze.

### <a name="validate-the-fiscal-registration-process"></a>Convalidare il processo di registrazione fiscale

È consigliabile convalidare il processo di registrazione fiscale nei seguenti casi:

- Hai completato tutte le impostazioni per un nuovo processo di registrazione. Queste impostazioni includono l'assegnazione dei processi di registrazione ai profili di funzionalità POS e ai profili hardware.
- Hai apportato modifiche a un processo di registrazione fiscale esistente e tali modifiche potrebbero causare la selezione di un connettore fiscale diverso in fase di esecuzione. (Ad esempio, hai modificato il gruppo di connettori per una fase del processo di registrazione fiscale, hai abilitato un profilo funzionale del connettore in un gruppo di connettori o hai aggiunto un nuovo profilo funzionale del connettore a un gruppo di connettori.)
- Hai apportato modifiche all'assegnazione dei profili tecnici di connettore ai profili hardware.

Per convalidare il processo di registrazione fiscale, attieniti alla procedura seguente.

1. In Commerce headquarters, vai alla pagina **Processo di registrazione fiscale** (**Retail e Commerce \> Impostazione canale \> Integrazione fiscale \> Processi di registrazione fiscale**).
1. Seleziona **Convalida** per convalidare il processo di registrazione fiscale.
1. Nella pagina **Programmazione distribuzione**, eseguire i processi **1090** e **1070** per trasferire i dati ai database del canale.

## <a name="set-up-fiscal-texts-for-discounts"></a>Impostare testi fiscali per sconti

In alcuni casi, è necessario stampare un testo speciale su una ricevuta fiscale se viene applicato uno sconto. È possibile impostare testi fiscali per sconti nella pagina **Gruppo di connettori fiscali** (**Retail e Commerce \> Impostazione canale \> Integrazione fiscale \> Gruppi di connettori fiscali**).

- Per gli sconti manuali applicati dal POS, è necessario impostare un testo fiscale per il codice informativo o il gruppo di codici informativi specificato come codice informativo **Sconto prodotti** nel profilo funzionalità POS.

    1. Nella pagina **Gruppo di connettori fiscali**, selezionare **Testo per ricevuta fiscale**.
    1. Nella scheda **Codici informativi** selezionare **Aggiungi** e quindi un codice informativo o un gruppo di codici informativi.
    1. Nel campo **Numero di codice Info** , seleziona un valore.
    1. Nel campo **Numero sottocodice**, selezionare un valore se un sottocodice è necessario per il codice informativo selezionato.
    1. Nel campo **Testo per ricevuta fiscale**, specificare un testo fiscale che deve essere stampato su una ricevuta fiscale.
    1. Impostare **Stampa input utente su ricevuta fiscale** su **Sì** per sostituire il testo su una ricevuta fiscale con informazioni che un utente immette manualmente dal POS. Questa opzione si applica solo ai codici informativi il cui tipo di input è **Testo**.

    > [!NOTE]
    > È possibile specificare un testo fiscale per diversi codici informativi per supportare gli scenari in cui sono utilizzati gruppi di codici informativi, codici informativi collegati e codici informativi attivati. In questi scenari, la ricevuta fiscale conterrà i testi fiscali di tutti i codici informativi collegati alla riga di transazione a cui lo sconto è stato applicato.

- Per gli sconti specifici del canale, è necessario definire un testo fiscale per l'ID sconto.

    1. Nella pagina **Gruppo di connettori fiscali**, selezionare **Testo per ricevuta fiscale**.
    1. Nella scheda **Sconti** selezionare **Aggiungi** e un ID sconto.
    1. Nel campo **Testo per ricevuta fiscale**, specificare un testo fiscale che deve essere stampato su una ricevuta fiscale.

    > [!NOTE]
    > Se più sconti sono applicati alla stessa riga di transazione, la ricevuta fiscale conterrà i testi fiscali di tutti gli sconti collegati a tale riga di transazione.

## <a name="set-error-handling-settings"></a>Configurare le impostazioni di gestione degli errori

Le opzioni di gestione degli errori disponibili nell'integrazione fiscale sono impostate nel processo di registrazione fiscale. Per ulteriori informazioni sulla gestione degli errori nell'integrazione fiscale, vedere [Gestione errori](fiscal-integration-for-retail-channel.md#error-handling).

Per impostare le impostazioni di gestione degli errori, segui questi passaggi.

1. Nella pagina **Processo di registrazione fiscale** (**Retail e Commerce \> Impostazione canale \> Integrazione fiscale \> Processi di registrazione fiscale**), è possibile impostare i seguenti parametri per ogni passaggio del processo di registrazione fiscale:

    - **Consenti di ignorare** - Questo parametro abilita l'opzione **Ignora** nella finestra di dialogo per la gestione degli errori.
    - **Consenti di contrassegnare come registrato** - Questo parametro abilita l'opzione **Contrassegna come registrato** nella finestra di dialogo per la gestione degli errori.
    - **Consenti posticipo** - Questo parametro abilita l'opzione **Posticipa** nella finestra di dialogo per la gestione degli errori.
    - **Continua in caso di errore** - Se questo parametro è abilitato, il processo di registrazione fiscale può continuare sul registratore di cassa POS se la registrazione fiscale di una transazione o di un evento non riesce. In caso contrario, per eseguire la registrazione della transazione o dell'evento successivo, l'operatore dovrà riprovare la registrazione fiscale non riuscita, ignorarla o contrassegnare la transazione o l'evento come registrato. Per ulteriori informazioni, vedere [Registrazione fiscale facoltativa](fiscal-integration-for-retail-channel.md#optional-fiscal-registration).

    > [!NOTE]
    > Se il parametro **Continua in caso di errore** è abilitato, i parametri **Consenti di ignorare** e **Consenti di contrassegnare come registrato** vengono disabilitati automaticamente.

1. Le opzioni **Contrassegna come registrato** e **Ignora** nella finestra di dialogo per la gestione degli errori richiedono che l'autorizzazione **Consenti di ignorare la registrazione o di contrassegnare come registrato** sia abilitata. Per abilitare questa autorizzazione,. vai alla pagina **Gruppi di autorizzazione** (**Retail e Commerce \> Dipendenti \> Gruppi di autorizzazioni**) e imposta l'opzione **Consenti di ignorare la registrazione o di contrassegnare come registrato** su **Sì**.
1. L'opzione **Posticipa** nella finestra di dialogo per la gestione degli errori richiede l'abilitazione dell'autorizzazione **Consenti posticipo**. Per abilitare l'autorizzazione,. vai alla pagina **Gruppi di autorizzazione** (**Retail e Commerce \> Dipendenti \> Gruppi di autorizzazioni**) e imposta l'opzione **Consenti posticipo** su **Sì**.
1. Le opzioni **Ignora**, **Contrassegna come registrato** e **Posticipa** consentono agli operatori di immettere informazioni aggiuntive quando la registrazione fiscale ha esito negativo. Per rendere questa funzionalità disponibile, è necessario specificare i codici informativi **Ignora**, **Contrassegna come registrato** e **Posticipa** in un gruppo di connettori fiscali. Le informazioni immesse dagli operatori sono salvate come transazione codice informativo collegata alla transazione fiscale. Per ulteriori informazioni sui codici informativi, vedere [Codici informativi e gruppi di codici informativi](../info-codes-retail.md).

    > [!NOTE]
    > La funzione di attivazione **Prodotto** non è supportata per i codici informativi utilizzati per **Ignora** e **Contrassegna come registrato** nei gruppi di connettori fiscali.

    - Nella pagina **Gruppo di connettori fiscali**, nella scheda **Codici informativi**, selezionare i codici informativi o i gruppi di codici informativi nei campi **Ignora**, **Contrassegna come registrato** e **Posticipa**.

    > [!NOTE]
    > Un documento fiscale e un documento non fiscale possono essere generati per qualsiasi passaggio di un processo di registrazione fiscale. Un'estensione di fornitore di documenti fiscali identifica ogni tipo di transazione o evento come correlato a documenti fiscali o non fiscali. La funzionalità di gestione degli errori è utilizzabile solo con documenti fiscali.
    >
    > - **Documento fiscale** - Un documento obbligatorio che deve essere registrato correttamente (ad esempio, una ricevuta fiscale).
    > - **Documento non fiscale** - Un documento supplementare per la transazione o l'evento (ad esempio, una distinta di gift card).

1. Se l'operatore deve poter continuare a elaborare l'operazione corrente (ad esempio, la creazione o la finalizzazione di una transazione) dopo un errore di verifica integrità, è necessario abilitare l'autorizzazione **Consenti di ignorare errore di verifica integrità** nella pagina **Gruppi di autorizzazione** (**Retail e Commerce \> Dipendenti \> Gruppi di autorizzazione**). Per ulteriori informazioni sulla procedura di verifica integrità, vedere [Verifica integrità della registrazione fiscale](fiscal-integration-for-retail-channel.md#fiscal-registration-health-check).

## <a name="set-up-fiscal-xz-reports-from-the-pos"></a>Configurare report X/Z fiscali dal POS

Per abilitare report X/Z fiscali per l'esecuzione dal POS, è necessario aggiungere nuovi pulsanti a un layout POS.

- Nella pagina **Griglie dei pulsanti**, seguire le istruzioni in [Aggiungere operazioni POS a layout POS tramite Progetto griglia dei pulsanti](../dev-itpro/add-pos-operations.md#add-a-custom-operation-button-to-the-pos-layout-in-retail-headquarters) per installare il designer e aggiornare un layout POS.

    1. Selezionare il layout da aggiornare. 
    1. Aggiungere un nuovo pulsante e impostare la proprietà del pulsante **Stampa X fiscale**.
    1. Aggiungere un nuovo pulsante e impostare la proprietà del pulsante **Stampa Z fiscale**.
    1. Nella pagina **Programmazione della distribuzione**, eseguire il processo **1090** per trasferire le modifiche al database del canale.

## <a name="enable-manual-execution-of-postponed-fiscal-registration"></a>Abilitare l'esecuzione manuale della registrazione fiscale posticipata

Per abilitare l'esecuzione manuale di una registrazione fiscale posticipata, è necessario aggiungere un nuovo pulsante a un layout POS.

- Nella pagina **Griglie dei pulsanti**, seguire le istruzioni in [Aggiungere operazioni POS a layout POS tramite Progetto griglia dei pulsanti](../dev-itpro/add-pos-operations.md#add-a-custom-operation-button-to-the-pos-layout-in-retail-headquarters) per installare il designer e aggiornare un layout POS.

    1. Selezionare il layout da aggiornare.
    1. Aggiungere un nuovo pulsante e impostare la proprietà del pulsante **Processo di registrazione fiscale completo**.
    1. Nella pagina **Programmazione della distribuzione**, eseguire il processo **1090** per trasferire le modifiche al database del canale.


## <a name="view-connection-parameters-and-other-information-in-pos"></a>Visualizzare i parametri di connessione e altre informazioni nel POS

Per visualizzare i parametri di connessione e altre informazioni nel POS, segui questi passaggi.

1. Apri Modern POS (MPOS) o Cloud POS (CPOS).
1. Selezionare **Impostazioni**. Se l'integrazione fiscale è abilitata, la sezione **Integrazione fiscale** a destra mostrerà le seguenti informazioni:

    - Stato della registrazione fiscale
    - Stato dell'ultima transazione fiscale
    - Numero di eventi di controllo in sospeso

1. Seleziona **Dettagli** per visualizzare le seguenti informazioni:

    - Passaggi del processo di registrazione
    - Parametri di connessione
    - Dettagli degli eventi di controllo
 
[!INCLUDE[footer-include](../../includes/footer-banner.md)]
