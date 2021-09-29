---
title: Codici a barre GS1 e codici QR
description: Questo argomento descrive come impostare i codici a barre GS1 e i codici QR in modo che le etichette possano essere scansionate in un magazzino.
author: Mirzaab
ms.date: 08/02/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 8f438e18356a6c16cc75bb59153ae7353d984a5a
ms.sourcegitcommit: ecd4c148287892dcd45656f273401315adb2805e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2021
ms.locfileid: "7500332"
---
# <a name="gs1-bar-codes-and-qr-codes"></a>Codici a barre GS1 e codici QR

[!include [banner](../includes/banner.md)]

I lavoratori del magazzino devono spesso completare diversi compiti quando usano uno scanner per dispositivi mobili per registrare i movimenti di un articolo, una paletta o un contenitore. Questi compiti possono includere sia la scansione di codici a barre che l'inserimento manuale di informazioni sul dispositivo mobile. I codici a barre utilizzano un formato specifico dell'azienda che si definisce e si gestisce utilizzando Microsoft Dynamics 365 Supply Chain Management.

I formati del codice a barre GS1 e del codice QR per le etichette di spedizione sono stati sviluppati per fornire uno standard globale per lo scambio di dati tra le aziende. I formati GS1 non solo codificano i dati, ma permettono anche di utilizzare un elenco predefinito di *identificatori di applicazione* per definire il significato dei dati. Lo standard GS1 definisce il formato dei dati e i vari tipi di dati che possono essere utilizzati per codificare. A differenza dei vecchi codici a barre, i codici a barre GS1 possono avere più elementi di dati. Pertanto, una singola scansione del codice a barre può catturare diversi tipi di informazioni sul prodotto, come il lotto e la data di scadenza.

Il supporto GS1 nel Supply Chain Management semplifica drasticamente il processo di scansione nei magazzini dove i pallet e i contenitori sono etichettati utilizzando i codici in formato GS1. I magazzinieri possono estrarre tutte le informazioni necessarie attraverso una singola scansione di un codice a barre GS1. Eliminando la necessità di fare più scansioni e/o inserire manualmente le informazioni, i codici a barre GS1 aiutano a ridurre il tempo associato alle attività. Allo stesso tempo, aiutano anche a migliorare la precisione.

I responsabili della logistica devono impostare l'elenco richiesto di identificatori di applicazioni e associare ciascuno di essi alle voci di menu appropriate del dispositivo mobile. Gli identificatori dell'applicazione possono poi essere usati in tutti i magazzini come impostazione globale per gli spostamenti e l'imballaggio. Pertanto, tutte le etichette di spedizione avranno una forma unificata.

Se non diversamente specificato, questo argomento usa il termine *codice a barre* per riferirsi sia ai codici a barre che ai codici QR.

## <a name="turn-on-the-gs1-feature"></a>Attivare la funzionalità GS1

Prima di poter utilizzare questa funzione, è necessario attivarla nel sistema. Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e abilitarla. Nell'area di lavoro **Gestione funzionalità**, la funzione è elencata nel modo seguente:

- **Modulo:** *Gestione Magazzino*
- **Nome della funzione:** *Scansione di codici a barre GS1*

## <a name="set-up-global-gs1-options"></a>Impostare le opzioni globali GS1

La pagina dei **parametri di gestione del magazzino** fornisce alcune impostazioni che stabiliscono opzioni globali GS1.

Per impostare le opzioni globali GS1, segui questi passi.

1. Fare clic su **Gestione magazzino \> Impostazione \> Parametri di gestione magazzino**.
1. Sulla FastTab **Codici a barre**, imposta i seguenti campi:

    - **Carattere FNC1** - Specifica i caratteri che devono essere interpretati come prefisso quando un codice a barre viene analizzato.
    - **Carattere datamatrix** - Specifica i caratteri che dovrebbero essere interpretati come prefisso quando viene analizzata una datamatrix.
    - **Carattere del codice QR** - Specifica i caratteri che dovrebbero essere interpretati come prefisso quando un codice QR viene analizzato.
    - **Separatore di gruppo** - Specifica il carattere che identifica le parti separate di un codice a barre o di un codice QR.
    - **Lunghezza massima dell'identificatore** - Specifica il numero massimo di caratteri consentito per l'identificatore dell'applicazione.

