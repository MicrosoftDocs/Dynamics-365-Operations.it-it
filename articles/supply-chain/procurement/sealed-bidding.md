---
title: Offerta nascosta per RdO
description: Questo argomento descrive come impostare un'offerta nascosta per mantenere segrete le risposte all'offerta del fornitore fino a quando non vengono sbloccate dal personale addetto agli acquisti.
author: GalynaFedorova
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: dfc19646d6724627c8a25bcfc8a6b2a70a73c261
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2022
ms.locfileid: "8675151"
---
# <a name="sealed-bidding-for-rfqs"></a>Offerta nascosta per RdO

[!include [banner](../includes/banner.md)]

Un'offerta nascosta mentiene segrete le risposte all'offerta del fornitore fino a quando non vengono sbloccate dal personale addetto agli acquisti. Tutte le offerte relative a una richiesta di offerta (RdO) sono disponibili per essere sbloccate alla scadenza dell'offerta. Prima che un'offerta venga sbloccata, solo gli utenti che hanno ruoli utente dedicati e che rappresentano il fornitore possono accedervi.

> [!IMPORTANT]
> La modifica o l'estensione dei moduli o la creazione di nuovi moduli o logica di business può vanificare la protezione fornita da Microsoft per le offerte nascoste. L'utente si assume il rischio di utilizzare eventuali modifiche, estensioni, nuovi moduli o logica di business o l'impossibilità di utilizzare la funzione di offerta nascosta a causa di tali modifiche, estensioni, nuovi moduli o logica di business.  Microsoft non è responsabile per eventuali danni derivanti da eventuali modifiche o estensioni ai moduli o nuovi moduli o logica di business creati dall'utente o creati da terzi. Microsoft non fornisce supporto tecnico o di altro tipo per eventuali modifiche, estensioni, nuovi moduli o logica di business apportate dall'utente o da terze parti per suo conto. Sei l'unico responsabile del rispetto di tutte le leggi o i regolamenti applicabili in materia di offerte nascoste.

## <a name="how-bids-are-kept-secure"></a>Come vengono mantenute sicure le offerte

L'offerta nascosta utilizza la crittografia asimmetrica per crittografare la chiave di crittografia dell'offerta (KEK) e la crittografia simmetrica per crittografare l'offerta effettiva. Il sistema si integra con Microsoft Azure Key Vault per generare e gestire le chiavi di crittografia utilizzate per crittografare le offerte nascoste. Ogni offerta ha la propria chiave di crittografia. Questa crittografia è conservata al sicuro in un key vault di proprietà dell'organizzazione che esegue Dynamics 365 Supply Chain Management. Il sistema accede al key vault su richiesta, ogni volta che sono richieste operazioni di crittografia e decrittografia.

## <a name="setup-and-configuration"></a>Impostazione e configurazione

Questa sezione descrive i prerequisiti che devono essere soddisfatti prima di poter inviare richieste di offerta che richiedono offerte nascoste.

### <a name="step-1-set-up-user-access-to-sealed-bidding"></a>Passaggio 1: impostare l'accesso degli utenti alle offerte nascoste

Quando si utilizzano le offerte nascoste, solo gli utenti impostati come contatto del fornitore possono visualizzare, modificare e inviare offerte per quel fornitore fino alla scadenza del periodo di offerta. Questi utenti devono avere il ruolo **Fornitore (esterno)** e devono essere impostati come contatto per il conto fornitore. Il contatto deve inoltre disporre dell'autorizzazione per collaborare con il fornitore, come descritto in [Configurare e mantenere la collaborazione con i fornitori](set-up-maintain-vendor-collaboration.md).

Poiché gli utenti che dispongono delle autorizzazioni appropriate e che sono configurati come contatti del fornitore possono accedere alle offerte nascoste per un fornitore, è importante tenere traccia di chi sono tali utenti. L'amministratore di sistema che imposta utenti e ruoli di sicurezza è responsabile della limitazione dell'accesso alle offerte nascoste agli utenti che sono realmente autorizzati a visualizzarle.

### <a name="step-2-enable-the-sealed-bidding-feature"></a>Passaggio 2: abilitare la funzione di offerta nascosta

