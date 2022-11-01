---
title: Automatizzare le compensazioni dei saldi contabili
description: Questo articolo fornisce informazioni generali sul processo di automazione delle compensazioni dei dati contabili.
author: abruer
ms.date: 9/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: b43eeeefa581b5d8b40dc2cf0187c7c781b18be3
ms.sourcegitcommit: 27ce4fc706100b626b81c3a1023238acd872e76c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/20/2022
ms.locfileid: "9708331"
---
# <a name="automate-ledger-settlements"></a>Automatizzare le compensazioni dei saldi contabili

[!include [banner](../includes/banner.md)]

In Microsoft Dynamics 365 Finance versione 10.0.31, la funzionalità  **Automatizza processo di compensazioni dei saldi contabili** è disponibile nell'area di lavoro  **Gestione funzionalità** . Puoi abilitare la funzionalità **Automatizza processo di compensazioni dei saldi contabili** solo se la funzionalità **Riconoscimento tra liquidazione saldi contabili e chiusura di fine anno** è stata abilitata.

La compensazione dei saldi contabili è il processo di abbinamento tra le transazioni in Dare e in Avere nella contabilità generale. Le organizzazioni che eseguono attività di compensazion dei saldi contabili in base a una pianificazione ricorrente possono ora automatizzare il processo. Durante il processo automatico di compensazione dei saldi contabili, una transazione di addebito e una transazione di accredito possono essere abbinate automaticamente solo se i loro importi nella valuta contabile sono uguali.Ad esempio, un importo di addebito di $1,00 può essere automaticamente abbinato a un importo di accredito di $1,00. Tuttavia, un valore di addebito di $1,00 non può essere automaticamente abbinato a due accrediti, ciascuno dei quali ha un valore di $0,50. La corrispondenza parziale degli importi delle transazioni contabili non è supportata.

L'automazione della compensazione dei saldi contabili definisce i seguenti dettagli:

- Quando vengono eseguite le compensazioni dei saldi contabili
- Quali criteri vengono utilizzati per abbinare gli addebiti e gli accrediti che possono essere compensati automaticamente
- In quale ordine vengono elaborate le informazioni sulla compensazione dei saldi contabili

## <a name="define-the-occurrence-of-ledger-settlements"></a>Definire l'occorrenza delle compensazioni dei saldi contabili

L'automazione della compensazione dei saldi contabili utilizza il framework di automazione dei processi. Diversi processi aziendali utilizzano questo framework per definire la ricorrenza di un processo selezionato. Per le compensazioni dei saldi contabili gli insediamenti contabili, vai a  **Amministrazione di sistema \> Imposta \> Automazioni di processo** o **Contabilità generale \> Impostazione contabilità generale \> Automazioni di processo**.

Innanzitutto, selezona l'opzione  **Crea nuova automazione processi** e seleziona  **Compensazioni dei saldi contabili**. Una procedura guidata consente di eseguire il processo di impostazione dell'automazione.

## <a name="general-page"></a>Pagina Generale

Nella pagina  **Generale**  della procedura guidata, immetti l'occorrenza della compensazione dei saldi contabili che stai creando. Ad esempio, se gli addebiti e gli accrediti corrispondenti vengono liquidati lunedì, inserisci un nome descrittivo come  **LedgerSettle\_Lun**. Il nome che hai inserito viene mostrato nella colonna **Regola di automazione** della pagina **Compensazioni dei saldi contabili** .

Le impostazioni restanti nella pagina sono generiche e definiscono il modello di occorrenza per questa versione delle compensazioni dei saldi contabili. Ad esempio, se un'occorrenza è per lunedì, è possibile definirla in modo che venga eseguita settimanalmente e quindi selezionare il lunedì come giorno della settimana in cui viene eseguita. È inoltre possibile immettere un orario di programmazione anticipato, ad esempio le 2:00, in modo che l'automazione dei processi venga completata prima dell'inizio del giorno lavorativo successivo. Si consiglia di pianificare l'automazione del processo in modo che venga eseguita al di fuori del normale orario di lavoro. In questo modo, contribuisci a ridurre l'impatto sul personale contabile durante la giornata lavorativa.

Per ulteriori informazioni sugli altri campi nella pagina  **Generale** , consultare la documentazione sull'automazione dei processi.