> [!NOTE]
> I prefissi dicono al sistema che un codice a barre è criptato secondo lo standard GS1. Fino a tre prefissi **(carattere FNC1**, **carattere Datamatrix** e **carattere QR code**) possono essere usati simultaneamente e per vari scopi.

## <a name="gs1-application-identifiers"></a>Identificatori applicazione GS1

I formati GS1 non solo codificano i dati, ma permettono anche di utilizzare un elenco predefinito di identificatori di applicazione per definire il significato dei dati. I responsabili della logistica devono impostare l'elenco richiesto di identificatori di applicazioni e associare ciascuno di essi alle voci di menu appropriate del dispositivo mobile. Gli identificatori possono poi essere usati in tutti i magazzini come impostazione globale per il trasloco e l'imballaggio. Pertanto, tutte le etichette di spedizione avranno una forma unificata.

Il sistema utilizza i dati, specialmente gli identificatori di applicazione predefiniti, per stabilire le regole che devono essere applicate al pezzo di informazione scannerizzato pertinente.

Ogni identificatore di applicazione segnala al sistema che i caratteri successivi nel codice a barre scansionato devono essere considerati un blocco di informazioni criptate. L'impostazione degli identificatori dell'applicazione definisce come il sistema deve interpretare un codice a barre e salvarlo come valore nel sistema.

I responsabili della logistica possono usare identificatori di applicazioni internazionali standard e/o crearne di propri.

### <a name="load-the-standard-application-identifiers"></a>Caricare gli identificatori di applicazioni standard

Per iniziare rapidamente, puoi caricare una lista di identificatori di applicazioni internazionali comuni. Puoi poi estendere o modificare l'elenco in seguito, secondo le tue esigenze.

Per caricare gli identificatori di applicazioni standard, segui questi passi.

1. Vai alla **gestione del magazzino \> Impostazione \> GS1 \> GS1 application identifier**.
1. Nel riquadro azioni, selezionare **Crea impostazione predefinita**.

> [!WARNING]
> Il comando **Crea impostazione predefinita** cancella tutti gli identificatori di applicazione attualmente definiti e li sostituisce con la lista standard. Tuttavia, dopo aver caricato la configurazione predefinita, è possibile personalizzare la lista come si desidera.

### <a name="set-up-custom-application-identifiers"></a>Impostare identificatori di applicazioni personalizzati

Se alcuni o tutti gli identificatori di applicazione che la vostra azienda usa differiscono dal set standard, potete creare i vostri codici da zero o personalizzare il set standard come volete.

Per impostare e personalizzare i vostri identificatori di applicazione GS1, segui questi passi.

1. Vai alla **gestione del magazzino \> Impostazione \> GS1 \> GS1 application identifier**.
1. Eseguire uno dei passaggi riportati di seguito.

    - Per creare un nuovo identificatore: Nel riquadro Azione, selezionare **Nuovo**.
    - Per modificare un identificatore esistente: Seleziona l'identificatore e poi, sul pannello delle azioni, seleziona **Modifica**.

1. Imposta i seguenti campi per l'identificatore nuovo o selezionato:

    - **Identificatore** dell'applicazione - Inserire il codice di identificazione dell'identificatore dell'applicazione. In genere, questo codice è un numero intero di due cifre, ma può essere più lungo. Per i valori decimali, l'ultima cifra indica il numero di cifre decimali. Per maggiori informazioni, vedi la descrizione della casella di controllo **Decimale** più avanti in questo elenco.
    - **Descrizione** - Inserisci una breve descrizione dell'identificatore.
    - **Lunghezza fissa** - Selezionate questa casella di controllo se i valori che vengono analizzati utilizzando questo identificatore di applicazione hanno un numero fisso di caratteri. Deselezionare questa casella di controllo se la lunghezza dei valori è variabile. In questo caso, devi indicare la fine del valore usando il carattere separatore di gruppo che hai specificato nella pagina dei **parametri di gestione del magazzino** .
    - **Lunghezza** - Inserisci il numero massimo di caratteri che possono apparire nei valori che vengono scansionati usando questo identificatore di applicazione. Se la casella di controllo **Lunghezza fissa** è selezionata, ci si aspetta esattamente questo numero di caratteri.
    - **Tipo** - Selezionate il tipo di valore che viene analizzato usando questo identificatore di applicazione *(numerico*, *alfanumerico* o *data*). Per le date, il formato previsto è YYMMDD (senza spazi o trattini).
    - **Decimale** - Seleziona questa casella di controllo se il valore include un punto decimale implicito. Se questa casella è selezionata, il sistema userà l'ultima cifra dell'identificatore dell'applicazione per determinare il numero di cifre decimali. Per esempio, se l'identificatore dell'applicazione è *3205*, le cinque cifre più a destra del valore saranno interpretate come provenienti dopo il punto decimale.

