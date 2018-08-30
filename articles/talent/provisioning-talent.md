---
title: Effettuare il provisioning di Talent
description: Questo argomento descrive il processo di provisioning di un nuovo ambiente per Microsoft Dynamics 365 for Talent.
author: rschloma
manager: AnnBe
ms.date: 11/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Talent
ms.custom: 17271
ms.assetid: ba1ad49d-8232-400e-b11f-525423506a3f
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2017-11-20
ms.dyn365.ops.version: Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 82f039b305503c604d64610f39838fa86a8eb08a
ms.openlocfilehash: 2fc4119f3b33aa583274f4d823e296752cdde41d
ms.contentlocale: it-it
ms.lasthandoff: 08/09/2018

---
# <a name="provision-talent"></a>Effettuare il provisioning di Talent

[!include [banner](includes/banner.md)]

Questo argomento descrive il processo di provisioning di un nuovo ambiente di produzione per Microsoft Dynamics 365 for Talent. In questo argomento si presuppone che sia stato acquistato Talent da un Cloud Solution Provider (CSP) o un contratto Enterprise Architecture (EA). Se si dispone di una licenza per Microsoft Dynamics 365 che include già il piano di assistenza per Talent e non è possibile completare i passaggi in questo argomento, contattare il Supporto tecnico.

Per iniziare, l'amministratore globale deve accede a [Microsoft Dynamics Lifecycle Services](http://lcs.dynamics.com) (LCS) e creare un nuovo progetto Talent. A meno che il problema di licenza non impedisca il provisioning di Talent, non è necessario rivolgersi all'assistenza del Supporto tecnico o ai rappresentanti di Dynamics Service Engineering (DSE).

## <a name="create-an-lcs-project"></a>Creare un progetto LCS
Per utilizzare LCS per la gestione degli ambienti Talent, è prima necessario creare un progetto LCS.

