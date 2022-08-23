---
title: Esercitazione sull'impostazione e l'installazione di Regression Suite Automation Tool
description: Questo articolo è un'esercitazione in cui viene illustrato come impostare e installare lo strumento Regression Suite Automation Tool (RSAT).
author: frankdahl
ms.date: 09/20/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2019-05-30
ms.dyn365.ops.version: AX 7.0.0, Operations
ms.custom: 21761, NotInToc
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: abcb327324829460b0278d95e77b473fa15e363c
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277456"
---
# <a name="set-up-and-install-regression-suite-automation-tool-tutorial"></a>Esercitazione sull'impostazione e l'installazione di Regression Suite Automation Tool

Questo articolo è un'esercitazione che consente di iniziare a utilizzare RSAT e gli strumenti ad esso associati.

[!include [banner](../../includes/banner.md)]

> [!NOTE]
> Utilizzare gli strumenti del browser Internet per scaricare e salvare questa pagina in formato PDF.

## <a name="key-concepts"></a>Concetti chiave

- Comprendere i prerequisiti di impostazione e installazione necessari per le varie applicazioni che supportano lo strumento Regression Suite Automation Tool (RSAT).
- Comprendere il modo in cui la funzionalità Registrazione attività in , insieme a Microsoft Dynamics Lifecycle Services (LCS) e Microsoft Azure DevOps, consente di creare, configurare, eseguire e analizzare test case nonché generare report sugli stessi.
- Consentire agli utenti funzionali di registrare attività aziendali utilizzando Registrazione attività e quindi convertire le registrazioni attività in un gruppo di test automatici, senza dover scrivere codice sorgente.

## <a name="before-you-begin"></a>Prima di iniziare

### <a name="prerequisites"></a>Prerequisiti

- Un ambiente in cui viene eseguito Microsoft Dynamics 365 for Finance and Operations versione 10.0 (aprile 2019) o versione successiva è necessario per questa esercitazione. Per i clienti che utilizzano Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition 7.3, è supportato anche l'aggiornamento 20 della piattaforma (PU20) o un aggiornamento successivo.
- L'utente deve disporre dei diritti di amministratore per l'ambiente.
- È necessario avere accesso ai servizi LCS del tenant del cliente e ad Azure DevOps (in precedenza noto come Microsoft Visual Studio Team Services\[VSTS\]).
- L'utente che crea e gestisce i gruppi di test deve disporre della licenza per Test manager o i piani di test di Azure DevOps. Anche le seguenti licenze forniranno accesso ai piani di test:
    - Licenza di Visual Studio Enterprise
    - Licenza di Visual Studio Test Professional
    - Licenza dei sottoscrittori di MSDN Platforms
- RSAT deve avere accesso all'ambiente di test tramite un Web browser.
- Per generare e modificare i parametri di test, è necessario che Microsoft Excel sia installato.

## <a name="configure-azure-devops"></a>Configura Azure DevOps

### <a name="user-eligibility"></a>Idoneità dell'utente