> [!NOTE]
> Il separatore di gruppo che è specificato nella pagina dei **parametri di gestione del magazzino** è opzionale se un valore che è seguito da un identificatore di applicazione ha una lunghezza fissa, o se la sua lunghezza è massimizzata (cioè, se la lunghezza è uguale al valore **Lunghezza** che è impostato per l'identificatore di applicazione).

## <a name="establish-the-generic-gs1-setup"></a>Stabilire la configurazione generica GS1

La configurazione generica GS1 stabilisce un insieme di mappature comuni. Queste mappature corrispondono ad ogni campo di input rilevante nell'applicazione mobile all'identificatore dell'applicazione che controlla come i valori dai codici a barre scansionati devono essere interpretati e memorizzati in quel campo. Per impostazione predefinita, queste impostazioni si applicano a tutte le scansioni per tutte le voci di menu del dispositivo mobile. Tuttavia, possono essere sovrascritti per uno o più campi specifici da una politica GS1 che è assegnata a una voce di menu specifica.

L'impostazione generica di GS1 permette la scansione di un solo valore alla volta. Pertanto, se volete caricare più valori di campo da una singola scansione, dovete impostare una politica GS1 per le voci di menu pertinenti.

Per ulteriori informazioni sulle politiche GS1, vedere la sezione successiva.

### <a name="load-the-standard-generic-gs1-setup"></a>Caricare il setup generico standard GS1

La pagina di **impostazione generica GS1** permette di caricare un set standard di mappature tra i campi del dispositivo mobile e gli identificatori standard dell'applicazione che sono creati dall'impostazione predefinita.

Per stabilire il setup generico di GS1, vai a **Gestione magazzino \> Impostazione \> GS1 \> Impostazione generica GS1**. Poi selezionate **Crea impostazione predefinita** per assegnare automaticamente un identificatore di applicazione adatto ad ogni campo che è tipicamente usato dalle voci di menu dei dispositivi mobili.

> [!WARNING]
> Se esiste già un setup generico GS1, il comando **Crea impostazione predefinita** lo cancella completamente e carica il setup standard.

### <a name="customize-the-standard-generic-gs1-setup"></a>Personalizzare la configurazione standard generica GS1

Per personalizzare la configurazione generica di GS1, segui questi passi.

1. Vai alla **gestione del magazzino \> Impostazione \> GS1 \> Impostazione generica GS1**.
1. Eseguire uno dei passaggi riportati di seguito.

    - Per creare una nuova mappatura: Nel riquadro Azione, selezionare **Nuovo**.
    - Per modificare una mappatura esistente: Seleziona la mappatura e poi, sul pannello delle azioni, seleziona **Modifica**.

1. Imposta i seguenti campi per la mappatura nuova o selezionata:

    - **Campo** - Seleziona o inserisci il campo di input dell'applicazione mobile a cui il valore in entrata dovrebbe essere assegnato. Il valore non è il nome visualizzato dai lavoratori. Invece, è il nome della chiave che viene assegnato al campo nel codice sottostante. L'impostazione predefinita fornisce un insieme di campi che probabilmente saranno utili, e include nomi chiave intuitivi per ogni campo e funzionalità programmate corrispondenti. Tuttavia, potreste dover parlare con i vostri partner di sviluppo per trovare le selezioni corrette per la vostra implementazione.
    - **Identificatore** di applicazione - Selezionare l'identificatore di applicazione applicabile, come definito nella pagina degli **identificatori di applicazione GS1** . L'identificatore stabilisce come il codice a barre sarà interpretato e memorizzato come valore per il campo nominato. Dopo aver selezionato un identificatore di applicazione, il campo **Descrizione** mostra la descrizione di esso.

## <a name="set-up-gs1-policies-that-you-can-assign-to-mobile-device-menu-items"></a>Impostare i criteri GS1 che si possono assegnare alle voci di menu dei dispositivi mobili

Lo scopo dello standard GS1 è di permettere ai lavoratori di caricare diversi valori quando scansionano un solo codice a barre una sola volta. Per raggiungere questo scopo, i manager della logistica devono impostare le politiche GS1 che dicono al sistema come interpretare i codici a barre multi-valore. In seguito, è possibile assegnare criteri alle voci di menu dei dispositivi mobili per controllare come un codice a barre sarà interpretato quando i lavoratori lo scansionano mentre stanno usando una specifica voce di menu.

Se nessun criterio GS1 è assegnato a una voce di menu, il sistema può catturare solo un singolo valore. Questo valore viene applicato all'input dell'app mobile che viene selezionato quando il lavoratore fa la scansione, come specificato dalla configurazione generica GS1. Se un criterio GS1 è assegnato alla voce di menu, il sistema usa ancora la configurazione generica GS1 per mappare il primo valore del codice a barre al campo selezionato. Tuttavia, può poi catturare valori di campo aggiuntivi, come specificato dalla politica applicabile.

### <a name="load-the-standard-specific-gs1-policies"></a>Caricare le politiche GS1 specifiche dello standard

Per iniziare rapidamente, si può caricare un set di politiche GS1. Potete poi estendere o modificare le politiche in seguito, secondo le vostre esigenze.

Per caricare gli identificatori di applicazioni standard, segui questi passi.

1. Vai alla **gestione del magazzino \> Impostazione \> GS1 \> Criteri GS1**.
1. Nel riquadro azioni, selezionare **Crea impostazione predefinita**.

> [!WARNING]
> Il comando **Crea impostazione predefinita** cancella tutte le politiche attualmente definite e le sostituisce con l'insieme standard di politiche. Tuttavia, dopo che la configurazione predefinita è stata caricata, è possibile personalizzare le politiche come si desidera.

### <a name="set-up-custom-specific-gs1-policies"></a>Impostare politiche GS1 specifiche e personalizzate

Per impostare e personalizzare le tue politiche GS1, segui questi passi.

1. Vai alla **gestione del magazzino \> Impostazione \> GS1 \> Criteri GS1**.
1. Eseguire uno dei passaggi riportati di seguito.

    - Per creare una nuova politica: Nel riquadro Azione, selezionare **Nuovo**.
    - Per modificare un criterio esistente: Seleziona il criterio nel pannello dell'elenco.

1. Nell'intestazione della politica nuova o selezionata, imposta i seguenti campi:

    - **Nome** della politica - Inserisci un nome per la politica.
    - **Descrizione** - Inserisci una breve descrizione della politica.

1. Nella FastTab sotto l'intestazione, mappate i nomi dei campi agli identificatori dell'applicazione come richiesto per la politica corrente. Usa i pulsanti sulla barra degli strumenti per aggiungere o rimuovere le righe secondo le tue esigenze. Per ciascuna riga, imposta i seguenti campi:

    - **Campo** - Seleziona o inserisci il campo di input dell'applicazione mobile a cui il valore in entrata dovrebbe essere assegnato. Il valore non è il nome visualizzato dai lavoratori. Invece, è il nome della chiave che viene assegnato al campo nel codice sottostante. L'impostazione predefinita fornisce un insieme di campi che probabilmente saranno utili, e include nomi chiave intuitivi per ogni campo e funzionalità programmate corrispondenti. Tuttavia, potreste dover parlare con i vostri partner di sviluppo per trovare le selezioni corrette per la vostra implementazione.
    - **Identificatore** di applicazione - Selezionare l'identificatore di applicazione applicabile, come definito nella pagina degli **identificatori di applicazione GS1** . L'identificatore stabilisce come il codice a barre sarà interpretato e memorizzato come valore per il campo nominato. Dopo aver selezionato un identificatore di applicazione, il campo **Descrizione** mostra la descrizione di esso.
    - **Ordinamento** - Ogni codice a barre multi-valore include una serie di identificatori di applicazione, ognuno dei quali è seguito da un valore. La politica GS1 applicabile identifica quale identificatore di applicazione è mappato ad ogni campo del database. Tuttavia, se un codice a barre usa lo stesso identificatore di applicazione più di una volta, il sistema usa l'ordine in cui gli identificatori di applicazione appaiono nel codice per mapparli ai campi. Per le righe che condividono un identificatore di applicazione con una o più altre righe, usa questo campo per stabilire l'ordine in cui le righe corrispondenti sono processate. La riga che ha il valore di ordinamento più basso sarà elaborata per prima.

> [!NOTE]
> Per i codici a barre che includono più di un identificatore di applicazione identico, *dovete* usare il campo **Ordinamento** per stabilire l'ordine dei campi.

## <a name="assign-gs1-policies-to-mobile-device-menu-items"></a>Assegnare i criteri GS1 alle voci di menu dei dispositivi mobili

Per impostazione predefinita, tutte le voci di menu dei dispositivi mobili forniscono campi di input dove i lavoratori possono scansionare un singolo valore, secondo la configurazione generica GS1. Se volete che i lavoratori siano in grado di scansionare più di un valore di campo in una singola scansione per qualsiasi voce di menu del dispositivo mobile, dovete assegnare una politica GS1 seguendo questi passi.

1. Passa a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Voci di menu del dispositivo mobile**.
1. Creare o aprire una voce di menu.
1. Nella FastTab **Generale**, imposta il campo **Criteri GS1** sulla policy che si applica alla voce di menu.

## <a name="gs1-setup-example"></a>Esempio di impostazione GS1

Questo esempio si applica a un sistema in cui le opzioni GS1 sono impostate nel modo seguente:

- Nella pagina dei **parametri di gestione del magazzino** , vengono stabilite le seguenti impostazioni globali:

  - **Carattere FNC1:** *\]C1*
  - **Separatore di gruppo:** *\~*

