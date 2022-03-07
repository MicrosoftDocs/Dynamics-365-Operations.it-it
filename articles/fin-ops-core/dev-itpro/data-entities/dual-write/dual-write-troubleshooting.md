---
title: Risoluzione dei problemi generali
description: In questo argomento vengono fornite informazioni sulla risoluzione dei problemi generali di integrazione della doppia scrittura tra le app Finance and Operations e Dataverse.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: b4adc2d83667a05d14a26ace23e5bd8026df4b5f
ms.sourcegitcommit: caa41c076f731f1e02586bc129b9bc15a278d280
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2021
ms.locfileid: "7380214"
---
# <a name="general-troubleshooting"></a>Risoluzione dei problemi generali

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

In questo argomento vengono fornite informazioni sulla risoluzione dei problemi generali di integrazione della doppia scrittura tra le app Finance and Operations e Dataverse.

> [!IMPORTANT]
> Alcuni problemi che questo argomento tratta potrebbero richiedere il ruolo di amministratore di sistema o le credenziali di amministratore del tenant Microsoft Azure Active Directory (Azure AD). La sezione per ogni problema spiega se sono richiesti ruolo o credenziali specifici.

## <a name="enable-and-view-the-plug-in-trace-log-in-dataverse-to-view-error-details"></a><a id="enable-view-trace"></a>Abilitare e visualizzare il log di traccia del plug-in Dataverse per visualizzare i dettagli dell'errore

**Ruolo richiesto per attivare il log di traccia e visualizzare gli errori:** amministratore di sistema

Per attivare il log di traccia, effettuare le seguenti operazioni.

1. Accedi all'app customer engagement, apri la pagina **Impostazioni** e quindi sotto **Sistema**, seleziona **Amministrazione**.
2. Nella pagina **Amministrazione** selezionare **Impostazioni di sistema**.
3. Nella scheda **Personalizzazione**, nella colonna **Analisi attività plug-in e flusso di lavoro personalizzato**, selezionare **Tutto** per abilitare il log di traccia del plug-in. Se si desidera registrare i log di traccia solo quando si verificano eccezioni, è possibile selezionare **Eccezione**.


Per visualizzare il log di traccia, effettuare le seguenti operazioni.

1. Accedi all'app customer engagement, apri la pagina **Impostazioni** e quindi sotto **Personalizzazione**, seleziona **Registro di traccia plug-in**.
2. Trovare i log di traccia dove la colonna **Nome tipo** è impostato su **Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PreCommmitPlugin**.
3. Fare doppio clic su un elemento per visualizzare il registro completo, quindi nella scheda dettaglio **Esecuzione**, esaminare il testo **Blocco messaggio**.

## <a name="enable-debug-mode-to-troubleshoot-live-synchronization-issues-in-finance-and-operations-apps"></a>Abilitare la modalità debug per risolvere i problemi di sincronizzazione in tempo reale nelle app Finance and Operations

**Ruolo richiesto per visualizzare gli errori:** amministratore di sistema

Gli errori di doppia scrittura che hanno origine in Dataverse possono apparire nell'app Finance and Operations. Per abilitare la registrazione dettagliata degli errori, segui questi passaggi:

1. Per tutte le configurazioni del progetto nelle app Finance and Operations è presente un flag **IsDebugMode** nella tabella **DualWriteProjectConfiguration**.
2. Apri la tabella **DualWriteProjectConfiguration** utilizzando il componente aggiuntivo di Excel. Per utilizzare il componente aggiuntivo, abilita la modalità di progettazione nel componente aggiuntivo di Excel di Finance and Operations e aggiungi la tabella **DualWriteProjectConfiguration** al foglio. Per ulteriori informazioni, vedi [Visualizzare e aggiornare i dati entità con Excel](../../office-integration/use-excel-add-in.md).
3. Imposta **IsDebugMode** su **Sì** nel progetto.
4. Esegui lo scenario che genera errori.
5. I log dettagliati sono archiviati nella tabella **DualWriteErrorLog**.
6. Per cercare i dati sul browser della tabella, utilizza il seguente collegamento: `https://999aos.cloudax.dynamics.com/?mi=SysTableBrowser&tableName=DualWriteErrorLog`, sostituendo `999` come necessario.
7. Aggiorna di nuovo dopo [KB 4595434](https://fix.lcs.dynamics.com/Issue/Details?kb=4595434&bugId=527820&dbType=3&qc=98e5dc124ac125c57ad633d885ac612aea3ddb8f4abf9d71ab3aa354f2e06cbe), disponibile per gli aggiornamenti della piattaforma 37 e successivi. Se hai installato questa correzione, la modalità di debug acquisirà più registri.  

## <a name="check-synchronization-errors-on-the-virtual-machine-for-the-finance-and-operations-app"></a>Controllare gli errori di sincronizzazione sulla macchina virtuale per l'app Finance and Operations

**Ruolo richiesto per visualizzare gli errori:** amministratore di sistema

1. Accedere a Microsoft Dynamics Lifecycle Services (LCS).
2. Aprire il progetto LCS per cui si è scelto di eseguire il test di doppia scrittura.
3. Selezionare il riquadro **Distribuzione ambienti ospitati nel cloud**.
4. Usare Remote Desktop per accedere alla macchina virtuale (VM) per l'app Finance and Operations. Utilizzare l'account locale mostrato in LCS.
5. Aprire il visualizzatore eventi.
6. Selezionare **Registri applicazioni e servizi \> Microsoft \> Dynamics \> AX-DualWriteSync \> Operativo**.
7. Rivedere l'elenco degli errori recenti.

## <a name="unlink-and-link-another-dataverse-environment-from-a-finance-and-operations-app"></a>Scollegare e collegare un altro ambiente Dataverse da un'app Finance and Operations

**Ruolo richiesto per scollegare l'ambiente:** amministratore di sistema per l'app Finance and Operations o Dataverse.

1. Accedere all'app Finance and Operations.
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

## <a name="how-to-enable-and-save-network-trace-so-that-traces-can-be-attached-to-support-tickets"></a>Come abilitare e salvare la traccia di rete in modo che le tracce possano essere allegate ai ticket di supporto

Il team di supporto potrebbe dover esaminare le tracce di rete per risolvere alcuni problemi. Segui questi passaggi per creare una traccia di rete:

### <a name="chrome"></a>Chrome

1. Nella scheda aperta, premi **F12** o scegli **Strumenti di sviluppo** per aprire gli strumenti di sviluppo.
2. Apri la scheda **Rete** e digita **integ** nella casella di testo del filtro.
3. Esegui il tuo scenario e osserva le richieste registrate.
4. Fai clic con il tasto destro del mouse sulle voci e seleziona **Salva tutto come HAR con contenuto**.

### <a name="microsoft-edge"></a>Microsoft Edge

1. Nella scheda aperta, premi **F12** o scegli **Strumenti di sviluppo** per aprire gli strumenti di sviluppo.
2. Apri la scheda **Rete**.
3. Esegui il tuo scenario.
4. Seleziona **Salva** per esportare i risultati come HAR.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