Assicurarsi che l'utente sia creato in Azure DevOps e che disponga di un livello di sottoscrizione che fornisce accesso ai piani di test di Azure. Una licenza dei piani di test di Azure DevOps è necessaria solo se l'utente creerà e gestirà test case (ovvero, non tutti gli utenti RSAT necessitano questa licenza). Per informazioni sui requisiti di licenza, vedere [Requisiti di licenza](/azure/devops/test/manual-test-permissions#license-requirements).

### <a name="create-a-new-azure-devops-project"></a>Creare un nuovo progetto Azure DevOps

RSAT utilizza Azure Devops per la gestione di test case e gruppi di test, la creazione di report e l'analisi dei risultati dell'esecuzione dei test.

> [!NOTE]
> È possibile utilizzare un progetto Azure DevOps esistente. Tuttavia, se il progetto Azure DevOps esistente è impostato in modo da avere un modello personalizzato, verrà visualizzato un messaggio "Errore di sincronizzazione VSTS" quando si sincronizzano i test case da Modellatore di processi aziendali (BPM) a Azure DevOps (vedere la sezione [Testare la sincronizzazione da BPM a Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops)). Se le seguenti procedure consigliate sono state seguite per il modello personalizzato, sarà possibile sincronizzare i test case ad Azure DevOps (queste procedure consigliate sono elencate nel messaggio di errore).

- Non eliminare i tipi di elementi di lavoro o i campi predefiniti.
- Non eliminare alcun stato di un tipo di elemento di lavoro.
- Non aggiungere alcun campo richiesto a un tipo di elemento di lavoro.

![Messaggio di errore con un elenco di procedure consigliate.](./media/setup_rsa_tool_02.png)

In caso contrario, per questa esercitazione, si consiglia di creare un nuovo progetto Azure DevOps. Per ulteriori informazioni, vedere [Problemi durante la sincronizzazione a BPM utilizzando un modello di elaborazione Azure DevOps (VSTS) personalizzato](https://blogs.msdn.microsoft.com/lcs/2018/11/28/issues-when-syncing-to-bpm-using-a-custom-azure-devops-vsts-process-template/).

1. Aprire l'URL di Azure DevOps (`https://dev.azure.com/<Azure DevOps Name>`).
2. Selezionare **Crea progetto** nell'angolo superiore destro della pagina Azure DevOps.

    ![Pulsante Crea progetto.](./media/setup_rsa_tool_03.png)

3. Completare i seguenti campi, quindi selezionare **Crea**:

    - **Nome progetto**
    - **Controllo versione** - Selezionare **Controllo della versione di Team Foundation**. Da notare che l'opzione predefinita, **Git**, non è supportata.
    - **Processo di elemento di lavoro**

    ![Finestra di dialogo Crea nuovo progetto.](./media/setup_rsa_tool_04.png)

### <a name="create-a-personal-access-token"></a>Creare un token di accesso personale

In questa esercitazione, si utilizzerà il Modellatore di processi aziendali (BPM) LCS per creare una libreria di test case e sincronizzare i propri test case con Azure DevOps. Sarà necessario un token di accesso personale per sincronizzare BPM con Azure DevOps.

1. Selezionare l'icona del profilo nell'angolo superiore destro della pagina per il progetto Azure DevOps e quindi selezionare **Sicurezza**.

    ![Comando Sicurezza.](./media/setup_rsa_tool_05.png)

2. Nel riquadro sinistro, sotto **Sicurezza**, selezionare **Token di accesso personali**. Selezionare quindi **Nuovo token**.

    ![Pulsante Nuovo token nella scheda Token di accesso personali in Impostazioni utente.](./media/setup_rsa_tool_06.png)

3. Completare i seguenti campi, quindi selezionare **Crea**:

    - **Nome**
    - **Scadenza (UTC)** - Selezionare **Definizione personalizzata** quindi utilizzare Selezione data per selezionare l'ultima data disponibile.
    - **Ambiti** - Selezionare l'opzione **Accesso completo**.

    ![Finestra di dialogo Creare un nuovo token di accesso personale.](./media/setup_rsa_tool_07.png)

    > [!NOTE]
    > Annotare il token di accesso personale creato. Questo token sarà necessario quando si imposta la configurazione RSAT.

    ![Token di accesso personale.](./media/setup_rsa_tool_08.png)

## <a name="configure-the-lcs-project"></a>Configurare il progetto LCS

È necessario un progetto Lifecycle Services (LCS) per la libreria di test principale. Il Modellatore di processi aziendali (BPM) LCS viene utilizzato come libreria principale per i test case. BPM è utilizzato per gestire e distribuire le librerie di test nei progetti LCS. Ad esempio, un partner Microsoft o un fornitore di software indipendente (ISV) che crea librerie di test rilascerà test case sotto forma di librerie BPM. In BPM, i test case sono organizzati per processo aziendale. BPM non definisce l'ordine di esecuzione o la frequenza del passaggio dei test. Queste informazioni sono gestite in Azure DevOps, come descritto nelle sezioni successive di questo articolo.  

Per il progetto LC, è possibile utilizzare un progetto partner o di implementazione cliente esistente.

### <a name="update-the-lcs-language"></a>Aggiornare la lingua LCS

> [!NOTE]
> Per visualizzare correttamente i processi aziendali nell'interfaccia utente, la lingua LCS preferita deve essere **Inglese (Stati Uniti)**.

1. Accedere al progetto di implementazione LCS.
2. Selezionare il pulsante **Impostazioni** (il simbolo dell'ingranaggio) nell'angolo superiore destro, quindi selezionare **Preferenza lingua**.

    ![Aggiornare la preferenza della lingua.](./media/setup_rsa_tool_09.png)

3. Nel campo **Lingua preferita** selezionare **Inglese (Stati Uniti)** e quindi **Salva**.

    ![Scheda Preferenza lingua in Impostazioni utente.](./media/setup_rsa_tool_10.png)

### <a name="configure-lcs-to-connect-to-the-azure-devops-project"></a>Configurare LCS per la connessione al progetto Azure DevOps

Se in precedenza è stato creato un nuovo progetto Azure DevOps, configurare il progetto LCS per eseguire la connessione allo stesso. Se il progetto LCS è già connesso al progetto Azure DevOps, è possibile passare alla sezione successiva.

1. Accedere al progetto di implementazione LCS.
2. Selezionare il pulsante **Menu** e quindi selezionare **Impostazioni progetto**.

    ![Comando Impostazioni progetto.](./media/setup_rsa_tool_11.png)

3. Nel riquadro sinistro, selezionare **Visual Studio Team Services**, quindi selezionare **Imposta Visual Studio Team Services**.

    ![Scheda Visual Studio Team Services in Impostazioni progetto.](./media/setup_rsa_tool_12.png)

4. Nel campo **URL sito Azure DevOps** immettere l'URL del sito Azure DevOps. Nel campo **Token di accesso personale**, immettere il token di accesso personale creato in precedenza.

    > [!NOTE]
    > Sebbene VSTS sia ora denominato Azure DevOps, per connettere LCS al progetto Azure DevOps, utilizzare il vecchio URL. Ad esempio, l'URL di Azure DevOps utilizzato in questa esercitazione è `https://dev.azure.com/D365FOFastTrack/`. Tuttavia, nella figura seguente, è `https://D365FOFastTrack.visualstudio.com/`.

    ![Passaggio 1 in Imposta Visual Studio Team Services.](./media/setup_rsa_tool_13.png)

5. Selezionare **Continua**.
6. Nel campo **Progetto Visual Studio Team Services**, selezionare il progetto VSTS sul sito selezionato per eseguire il collegamento al progetto LCS. Per impostazione predefinita, il campo **Modello di processo** è impostato su **Agilità**. Per un modello predefinito, esaminare le Linee guida per le procedure consigliate nella sezione [Creare un nuovo progetto Azure DevOps](#create-a-new-azure-devops-project). Quindi selezionare **Continua**.

    ![Passaggio 2 in Imposta Visual Studio Team Services.](./media/setup_rsa_tool_14.png)

7. Esaminare le impostazioni e quindi selezionare **Salva**.

    ![Passaggio 3 in Imposta Visual Studio Team Services.](./media/setup_rsa_tool_15.png)

8. Selezionare **Autorizza** per autorizzare LCS ad accedere al sito Azure DevOps configurato per conto dell'utente e per attivare le funzionalità che si integrano con VSTS.

    ![Pulsante Autorizza.](./media/setup_rsa_tool_16.png)

9. Viene visualizzato il messaggio "Si sta per essere reindirizzati a un sito esterno per autorizzare LCS a connettersi a Visual Studio Team Services per conto dell'utente. Continuare?" Selezionare **Sì**.

    ![Finestra di messaggio.](./media/setup_rsa_tool_17.png)

10. Selezionare **Accetta**.

    ![Autorizzare l'accesso.](./media/setup_rsa_tool_18.png)

11. Se si è autorizzati come utente, viene visualizzata di nuovo la pagina delle impostazioni del progetto LCS.

    ![Utente autorizzato.](./media/setup_rsa_tool_19.png)

### <a name="create-a-new-bpm-library"></a>Creare nuova libreria BPM

1. Accedere al progetto di implementazione LCS.
2. Selezionare il pulsante **Menu** e quindi selezionare **Modellatore di processi aziendali**.

    ![Comando Modellatore di processi aziendali.](./media/setup_rsa_tool_20.png)

3. Selezionare **Nuova libreria**.

    ![Pulsante Nuova libreria.](./media/setup_rsa_tool_21.png)

4. Nel campo **Nome libreria**, immettere un nome e selezionare **Crea**. Per questa esercitazione, denominare la libreria BPM **RSAT**.

    ![Finestra di dialogo Crea nuova libreria.](./media/setup_rsa_tool_22.png)

5. Aprire la nuova raccolta libreria BPM **RSAT**.
6. Selezionare **Processo aziendale di base di esempio**, quindi a destra, selezionare **Modalità di modifica**.

    ![Pulsante Modalità di modifica.](./media/setup_rsa_tool_23.png)

7. Modificare il valore dei campi **Nome** e **Descrizione** per **creare un prodotto**. Quindi selezionare **Salva**.

    ![Campi Nome e descrizione.](./media/setup_rsa_tool_24.png)

## <a name="environment"></a>Ambiente

### <a name="version-requirement"></a>Requisiti di versione

È necessario un ambiente di test o sandbox in cui viene eseguita la versione 10. Per i clienti che utilizzano la versione 7.3, è supportato anche l'update 20 della piattaforma o un update successivo.

> [!NOTE]
> RSAT deve avere accesso all'ambiente di test tramite un Web browser.

### <a name="user-criteria"></a>Criteri utente

L'utente deve disporre dei diritti di amministratore per questo ambiente.

### <a name="set-up-help-settings-to-connect-with-lcs"></a>Configurare le impostazioni della Guida per connettersi a LCS

Questo passaggio è necessario per eseguire la connessione a LCS di modo che le registrazioni attività possano essere salvate nella libreria BPM appropriata in LCS tramite il client.

1. Avviare il client.
2. Passare ad **Amministrazione sistema \> Impostazioni \> Parametri di sistema**.
3. Nella scheda **Guida**, nel campo **Configurazione Guida di Lifecycle Services**, selezionare il progetto LCS pertinente (**RSAT** per questa esercitazione).

    ![Campo Configurazione Guida di Lifecycle Services nella scheda Guida.](./media/setup_rsa_tool_25.png)

    Le librerie BPM vengono inserite nel progetto LCS appropriato.

4. Selezionare **Salva**.
5. È possibile che sia necessario aggiornare il browser per visualizzare il contenuto della Guida aggiornato.

    ![Notifica sull'aggiornamento del browser.](./media/setup_rsa_tool_26.png)

## <a name="task-recordings"></a>Registrazioni attività

> [!NOTE]
> Verificare che tutte le registrazioni attività siano avviate del dashboard principale. Fare in modo che le singole registrazioni siano brevi e focalizzarsi su un'attività aziendale, ad esempio la creazione di un ordine cliente.

### <a name="create-a-task-recording-and-save-it-to-the-bpm-library"></a>Creare una registrazione attività e salvarla nella libreria BPM

Creare una registrazione attività corrispondente che è possibile collegare al processo aziendale semplice creato nella nuova libreria BPM.

1. Avviare il client.
2. Nel dashboard principale, selezionare il pulsante **Impostazioni** (il simbolo di ingranaggio) e quindi **Registrazione attività**.

    ![Selezionare Registratore attività nel menu Impostazioni.](./media/setup_rsa_tool_27.png)

3. Selezionare **Crea registrazione**.

    ![Pulsante Crea registrazione.](./media/setup_rsa_tool_28.png)

4. Compilare i campi **Nome registrazione** e **Descrizione registrazione** e selezionare **Avvia**.

    ![Campi Nome registrazione e Descrizione registrazione.](./media/setup_rsa_tool_29.png)

5. Registrare i passaggi per la creazione di un prodotto. Al termine, selezionare **Interrompi** per interrompere la registrazione.

    ![Passaggi per la creazione di un prodotto.](./media/setup_rsa_tool_30.png)

6. Selezionare **Salvare in Lifecycle Services**.

    ![Salvare la registrazione delle attività in Lifecycle Services.](./media/setup_rsa_tool_31.png)

    Le informazioni sulla libreria vengono caricate da LCS.

    ![Caricamento delle informazioni sulla libreria.](./media/setup_rsa_tool_32.png)

7. Selezionare la libreria BPM a cui associare la registrazione attività. Per questa esercitazione, selezionare la libreria BPM **RSAT** creata in precedenza e il processo aziendale **Creare un prodotto** sottostante. Selezionare **OK**.

    ![Associare la registrazione attività a una libreria BPM e a un processo aziendale.](./media/setup_rsa_tool_33.png)

    Viene visualizzato il messaggio "Salvataggio in Lifecycle Services completato".

    ![Messaggio su un salvataggio completato in LCS.](./media/setup_rsa_tool_34.png)

8. Per salvare la registrazione attività localmente e quindi aggiornarla a BPM mediante LCS, effettuare le seguenti operazioni:

    1. Al termine della registrazione, selezionare **Salva nel PC**.

        ![Salva nel PC.](./media/setup_rsa_tool_35.png)

    2. Nella barra di notifica del browser, selezionare **Salva** o **Salva con nome** per salvare il file nel computer locale.

        ![Barra di notifica.](./media/setup_rsa_tool_36.png)

    3. Passare alla libreria BPM **RSAT** e selezionare il processo aziendale per salvare la registrazione attività.
    4. Nella scheda **Panoramica**, selezionare **Carica**.

        ![Pulsante Carica.](./media/setup_rsa_tool_37.png)

    5. Selezionare **Sfoglia** e il file .axtr salvato in precedenza. Quindi selezionare **Carica**.

        ![Selezione del file .axtr da caricare.](./media/setup_rsa_tool_38.png)

### <a name="test-the-synchronization-from-bpm-to-azure-devops"></a>Testare la sincronizzazione da BPM a Azure DevOps

Ora che una registrazione attività è associata al processo aziendale, è necessario verificare che il processo aziendale e la registrazione attività associata possano essere sincronizzati con Azure DevOps rispettivamente come funzionalità e test case utilizzando la funzionalità di sincronizzazione VSTS in LCS.

> [!NOTE]
> Il tipo di elemento di lavoro corrispondente creato in Azure DevOps varierà, in base al modello di processo selezionato durante la configurazione del progetto LCS con Azure DevOps, come descritto nella sezione [Creare un nuovo progetto Azure DevOps](#create-a-new-azure-devops-project).

1. Passare alla libreria BPM e aprire la libreria **RSAT** creata in precedenza.
2. Selezionare il pulsante con i puntini di sospensione (**...**) e selezionare **Sincronizzazione VSTS**.

    ![Comando Sincronizzazione VSTS nel menu con i puntini di sospensione.](./media/setup_rsa_tool_39.png)

    Al termine della sincronizzazione di VSTS, sul lato sinistro viene visualizzata una scheda **Requisiti** che include l'elemento di lavoro di Azure DevOps corrispondente.

    > [!NOTE]
    > L'elemento di lavoro creato in Azure DevOps avrà il nome della libreria BPM come prefisso del titolo.

    ![Scheda Requisiti.](./media/setup_rsa_tool_40.png)

3. Aggiorna la pagina.
4. Selezionare il pulsante con i puntini di sospensione (**...**). Verrà visualizzata un'ulteriore opzione, **Test case di sincronizzazione**. Selezionare questa opzione.

    ![Comando Test case di sincronizzazione nel menu con i puntini di sospensione.](./media/setup_rsa_tool_41.png)

    > [!NOTE]
    > Se l'opzione **Test case di sincronizzazione** non è disponibile dopo l'aggiornamento della pagina, passare alla pagina principale per BPM e selezionare **Test case di sincronizzazione** per l'intera libreria. In questo modo, si forza una sincronizzazione per l'intera libreria.
    >
    > ![Selezionare Test case di sincronizzazione per l'intera libreria.](./media/setup_rsa_tool_42.png)

    Al termine della sincronizzazione, viene creato un nuovo test case nella scheda **Requisiti**.

    ![Nuovo test case nella scheda Requisiti.](./media/setup_rsa_tool_43.png)

5. Passare al progetto di Azure DevOps e selezionare **Boards \> Elementi di lavoro**.

    ![Comando Elementi di lavoro in Boards.](./media/setup_rsa_tool_44.png)

6. Verificare che l'elemento di lavoro e il test case creato mediante la sincronizzazione con BPM siano presenti.

    ![Elemento di lavoro e test case.](./media/setup_rsa_tool_45.png)

## <a name="install-and-configure-rsat"></a>Installare e configurare RSAT

RSAT può essere installato in qualsiasi computer in cui è in esecuzione Windows 10 e che può essere connesso all'ambiente tramite un Web browser (Internet Explorer o Google Chrome).

> [!NOTE]
> Prima di installare una nuova versione dello strumento, si consiglia di disinstallare la versione precedente.

### <a name="install-an-authentication-certificate"></a>Installare un certificato di autenticazione

Per abilitare l'autenticazione, è necessario generare e installare un certificato nello stesso computer in cui RSAT è in esecuzione.

#### <a name="generate-a-certificate"></a>Generare un certificato

1. Per generare un file di certificato, aprire una finestra di Microsoft Windows PowerShell come amministratore ed eseguire il comando seguente.

    ```powershell
    $certificate = New-SelfSignedCertificate -dnsname 127.0.0.1 -CertStoreLocation cert:\LocalMachine\My -FriendlyName "D365 Automated testing certificate" -Provider "Microsoft Strong Cryptographic Provider"
    ```

2. Aprire il gestore di certificati immettendo **certlm.msc** nella finestra di dialogo **Esegui** e confermare che il certificato **D365 Automated testing certificate** venga creato in **Personale \> Certificati**.

    > [!NOTE]
    > Assicurarsi di immettere **certlm.msc** e non **certmgr.msc**, poiché i certificati sono archiviati nel computer locale.

    ![Certificato D365 Automated testing certificate.](./media/setup_rsa_tool_46.png)

3. Fare clic con il pulsante destro del mouse sul certificato, quindi selezionare **Copia**.
4. Accedere a **Autorità di certificazione principale attendibili \> Certificati**.

    ![Cartella Certificati nella cartella Autorità di certificazione principale attendibili.](./media/setup_rsa_tool_47.png)

5. Nel menu **Azione**, selezionare **Incolla** per copiare il certificato nella posizione **Autorità di certificazione principale attendibili**.

    ![Comando Incolla del menu Azione.](./media/setup_rsa_tool_48.png)

6. Per ottenere l'identificazione personale del certificato installato, ma senza spazi o caratteri speciali, aprire una finestra di Windows PowerShell come amministratore ed eseguire i comandi seguenti.

    ```powershell
    cd Cert:\LocalMachine\My

    Get-ChildItem | Where-Object { $_.Subject -like "CN=127.0.0.1" }
    ```

    > [!NOTE]
    > Salvare l'identificazione personale, poiché sarà necessaria in seguito quando si aggiorneranno i file .wif per Server oggetti applicativi (AOS) e si imposterà la configurazione RSAT.

#### <a name="configure-the-aos-computer-to-trust-the-connection"></a>Configurare il computer AOS per consentire la connessione

> [!NOTE]
> Se l'ambiente è di livello 2+, l'identificazione personale del certificato deve essere aggiornata nel file wif.config per **tutti** i computer AOS per l'ambiente.

1. Stabilire una connessione Remote Desktop Protocol (RDP) al computer AOS. Le informazioni di accesso sono disponibili nella pagina dei dettagli dell'ambiente in LCS.
2. Aprire Microsoft Internet Information Services (IIS) e trovare **AOSService** nell'elenco dei siti.

    ![AOSService nell'elenco dei siti.](./media/setup_rsa_tool_49.png)

3. Fare clic con il pulsante destro del mouse su **Esplora** per aprire la cartella **\<Drive\>: \\AosService\\Webroot**. Individuare il file **wif.config**.

    ![File Wif.config nella cartella Webroot.](./media/setup_rsa_tool_50.png)

4. Aggiornare il file **wif.config** aggiungendo una nuova voce di autorità per il certificato e il nome dell'autorità, come illustrato nell'esempio riportato di seguito.

    ```Xml
    <issuerNameRegistry type="Microsoft.Dynamics.AX.Security.SharedUtility.AxIssuerNameRegistry,Microsoft.Dynamics.AX.Security.SharedUtility">
        <authority name="CN=127.0.0.1">
            <keys>
                <add thumbprint="xxxxxxxxxxxxxxxxxxxx" />
                <add thumbprint="xxxxxxxxxxxxxxxxxxxx" />
            </keys>
            <validIssuers>
                <add name="CN=127.0.0.1" />
            </validIssuers>
        </authority>
    ```

    > [!NOTE]
    > Se più utenti utilizzano la stessa applicazione, ogni utente deve generare identificazioni digitali distinte e ognuna di queste identificazioni deve essere aggiunta nella sezione **\<keys\>**.

5. Se vi sono più computer AOS, ripetere i passaggi da 3 a 4 per ogni computer aggiuntivo.

    > [!NOTE]
    > A differenza degli ambienti di livello 2 meno recenti, quelli nuovi sono distribuiti con due istanze AOS.

6. Eseguire **iisreset** su tutti i computer AOS.

    > [!NOTE]
    > Se non si dispone dei diritti di amministratore per eseguire **iisreset** in un computer di livello 1, nella pagina Dettagli ambiente in LCS selezionare Gestisci > Riavvia servizi.

#### <a name="tier-2-environment"></a>Ambiente di livello 2+

Se si utilizza un ambiente di livello 2+ (Sandbox test di accettazione standard o superiore), verificare o configurare l'impostazione del Registro di sistema seguente nel computer in cui RSAT è installato. Questo passaggio è necessario in quanto consente di evitare errori di connessione RSAT o di autenticazione.

```PowerShell
if ((Test-Path HKLM:\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319))
{
    Set-ItemProperty HKLM:\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319 -Name SchUseStrongCrypto -Value 1 -Type dword -Force -Confirm:$false
}
```

### <a name="install-rsat"></a>Installare RSAT

1. Andare a <https://www.microsoft.com/download/details.aspx?id=57357> e selezionare **Scarica**.
2. Selezionare tutti i file e quindi **Avanti**.

    ![Selezionare tutti i file.](./media/setup_rsa_tool_51.png)

3. Fare doppio clic sul pacchetto .msi per l'eseguire il programma di installazione. Quindi, al termine dell'installazione, selezionare **Fine**.

    ![File del programma di installazione di RSAT.](./media/setup_rsa_tool_52.png)

### <a name="install-selenium-and-browser-drivers"></a>Installare i driver del browser e Selenium

Nelle versioni precedenti di RSAT, si dovevano installare i driver del browser e Selenium. Non è più necessario installare questi driver poiché vengono installati automaticamente.

1. La prima volta che si apre RSAT, viene richiesto di scaricare e installare automaticamente Selenium. Per ulteriori informazioni, vedere la sezione [Configurare RSAT](#configure-rsat).
2. Prima di eseguire un test case, viene richiesto di scaricare e installare automaticamente il driver del browser corrispondente al browser predefinito selezionato nella configurazione RSAT. Per ulteriori informazioni, vedere la sezione [Caricare ed eseguire test case](#load-and-run-test-cases).

## <a name="get-started-with-rsat"></a>Introduzione a RSAT

### <a name="create-a-test-plan-and-test-suites"></a>Creare un piano di test e gruppi di test

1. Passare al progetto Azure DevOps e selezionare **Piani di test**.

    ![Comando Piani di test.](./media/setup_rsa_tool_53.png)

2. Selezionare **Nuovo piano di test**.

    ![Pulsante Nuovo piano di test.](./media/setup_rsa_tool_54.png)

3. Completare il campo **Nome** e selezionare **Crea**. Per questa esercitazione, denominare il piano di test **Piano di test RSAT**.

    ![Finestra di dialogo Nuovo piano di test.](./media/setup_rsa_tool_55.png)

4. Selezionare il segno **+** e quindi selezionare **Gruppo statico** per creare un gruppo statico sotto il nuovo piano di test. Denominare il nuovo gruppo di test **T01 - Produzione per scorte**.

    > [!NOTE]
    > È inoltre possibile creare un gruppo basato su query, se i nuovi test case da BPM devono essere inseriti automaticamente nel gruppo di test RSAT.

    ![Creazione di un gruppo statico.](./media/setup_rsa_tool_56.png)

### <a name="attach-test-cases-to-test-suites"></a>Associare test case a gruppi di test

1. Selezionare **Aggiungi esistente** a destra per aggiungere case test esistenti al gruppo di test.

    ![Pulsante Aggiungi esistente.](./media/setup_rsa_tool_57.png)

2. Nella pagina **Aggiungi test case a gruppo** selezionare **Esegui query**, quindi selezionare il test case da aggiungere al gruppo di test. Per questa esercitazione, selezionare il test case **Creare un nuovo prodotto**. Selezionare quindi **Aggiungi test case** nell'angolo in basso a destra della pagina (questo pulsante non è presente nell'illustrazione seguente).

    ![Pulsante Esegui query.](./media/setup_rsa_tool_58.png)

    Il test case viene aggiunto al gruppo di test **T01- Produzione per scorte**.

    ![Test case aggiunto al gruppo di test.](./media/setup_rsa_tool_59.png)

### <a name="configure-rsat"></a>Configura RSAT

1. Aprire RSAT.

    ![Icona RSAT.](./media/setup_rsa_tool_60.png)

2. Viene visualizzato il messaggio di avviso "Per Regression Suite Automation Tool è necessario Selenium. Scaricare e installare automaticamente Selenium ora?". Selezionare **Sì**.

    ![Messaggio che avverte che Regression Suite Automation Tool richiede Selenium.](./media/setup_rsa_tool_61.png)

3. Fare clic sul pulsante **Impostazioni** (il simbolo di ingranaggio) nell'angolo superiore destro e quindi, nella finestra di dialogo visualizzata, riempire i seguenti campi:

    - **URL di Azure DevOps** - Immettere l'URL del progetto Azure DevOps, ad esempio `https://yourAzureDevOpsUrlHere.visualStudio.com`.
    - **Token di accesso** - Immettere il token di accesso che consente la connessione dello strumento a Azure DevOps. Utilizzare il token di accesso personale creato in precedenza in questa esercitazione. Per ulteriori informazioni, vedere [Autenticare l'accesso con token di accesso personali](https://www.visualstudio.com/docs/setup-admin/team-services/use-personal-access-tokens-to-authenticate).
    - **Nome progetto** - Selezionare il nome del progetto Azure DevOps.
    - **Piano di test** - Selezionare il piano di test Azure DevOps che contiene i test case. Per ulteriori informazioni, vedere [Creare piani di test e gruppi di test](https://www.visualstudio.com/docs/test/manual-exploratory-testing/getting-started/create-a-test-plan). Dopo avere selezionato un piano di test, selezionare **Test connessione** per testare la connessione a Azure DevOps.
    - **Nome host** - Immettere il nome host dell'ambiente di test, ad esempio **\<myaos\>.cloudax.dynamics.com**. Non includere il prefisso **http://** o **https://**.
    - **Nome host SOAP** - Immettere il nome host SOAP dell'ambiente di test. In genere, il nome host SOAP corrisponde al nome host, ma presenta il suffisso **soap**. Ad esempio: **\<myaos\>soap.cloudax.dynamics.com**. Non includere il prefisso **http://** o **https://**.

        > [!NOTE]
        > Per trovare il nome host e il nome host SOAP, aprire Gestione IIS, fare clic con il pulsante destro del mouse su **Siti \> AOSService** e selezionare **Modifica binding**. I valori nella colonna **Nome host** indicano il nome host e il nome host SOAP (il nome host SOAP ha il suffisso **soap** nell'URL).

        ![Nome host e nome host SOAP nella colonna Nome host.](./media/setup_rsa_tool_63.png)

    - **Nome utente amministratore** - Immettere l'indirizzo di posta elettronica di un utente amministratore nell'ambiente di test.
    - **Identificazione personale** - Immettere l'identificazione personale del certificato di autenticazione come descritto in precedenza in questa esercitazione.
    - **Directory di lavoro** - Specificare il percorso della cartella per l'archiviazione dei file di automazione dei test, ad esempio i file di dati di test di Excel. Ad esempio, immettere o selezionare **C:\\ITemp\\RegressionTool**.

        > [!NOTE]
        > Se il nome della cartella presenta degli spazi, l'esecuzione avrà esito negativo in quanto la cartella non viene trovata. Questo problema è noto e dovrebbe risultare risolto nell'ultima versione dello strumento.

    - **Browser predefinito** - Selezionare **Internet Explorer** o **Google Chrome**. Verificare che i driver del browser siano installati.
    - **Timeout esecuzione dei test** - Specificare il timeout, in minuti, per le esecuzioni dei test. Alla scadenza del timeout, tutte le finestre attive vengono chiuse e i test case in sospeso hanno esito negativo.
    - **Tiemout azione dei test** - Questo campo controlla il timeout, in minuti, per le richieste del server dell'ambiente di Finance and Operations. In genere, il valore predefinito (2 minuti) è sufficiente. Tuttavia, per gli ambienti più lenti, è possibile aumentare il valore se si verificano errori relativi ai timeout.
    - **Nome società** - Immettere il nome della società da utilizzare come società predefinita quando vengono creati i file di parametri di Excel. È possibile modificare la società in seguito modificando il file di parametri di Excel.

    ![Finestra di dialogo Impostazioni.](./media/setup_rsa_tool_62.png)

4. Selezionare **Applica** per applicare e salvare le impostazioni.

    Per salvare le impostazioni correnti in un file di configurazione nel computer, selezionare **Salva con nome**. Per ripristinare le impostazioni da un file di configurazione nel computer, selezionare **Apri**.

5. Selezionare **Chiudi** per chiudere la finestra di dialogo.

### <a name="load-and-run-test-cases"></a>Caricare ed eseguire test case

1. Selezionare **Carica** per caricare il piano di test **Piano di test RSAT** dal progetto. Azure DevOps.

    ![Pulsante Carica.](./media/setup_rsa_tool_64.png)

2. Selezionare il test case **Creare un nuovo prodotto** nel gruppo di test e selezionare **Nuovo \> Genera file di esecuzione di test e di parametri**.

    ![Comando Genera file di esecuzione di test e di parametri nel menu Nuovo.](./media/setup_rsa_tool_65.png)

    Il file di parametri di Excel viene creato nella cartella locale specificata nella configurazione RSAT (ad esempio **C:\\Temp\\RegressionTool**).

    ![File di parametri di Excel creato.](./media/setup_rsa_tool_66.png)

3. Per salvare i file di parametri, selezionare **Carica**. I file di automazione di test di tutti i test case selezionati vengono caricati in Azure DevOps per un utilizzo futuro (tali file includono i file di parametri di test di Excel).

    In questo modo, è possibile selezionare **Carica** per caricare i file di parametri (nonché i file di automazione) del test case direttamente da Azure DevOps. Non è necessario generare nuovamente i file di parametri. Questo approccio risulterà importante in seguito, quando si desidera mantenere le modifiche nel file di parametri ed evitare che vengano sovrascritte.

4. Per verificare che i file di automazione e di parametri vengono salvati in Azure DevOps, accedere al progetto Azure DevOps selezionare **Boards \> Elementi di lavoro**, quindi selezionare il test case **Creare un nuovo prodotto**. Nella scheda **Allegati**, dovrebbero essere visualizzati quattro file:

    - **.cs** - File di automazione C\#
    - **.dll** - File di automazione compilato come assembly
    - **.xlsx** – File di parametri di Excel
    - **.xml** - File di registrazione

    ![File nella scheda Allegati.](./media/setup_rsa_tool_67.png)

5. Selezionare il test case da eseguire e selezionare **Esegui**.

    > [!NOTE]
    > Prima di eseguire i test case, se si utilizza Internet Explorer come browser, verificare che la risoluzione dello schermo sia **100%** in **Impostazioni di visualizzazione di Windows \> Ridimensionamento e layout**. Se non è possibile modificare questa impostazione su una macchina virtuale (VM), modificarla nel client (computer portatile) utilizzato per accedere alla macchina virtuale. Le impostazioni di risoluzione verranno ereditate dalle impostazioni di visualizzazione della macchina virtuale.

    ![Risoluzione dello schermo impostata su 100%.](./media/setup_rsa_tool_68.png)

6. Se i driver del browser non sono installati nel sistema, verrà visualizzato il messaggio di avviso "Per eseguire questa operazione è necessario il driver \<browser name\>. Scaricare e installare automaticamente il driver ora? Selezionare **Sì**.

    ![Messaggio di avviso per Internet Explorer.](./media/setup_rsa_tool_69.png)

    ![Messaggio di avviso per Chrome.](./media/setup_rsa_tool_70.png)

    > [!NOTE]
    > Se si utilizza Chrome come browser e viene visualizzato un messaggio di errore in cui viene indicato che la sessione non è stata creata in quanto la versione di Chrome non è corretta, scaricare il driver di Chrome più recente da <http://chromedriver.chromium.org/downloads> nella cartella **C:\\Programmi (x86)\\Regression Suite Automation Tool\\Common\\External\\Selenium**.

    ![Messaggio di errore per Chrome.](./media/setup_rsa_tool_71.png)

    Il test case viene eseguito e il campo **Risultato** aggiornato.

    ![Campo Risultato aggiornato.](./media/setup_rsa_tool_72.png)

    Se si è svolta questa esercitazione come descritto, il test case **Creare un nuovo prodotto** avrà esito negativo poiché l'attività registrata per la creazione di un prodotto ha salvato il nome del prodotto come valore hardcoded. Se si esegue di nuovo lo stesso test case, dovrebbe essere visualizzato un messaggio di errore in quanto il prodotto esiste già.

    ![Campo Risultato impostato su Non superato.](./media/setup_rsa_tool_72.png)

### <a name="view-the-test-results"></a>Visualizzare i risultati dei test

1. Fare doppio sul test case non riuscito.

    Viene visualizzato un messaggio di errore.

    ![Messaggio di errore.](./media/setup_rsa_tool_73.png)

2. Selezionare **Dettagli** per visualizzare l'intero messaggio di errore.

    ![Messaggio di errore completo.](./media/setup_rsa_tool_74.png)

3. Per visualizzare una versione dettagliata del messaggio di errore in Azure DevOps, selezionare **Apri in Azure DevOps**. In Azure DevOps, è possibile visualizzare lo stato del test case e del messaggio di errore dettagliato.

    ![Messaggio di errore dettagliato in Azure DevOps.](./media/setup_rsa_tool_75.png)

4. Per visualizzare i risultati dei test direttamente nel progetto Azure DevOps, passare a **Piani di test \> Piani di test \> Esecuzioni**. Fare doppio clic sull'esecuzione di test per la quale si desidera visualizzare ulteriori dettagli.

    ![Elenco delle esecuzioni di test in Azure DevOps.](./media/setup_rsa_tool_76.png)

5. La scheda **Riepilogo esecuzione** indica che il test case non è riuscito, ma non fornisce il messaggio di errore vero e proprio. Per visualizzare il messaggio di errore dettagliato, selezionare la scheda **Risultati test**.

    ![Scheda Riepilogo esecuzione.](./media/setup_rsa_tool_77.png)

    La scheda **Risultati test** fornisce informazioni sul test case, nonché il risultato e il messaggio di errore.

    ![Scheda Risultati test.](./media/setup_rsa_tool_78.png)

6. Fare doppio clic sul record pertinente per visualizzare il messaggio di errore dettagliato.

    ![Messaggio di errore dettagliato.](./media/setup_rsa_tool_79.png)

    > [!NOTE]
    > Tutti i messaggi di errore sono disponibili localmente in **C:\\Utenti\\\$YourUserName\\AppData\\Roaming\\regressionTool\\errormsg-.txt**.

7. È inoltre possibile esportare i risultati delle esecuzioni dei test dal livello piano di test selezionando **Esporta**.

    ![Esportare un piano di test.](./media/setup_rsa_tool_80.png)

### <a name="modify-the-excel-parameter-file"></a>Modificare il file di parametri di Excel

1. Aprire RSAT.
2. Selezionare il test case derivati, quindi selezionare **Modifica** per aprire il file di parametri di Excel.

    Nel foglio **EcoResProductCreate**, notare che il valore del campo **Numero prodotto** è hardcoded. È necessario aggiornare questo campo a un nuovo numero di prodotto prima di eseguire di nuovo il test case.

3. Per generare un numero di prodotto univoco per ogni esecuzione senza dover riaprire il file di parametri di Excel e aggiornare manualmente il numero di prodotto ogni volta, utilizzare la seguente formula di Excel.

    ```vba
    ="RSAT_"&TEXT(NOW(),"yyymmddhhmm")
    ```

    > [!NOTE]
    > Oltre alla scheda **Generale**, il file di parametri di Excel contiene una scheda dati per ogni pagina modulo visitata dal test case.

    ![Campo Numero prodotto.](./media/setup_rsa_tool_81.png)

4. Selezionare **Salva**, quindi chiudere la cartella di lavoro di Excel.
5. Selezionare **Carica** per salvare il file di parametri di Excel in Azure DevOps.

    ![Messaggio che indica il completamento del caricamento.](./media/setup_rsa_tool_82.png)

    > [!NOTE]
    > Per eseguire test case in un contesto utente specifico, immettere l'ID di posta elettronica dell'utente nel campo **Verifica utente** della scheda **Generale** del file di parametri di Excel. Nell'ultima versione di RSAT, il layout dei campi nel file di parametri di Excel è stato aggiornato, ma il concetto è invariato.
    >
    > ![Campo Verifica utente.](./media/setup_rsa_tool_83.png)

### <a name="validate-the-results"></a>Convalidare i risultati

- Selezionare **Esegui** per eseguire di nuovo il test case e verificare che ha avuto esito positivo. È possibile visualizzare i risultati dei test come descritto nella sezione [Visualizzare i risultati dei test](#view-the-test-results).

    ![Campo Risultato impostato su Superato.](./media/setup_rsa_tool_84.png)

### <a name="chaining-of-test-cases"></a>Concatenamento dei test case

Una funzionalità importante di RSAT è il concatenamento dei test case (ovvero la capacità di un test di passare valori ad altri test). I test case vengono eseguiti in base all'ordine definito nel piano di test di Azure DevOps (questo ordine può essere aggiornato nello strumento di test stesso). Di conseguenza, se si desidera passare variabili da un test case a un altro, è molto importante che i test siano nell'ordine corretto.

In questa sezione, si creerà una variabile salvata nel primo test case, si creerà un secondo test case e quindi si passerà la variabile salvata dal primo test case al secondo test case. Successivamente si eseguiranno i test case come test case concatenato in RSAT.

#### <a name="modify-an-existing-task-recording-to-create-a-saved-variable"></a>Modificare una registrazione attività esistente per creare una variabile salvata

1. Avviare il client.
2. Selezionare il pulsante **Impostazioni** (il simbolo di ingranaggio) e quindi **Registrazione attività**.
3. Selezionare **Modifica registrazione**.

    ![Pulsante Modifica registrazione.](./media/setup_rsa_tool_85.png)

4. Selezionare **Aprire da Lifecycle Services**

    ![Pulsante Aprire da Lifecycle Services.](./media/setup_rsa_tool_86.png)

5. Selezionare **Selezionare la libreria di Lifecycle Services**.

    ![Pulsante Selezionare la libreria di Lifecycle Services.](./media/setup_rsa_tool_87.png)

    Le librerie BPM vengono caricate da LCS.

    ![Caricamento delle librerie BPM.](./media/setup_rsa_tool_88.png)

6. Dopo il caricamento delle librerie BPM da LCS, selezionare la libreria BMP **RSAT** e il processo aziendale **Creare un nuovo prodotto** a cui la registrazione attività era associata. Selezionare **OK**.

    ![Selezionare una libreria BPM e un processo aziendale.](./media/setup_rsa_tool_89.png)

7. Il nome della registrazione attività appropriata viene immesso nel campo **Nome registrazione**. Selezionare **Avvia**.

    ![Nome della registrazione attività nel campo Nome registrazione.](./media/setup_rsa_tool_90.png)

8. Andare a **Gestione informazioni sul prodotto \> Prodotti** e selezionare **Nuovo** per aprire la pagina in cui la registrazione attività originale, **Creare un prodotto**, è stata registrata.
9. Selezionare **Inserisci passaggio**.

    > [!NOTE]
    > Il nuovo passaggio viene inserito **dopo** il passaggio selezionato nel riquadro.

    ![Pulsante Inserisci passaggio.](./media/setup_rsa_tool_91.png)

10. Fare clic con il pulsante destro del mouse sul campo **Numero prodotto** e selezionare **Registrazione attività \> Copia**.

    ![Comando Copia.](./media/setup_rsa_tool_92.png)

11. Un nuovo passaggio viene aggiunto nel riquadro. Annotare il valore nel campo **Numero prodotto**, poiché sarà necessario in seguito.

    ![Nuovo passaggio aggiunto.](./media/setup_rsa_tool_93.png)

12. Selezionare **Fine modifica**.
13. Selezionare **Salvare in Lifecycle Services** e associare la nuova registrazione attività alla stessa libreria BPM e allo stesso processo aziendale a cui la registrazione attività originale era associata. Per ulteriori informazioni, vedere la sezione [Creare una registrazione attività e salvarla nella libreria BPM](#create-a-task-recording-and-save-it-to-the-bpm-library).
14. Passare alla libreria BPM e selezionare **Test case di sincronizzazione** per sovrascrivere la registrazione attività associata al test case in Azure DevOps, come descritto nella sezione [Testare la sincronizzazione da BPM a Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops).
15. Aprire RSAT e selezionare **Carica** per caricare di nuovo tutti i test case nel gruppo di test. È necessario rigenerare i file di automazione e di parametri per il test case appropriato selezionando il test case e quindi **Nuovo \> Genera file di esecuzione di test e di parametri**, come descritto nella sezione [Caricare ed eseguire test case](#load-and-run-test-cases).

    > [!NOTE]
    > Se il file di parametri di Excel era aperto, la rigenerazione avrà esito negativo. Di conseguenza, verificare che il file di parametri di Excel per il test case venga chiuso prima di generare il nuovo file di parametri di Excel.

16. Selezionare **Modifica** per aprire il nuovo file di parametri di Excel. Verrà visualizzata una nuova voce **Variabile salvata** nella riga 9. Questa variabile, **{{ecoResProductCreate\_Identification\_ProductNumber\_Copy}}**, viene salvata nel file XML della registrazione attività e può essere utilizzata nei test successivi.

    ![Voce di variabile salvata.](./media/setup_rsa_tool_94.png)

#### <a name="create-a-new-test-case"></a>Creare un nuovo test case

1. Andare alla libreria BPM **RSAT**.
2. Selezionare **Processo aziendale di supporto di esempio**, quindi a destra, selezionare **Modalità di modifica**.
3. Impostare i campi **Nome** e **Descrizione** su **Rilasciare un prodotto**. Quindi selezionare **Salva**.

    ![Nome e descrizione modificati per rilasciare un prodotto.](./media/setup_rsa_tool_95.png)

#### <a name="create-a-new-task-recording-that-has-a-validate-function"></a>Creare una nuova registrazione attività che include una funzione Convalida

- Creare una registrazione attività per rilasciare il prodotto creato in precedenza alla persona giuridica USRT. Per ulteriori informazioni, vedere la sezione [Creare una registrazione attività e salvarla nella libreria BPM](#create-a-task-recording-and-save-it-to-the-bpm-library).

    > [!NOTE]
    > Per i test case concatenati, è sempre consigliabile individuare o filtrare il record necessario *digitando manualmente il valore del campo*. In tal modo, lo strumento può determinare il record in base al quale eseguire l'azione nel test case successivo.

    ![Nuova registrazione attività che include una funzione Convalida.](./media/setup_rsa_tool_96.png)

    Come illustrato nella figura precedente, dopo l'individuazione del prodotto mediante il filtro rapido, ma prima di selezionare **Rilascia prodotti**, si convalida il valore del campo **Numero prodotto** per assicurarsi che l'ID prodotto è l'ID prodotto creato in precedenza. Per convalidare il valore, fare clic con il pulsante destro del mouse sul campo **Numero prodotto** e scegliere **Registrazione attività \> Convalida \> Valore corrente**.

    ![Convalidare il valore corrente.](./media/setup_rsa_tool_97.png)

#### <a name="save-the-task-recording-to-bpm"></a>Salvare la registrazione attività in BPM

1. Al termine della registrazione attività, selezionare **Salvare in Lifecycle Services**.

    ![Salvare la registrazione delle attività completata in Lifecycle Services.](./media/setup_rsa_tool_98.png)

2. Le informazioni sulla libreria vengono caricate da LCS.

    ![Caricamento delle informazioni sulla libreria da LCS.](./media/setup_rsa_tool_99.png)

3. Selezionare la libreria BPM a cui associare la registrazione attività. Per questa esercitazione, selezionare la libreria BPM **RSAT** creata in precedenza e il processo aziendale **Rilasciare un prodotto** sottostante. Selezionare **OK**.

#### <a name="sync-bpm-to-azure-devops"></a>Sincronizzare BPM con Azure DevOps

1. Passare alla libreria BPM e aprire la libreria **RSAT**.
2. Selezionare **Sincronizzazione VSTS** e quindi **Test case di sincronizzazione**. Per ulteriori informazioni, vedere la sezione [Testare la sincronizzazione da BPM a Azure DevOps](#test-the-synchronization-from-bpm-to-azure-devops).

    Al termine della sincronizzazione, il nuovo elemento di lavoro e il test case corrispondente per il processo aziendale **Rilasciare un prodotto** vengono visualizzati in Azure DevOps in **Boards \> Elementi di lavoro**.

#### <a name="add-the-new-test-case-to-the-existing-test-suite"></a>Aggiungere il nuovo test case al gruppo di test esistente

1. Passare a **Piani di test \> Piani di test** e selezionare il piano **Piano di test RSAT**.
2. Selezionare **Aggiungi esistente**.
3. Nella pagina **Aggiungi test case a gruppo**, selezionare **Esegui query**.
4. Selezionare il nuovo test case creato per **Rilasciare un prodotto** e selezionare **Aggiungi test case** in basso a destra nella pagina (questo pulsante non è presente nella seguente illustrazione).

    ![Pagina Aggiungi test case a gruppo.](./media/setup_rsa_tool_100.png)

    Nel gruppo di test sono ora presenti due test case.

    ![Gruppo di test con due test case.](./media/setup_rsa_tool_101.png)

#### <a name="load-test-cases-into-rsat"></a>Caricare test case in RSAT

1. Aprire RSAT e selezionare **Carica**.
2. I test case vengono caricati e viene visualizzato l'avviso "Questa operazione sovrascriverà i file di dati di test di Excel; le modifiche locali andranno perse. Continuare?". Selezionare **Sì** per aggiornare i file di parametri di Excel nel sistema locale ma non i file di parametri di Excel caricati in Azure DevOps.

    ![Questa azione sovrascriverà i file di dati di test di Excel.](./media/setup_rsa_tool_102.png)

    Entrambi i case test vengono caricati, insieme al file di parametri di Excel per il primo test case. Poiché si è selezionato **Carica** nell'ultima esecuzione, i file di parametri vengono acquisiti da Azure DevOps.

    ![Test case caricati.](./media/setup_rsa_tool_103.png)

3. Selezionare solo il secondo test case e quindi **Nuovo \> Genera file di esecuzione di test e di parametri**.

#### <a name="edit-the-excel-parameter-file"></a>Modificare il file di parametri di Excel

1. Selezionare solo il secondo test case e quindi **Modifica** per aprire il file di parametri di Excel corrispondente.
2. Copiare la variabile salvata **{{EcoResProductCreate\_Identification\_ProductNumber\_Copy}}** (vedere la sezione [Modificare una registrazione attività esistente per creare una variabile salvata](#modify-an-existing-task-recording-to-create-a-saved-variable)) dal primo test case in tutti i campi in cui il numero di prodotto è utilizzato. In questo caso, si copia la variabile nei campi **Numero prodotto** **Convalida numero prodotto** nel foglio **EcoResProductListPage**.

    ![Campi Numero prodotto e Convalida numero prodotto.](./media/setup_rsa_tool_104.png)

    > [!NOTE]
    > Le variabili possono essere passate da un test all'altro solo durante la stessa esecuzione di test. I nomi delle variabili devono corrispondere esattamente.

3. Selezionare **Salva**, quindi chiudere la cartella di lavoro di Excel.
4. Selezionare **Carica** per salvare le modifiche apportate al file di parametri di Excel.

#### <a name="run-the-chained-test-cases"></a>Eseguire i test case concatenati

1. Selezionare entrambi i test case e selezionare **Esegui**.
2. Verificare che entrambi i test casi abbiano avuto esito positivo.

    ![Campo Risultato impostato su Superato per entrambi i test case.](./media/setup_rsa_tool_105.png)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
