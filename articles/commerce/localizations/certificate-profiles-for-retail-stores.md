---
title: Profili certificato definiti dall'utente per i punti vendita al dettaglio
description: Questo argomento fornisce una panoramica su come vengono utilizzati i certificati nei punti vendita al dettaglio.
author: josaw
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailFormLayout, RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: epopov
ms.search.validFrom: 2020-10-09
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 9cb82a6d6336bb69fe818fb33e04ad621382b383055b24a4e79eee5ddff217ac
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6719932"
---
# <a name="user-defined-certificate-profiles-for-retail-stores"></a>Profili certificato definiti dall'utente per i punti vendita al dettaglio

[!include [banner](../includes/banner.md)]


## <a name="overview"></a>Panoramica

In questo argomento viene fornita una panoramica dei profili certificato disponibili in Microsoft Dynamics 365 Commerce. Questa funzionalità estende la funzionalità [Gestire segreti per i canali di vendita al dettaglio](../dev-itpro/manage-secrets.md) aggiungendo supporto per i certificati locali.

Quando il POS viene eseguito in modalità offline, non può accedere ai certificati archiviati nell'insieme di credenziali delle chiavi. Al suo posto deve essere utilizzato il certificato locale. Sono supportate le seguenti operazioni:

- Utilizzo di certificati locali in scenari di fallback dell'insieme di credenziali delle chiavi
- Utilizzo di certificati locali senza un insieme di credenziali delle chiavi (ad esempio in un'installazione locale)
- Aggiornamento graduale dei certificati, dove alcuni punti vendita e terminali utilizzano una nuova versione del certificato, ma altri punti vendita e terminali continuano a utilizzare la versione precedente

La funzionalità dei profili di certificato consente di specificare un certificato predefinito e impostare l'ordine in cui viene effettuata la ricerca di certificati nello stesso profilo di certificato. Questa funzionalità fornisce anche un approccio di configurazione simile per i certificati locali e per i certificati dell'insieme di credenziali delle chiavi. Puoi aggiungere impostazioni specifiche dell'azienda per i certificati, ma l'identificatore univoco interaziendale per ogni certificato può essere utilizzato nei canali di Commerce.

### <a name="scenarios"></a>Scenari

La funzionalità dei profili di certificato supporta i seguenti scenari nei canali di Commerce:

- Utilizzo di un certificato locale in scenari di fallback dell'insieme di credenziali delle chiavi. Di seguito sono riportati alcuni esempi di scenari di fallback:

    - L'archivio dell'insieme di credenziali delle chiavi non è accessibile.
    - Non è stato trovato un certificato nell'archivio dell'insieme di credenziali delle chiavi.
    - Il POS è eseguito in modalità offline.

- Utilizzo di certificati locali ma senza archiviarli nell'insieme di credenziali delle chiavi (ad esempio in un'installazione locale).
- Esecuzione di un aggiornamento graduale dei certificati, dove una nuova versione del certificato viene utilizzata solo nei punti vendita o sui terminali in cui la nuova versione è già disponibile.
- Utilizzo dello stesso certificato in più aziende.

## <a name="set-up-certificate-profiles"></a>Impostare profili di certificato

La seguente procedura spiega come impostare profili di certificato. Prima di utilizzare i profili di certificato nei canali di Commerce, segui questi passaggi per configurare le impostazioni.

1. Nell'area di lavoro **Gestione funzionalità**, attiva la funzionalità **Profili di certificato definiti dall'utente per punti vendita al dettaglio**.
2. Accedi a **Amministrazione sistema \> Imposta \> Profili certificato**.
3. Crea un record e impostane i campi **Profilo certificato**, **Nome** e **Descrizione**.

    > [!NOTE]
    > Il profilo certificato è un identificatore univoco di un certificato in tutte le società e componenti di Commerce.

3. Nella scheda **Persone giuridiche**, aggiungi una riga e selezionare la persona giuridica (azienda) per la quale deve essere utilizzato il profilo di certificato corrente. Se il profilo di certificato deve essere utilizzato per più persone giuridiche, ripeti questo passaggio per aggiungere una riga per ciascuna persona giuridica aggiuntiva.
4. Seleziona **Impostazioni** per aprire la pagina **Impostazioni del profilo certificato**, in cui puoi immettere impostazioni specifiche dell'azienda per il profilo di certificato.

### <a name="certificate-profile-settings"></a>Impostazioni del profilo di certificato

Quando selezioni **Impostazioni** per le righe del profilo di certificato, viene visualizzata la pagina **Impostazioni del profilo certificato**. Questa pagina consente di specificare quali certificati possono essere utilizzati quando il profilo di certificato corrente viene chiamato nei canali di Commerce. È inoltre possibile specificare l'ordine in cui deve essere eseguita la ricerca di certificati.

> [!NOTE]
> Il campo **Priorità** viene impostato automaticamente. Il valore **1** rappresenta la priorità massima. Quando viene aggiunta una nuova riga nella pagina **Impostazioni del profilo certificato**, la priorità di tale riga è impostata su un numero che è uno in più rispetto alla priorità della riga precedente. Per modificare la priorità di una riga specifica, seleziona la riga, quindi seleziona **Sposta su** per aumentare la priorità o **Sposta giù** per diminuire la priorità.

