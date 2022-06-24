---
title: Risoluzione dei problemi generali
description: In questo articolo vengono fornite informazioni generale sulla risoluzione dei problemi di integrazione della doppia scrittura tra Finanza e operazioni e Dataverse.
author: RamaKrishnamoorthy
ms.date: 04/18/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 620f6f999859eff0ccd8aeb1cff12ddd56fa9926
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8853657"
---
# <a name="general-troubleshooting"></a>Risoluzione dei problemi generali

[!include [banner](../../includes/banner.md)]



In questo articolo vengono fornite informazioni generale sulla risoluzione dei problemi di integrazione della doppia scrittura tra Finanza e operazioni e Dataverse.

> [!IMPORTANT]
> Alcuni problemi che questo articolo tratta potrebbero richiedere il ruolo di amministratore di sistema o le credenziali di amministratore del tenant Microsoft Azure Active Directory (Azure AD). La sezione per ogni problema spiega se sono richiesti ruolo o credenziali specifici.

## <a name="enable-and-view-the-plug-in-trace-log-in-dataverse-to-view-error-details"></a><a id="enable-view-trace"></a>Abilitare e visualizzare il log di traccia del plug-in Dataverse per visualizzare i dettagli dell'errore

I registri di traccia possono essere utili durante la risoluzione dei problemi di sincronizzazione in tempo reale della doppia scrittura tra Finance & Operations e Dataverse. I log possono fornire dettagli specifici ai team che forniscono supporto tecnico e progettuale per Dynamics 365. Questo articolo illustra come abilitare i log di traccia e come visualizzarli. I registri di traccia sono gestiti nella pagina Impostazioni di Dynamics 365 e richiedono privilegi di livello di amministratore per la modifica e la visualizzazione. 

**Ruolo richiesto per attivare il log di traccia e visualizzare gli errori:** amministratore di sistema

### <a name="turn-on-the-trace-log"></a>Attivare il log di traccia
Per attivare il log di traccia, effettuare le seguenti operazioni.

1.  Accedi a Dynamics 365, quindi seleziona **Impostazioni** nella barra di spostamento in alto. Nella pagina del sistema fai clic su **Amministrazione**.
2.  Nella pagina Amministrazione fai clic su **Impostazioni di sistema**.
3.  Seleziona la scheda **Personalizzazione** e il plug-in, e quindi nella sezione del traccia dell'attività del flusso di lavoro personalizzato, modifica il menu a discesa in **Tutto**. Questo traccia tutte le attività e fornisce una serie completa di dati per i team che devono esaminare potenziali problemi.

> [!NOTE]
> Impostando il menu a discesa su **Eccezione** fornirà informazioni di traccia solo quando si verificano eccezioni (errori).

Una volta abilitati, i log di traccia del plug-in continueranno a essere raccolti finché non vengono disattivati manualmente tornando in questa posizione e selezionando **Disattivato**.

### <a name="view-the-trace-log"></a>Visualizzare il log di traccia
Per visualizzare il log di traccia, effettuare le seguenti operazioni.

1. Nella pagina delle impostazioni di Dynamics 365, seleziona **Impostazioni** nella barra di spostamento in alto. 
2. Seleziona **Log di traccia plug-in** nella sezione **Personalizzazioni** della pagina.
3. Puoi trovare voci nell'elenco dei log di traccia, in base al nome del tipo e/o al nome del messaggio.
4. Apri la voce desiderata per visualizzare il log completo. Nella Blocco messaggi nella sezione Esecuzione fornirà le informazioni disponibili per il plug-in. Se disponibili, verranno forniti anche i dettagli dell'eccezione. 

Puoi copiare il contenuto dei log di traccia e incollarlo in un'altra applicazione come Blocco note o altri strumenti per visualizzare registri o file di testo per visualizzare più facilmente tutto il contenuto. 

## <a name="enable-debug-mode-to-troubleshoot-live-synchronization-issues-in-finance-and-operations-apps"></a>Abilitare la modalità debug per risolvere i problemi di sincronizzazione in tempo reale nelle app per finanza e operazioni

**Ruolo richiesto per visualizzare gli errori:** amministratore di sistema

Gli errori di doppia scrittura che hanno origine in Dataverse possono apparire nell'app per finanza e operazioni. Per abilitare la registrazione dettagliata degli errori, segui questi passaggi:

1. Per tutte le configurazioni del progetto nelle app per finanza e operazioni è presente un flag **IsDebugMode** nella tabella **DualWriteProjectConfiguration**.
2. Apri la tabella **DualWriteProjectConfiguration** utilizzando il componente aggiuntivo di Excel. Per utilizzare il componente aggiuntivo, abilita la modalità di progettazione nel componente aggiuntivo di Excel di Finanza e operazioni e aggiungi la tabella **DualWriteProjectConfiguration** al foglio. Per ulteriori informazioni, vedi [Visualizzare e aggiornare i dati entità con Excel](../../office-integration/use-excel-add-in.md).
3. Imposta **IsDebugMode** su **Sì** nel progetto.
4. Esegui lo scenario che genera errori.
5. I log dettagliati sono archiviati nella tabella **DualWriteErrorLog**.
6. Per cercare i dati sul browser della tabella, utilizza il seguente collegamento: `https://999aos.cloudax.dynamics.com/?mi=SysTableBrowser&tableName=DualWriteErrorLog`, sostituendo `999` come necessario.
7. Aggiorna di nuovo dopo [KB 4595434](https://fix.lcs.dynamics.com/Issue/Details?kb=4595434&bugId=527820&dbType=3&qc=98e5dc124ac125c57ad633d885ac612aea3ddb8f4abf9d71ab3aa354f2e06cbe), disponibile per gli aggiornamenti della piattaforma 37 e successivi. Se hai installato questa correzione, la modalità di debug acquisirà più registri.  

## <a name="check-synchronization-errors-on-the-virtual-machine-for-the-finance-and-operations-app"></a>Controllare gli errori di sincronizzazione sulla macchina virtuale per l'app per finanza e operazioni

**Ruolo richiesto per visualizzare gli errori:** amministratore di sistema

1. Accedere a Microsoft Dynamics Lifecycle Services (LCS).
2. Aprire il progetto LCS per cui si è scelto di eseguire il test di doppia scrittura.
3. Selezionare il riquadro **Distribuzione ambienti ospitati nel cloud**.
4. Usare Remote Desktop per accedere alla macchina virtuale (VM) per l'app per finanza e operazioni. Utilizzare l'account locale mostrato in LCS.
5. Aprire il visualizzatore eventi.
6. Selezionare **Registri applicazioni e servizi \> Microsoft \> Dynamics \> AX-DualWriteSync \> Operativo**.
7. Rivedere l'elenco degli errori recenti.

## <a name="dual-write-ui-landing-page-showing-blank"></a>Pagina di destinazione dell'interfaccia utente a doppia scrittura visualizzata vuota
Quando si apre la pagina a doppia scrittura nel browser Microsoft Edge o Google Chrome, la home page non viene caricata e viene visualizzata una pagina vuota o un errore come "Si è verificato un errore".
In Devtools, viene visualizzato un errore nei registri della console:

>bundle.eed39124e62c58ef34d2.js:37 DOMException: impossibile leggere la proprietà 'sessionStorage' da 'Window': accesso negato per questo documento. at t.storeInSessionStorage (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:16:136860 ) at new t (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:69:20103 ) at ci (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:44115 ) at Eo (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:58728 ) at jo (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:65191 ) at Nr (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:84692 ) at Or (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:85076 ) at Ss (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:91750 ) at vs (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:91130 ) at hs (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:90151 )

L'interfaccia utente utilizza l'archiviazione della sessione del browser per memorizzare alcuni valori di proprietà per il caricamento della home page. Affinché ciò funzioni, i cookie di terze parti devono essere consentiti nel browser del sito. L'errore è indicativo del fatto che l'interfaccia utente non è in grado di accedere all'archiviazione della sessione. Ci possono essere due scenari in cui si verifica questo problema:

1.  Stai aprendo l'interfaccia utente in modalità di navigazione in incognito di Edge/Chrome e i cookie di terze parti in modalità di navigazione in incognito sono bloccati.
2.  Hai bloccato del tutto i cookie di terze parti in Edge/Chrome.

### <a name="mitigation"></a>Attenuazione
I cookie di terze parti devono essere consentiti nelle impostazioni del browser.

### <a name="google-chrome-browser"></a>Browser Google Chrome
1 opzione:
1.  Vai alle impostazioni inserendo chrome://settings/ nella barra degli indirizzi, quindi vai su Privacy e sicurezza -> Cookie e altri dati del sito.
2.  Seleziona "Consenti tutti i cookie". Se non desideri farlo, scegli la seconda opzione.

2 opzione:
1.  Vai alle impostazioni inserendo chrome://settings/ nella barra degli indirizzi, quindi vai su Privacy e sicurezza -> Cookie e altri dati del sito.
2.  Se è selezionato "Blocca cookie di terze parti in incognito" o "Blocca cookie di terze parti", vai su "Siti che possono sempre utilizzare i cookie" e fai clic su **Aggiungi**. 
3.  Aggiungi il nome del tuo sito per le app Finance + Operations - https://<tua_istanza_FinOp>.cloudax.dynamics.com. Assicurati di selezionare la casella di controllo "Tutti i cookie, solo su questo sito". 

### <a name="microsoft-edge-browser"></a>Browser Microsoft Edge
1.  Vai in Impostazioni -> Autorizzazioni sito -> Cookie e dati del sito.
2.  Disattiva "Blocca cookie di terze parti".  

## <a name="unlink-and-link-another-dataverse-environment-from-a-finance-and-operations-app"></a>Scollega e collega un altro ambiente Dataverse da un'app per finanza e operazioni

**Ruolo richiesto per scollegare l'ambiente**: amministratore di sistema per l'app per finanza e operazioni o Dataverse.

1. Accedere all'app per finanza e operazioni.
2. Andare a **Aree di lavoro \>Gestione dei dati** e selezionare il riquadro **Doppia scrittura**.
3. Selezionare tutti i mapping in esecuzione e scegliere **Interrompi**.
4. Selezionare **Scollega ambiente**.
5. Selezionare **Sì** per confermare l'operazione.

Ora è possibile collegare un nuovo ambiente.

## <a name="unable-to-view-the-sales-order-line-information-form"></a>Impossibile visualizzare il modulo delle informazioni sulla riga ordine cliente 

Quando si crea un ordine cliente in Dynamics 365 Sales, se si fa clic su **+ Aggiungi prodotti** si potrebbe essere reindirizzati al Dynamics 365 Project Operations modulo della riga ordine. Da quel modulo non è possibile visualizzare il modulo **Informazioni** della riga ordine cliente. L'opzione **Informazioni** non appare nel menu a discesa sotto **Nuova riga ordine**. Ciò accade perché Project Operations è stato installato nell'ambiente.

Per riattivare l'opzione del modulo **Informazioni**, attenersi alla seguente procedura:

1. Passare alla tabella **Riga ordine**.
2. Trovare il modulo **Informazioni** sotto il nodo dei moduli.
3. Selezionare il modulo **Informazioni** e fare clic su **Abilita ruoli di sicurezza**.
4. Cambiare l'impostazione di sicurezza su **Mostra a tutti**.

## <a name="how-to-ensure-data-integration-is-using-the-most-current-finance-and-operations-schema"></a>Come garantire che l'integrazione dei dati utilizzi lo schema per la finanza e le operazioni più aggiornato

Potresti riscontrare problemi con i dati nell'integrazione dei dati se non viene utilizzato lo schema più aggiornato. I passaggi seguenti ti aiuteranno ad aggiornare l'elenco di entità nelle app per la finanza e le operazioni e le entità nell'integratore di dati.

### <a name="refresh-entity-list-in-finance-and-operations-environment"></a>Aggiornare l'elenco di entità nelle app per la finanza e le operazioni
1.  Accedi all'ambiente delle app per la finanza e le operazioni.
2.  Seleziona **Gestione dati**.
3.  In Gestione dati seleziona **Parametri framework**.
4.  Nella pagina **Parametri framework di importazione/esportazione dei dati**, seleziona la scheda **Impostazioni entità**, quindi **Aggiorna elenco entità**. L'aggiornamento potrebbe richiedere più di 30 minuti, a seconda del numero di entità coinvolte.
5.  Passa a **Gestione dati** e seleziona **Entità di dati** per convalidare che le entità previste siano elencate. Se le entità previste non sono elencate, verifica che le entità appaiano nel tuo ambiente per la finanza e le operazioni e ripristina le entità mancanti, se necessario.

#### <a name="if-the-refresh-fails-to-resolve-the-issue-delete-and-re-add-the-entities"></a>Se l'aggiornamento non riesce a risolvere il problema, elimina e aggiungi nuovamente le entità

> [!NOTE]
> Potrebbe essere necessario interrompere tutti i gruppi di elaborazione che stanno utilizzando attivamente le entità prima dell'eliminazione.

1.  Seleziona **Gestione dati** nel tuo ambiente per la finanza e le operazioni e seleziona **Entità di dati**.
2.  Cerca le entità che hanno problemi e annota l'entità di destinazione, la tabella di gestione temporanea, il nome dell'entità e altre impostazioni. Elimina l'entità o le entità dall'elenco.
3.  Seleziona **Nuovo** e aggiungi nuovamente l'entità o le entità utilizzando i dati del passaggio 2. 

#### <a name="refresh-entities-in-data-integrator"></a>Aggiornare le entità nell'integratore di dati
Accedi all'interfaccia di amministrazione di Power Platform e seleziona **Integrazione dati**. Apri il progetto in cui si verificano i problemi e seleziona **Aggiorna entità**.

## <a name="how-to-enable-and-save-network-trace-so-that-traces-can-be-attached-to-support-tickets"></a>Come abilitare e salvare la traccia di rete in modo che le tracce possano essere allegate ai ticket di supporto

Il team di supporto potrebbe dover esaminare le tracce di rete per risolvere alcuni problemi. Segui questi passaggi per creare una traccia di rete:

### <a name="google-chrome-browser"></a>Browser Google Chrome

1. Nella scheda aperta, premi **F12** o scegli **Strumenti di sviluppo** per aprire gli strumenti di sviluppo.
2. Apri la scheda **Rete** e digita **integ** nella casella di testo del filtro.
3. Esegui il tuo scenario e osserva le richieste registrate.
4. Fai clic con il tasto destro del mouse sulle voci e seleziona **Salva tutto come HAR con contenuto**.

### <a name="microsoft-edge-browser"></a>Browser Microsoft Edge

1. Nella scheda aperta, premi **F12** o scegli **Strumenti di sviluppo** per aprire gli strumenti di sviluppo.
2. Apri la scheda **Rete**.
3. Esegui il tuo scenario.
4. Seleziona **Salva** per esportare i risultati come HAR.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