- Nella pagina degli **identificatori di applicazione GS1** , i seguenti identificatori di applicazione sono rilevanti per questo esempio.

    | Identificatore applicazione | descrizione | Lunghezza fissa | Durata | Tipo | Decimali |
    |---|---|---|---|---|---|
    | 01 | GTIN | Selezionate | 14 | Numerico | Liquidata |
    | 10 | Numero batch | Liquidata | 20 | Alfanumerico | Liquidata |
    | 17 | Data di scadenza | Selezionate | 6 | Data | Liquidata |
    | 30 | Quantità di ricezione | Liquidata | 8 | Numerico | Liquidata |

- Nella pagina **di impostazione generica GS1** , le seguenti impostazioni per la politica generica GS1 sono rilevanti per questo esempio.

    | Campo | Identificatore applicazione | descrizione |
    |---|---|---|
    | ItemId | 01 | GTIN |

- Nella pagina dei **criteri GS1** , c'è un criterio in cui il campo del **nome del criterio** è impostato su *Acquisto in ricezione*. Questa polizza include le seguenti linee.

    | Campo | Identificatore applicazione | descrizione | Ordinamento |
    |---|---|---|---|
    | ExpDate | 17 | Data di scadenza | 0 |
    | InventBatchId | 10 | Numero batch | 0 |
    | Quantità | 30 | Quantità di ricezione | 0 |

