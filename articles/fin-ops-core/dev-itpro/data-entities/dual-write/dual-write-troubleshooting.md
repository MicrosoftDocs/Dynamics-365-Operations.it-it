---
title: Risoluzione dei problemi generali
description: In questo argomento vengono fornite informazioni sulla risoluzione dei problemi generali di integrazione della doppia scrittura tra le app Finance and Operations e Dataverse.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 4b97fffce6d1c3ea143e0d8445769e794d0c46a4
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5566102"
---
# <a name="general-troubleshooting"></a>Risoluzione dei problemi generali

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



In questo argomento vengono fornite informazioni sulla risoluzione dei problemi generali di integrazione della doppia scrittura tra le app Finance and Operations e Dataverse.

> [!IMPORTANT]
> Alcuni problemi che questo argomento tratta potrebbero richiedere il ruolo di amministratore di sistema o le credenziali di amministratore del tenant Microsoft Azure Active Directory (Azure AD). La sezione per ogni problema spiega se sono richiesti ruolo o credenziali specifici.

## <a name="when-you-try-to-install-the-dual-write-package-by-using-the-package-deployer-tool-no-available-solutions-are-shown"></a>Quando si tenta di installare il pacchetto di doppia scrittura utilizzando lo strumento di distribuzione pacchetti, non vengono visualizzate le soluzioni disponibili

Alcune versioni dello strumento di distribuzione dei pacchetti non sono compatibili con il pacchetto della soluzione di doppia scrittura. Per installare correttamente il pacchetto, assicurarsi di utilizzare la [versione 9.1.0.20](https://www.nuget.org/packages/Microsoft.CrmSdk.XrmTooling.PackageDeployment.Wpf/9.1.0.20) o successive dello strumento di distribuzione pacchetti.

Dopo aver installato lo strumento di distribuzione pacchetti, installare il pacchetto della soluzione seguendo questi passaggi.

1. Scaricare l'ultimo file del pacchetto della soluzione da Yammer.com. Dopo aver scaricato il file zip del pacchetto, fare clic con il tasto destro del mouse e selezionare **Proprietà**. Selezionare la casella di controllo **Sblocca**, quindi selezionare **Applica**. Se la casella di controllo **Sblocca** non è visibile, il file zip è già sbloccato ed è possibile saltare questo passaggio.

    ![Finestra di dialogo Proprietà](media/unblock_option.png)

2. Estrarre il file zip del pacchetto e copiare tutti i file nella cartella **Dynamics365FinanceAndOperationsCommon.PackageDeployer.2.0.438**.

    ![Contenuto della cartella Dynamics365FinanceAndOperationsCommon.PackageDeployer.2.0.438](media/extract_package.png)

3. Incollare tutti i file copiati nella cartella **Strumenti** dello strumento di distribuzione pacchetti. 
4. Eseguire **PackageDeployer.exe** per selezionare l'ambiente Dataverse e installare le soluzioni.

    ![Contenuto della cartella Strumenti](media/paste_copied_files.png)

## <a name="enable-and-view-the-plug-in-trace-log-in-dataverse-to-view-error-details"></a><a id="enable-view-trace"></a>Abilitare e visualizzare il log di traccia del plug-in Dataverse per visualizzare i dettagli dell'errore

**Ruolo richiesto per attivare il log di traccia e visualizzare gli errori:** amministratore di sistema

Per attivare il log di traccia, effettuare le seguenti operazioni.

1. Accedere all'app basata su modello in Dynamics 365, aprire la pagina **Impostazioni** e quindi in **Sistema** selezionare **Amministrazione**.
2. Nella pagina **Amministrazione** selezionare **Impostazioni di sistema**.
3. Nella scheda **Personalizzazione**, nella colonna **Analisi attività plug-in e flusso di lavoro personalizzato**, selezionare **Tutto** per abilitare il log di traccia del plug-in. Se si desidera registrare i log di traccia solo quando si verificano eccezioni, è possibile selezionare **Eccezione**.


Per visualizzare il log di traccia, effettuare le seguenti operazioni.

1. Accedere all'app basata su modello in Dynamics 365, aprire la pagina **Impostazioni** e quindi in **Personalizzazione** selezionare **Registro di traccia plug-in**.
2. Trovare i log di traccia dove la colonna **Nome tipo** è impostato su **Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PreCommmitPlugin**.
3. Fare doppio clic su un elemento per visualizzare il registro completo, quindi nella scheda dettaglio **Esecuzione**, esaminare il testo **Blocco messaggio**.

## <a name="enable-debug-mode-to-troubleshoot-live-synchronization-issues-in-finance-and-operations-apps"></a>Abilitare la modalità debug per risolvere i problemi di sincronizzazione in tempo reale nelle app Finance and Operations

**Ruolo richiesto per visualizzare gli errori:** amministratore di sistema. Gli errori di doppia scrittura originati da Dataverse possono apparire nell'app Finance and Operations. In alcuni casi, il testo completo del messaggio di errore non è disponibile perché il messaggio è troppo lungo o contiene informazioni di identificazione personale (PII). È possibile attivare la registrazione dettagliata degli errori seguendo questi passaggi.

1. Tutte le configurazioni del progetto nelle app Finance and Operations hanno una proprietà **IsDebugMode** nella tabella **DualWriteProjectConfiguration**. Aprire la tabella **DualWriteProjectConfiguration** utilizzando il componente aggiuntivo di Excel.

    > [!TIP]
    > Un modo semplice per aprire la tabella è attivare la modalità **Progettazione** nel componente aggiuntivo di Excel e quindi aggiungere **DualWriteProjectConfigurationEntity** al foglio di lavoro. Per ulteriori informazioni, vedere [Aprire i dati della tabella in Excel e aggiornarli tramite il componente aggiuntivo di Excel](../../office-integration/use-excel-add-in.md).

2. Impostare la proprietà **IsDebugMode** su **Sì** per il progetto.
3. Esegui lo scenario che genera errori.
4. I log dettagliati sono disponibili nella tabella DualWriteErrorLog. Per cercare i dati nel browser delle tabelle, utilizzare il seguente URL (sostituire **XXX** come appropriato):

    `https://XXXaos.cloudax.dynamics.com/?mi=SysTableBrowser&tableName=DualWriteErrorLog`

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


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]