Prima di iniziare a configurare o utilizzare questa funzionalità, devi assicurarti che sia disponibile nel sistema. Gli amministratori possono utilizzare l'area di lavoro della **[gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** per controllare lo stato della funzione e se necessario abilitarla. Nell'area di lavoro **Gestione funzionalità**, la funzione è elencata nel modo seguente:

- **Modulo:** *Attività di approvvigionamento*
- **Nome funzionalità:** *Offerta nascosta per RdO*

### <a name="step-3-set-up-azure-key-vault"></a>Passaggio 3: impostare Azure Key Vault

Supply Chain Management utilizza chiavi di crittografia per proteggere tutte le offerte nascoste e mantenerle segrete fino al momento opportuno. Usa le capacità di Key Vault per generare e gestire le chiavi richieste. Pertanto, è necessario configurare una connessione da Supply Chain Management a un key vault per abilitare il sistema.

> [!IMPORTANT]
> Gli insiemi di credenziali delle chiavi per offerta nascosta devono soddisfare i seguenti requisiti:
>
> - Se si utilizza un sandbox per lo sviluppo e il test, è necessario disporre di un insieme di credenziali delle chiavi dedicato per il sandbox e uno separato per la produzione.
> - Ogni insieme di credenziali delle chiavi deve essere creato in una sottoscrizione di Azure di proprietà dell'organizzazione (non la sottoscrizione in cui si esegue Supply Chain Management).
> - Ogni insieme di credenziali delle chiavi deve essere utilizzato esclusivamente per offerta nascosta. Non è possibile utilizzare gli insieme di credenziali delle chiavi per offerta nascosta per alcun altro scopo.

Ogni offerta recupera la propria chiave segreta. Questa chiave viene utilizzata ogni volta che un utente visualizza, aggiorna o sblocca l'offerta.

Il Key Vault genera la chiave che viene utilizzata per recuperare il segreto quando il fornitore seleziona **Offerta** nell'interfaccia di collaborazione del fornitore. La chiave quindi scade dopo un tempo prestabilito che il responsabile degli acquisti imposta nella pagina **Parametri di approvvigionamento** in Supply Chain Management. Dopo la scadenza della chiave, nessuno sarà in grado di visualizzare, modificare o sbloccare l'offerta. Pertanto, è importante configurare la scadenza della chiave in modo che ci sia il tempo sufficiente per il completamento del processo di offerta.

Nei tre passaggi successivi, imposterai la connessione al Key Vault. Innanzitutto, imposterai un key vault da utilizzare con le offerte nascoste. Successivamente, configurerai Supply Chain Management per comunicare con il key vault. Infine, imposterai l'ora di scadenza per la chiave.

### <a name="step-4-set-up-a-key-vault-to-use-with-sealed-bidding"></a>Passaggio 4: impostare un key vault da utilizzare con le offerte nascoste

Per impostare il key vault, effettua le seguenti operazioni. L'ordine dei passaggi è importante.