- Nella pagina delle **voci di menu del dispositivo mobile** , c'è una voce di menu che si chiama *Acquisto di ricezione*. Il suo campo di **politica GS1** è impostato su *Acquisto in ricezione*.

Dopo che la merce per un ordine di acquisto arriva al magazzino, il lavoratore segue questi passi.

1. Sul dispositivo mobile, selezionare la voce di menu **Acquisto in ricezione** .
1. Inserisci il numero dell'ordine di acquisto.
1. Selezionate il campo **Articolo** e scansionate il seguente codice a barre: *\]C10100000012345678\~3030\~10b1\~17220215*.

A causa delle impostazioni stabilite per questo esempio, il sistema analizza il codice a barre scansionato nel modo seguente.

| Chiave di campo | ID domanda di lavoro | Valore | Nota |
|---|---|---|---|
| ItemId | 01 | 00000012345678 | Poiché il lavoratore ha scansionato il campo **Articolo** , il primo valore del codice a barre è mappato su quel campo. La mappatura è presa dal setup generico GS1. |
| Quantità | 30 | 30 | Poiché diversi valori di campo vengono catturati in una singola scansione, questa mappatura e tutte le altre mappature sono prese dalla politica GS1 che è assegnata alla voce del menu **Ricevimento acquisto** . Questo valore è la quantità che è stata ricevuta. |
| InventBatchId | 10 | b1 | Questo valore è l'ID del lotto. |
| ExpDate | 17 | 220215 | Il formato della data è YYMMDD. Pertanto, la data di scadenza è il 15 febbraio 2022. |

La ricevuta viene poi registrata e i valori del database rilevanti vengono inseriti dopo la singola scansione.