Quando aggiungi una nuova riga alla pagina **Impostazioni del profilo certificato**, imposta i seguenti campi:

- **Tipo di ubicazione** - Seleziona l'ubicazione in cui è archiviato il certificato. Questo campo ha due possibili valori: **Certificato locale** e **Insieme di credenziali delle chiavi**.
- **Certificato insieme di credenziali delle chiavi** - Questo campo è obbligatorio se si imposta il campo **Tipo di ubicazione** su **Insieme di credenziali delle chiavi**. Utilizzalo per specificare un segreto del certificato dell'insieme di credenziali delle chiavi.

    > [!NOTE]
    > Prima di utilizzare un certificato dell'insieme di credenziali delle chiavi nei profili di certificato, assicurati di caricare un certificato nell'archivio dell'insieme di credenziali delle chiavi e segui le istruzioni in [Configurazione del client Azure Key Vault](../../finance/localizations/setting-up-azure-key-vault-client.md).

- **Nome punto vendita** - Questo campo è facoltativo ed è disponibile solo se imposti il campo **Tipo di ubicazione** su **Certificato locale**. Usalo per specificare un nome di punto vendita predefinito che deve essere usato per cercare certificati locali.
- **Ubicazione punto vendita** - Questo campo è facoltativo ed è disponibile solo se imposti il campo **Tipo di ubicazione** su **Certificato locale**. Usalo per specificare un'ubicazione di punto vendita predefinita che deve essere usata per cercare certificati locali.

    > [!NOTE]
    > Il nome e l'ubicazione del punto vendita predefiniti vengono aggiunti per semplificare il processo di ricerca dei certificati locali nel runtime di Commerce. X509StoreProvider ha un elenco di cartelle in cui sono archiviati i certificati. Se il nome e l'ubicazione del punto vendita predefiniti non sono specificati, X509StoreProvider prova a trovare un certificato nelle altre cartelle del relativo elenco.

- **Identificazione personale** - Questo campo è obbligatorio ed è disponibile solo se imposti il campo **Tipo di ubicazione** su **Certificato locale**. Usalo per specificare l'identificazione personale del certificato.
- **Commenti** - Questo campo è facoltativo e consente agli utenti di immettere note.

### <a name="workflow-searching-certificates-in-the-commerce-runtime"></a>Flusso di lavoro: ricerca di certificati nel runtime di Commerce

Di seguito è riportato il flusso di lavoro di base utilizzato per cercare un certificato quando un profilo di certificato viene chiamato nel runtime di Commerce.

1. Il sistema identifica se il profilo di certificato ha impostazioni specifiche dell'azienda per la persona giuridica corrente.
1. Il sistema tenta di trovare il certificato utilizzando i valori nella pagina **Impostazioni del profilo certificato** per la riga in cui il campo **Priorità** è impostato su **1**.

    - Se il campo **Tipo di ubicazione** è impostato su **Insieme di credenziali delle chiavi**, il valore di **Segreto del certificato insieme di credenziali delle chiavi** viene utilizzato per cercare il certificato nella pagina **Parametri insieme di credenziali delle chiavi**. Il certificato viene quindi cercato nell'archivio dell'insieme di credenziali delle chiavi.
    - Se il campo **Tipo di ubicazione** è impostato su **Certificato locale**, X509StoreProvider cerca dapprima il certificato utilizzando il nome e l'ubicazione del punto vendita predefiniti, se questi parametri sono specificati. Quindi cerca in tutte le altre cartelle nel relativo elenco di cartelle.

1. Se il certificato non viene trovato, il processo viene ripetuto per la riga in cui il campo **Priorità** è impostato su **2** e così via.

> [!NOTE]
> Se il profilo di certificato non ha impostazioni per la persona giuridica corrente o se la ricerca del certificato non ha fornito un esito positivo per tutte le righe nella pagina **Impostazioni del profilo certificato**, il certificato non viene trovato.

#### <a name="caching-the-results-of-certificate-searches"></a>Memorizzazione nella cache dei risultati delle ricerche di certificati

I risultati delle ricerche di certificati vengono memorizzati nella cache. Il tempo di scadenza predefinito per una cache è un'ora. Tuttavia, questo tempo può essere personalizzato e può essere impostato su un valore massimo di 24 ore.

### <a name="gradual-update"></a>Aggiornamento graduale

Se viene introdotta una nuova versione del certificato, ma non può essere aggiornata in tutti i punti vendita contemporaneamente, la funzionalità dei profili di certificato abilita l'aggiornamento graduale del certificato.

1. Trova un profilo di certificato e la riga da aggiornare, quindi seleziona **Impostazioni**.
1. Aggiungi una riga e specifica le impostazioni relative all'ultima versione del certificato.
1. Aumenta il valore **Priorità** della nuova riga. Usa il pulsante **Sposta su** per spostare la riga in modo che si trovi sopra la riga della versione precedente dello stesso certificato.

> [!NOTE]
> Nel runtime di Commerce, verrà chiamata dapprima la nuova versione del certificato. Se il certificato non è stato ancora aggiornato in un punto vendita specifico o su un terminale specifico, verrà chiamata la versione precedente.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]