1. Accedere a [LCS](https://lcs.dynamics.com/Logon/Index) utilizzando l'account usato per iscriversi a Talent.
2. Selezionare il segno più (**+**) per creare un progetto.
3. Selezionare **Microsoft Dynamics 365 for Talent** come nome e versione di prodotto.
4. Selezionare la metodologia **Dynamics 365 for Talent**.
5. Selezionare **Crea**.

Per informazioni su come iniziare a utilizzare Talent, vedere la metodologa di **Talent** creata nel nuovo progetto. Al termine della creazione del progetto, attenersi alla seguente procedura per eseguire il provisioning dell'ambiente Talent.

## <a name="provision-a-talent-project"></a>Eseguire il provisioning di un progetto Talent
Dopo avere creato un progetto LCS, è possibile eseguire il provisioning di Talent in un ambiente.

1. Nel progetto LCS selezionare il riquadro **Gestione app Talent**.
2. Il provisioning di Talent viene sempre eseguito in un ambiente Microsoft PowerApps, per consentire l'integrazione e l'estensibilità di PowerApps. Leggere la sezione relativa alla selezione di un ambiente PowerApps in questo argomento prima di continuare. 
3. Se non si dispone già di un ambiente PowerApps, seguire i passaggi nella sezione "Creare un nuovo ambiente PowerApps (se necessario)" di questo argomento prima di continuare.

    > [!NOTE]
    > Per visualizzare gli ambienti esistenti o crearne di nuovi, l'amministratore di tenant che esegue il provisioning di Talent deve essere assegnato alla licenza PowerApps Piano 2. Se l'organizzazione non dispone di una licenza PowerApps Piano 2, se ne può ottenere una dal CSP o dalla [pagina dei prezzi di PowerApps](https://powerapps.microsoft.com/en-us/pricing/).

4. Selezionare **Aggiungi** e quindi selezionare l'ambiente in cui eseguire il provisioning di Talent.
5. Selezionare "Includi dati dimostrativi" se si desidera che l'ambiente includa lo stesso set di dati dimostrativi utilizzato in passato nell'esperienza dei test drive di Talent.  Questa opzione è utile negli ambienti di formazione o dimostrativi a lungo termine e non deve mai essere utilizzata per gli ambienti di produzione.  Tenere presente che è necessario scegliere questa opzione per la distribuzione di apertura e che non è possibile aggiornare una distribuzione esistente in seguito.
6. Selezionare **Sì** per accettare le condizioni e iniziare la distribuzione.

    Il nuovo ambiente appare nell'elenco di ambienti nel riquadro di navigazione a sinistra. Tuttavia, non è possibile iniziare a utilizzare l'ambiente prima che lo stato di distribuzione sia stato aggiornato a **Distribuito**. Questo processo richiede normalmente solo alcuni minuti. Se il processo di approvvigionamento ha esito negativo, è necessario contattare il Supporto tecnico.

7. Selezionare **Accesso a Talent** per utilizzare il nuovo ambiente.

> [!NOTE]
> Se non sono ancora stati completati i requisiti finali, è possibile distribuire un'istanza di prova di Talent nel progetto. È quindi possibile utilizzare l'istanza per testare la soluzione finché non si esegue la conferma. Se si utilizza il nuovo ambiente per i test, è necessario ripetere questa procedura per creare un ambiente di produzione.

> [!NOTE]
> Poiché solo due ambienti LCS sono consentiti con la sottoscrizione Talent, è anche possibile considerare la possibilità di utilizzare gratuitamente per 60 giorni un [ambiente di prova Talent](https://dynamics.microsoft.com/en-us/talent/overview/). Sebbene un ambiente di prova sia di proprietà dell'utente che lo ha richiesto, altri utenti possono essere invitati tramite l'esperienza di amministrazione del sistema per l'ambiente Core HR. Gli ambienti di prova contengono dati fittizi che possono essere utilizzati per esplorare il programma in modo sicuro. Tali ambienti non sono destinati all'utilizzo come ambienti di produzione. Si noti che quando un ambiente di prova scade dopo 60 giorni, tutti i dati in esso contenuti verranno cancellati e non potranno essere recuperati. È possibile registrarsi per un nuovo ambiente di prova dopo che l'ambiente esistente è scaduto.

## <a name="select-a-powerapps-environment"></a>Selezionare un ambiente PowerApps

L'integrazione tra Talent e gli ambienti PowerApps consente di integrare ed estendere l'utilizzo dei dati Talent tramite gli strumenti PowerApps. La comprensione dello scopo degli ambienti PowerApps non aiuta soltanto a creare app per estendere Talent, ma anche a selezionare l'ambiente corretto per il provisioning di Talent. Per informazioni sugli ambienti di PowerApps, incluso l'ambito dell'ambiente, l'accesso all'ambiente e la creazione e la scelta di un ambiente, vedere [Annuncio degli ambienti PowerApps](https://powerapps.microsoft.com/en-us/blog/powerapps-environments/) 

Utilizzare le seguenti linee guida per la determinazione dell'ambiente PowerApps in cui distribuire Talent: 
1. In LCS, selezionare Gestione ambienti o passare direttamente all'interfaccia di amministrazione di PowerApps, nella quale è possibile visualizzare gli ambienti esistenti e crearne di nuovi.
2. In un singolo ambiente PowerApps viene mappato un singolo ambiente Talent.
3. Un ambiente PowerApps "contiene" l'applicazione Talent e le corrispondenti applicazioni PowerApps, Flow e CDS. Se l'ambiente PowerApps viene eliminato, vengono eliminate anche le app in esso contenute.
4. È consigliabile considerare l'utilizzo di strategie di integrazione e di test di dati, ad esempio Sandbox, UAT, produzione. Pertanto, si consiglia di valutare le varie implicazioni per la distribuzione, poiché non è facile cambiare l'ambiente Talent mappato a un ambiente PowerApps successivamente.
5. Gli ambienti PowerApps seguenti non possono essere utilizzati per Talent e saranno filtrati in base all'elenco di selezione in LCS:
 
    **Ambienti CDS 2.0** - CDS 2.0 è disponibile al pubblico dal 21 marzo 2018. Talent non supporta tuttavia ancora CDS 2.0. Sebbene sia possibile visualizzare e creare database CDS 2.0 nell'interfaccia di amministrazione di PowerApps, questi non saranno utilizzabili in Talent. L'opzione per utilizzare gli ambienti CDS 2.0 nelle distribuzioni Talent sarà disponibile in una data successiva.
   
   > [!Note]
   > Per differenziare gli ambienti CDS 1.0 e 2.0 nel portale di amministrazione, selezionare un ambiente e consultare **Dettagli**. Gli ambienti CDS 2.0 fanno tutti riferimento al fatto che "è possibile gestire queste impostazioni nell'interfaccia di amministrazione di Dynamics 365", puntano a una versione di istanza e non hanno la scheda Database. 
 
   **Ambienti PowerApps predefiniti** Sebbene ogni tenant venga dotato automaticamente di un ambiente PowerApps predefinito, non è consigliabile utilizzarli con Talent poiché tutti gli utenti del tenant hanno accesso all'ambiente PowerApps e possono danneggiare erroneamente i dati di produzione durante i test e l'esplorazione con le integrazioni di PowerApps o Flow.
   
   <strong>Ambienti Test Drive</strong> - Gli ambienti con un nome simile a "TestDrive – alias@domain" vengono creati con un periodo di validità di 60 giorni trascorsi i quali gli ambienti vengono rimossi automaticamente.
   
   **Regioni non supportate** - Attualmente Talent è supportato solo nelle regioni seguenti: Stati Uniti, Europa e Australia.
  
6. Non c'è alcuna azione specifica da eseguire dopo aver determinato l'ambiente corretto da utilizzare. Continuare il processo di provisioning. 
 
## <a name="create-a-new-powerapps-environment-if-required"></a>Creare un nuovo ambiente PowerApps (se necessario)

Eseguire uno script PowerShell per creare un nuovo ambiente PowerApps per Talent nel contesto dell'amministratore del tenant con la licenza piano 2 di PowerApps. Lo script automatizza le seguenti operazioni:


 + Creazione di un ambiente PowerApps
 + Creazione di un database CDS 1.0
 + Cancellare tutti i dati di esempio nel database CDS 1.0


Per eseguire lo script, attenersi alle istruzioni seguenti:

1. Scaricare il file ProvisionCDSEnvironment.zip dal percorso seguente: [Script ProvisionCDSEnvironment](https://go.microsoft.com/fwlink/?linkid=870436)  

2. Dalla cartella di download, fare clic con il pulsante destro del mouse sul file ProvisionCDSEnvironment.zip appena scaricato e selezionare **Proprietà**.  Se è presente una nota sulla sicurezza nella parte inferiore della finestra di dialogo indicante che "il file proviene da un altro computer e potrebbe essere bloccato per la protezione del computer", selezionare la casella di controllo **Sblocca**, quindi fare clic su **Applica** e **OK**.

3. Decomprimere l'intero contenuto del file ProvisionCDSEnviroinment.zip in una cartella che non sia quella principale.

4. Eseguire il programma Windows PowerShell o Windows PowerShell ISE come amministratore.

   Consultare l'argomento relativo all'[impostazione dei criteri di esecuzione](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.security/set-executionpolicy?view=powershell-6) per ulteriori informazioni sull'impostazione dei criteri di esecuzione allo scopo di consentire l'esecuzione degli script. È consigliabile utilizzare "Set-ExecutionPolicy -ExecutionPolicy Unrestricted -Scope Process", ma è necessario assicurarsi di tenere traccia dei criteri di sicurezza della società e di chiudere la finestra di PowerShell al termine. 
  
5. In PowerShell, spostarsi nella cartella dove è stato decompresso il file ed eseguire il seguente comando, sostituendo i valori come indicato di seguito:
 
   ```.\ProvisionCDSEnvironment -EnvironmentName MyNewEnvironment -Location YourLocation```

    
   **MyNewEnvironment** deve essere sostituito con il nome dell'ambiente. Questo nome sarà visualizzato in LCS e sarà visibile quando gli utenti selezionano l'ambiente Talent da utilizzare. 

   **YourLocation** deve essere sostituito con una delle regioni in cui Talent è supportato: Stati Uniti, Europa, Australia. 

   **-Verbose** è facoltativo e offre informazioni dettagliate da inviare al supporto in caso di problemi.

6. Continuare il processo di provisioning.
 

## <a name="grant-access-to-the-environment"></a>Concedere l'accesso all'ambiente
Per impostazione predefinita, l'accesso è consentito solo all'amministratore globale che ha creato ambiente. Tuttavia, è necessario concedere l'accesso in modo esplicito ad altri utenti dell'applicazione. Per concedere l'accesso, è necessario [aggiungere gli utenti](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/create-new-users) e [assegnare i ruoli appropriati correlati](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/assign-users-security-roles) nell'ambiente Core HR. L'amministratore globale che ha distribuito Talent deve inoltre avviare le applicazioni Attract e Onboard per completare l'inizializzazione e abilitare l'accesso per altri utenti del tenant.  Se questa operazione non viene eseguita, gli altri utenti non potranno accedere alle applicazioni Attract e Onboard e riceveranno errori di violazione dell'accesso.