1. Se non hai già configurato una sottoscrizione di Azure separata dalla sottoscrizione in cui stai eseguendo Supply Chain Management, configurala.
1. Configura un key vault nell'archiviazione di Azure separata. Per ulteriori informazioni, vedi [Gestione del Key Vault di Archiviazione di Azure](https://support.microsoft.com/help/4040294/maintaining-azure-key-vault-storage).
1. Configura la tua app Supply Chain Management per lavorare come client per il tuo key vault. Per ulteriori informazioni, vedi [Impostazione del client Key Vault di Azure](https://support.microsoft.com/help/4040305/setting-up-azure-key-vault-client).

### <a name="step-5-configure-key-vault-parameters-in-supply-chain-management"></a>Passaggio 5: configurare i parametri di Key Vault in Supply Chain Management

Per configurare Supply Chain Management in modo che comunichi con il key vault durante le offerte nascoste, segui questi passaggi.

1. Accedi a Supply Chain Management e vai in **Amministrazione di sistema \> Impostazioni \> Parametri Key Vault**.
1. Seleziona **Nuovo** per creare un record e impostare i seguenti campi:

    - **Nome** - immetti un nome.
    - **Descrizione** - immetti una descrizione.
    - **URL Key Vault** – Immetti l'URL predefinito per il key vault.
    - **Client Key Vault** – Immetti l'ID client interattivo dell'applicazione Active Directory associata a un key vault per l'autenticazione.
    - **Chiave segreta Key Vault** – Immetti il riferimento segreto per il certificato.
    - **Abilitato per offerta nascosta** – Imposta questa opzione su *Sì*.

![Pagina Parametri Key Vault](media/sealed-bidding-key-vault-param.png "Pagina Parametri Key Vault")

> [!NOTE]
> Puoi abilitare solo una configurazione di key vault per offerte nascoste alla volta. Prima di disabilitare una configurazione di Key Vault esistente, è necessario assicurarsi che tutte le offerte nascoste che la utilizzano non siano nascoste. Ispeziona ogni caso di richiesta di offerta di tipo *Nascosto* e assicurati che tutte le risposte non siano nascoste.

### <a name="step-6-set-the-key-expiration-time"></a>Passaggio 6: impostare l'ora di scadenza della chiave

Per impostare l'ora di scadenza applicata alla chiave generata per ogni nuova offerta, attieniti alla seguente procedura.

1. Vai a **Parametri di approvvigionamento \> Impostazioni \> Parametri di approvvigionamento**.
1. Nella scheda **Richiesta di offerta** nel campo **Offset giorni** immetti il numero di giorni per il periodo di richiesta di offerta. Quando viene creata una richiesta di offerta, il numero di giorni immesso qui viene aggiunto alla data di sistema per definire la data di scadenza predefinita per la richiesta di offerta.
1. Nel campo **Offset giorno di scadenza chiave di crittografia**, inserisci il numero di giorni di validità di ogni chiave di crittografia dopo essere stata emessa. Dopo la scadenza della chiave di crittografia, nessuno sarà in grado di visualizzare, modificare o sbloccare l'offerta nascosta che la utilizza.

> [!TIP]
> Il valore del campo **Offset giorno di scadenza chiave di crittografia** non deve essere inferiore al valore del campo **Offset giorni**.

### <a name="step-7-set-the-default-bid-type"></a><a name="set-default-bid-type"></a>Passaggio 7: impostare il tipo di offerta predefinito

Ogni caso di richiesta di offerta ha un tipo di offerta. Il tipo di offerta definisce se il caso di richiesta di offerta fornisce un'offerta aperta o nascosta.

#### <a name="rfq-cases-that-dont-have-a-solicitation-type"></a>Casi di richiesta di offerta che non hanno un tipo di sollecito

Per impostare il tipo di offerta predefinito assegnato ai nuovi casi di richiesta di offerta a cui non è stato assegnato un tipo di sollecito al momento della creazione, attieniti alla seguente procedura.

1. Vai a **Parametri di approvvigionamento \> Impostazioni \> Parametri di approvvigionamento**.
1. Nella schea **Richiesta di offerta** imposta il campo **Tipo di offerta** su *Nascosto*.

#### <a name="rfq-cases-that-have-a-solicitation-type"></a>Casi di richiesta di offerta che hanno un tipo di sollecito

Per impostare il tipo di offerta predefinito assegnato ai nuovi casi di richiesta di offerta a cui è stato assegnato un tipo di sollecito al momento della creazione, attieniti alla seguente procedura.

1. Vai a **Approvvigionamento \> Impostazioni \> Richiesta di offerta \> Tipo di sollecito**.
1. Crea un nuovo tipo di sollecito o seleziona un tipo di sollecito esistente in cui desideri utilizzare un'offerta di tipo *Nascosto*.
1. Imposta il campo **Tipo di offerta** su *Nascosto*.
1. Ripeti questi passaggi per ogni ulteriore tipo di sollecito in cui desideri implementare l'offerta nascosta.

> [!TIP]
> Non è necessario assegnare un tipo di sollecito quando viene creata una nuova richiesta di offerta. Se viene assegnato un tipo di sollecito, il tipo di offerta predefinito di una richiesta di offerta può recuperarlo. In caso contrario, è possibile utilizzare il tipo di richiesta predefinito definito in Parametri di approvvigionamento.

## <a name="the-sealed-bidding-process"></a>Processo di offerta nascosta

L'offerta nascosta segue quasi lo stesso processo descritto in [Panoramica delle richieste di offerta (RdO)](request-quotations.md). La differenza principale è che i dati dell'offerta e i relativi allegati vengono mantenuti crittografati fino a quando l'offerta non viene aperta.

> [!IMPORTANT]
> I [questionari](/dynamicsax-2012/appuser-itpro/view-and-respond-to-questionnaires) non sono crittografati e non devono essere utilizzati per raccogliere informazioni sensibili

Ecco una panoramica del processo:

1. Crea e invia una RdO per uno o più fornitori.
1. I fornitori rispondono inviando la loro offerta nascosta.
1. Apri le offerte dopo il tempo di scadenza dell'inserimento dell'offerta.
1. Le offerte diventano visibili e puoi valutarle e confrontarle.
1. Dopo che un'offerta è stata accettata, generi un ordine di acquisto, un contratto di acquisto o aggiorni una richiesta di acquisto.

### <a name="create-an-rfq-case-that-uses-sealed-bidding"></a>Creare un caso di richiesta di offerta che utilizza offerte nascoste

Il processo di creazione di un caso RdO per le offerte nascoste è quasi lo stesso del processo per le offerte non nascoste. Per informazioni su come creare entrambi i tipi di casi di richiesta di offerta, vedi [Creare una richiesta di offerta](tasks/create-request-quotation.md). Questa sezione evidenzia alcune considerazioni importanti quando si crea una richiesta di offerta per offerte nascoste.

I casi RdO per le offerte nascoste devono avere un valore **Tipo di offerta** di *Nascosto*. Esistono tre modi per assegnare questo valore a un caso di richiesta di offerta:

- Imposta il valore direttamente nel caso di richiesta di offerta dopo averlo creato.
- Definisci l'offerta nascosta come tipo di offerta predefinito per tutti i casi di richiesta di offerta in Parametri di approvvigionamento. (Vedi la sezione [Impostare il tipo di offerta predefinito](#set-default-bid-type) precedente in questo argomento.)
- Quando crei un nuovo caso di richiesta di offerta, seleziona un tipo di sollecito impostato per l'offerta nascosta. (Vedi la sezione [Impostare il tipo di offerta predefinito](#set-default-bid-type).)

Per le offerte nascoste, i valore **Data e ora di scadenza** del caso RdO stabilisce quando le offerte presentate possono essere aperte. Il valore **Data e ora di scadenza** su ogni riga corrisponderà al valore sull'intestazione.

Non è possibile modificare il tipo di offerta dopo l'invio di un caso di richiesta di offerta.

### <a name="vendors-respond-to-an-rfq"></a>I fornitori rispondono a una richiesta di offerta

I fornitori che rispondono a un'offerta nascosta utilizzano la stessa procedura che utilizzano per rispondere alle offerte aperte, come indicato in [Utilizzo delle richieste di offerta nell'area di lavoro Offerta fornitore](vendor-collaboration-work-customers-dynamics-365-operations.md#working-with-rfqs-in-the-vendor-bidding-workspace). Per istruzioni dettagliate su come lavorare sia con le offerte aperte che con le offerte nascoste, vedi [Immettere e confrontare offerte RdO e acquisire contratti](tasks/enter-compare-rfq-bids-award-contracts.md). L'unica differenza tra l'elaborazione per le offerte nascoste e l'elaborazione per le offerte aperte è che, fino alla scadenza del periodo di offerta, i professionisti dell'approvvigionamento non possono aprire l'offerta nascosta di un fornitore. Solo un contatto per il fornitore può aprire l'offerta nascosta di quel venditore.

> [!IMPORTANT]
> Per le offerte nascoste, i fornitori possono caricare gli allegati solo in formato PDF. Non saranno accettati altri formati.

Dopo che un utente fornitore registrato seleziona **Offerta** in una richiesta di offerta nascosta, può inserire i dati dell'offerta e tali dati verranno mantenuti al sicuro. I fornitori possono salvare il proprio lavoro mentre preparano un'offerta, tornare a lavorarci tutte le volte che è necessario e quindi inviarlo quando è pronto. I fornitori possono anche visualizzare la loro offerta dopo averla inviata. Se i fornitori devono modificare la propria offerta dopo averla inviata, possono richiamarla, aggiornarla e ripresentarla in qualsiasi momento fino alla scadenza del periodo di offerta.

Le seguenti condizioni si applicano durante le offerte nascoste:

- Durante le offerte nascoste, il sistema crea un giornale di registrazione *Richiesta di offerta*.
- Quando un fornitore invia un'offerta, vengono creati giornali di registrazione RdO senza righe con un prezzo nascosto.
- Dopo che il caso è stato sbloccato, vengono creati i giornali di registrazione RdO con un prezzo e un importo. Puoi accedere a questo giornale selezionando **Giornali di registrazione richiesta di offerta** nella pagina **Tutte le richieste di offerta**.
- Il sistema memorizza un registro per ogni azione che gli utenti eseguono su un'offerta nascosta. Queste azioni includono la visualizzazione, la modifica e il salvataggio dell'offerta. Questo registro è visibile sia al fornitore che ai professionisti dell'approvvigionamento che hanno accesso all'offerta.
- Man mano che l'offerta avanza, i professionisti dell'approvvigionamento possono visualizzarne lo stato. Lo stato sarà *Aggiornamento in corso del fornitore* o *Inviata dal fornitore*.
- Lo stato delle righe in un'offerta nascosta rimane *Inviato* fino a quando l'offerta non viene aperta.
- Se il fornitore sceglie di rifiutare un'offerta, l'offerta avrà uno stato **Avanzamento risposta** di *Rifiutato dal fornitore*. Questo stato sarà visibile al personale addetto all'approvvigionamento.
- Le risposte nei questionari **non** sono memorizzate in forma crittografata nel database. Pertanto, non vengono sbloccate. Tuttavia, non saranno visibili nell'interfaccia utente della richiesta di offerta finché il caso non verrà aperto.

### <a name="all-sealed-bid-activities-are-logged"></a>Tutte le attività di offerta nascosta vengono registrate

Un registro dettagliato registra tutte le attività e le azioni dell'utente per un'offerta. Il registro delle attività consente alle organizzazioni di determinare chi ha aggiornato un'offerta durante il suo ciclo di vita e quali sono stati gli aggiornamenti. Consente inoltre alle organizzazioni di verificare che solo le persone autorizzate hanno avuto accesso a un'offerta nascosta. Il registro delle attività è disponibile nella pagina **Attività** di ogni offerta.

### <a name="review-rfq-activity"></a>Rivedere l'attività di richiesta di offerta

Ogni interazione con l'offerta viene registrata e può essere visualizzata nella pagina **Attività**. Nella figura seguente viene illustrato un esempio.

![Esempio della pagina Attività](media/sealed-bidding-rfq-activity.png "Esempio della pagina Attività")

I fornitori possono accedere alla pagina **Attività** selezionando **Attività** nella pagina **Offerta nascosta richiesta di offerta**. Il personale addetto all'approvvigionamento può accedervi selezionando **Attività** nella pagina **Richiesta di offerta**. Il registro delle attività offre visibilità completa per i fornitori e per il personale ddetto all'approvvigionamento che ha avuto accesso all'offerta. Pertanto, può rivelare qualsiasi accesso non autorizzato.

### <a name="unseal-sealed-bids"></a>Sbloccare le offerte nascoste

Quando il valore **Data e ora di scadenza** che è stato configurato per un caso di richiesta di offerta nascosta viene superato, il pulsante **Sblocca** diventa disponibile. Seleziona **Sblocca** per sbloccare tutte le offerte per il caso RdO selezionato. Tutti i dati dell'offerta e gli allegati diventano quindi visibili in modo da poter gestire le risposte al caso. Inoltre, vengono creati giornali di registrazione che contengono i dati delle offerte inviate.

L'evento di sblocco viene registrato e può essere visualizzato nella pagina **Attività**.

### <a name="process-accepted-bids"></a>Elaborare le offerte accettate

Il processo di confronto e approvazione delle offerte precedentemente nascoste è lo stesso del processo per le offerte aperte. Per informazioni su come valutare, confrontare, rifiutare e accettare offerte sbloccate, vedi [Immettere e confrontare offerte RdO e acquisire contratti](tasks/enter-compare-rfq-bids-award-contracts.md).

## <a name="the-rfq-activity-log-can-never-be-deleted"></a>Il registro delle attività delle richieste di offerta non può mai essere eliminato

Nessuno, nemmeno gli amministratori e il supporto Microsoft, possono modificare o eliminare il registro delle attività di richieste di offerta. Questa restrizione aiuta a garantire l'equità del processo di offerta nascosta. Aiuta anche a garantire che venga mantenuto un audit trail accurato.