## <a name="ledger-settlements-match-criteria-page"></a>Pagina Criteri di corrispondenza compensazioni dei saldi contabili

La pagina successiva della procedura guidata è a pagina  **Criteri di corrispondenza compensazioni dei saldi contabili** . Viene utilizzata per definire i conti principali inclusi nell'occorrenza di automazione del processo e i criteri utilizzati per determinare la corrispondenza di addebiti e accrediti.

### <a name="account-selection"></a>Selezione del conto

Vengono visualizzati i conti principali definiti in precedenza come conti di compensazione dei saldi contabili per la persona giuridica. (I conti principali vengono definiti come conti di compensazione dei saldi contabili in **Cotabilità generale \> Impostazione contabilità generale \> Parametri di contabilità generale \> Compensazioni dei saldi contabili**.)

### <a name="main-account-and-posting-layer"></a>Conto principale e livello di registrazione

I valori  **Conto principale** e **Livello di registrazione**  sono criteri di corrispondenza obbligatori. I valori **Conto principale** e **Livello di registrazione** delle transazioni Dare e Avere della cpntabilità generale devono essere uguali per essere associati durante il processo automatico di compensazione dei saldi contabili.

### <a name="posting-type"></a>Tipo di registrazione

Seleziona l'opzione **Tipo di registrazione** se le transazioni in Dare e in Avere della contabilità generale devono avere lo stesso tipo di registrazione per essere associate durante il processo automatico di compensazione dei saldi contabili.

### <a name="financial-dimensions"></a>Dimensioni finanziarie

Seleziona l'opzione **Dimensioni finanziarie** se le transazioni in Dare e in Avere della contabilità generale devono avere lo stesso tipo di dimensioni finanziarie per essere associate durante il processo automatico di compensazione dei saldi contabili. Quando questa opzione è selezionata, i criteri per i valori della dimensione finanziaria devono essere selezionati nell'elenco **Dimensioni finanziarie disponibili**. L'elenco **Dimensioni finanziarie disponibili** non contiene la dimensione del conto principale, perché è automaticamente richiesta come parte dei criteri di corrispondenza.

## <a name="view-the-results-of-a-ledger-settlement-automation"></a>Visualizzare i risultati di un'automazione della compensazione dei saldi contabili

Dopo la creazione della serie di automazioni delle compensazioni dei saldi contabili, le occorrenze di ciascuna compensazione dei saldi contabili sono visualizzate nella vista settimanale delle automazioni dei processi. Viene inoltre visualizzato lo stato di ciascuna occorrenza. Vengono utilizzati i seguenti stati:

- **Programmata**  - L'automazione è programmata, ma non è ancora stata eseguita.
- **Esecuzione** – L'automazione è attualmente in esecuzione.
- **Errore**  - L'automazione è stata eseguita, ma si è verificato un errore. È possibile visualizzare gli errori selezionando il pulsante  **Visualizza risultati** .
- **Completata**  - L'automazione è stata eseguita correttamente. È possibile visualizzare i risultati della compensazione sulla pgina **Compensazioni dei saldi contabili**.

Per visualizzare i risultati corrispondenti, vai a **Contabilità generale \> Attività periodiche \> Compensazioni dei saldi contabili**. Il campo **Regola di automazione** campo nella pagina **Compensazioni dei saldi contabili** mostra il nome dell'attività pianificata di compensazione dei saldi contabili automatizzata utilizzata per liquidare la transazione. I tentativi di compensazione non riusciti non aggiorneranno il valore **Regola di automazione**. Se si storna manualmente una transazione che è stata precedentemente liquidata con successo dal processo di automazione, il valore **Regola di automazione** verrà rimosso.

Il campo **Data liquidazione** per i record corrispondenti mostra la data in cui è stato eseguito il processo di automazione.

## <a name="editing-a-ledger-settlement-automation"></a>Modifica di un'automazione di compensazione dei saldi contabili

Il framework di automazione dei processi consente di modificare la serie e le occorrenze create per la compensazione dei saldi contabili. La serie può essere modificata nella pagina  **Automazione processi**  o nella vista settimanale delle automazioni dei processi. Ad esempio, se il responsabile decide di eseguire la compensazione dei saldi contabili il mercoledì anziché il lunedì, può trovare un'occorrenza nella vista settimanale e selezionare  **Visualizza/Modifica - Serie**.

