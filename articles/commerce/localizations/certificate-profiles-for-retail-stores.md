---
title: Profili certificato definiti dall'utente per i punti vendita al dettaglio
description: In questo articolo viene fornita una panoramica dei profili certificato disponibili in Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 09/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: v-chgriffin
ms.search.validFrom: 2020-10-09
ms.dyn365.ops.version: 10.0.15
ms.search.industry: Retail
ms.search.form: RetailFormLayout, RetailParameters
ms.openlocfilehash: 5baf043a43210d819b605546089e981c86922ca9
ms.sourcegitcommit: 4f28f262cfb8f047cb5c0070261aa0748835e74b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/21/2022
ms.locfileid: "9558439"
---
# <a name="user-defined-certificate-profiles-for-retail-stores"></a>Profili certificato definiti dall'utente per i punti vendita al dettaglio

[!include [banner](../includes/banner.md)]

In questo articolo viene fornita una panoramica dei profili certificato disponibili in Microsoft Dynamics 365 Commerce. Questa funzionalità estende la funzionalità [Gestire segreti per i canali di vendita al dettaglio](../dev-itpro/manage-secrets.md) aggiungendo supporto per i certificati locali.

Quando il POS viene eseguito in modalità offline, non può accedere ai certificati archiviati in Microsoft Azure Key Vault. Al suo posto deve essere utilizzato il certificato locale. Sono supportate le seguenti operazioni:

- Utilizzo di certificati locali in scenari di fallback del Key Vault
- Utilizzo di certificati locali senza Key Vault (ad esempio in un'installazione locale)
- Aggiornamento graduale dei certificati, dove alcuni punti vendita e terminali utilizzano una nuova versione del certificato, ma altri punti vendita e terminali continuano a utilizzare la versione precedente

La funzionalità dei profili di certificato consente di specificare un certificato predefinito e impostare l'ordine in cui viene effettuata la ricerca di certificati nello stesso profilo di certificato. Questa funzionalità fornisce anche un approccio di configurazione simile per i certificati locali e per i certificati dell'insieme di credenziali delle chiavi. Puoi aggiungere impostazioni specifiche dell'azienda per i certificati, ma l'identificatore univoco interaziendale per ogni certificato può essere utilizzato nei canali di Commerce.

### <a name="scenarios"></a>Scenari

La funzionalità dei profili di certificato supporta i seguenti scenari nei canali di Commerce:

- Utilizzo di un certificato locale in scenari di fallback del Key Vault. Di seguito sono riportati alcuni esempi di scenari di fallback:

    - L'archivio dell'insieme di credenziali delle chiavi non è accessibile.
    - Non è stato trovato un certificato nell'archivio dell'insieme di credenziali delle chiavi.
    - Il POS è eseguito in modalità offline.

- Utilizzo di certificati locali ma senza archiviarli nel Key Vault (ad esempio in un'installazione locale).
- Esecuzione di un aggiornamento graduale dei certificati, dove una nuova versione del certificato viene utilizzata solo nei punti vendita o sui terminali in cui la nuova versione è già disponibile.
- Utilizzo dello stesso certificato in più aziende.

## <a name="set-up-certificate-profiles"></a>Impostare profili di certificato

La seguente procedura spiega come impostare profili di certificato.

### <a name="set-up-key-vault"></a>Impostare il Key Vault

È necessario completare i passaggi seguenti prima di poter utilizzare un certificato digitale archiviato in Key Vault.

1. Crea un account di archiviazione Key Vault. Consigliamo di distribuire l'account di archiviazione nella stessa area geografica di Commerce Scale Unit.
1. Carica il certificato digitale nell'account di archiviazione Key Vault.
1. Autorizza l'applicazione Application Object Server (AOS) a leggere i segreti dall'account di archiviazione Key Vault.

Per ulteriori informazioni su come lavorare con Key Vault, vedi [Introduzione ad Azure Key Vault](/azure/key-vault/key-vault-get-started).

### <a name="set-up-system-parameters"></a>Imposta parametri di sistema

Prima di configurare i profili dei certificati nei canali Commerce, è necessario abilitare Commerce per l'utilizzo sia dei certificati archiviati in Key Vault che dei profili dei certificati.

Per configurare i parametri di sistema in Commerce headquarters, segui questi passaggi.

1. Sulla pagina **Parametri di sistema** imposta l'opzione **Usa l'archivio certificati avanzato** su **sì**.
1. Nell'area di lavoro **Gestione funzionalità**, attiva la funzionalità **Profili di certificato definiti dall'utente per punti vendita al dettaglio**.

### <a name="set-up-key-vault-parameters"></a>Impostare i parametri Key Vault

Nella pagina **Parametri Key Vault** è necessario specificare i seguenti parametri per accedere all'archivio Key Vault:

- **Nome** e **Descrizione** – Il nome e la descrizione dell'account di archiviazione Key Vault.
- **URL Key Vault** – L'URL dell'account di archiviazione Key Vault.
- **Client Key Vault** – Un ID client interattivo dell'applicazione Azure Active Directory (Azure AD) associata a un account di archiviazione key vault per scopi di autenticazione. Questo client deve avere accesso per leggere i segreti dall'account di archiviazione.
- **Chiave segreta Key Vault** – Una chiave segreta associata all'applicazione Azure AD utilizzata per l'autenticazione nell'account di archiviazione Key Vault.
- **Nome**, **Descrizione**, e **Riferimento segreto** – Il nome, la descrizione e il riferimento segreto del certificato.

Per ulteriori informazioni, vedi [Impostare il client Key Vault di Azure](../../finance/localizations/setting-up-azure-key-vault-client.md).

### <a name="configure-a-certificate-profile"></a>Configurare un profilo certificato

Per configurare un profilo certificato in Commerce Headquarters, segui questi passaggi.

1. Accedi a **Amministrazione sistema \> Imposta \> Profili certificato**.
1. Nel riquadro azioni seleziona **Nuovo** per creare un record.
1. Immetti i valori nei campi **Profilo certificato**, **Nome**, e **Descrizione**.

    > [!NOTE]
    > Il profilo certificato è un identificatore univoco di un certificato in tutte le società e componenti di Commerce.

1. Nella Scheda dettaglio **Persone giuridiche**, seleziona **Aggiungi** per aggiungere una riga.
1. In **Persona giuridica**, seleziona la persona giuridica (azienda) per la quale deve essere utilizzato il profilo di certificato corrente.

    Se il profilo di certificato deve essere utilizzato per più persone giuridiche, ripeti i passaggi 4 e 5 per aggiungere una riga per ciascuna persona giuridica aggiuntiva.

1. Seleziona **Impostazioni** per aprire la pagina **Impostazioni del profilo certificato**, in cui puoi immettere impostazioni specifiche dell'azienda per il profilo di certificato. Specifica quali certificati possono essere utilizzati quando il profilo di certificato corrente viene chiamato nei canali di Commerce. Aggiungi tutti i certificati di cui hai bisogno e stabilisci le priorità. Se un certificato con priorità più alta non è disponibile, verrà utilizzato il certificato successivo, in base alla priorità. Per ulteriori informazioni, vedi la sezione [Flusso di lavoro: ricerca di certificati in Commerce runtime](#workflow-searching-certificates-in-the-commerce-runtime).

    > [!NOTE]
    > Il campo **Priorità** viene impostato automaticamente. Il valore **1** rappresenta la priorità massima. Quando viene aggiunta una nuova riga nella pagina **Impostazioni del profilo certificato**, la priorità di tale riga è impostata su un numero che è uno in più rispetto alla priorità della riga precedente. Per modificare la priorità di una riga specifica, seleziona la riga, quindi seleziona **Sposta su** per aumentare la priorità o **Sposta giù** per diminuire la priorità.

1. Quando aggiungi una nuova riga alla pagina **Impostazioni del profilo certificato**, imposta i seguenti campi:

    - **Tipo di ubicazione** - Seleziona l'ubicazione in cui è archiviato il certificato. Questo campo ha due possibili valori: **Certificato locale** e **Insieme di credenziali delle chiavi**.
    - **Certificato insieme di credenziali delle chiavi** - Questo campo è obbligatorio se si imposta il campo **Tipo di ubicazione** su **Insieme di credenziali delle chiavi**. Utilizzalo per specificare un segreto del certificato dell'insieme di credenziali delle chiavi.
    - **Nome punto vendita** - Questo campo è facoltativo ed è disponibile solo se imposti il campo **Tipo di ubicazione** su **Certificato locale**. Usalo per specificare un nome di punto vendita predefinito che deve essere usato per cercare certificati locali.
    - **Ubicazione punto vendita** - Questo campo è facoltativo ed è disponibile solo se imposti il campo **Tipo di ubicazione** su **Certificato locale**. Usalo per specificare un'ubicazione di punto vendita predefinita che deve essere usata per cercare certificati locali.

        > [!NOTE]
        > Il nome e l'ubicazione del punto vendita predefiniti vengono aggiunti per semplificare il processo di ricerca dei certificati locali in Commerce runtime. X509StoreProvider ha un elenco di cartelle in cui sono archiviati i certificati. Se il nome e l'ubicazione del punto vendita predefiniti non sono specificati, X509StoreProvider prova a trovare un certificato nelle altre cartelle del relativo elenco. Per ulteriori informazioni sui valori disponibili per il nome del negozio e la posizione del negozio, vedi [Enumerazione StoreName](/dotnet/api/system.security.cryptography.x509certificates.storename) ed [Enumerazione StoreLocation](//dotnet/api/system.security.cryptography.x509certificates.storelocation).

    - **Identificazione personale** - Questo campo è obbligatorio ed è disponibile solo se imposti il campo **Tipo di ubicazione** su **Certificato locale**. Usalo per specificare l'identificazione personale del certificato.

        > [!IMPORTANT]
        > È necessario garantire che l'utente che esegue l'applicazione che deve utilizzare il certificato locale (ad esempio Modern POS in modalità offline) disponga almeno dell'accesso in sola lettura alla chiave privata del certificato.

    - **Commenti** - Questo campo è facoltativo e consente agli utenti di immettere note.

## <a name="workflow-searching-certificates-in-the-commerce-runtime"></a>Flusso di lavoro: ricerca di certificati in Commerce runtime

Di seguito è riportato il flusso di lavoro di base utilizzato per cercare un certificato quando un profilo di certificato viene chiamato in Commerce runtime.

1. Il sistema identifica se il profilo di certificato ha impostazioni specifiche dell'azienda per la persona giuridica corrente.
1. Il sistema tenta di trovare il certificato utilizzando i valori nella pagina **Impostazioni del profilo certificato** per la riga in cui il campo **Priorità** è impostato su **1**.

    - Se il campo **Tipo di ubicazione** è impostato su **Insieme di credenziali delle chiavi**, il valore di **Segreto del certificato insieme di credenziali delle chiavi** viene utilizzato per cercare il certificato nella pagina **Parametri insieme di credenziali delle chiavi**. Il certificato viene quindi cercato nell'archivio dell'insieme di credenziali delle chiavi.
    - Se il campo **Tipo di ubicazione** è impostato su **Certificato locale**, X509StoreProvider cerca dapprima il certificato utilizzando il nome e l'ubicazione del punto vendita predefiniti, se questi parametri sono specificati. Quindi cerca in tutte le altre cartelle nel relativo elenco di cartelle.

1. Se il certificato non viene trovato, il processo viene ripetuto per la riga in cui il campo **Priorità** è impostato su **2** e così via.

> [!NOTE]
> Se il profilo di certificato non ha impostazioni per la persona giuridica corrente o se la ricerca del certificato non ha fornito un esito positivo per tutte le righe nella pagina **Impostazioni del profilo certificato**, il certificato non viene trovato.

### <a name="caching-the-results-of-certificate-searches"></a>Memorizzazione nella cache dei risultati delle ricerche di certificati

I risultati delle ricerche di certificati vengono memorizzati nella cache. Il tempo di scadenza predefinito per una cache è un'ora. Tuttavia, questo tempo può essere personalizzato e può essere impostato su un valore massimo di 24 ore.

## <a name="gradual-update"></a>Aggiornamento graduale

Se viene introdotta una nuova versione del certificato, ma non può essere aggiornata in tutti i punti vendita contemporaneamente, la funzionalità dei profili di certificato abilita l'aggiornamento graduale del certificato.

1. Trova un profilo di certificato e la riga da aggiornare, quindi seleziona **Impostazioni**.
1. Aggiungi una riga e specifica le impostazioni relative all'ultima versione del certificato.
1. Aumenta il valore **Priorità** della nuova riga. Usa il pulsante **Sposta su** per spostare la riga in modo che si trovi sopra la riga della versione precedente dello stesso certificato.
> [!NOTE]
> In Commerce runtime, verrà chiamata dapprima la nuova versione del certificato. Se il certificato non è stato ancora aggiornato in un punto vendita specifico o su un terminale specifico, verrà chiamata la versione precedente.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