Se si modifica una serie, il sistema richiede di specificare se la modifica deve essere apportata a tutte le ricorrenze esistenti o solo a nuove ricorrenze. Le occorrenze storiche il cui stato è **Completata** o  **Errore**  non verranno modificate.

È inoltre possibile aggiungere una nuova occorrenza o modificare un'occorrenza esistente. Ad esempio, la successiva occorrenza di compensazione dei saldi contabili è programmata per mercoledì 1° gennaio, ma questa data è un giorno festivo. L'occorrenza può essere modificata dalla pagina  **Automazione dei processi**  o nella vista settimanale delle automazioni dei processi. Viene aperta una pagina che mostra i dettagli della programmazione e i criteri di corrispondenza. Qui è possibile modificare l'ora e la data programmate. È inoltre possibile modificare i criteri di corrispondenza, se necessario. 

È anche possibile disabilitare un'occorrenza o una serie. Per disabilitare un'occorrenza e sospenderne l'elaborazione, selezionarla nella vista settimanale delle automazioni dei processi, quindi selezionare  **Disabilita**. È possibile disabilitare una serie nella pagina **Automazione processi** .

## <a name="security-for-ledger-settlement-automation"></a>Sicurezza per l'automazione di compensazione dei saldi contabili

I diritti **Gestisci impostazioni serie di automazione di compensazioni dei saldi contabili** sono stati aggiunti ai ruoli Responsabile della contabilità e Supervisore della contabilità e i diritti **Visualizza impostazioni serie di automazione di compensazioni dei saldi contabili** sono stati aggiunti ai ruoli Contabile, Responsabile contabilità e Supervisore contabilità per le automazioni di compensazione dei saldi contabili. Questi diritti sono le impostazioni di sicurezza predefinite, ma possono essere modificati in base ai requisiti dell'organizzazione.

## <a name="general-ledger-parameters-for-ledger-settlement-automation"></a>Parametri di contabilità generale per l'automazione della compensazione dei saldi contabili

Il campo **Saldo tipico liquidazione** indica l'ordine in cui verrà elaborata la compensazione automatica dei saldi contabili. Per configurare o visualizzare il valore **Saldo tipico liquidazione**, vai a **Contabilità generale \> Imposta \> Parametri di contabilità generale** e seleziona la scheda **Compensazioni dei saldi contabili**.

Se **Addebito** è selezionato, il processo di compensazione dei saldi contabili automatizzato inizia sul lato addebito e ricerca gli accrediti corrispondenti. Se **Accredito** è selezionato, il processo di compensazione dei saldi contabili automatizzato inizia sul lato accredito e ricerca gli addebiti corrispondenti. Questa opzione dovrebbe riflettere il saldo tipico del conto principale.

## <a name="processing-a-ledger-settlement-automation"></a>Elaborazione di un'automazione di compensazione dei saldi contabili

Quando viene eseguita l'automazione, il sistema seleziona le transazioni contabili per i conti principali definiti per le serie di automazione dei processi. Ordina le transazioni per data, utilizzando un intervallo di date dall'inizio dell'anno fiscale alla data in cui viene eseguita l'automazione dei processi. La corrispondenza viene eseguita in base ai criteri di corrispondenza specificati. I valori assoluti degli importi in valuta contabile del debito e del credito devono corrispondere per essere regolati.

Mentre un conto principale viene elaborato da un'occorrenza di un'automazione di compensazione dei saldi contabili, non è possibile visualizzarlo nella pagina **Compensazioni dei saldi contabili**. È necessario attendere il completamento del processo di automazione. È consigliabile pianificare l'automazione del processo in modo che venga eseguita al di fuori dell'orario di lavoro, per evitare conflitti.

Il processo di automazione includerà tutte le transazioni che soddisfano i criteri, ad eccezione delle transazioni che sono state contrassegnate manualmente per la compensazione nella pagina **Compensazioni dei saldi contabili**.

## <a name="reversal-of-transactions-that-are-settled-by-the-automation-process"></a>Storno di transazioni compensate dal processo di automazione

È possibile stornare una compensazione effettuata dal processo di compensazione dei saldi contabili. Quando una transazione che è stata precedentemente liquidata dal processo di automazione viene stornata, il valore **Regola di automazione** verrà rimosso.
