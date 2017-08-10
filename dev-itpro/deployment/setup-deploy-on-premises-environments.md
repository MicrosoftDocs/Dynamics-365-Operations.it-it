---
title: Impostare e distribuire in ambienti locali
description: In questo argomento vengono fornite informazioni su come pianificare, impostare e distribuire un ambiente locale.
author: kfend
manager: AnnBe
ms.date: 06/14/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core
ms.custom: 55651
ms.assetid: 
ms.search.region: Global
ms.author: sarvanisathish
ms.search.validFrom: 2016-08-30T00:00:00.000Z
ms.dyn365.ops.version: Platform update 8
ms.translationtype: HT
ms.sourcegitcommit: d100f6dbcbdf8f4c12ab04670fb598a88d48d84b
ms.openlocfilehash: 7caf033ab2de5afd6a2d88fa2d41631df4542cbe
ms.contentlocale: it-it
ms.lasthandoff: 08/10/2017

---

# <a name="set-up-and-deploy-on-premises-environments"></a>Impostare e distribuire in ambienti locali

In questo documento viene descritto come pianificare la distribuzione, impostare l'infrastruttura e distribuire Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (locale).

## <a name="finance-and-operations-components"></a>Componenti di Finance and Operations

L'applicazione Finance and Operations è costituita da tre componenti principali:

- Server oggetti applicativi (AOS)
- Business Intelligence (BI)
- Report finanziari e strumento di creazione report di gestione

Questi componenti dipendono dal seguente software di sistema:

- Microsoft Windows Server 2016
- Microsoft SQL Server SP1 2016, con le seguenti funzionalità:

    - Ricerca indice full-text attivata.
    - SQL Server Reporting Services (SSRS).
    - SQL Server Integration Services (SSIS).
    
     > [!NOTE]
     > L'applicazione non verrà eseguita se la ricerca indice full-text non è attivata.

- SQL Server Management Studio
- Microsoft Azure Service Fabric autonomo
- Windows PowerShell 5.0 o versione successiva
- Active Directory Federation Services (AD FS) su Windows Server 2016

  Il controller di dominio deve essere Windows Server 2012 R2 o versione successiva con un livello funzionale di dominio 2012 R2 o superiore

  Per ulteriori informazioni sui livelli funzionali di dominio, vedere: 
  - [Livelli funzionali di Active Directory](https://technet.microsoft.com/en-us/library/cc787290(v=ws.10).aspx)
  - [Informazioni sui livelli funzionali di Active Directory Domain Services](https://technet.microsoft.com/en-us/library/understanding-active-directory-functional-levels(v=ws.10).aspx)


## <a name="lifecycle-services"></a>Lifecycle Services

I bit di Finance and Operations vengono distribuiti tramite Microsoft Dynamics Lifecycle Services (LCS). Prima di poter distribuire, è necessario acquistare i codici di licenza tramite il canale [Contratti Enterprise](https://www.microsoft.com/en-us/Licensing/licensing-programs/enterprise.aspx) e impostare un progetto locale in LCS. Le distribuzioni possono essere avviate solo da LCS. Per ulteriori informazioni sull'impostazione dei progetti locali in LCS, vedere [Creare un progetto locale in Lifecycle Services](../lifecycle-services/lbd-create-lcs-on-prem-project.md).

## <a name="authentication"></a>Autenticazione

L'applicazione locale funziona con AD FS. Per interagire con LCS, è necessario configurare anche Azure Active Directory (Azure AD).

## <a name="standalone-service-fabric"></a>Service Fabric autonomo

Finance and Operations usa Service Fabric autonomo. Per ulteriori informazioni, vedere la [documentazione di Service Fabric](/azure/service-fabric/).

## <a name="infrastructure"></a>Infrastruttura

Finance and Operations è progettato per lavorare in un architettura iperconvergente. La configurazione hardware include i seguenti componenti:

- Cluster Service Fabric autonomo basato su macchine virtuali (VM) Windows Server 2016
- SQL Server (sia SQL di cluster che Always-On sono supportati)
- AD FS per l'autenticazione
- Condivisione di file Server Message Block (SMB) versione 3 per l'archiviazione
- Facoltativo: Microsoft Office Server 2017

Per ulteriori informazioni, vedere [Requisiti di sistema](../get-started/system-requirements.md) e linee guida per il dimensionamento.

### <a name="hardware-layout"></a>Layout dell'hardware

Progettare l'infrastruttura e il cluster Service Fabric, in base al dimensionamento consigliato in [Dimensionamento hardware per ambienti locali](../get-started/hardware-sizing-on-premises-environments.md). Per ulteriori informazioni su come pianificare il cluster  Service Fabric, vedere [Pianificare e preparare la distribuzione del cluster Service Fabric autonomo](/azure/service-fabric/service-fabric-cluster-standalone-deployment-preparation).

Nella tabella seguente viene illustrato un esempio di layout dell'hardware. Questo esempio viene utilizzato in questo argomento per illustrare le impostazioni.

> [!NOTE]
> Il nodo principale del cluster Service Fabric deve disporre di almeno tre nodi. In questo esempio, **OrchestratorType** viene designato come tipo di nodo principale.

| Scopo computer                                 | Nome computer    | Indirizzo IP    |
|-------------------------------------------------|-----------------|---------------|
| Controller di dominio                               | DAX7SQLAODC1    | 10.179.108.2  |
| AD FS                                           | DAX7SQLAOADFS1  | 10.179.108.3  |
| File server                                     | DAX7SQLAOFILE1  | 10.179.108.4  |
| Cluster SQL Always-On                           | DAX7SQLAOSQLA01 | 10.179.108.5  |
|                                                 | DAX7SQLAOSQLA02 | 10.179.108.6  |
|                                                 | DAX7SQLAOSQLA   | 10.179.108.9  |
| Cliente                                          | SQLAOCLIENT1    | 10.179.108.11 |
| Cluster Service Fabric/AOS 1                    | SQLAOSF1AOS1    | 10.179.108.12 |
| Cluster Service Fabric/AOS 2                    | SQLAOSF1AOS2    | 10.179.108.13 |
| Cluster Service Fabric/AOS 3                    | SQLAOSF1AOS3    | 10.179.108.14 |
| Cluster Service Fabric/Orchestrator 1           | SQLAOSF1ORCH1   | 10.179.108.15 |
| Cluster Service Fabric/Orchestrator 2           | SQLAOSF1ORCH2   | 10.179.108.16 |
| Cluster Service Fabric/Orchestrator 3           | SQLAOSF1ORCH3   | 10.179.108.17 |
| Cluster Service Fabric/nodo strumento di creazione report di gestione | SQLAOSMR1       | 10.179.108.18 |
| Cluster Service Fabric/nodo SSRS                | SQLAOSFBIN1     | 10.179.108.10 |

## <a name="setup"></a>Imposta

### <a name="prerequisites"></a>Prerequisiti

Prima di iniziare la configurazione, è necessario soddisfare i prerequisiti seguenti. L'impostazione dei prerequisiti non rientra nell'ambito di questo documento.

- Active Directory Domain Services (AD DS) viene installato e configurato nella rete.
- AD FS è distribuito.
- SQL Server, SSRS e Management Studio sono installati.

### <a name="overview"></a>Panoramica

I passaggi elencati di seguito devono essere eseguiti per impostare l'infrastruttura per Finance and Operations.

1. Pianificare il nome del dominio e le zone DNS
2. Pianificare e acquisire i certificati
3. Pianificare gli account di servizio e utenti
4. Creare le zone DNS e aggiungere i record A
5. Unire le macchine virtuali al dominio
6. Aggiungere il software necessario alle macchine virtuali
7. Scaricare gli script di impostazione da LCS
8. Descrivere la configurazione
9. Installare i certificati
10. Impostare un cluster Service Fabric autonomo
11. Configurare la connettività LCS per il tenant
12. Impostare l'archiviazione file
13. Impostare SQL Server
14. Configurare i database
15. Crittografare le credenziali
16. Imposta SSRS
17. Configurare AD FS

### <a name="plan-your-domain-name-and-dns-zones"></a>Pianificare il nome del dominio e le zone DNS

Si consiglia di utilizzare un dominio pubblicamente registrato per l'installazione di produzione di AOS. In questo modo, è possibile accedere all'esterno della rete, se l'accesso esterno è richiesto.

Ad esempio, se il dominio della società è contoso.com, la zona di Finance and Operations (locale) potrebbe essere d365ffo.onprem.contoso.com e i nomi host potrebbero essere i seguenti:

- ax.d365ffo.onprem.contoso.com per i computer AOS
- sf.d365ffo.onprem.contoso.com per il cluster Service Fabric

### <a name="plan-and-acquire-your-certificates"></a>Pianificare e acquisire i certificati

I certificati Secure Sockets Layer (SSL) sono necessari per garantire la distribuzione di un cluster Service Fabric e di tutte le applicazioni. Per i carichi di lavoro sandbox e di produzione, è consigliabile acquisire i certificati da un'autorità di certificazione (CA), ad esempio [DigiCert](https://www.digicert.com/ssl-certificate/), [Comodo](https://ssl.comodo.com/), [Symantec](https://www.websecurity.symantec.com/ssl-certificate), [GoDaddy](https://www.godaddy.com/web-security/ssl-certificate) o [GlobalSign](https://www.globalsign.com/en/ssl/). Se il dominio viene impostato con [Servizi certificati Active Directory](https://technet.microsoft.com/en-us/library/cc772393(v=ws.10).aspx), è possibile creare i certificati tramite Servizi certificati Active Directory. Ogni certificato deve contenere una chiave privata creata per lo scambio di chiavi e deve essere esportabile in un file PFX (Personal Information Exchange).

I certificati autofirmati possono essere utilizzati solo per scopi di test. Per comodità, gli script di impostazione includono script che generano ed esportano certificati autofirmati. Come illustrato in precedenza, i certificati devono essere utilizzati solo per scopi di test.

| Scopo                                      | Spiegazione | Requisiti aggiuntivi |
|----------------------------------------------|-------------|-------------------------|
| Certificato SSL di SQL Server                   | Questo è utilizzato per crittografare i dati che vengono trasmessi attraverso una rete tra un'istanza di SQL Server e un'applicazione client. | <p>Il nome del dominio del certificato deve corrispondere al nome di dominio completo (FQDN) del listener o dell'istanza di SQL Server.</p><p>Ad esempio, se il listener SQL è ospitato nel computer DAX7SQLAOSQLA, il nome DNS del certificato è DAX7SQLAOSQLA.onprem.contoso.com.</p> |
| Certificato del server Service Fabric            | Questo certificato è utilizzato per consentire comunicazioni protette da nodo a nodo tra i nodi di Service Fabric. Il certificato viene inoltre utilizzato come certificato del server che viene inviato al client connesso al cluster. | <p>Il nome del dominio del certificato deve corrispondere alla zona DNS in cui sono ospitati AOS e Service Fabric.</p><p>Ad esempio, il nome del dominio del certificato potrebbe essere \*.onprem.contoso.com o \*.contoso.com.</p><p>Se si utilizza un certificato con caratteri jolly, il carattere jolly si applica a un solo livello. Un sottodominio, il nome alternativo del soggetto (SAN), deve essere applicato al certificato se è per più di un livello, come \*.contoso.com nell'esempio precedente.</p> |
| Certificato del client Service Fabric            | Questo certificato è utilizzato dai client per visualizzare e gestire il cluster Service Fabric. | |
| Certificato di crittografia                     | Questo certificato è utilizzato per crittografare dati riservati come le password degli account utente e di SQL Server. | <p>L'utilizzo della chiave del certificato deve includere la crittografia dei dati (10) e non deve includere l'autenticazione del server o l'autenticazione del client.</p><p>Per ulteriori informazioni, vedere [Gestione dei segreti nelle applicazioni Service Fabric](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-application-secret-management).</p> |
| Certificato AOS SSL                          | <p>Il certificato viene utilizzato come certificato del server che viene inviato al client per il sito Web AOS. Viene inoltre utilizzato per abilitare i certificati Windows Communication Foundation (WCF)/Simple Object Access Protocol (SOAP).</p><p>Il certificato del server Service Fabric può essere utilizzato se è un certificato con caratteri jolly.</p> | <p>Il nome del dominio del certificato deve corrispondere alla zona DNS in cui sono ospitati AOS e Service Fabric.</p><p>Ad esempio, il nome del dominio del certificato potrebbe essere \*.d365ffo.onprem.contoso.com, \*.onprem.contoso.com o \*.contoso.com.</p><p>Se si utilizza un certificato con caratteri jolly, il carattere jolly si applica a un solo livello. Un sottodominio, SAN, deve essere applicato al certificato se è per più di un livello, come \*.contoso.com nell'esempio precedente.</p> |
| Certificato di autenticazione sessione           | Questo certificato è utilizzato da AOS per proteggere le informazioni della sessione utente. | Si tratta anche del certificato di **condivisione di file** da utilizzare al momento della distribuzione da LCS. |
| Certificato di firma e crittografia dei dati | Questi certificati vengono utilizzati da AOS per crittografare i dati riservati. | |
| Certificato client di report finanziari       | Questo certificato è utilizzato per consentire comunicazioni protette tra i servizi di report finanziari e AOS. | |
| Certificato di report                        | Questo certificato è utilizzato per consentire comunicazioni protette tra SSRS e AOS. | |
| Certificato agente locale ospitato in locale           | <p>Questo certificato è utilizzato per consentire comunicazioni protette tra un agente locale ospitato in locale e LCS.</p><p>Il certificato consente all'agente locale di agire per conto del tenant Azure AD e di comunicare con LCS per gestire e controllare le distribuzioni.</p> | |

### <a name="plan-your-users-and-service-accounts"></a>Pianificare gli account di servizio e utenti

È necessario creare più account utente o di servizio per il funzionamento di Finance and Operations (locale). È necessario creare una combinazione di account del servizio gestito del gruppo (gMSA), account di dominio e account SQL. Nella seguente tabella vengono indicati gli account utente, lo scopo e i nomi di esempio che verranno utilizzati in questo argomento.

| Account utente                                            | Tipo           | Scopo | Nome utente |
|---------------------------------------------------------|----------------|---------|-----------|
| Account del servizio di applicazione di report finanziari         | gMSA           |         | Contoso\\svc-FRAS$ |
| Account del servizio di elaborazione di report finanziari             | gMSA           |         | Contoso\\svc-FRPS$ |
| Account del servizio di progettazione con un solo clic di report finanziari | gMSA           |         | Contoso\\svc-FRCO$ |
| Account del servizio AOS                                     | gMSA           | Questo utente deve essere creato per il controllo futuro. Si pianifica di abilitare AOS per l'utilizzo con gMSA nelle versioni future. Creando questo utente al momento dell'impostazione, si contribuisce a garantire una transizione facile a gMSA. | Contoso\\svc-AXSF$ |
| Account del servizio AOS                                     | Account di dominio | AOS utilizza questo utente nella versione GA. | Contoso\\AXServiceUser |
| Utente amministratore di database AOS SQL                                   | Utente SQL       | Finance and Operations utilizza questo utente per eseguire l'autenticazione con SQL\*. Questo utente verrà sostituito dall'utente gMSA nelle versioni future. | AXDBAdmin |
| Account del servizio agente di distribuzione locale                  | gMSA           | Questo account viene utilizzato dall'agente locale per gestire la distribuzione nei diversi nodi. | Contoso\\Svc-LocalAgent$ |

\* Il nome utente e la password SQL per l'autenticazione SQL sono protetti perché crittografati e archiviati nella condivisione file.

### <a name="create-dns-zones-and-add-a-records"></a>Creare le zone DNS e aggiungere i record A

DNS è integrato con AD DS e consente di organizzare, gestire e trovare le risorse in una rete. Creare una zona di ricerca diretta DNS e i record A per il nome host AOS e il cluster Service Fabric. Con queste impostazioni di esempio, il nome della zona DNS è d365ffo.onprem.contoso.com e i record A/nomi host sono:

- **ax**.d365ffo.onprem.contoso.com per i computer AOS
- **sf**.d365ffo.onprem.contoso.com per il cluster Service Fabric

#### <a name="add-a-dns-zone"></a>Aggiungere una zona DNS

Attenersi alla procedura riportata di seguito per aggiungere una zona DNS.

1. Accedere al computer del controller di dominio, fare clic su **Start** e avviare il Gestore DNS digitando **dnsmgmt.msc**.
2. Fare clic con il pulsante destro del mouse sul nome del controller di dominio, quindi fare clic su **Nuova zona** \> **Avanti**.
3. Selezionare **Zona primaria**.
4. Lasciare selezionata la casella di controllo **Archivia la zona in Active Directory (disponibile solo se il server DNS è un controller di dominio)** e fare clic su **Avanti**.
5. Selezionare **In tutti i server DNS eseguiti nei controller di dominio del dominio seguente: Contoso.com** e fare clic su **Avanti**.
6. Selezionare **Zona di ricerca diretta** e fare clic su **Avanti**.
7. Immettere il nome della zona per l'impostazione e fare clic su **Avanti**. Ad esempio, immettere **d365ffo.onprem.contoso.com**.
8. Selezionare **Non consentire aggiornamenti dinamici** e fare clic su **Avanti**.

#### <a name="set-up-an-a-record-for-aos"></a>Impostare un record A per AOS

Nella nuova zona DNS, creare un record A denominato **ax.d365ffo.onprem.contoso.com** per **ogni** nodo del cluster Service Fabric di tipo **AOSNodeType**. Non creare i record A per gli altri tipi di nodo.

1. Fare clic con il pulsante destro del mouse sulla nuova zona, quindi scegliere **Nuovo host**.
2. Immettere il nome e l'indirizzo IP del nodo Service Fabric (ad esempio 10.179.108.12) e fare clic su **Aggiungi host**.

#### <a name="set-up-an-a-record-for-the-orchestrator"></a>Impostare un record A per l'orchestrator

Nella nuova zona DNS, creare un record A denominato **sf.d365ffo.onprem.contoso.com** per **ogni** nodo del cluster Service Fabric di tipo **OrchestratorType**. Non creare i record A per gli altri tipi di nodo.

1. Fare clic con il pulsante destro del mouse sulla nuova zona, quindi scegliere **Nuovo host**.
2. Immettere il nome e l'indirizzo IP del nodo Service Fabric (ad esempio 10.179.108.15) e fare clic su **Aggiungi host**.

#### <a name="join-vms-to-the-domain"></a>Unire le macchine virtuali al dominio

Unire ciascuna macchina virtuale al dominio completando i passaggi riportati in [Come unire Windows Server 2016 a un dominio Active Directory](http://www.tomsitpro.com/articles/join-windows-server-2016-to-ad-domain,2-1063.html). In alternativa, utilizzare lo script Windows PowerShell.

```
$domainName = Read-Host -Prompt 'Specify domain name (ex: contoso.com)'
Add-Computer -DomainName $domainName -Credential (Get-Credential -Message 'Enter domain credential')
Restart-Computer
```
Dopo che le VM si state unite al dominio, aggiungere gli account del servizio AOS (Contoso\svc-AXSF$ , Contoso\svc-AXSF$ ) al gruppo Administrators locale. Puoi leggere l'articolo [Aggiungere un membro al gruppo locale](https://technet.microsoft.com/en-us/library/cc772524(v=ws.11).aspx) per le informazioni su come effettuare questa operazione.

#### <a name="disable-user-access-control"></a>Disabilitare il controllo di accesso dell'utente 

Eseguire il seguente script per disabilitare il controllo di accesso dell'utente in **ciascun** nodo Service Fabric.
```
$RegPath = "HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System"
New-ItemProperty -Path $RegPath -Name "EnableLUA" -Value 0 -PropertyType "DWORD" -Force
New-ItemProperty -Path $RegPath -Name "ConsentPromptBehaviorAdmin" -Value 0 -PropertyType "DWORD" -Force
New-ItemProperty -Path $RegPath -Name "EnableUIADesktopToggle" -Value 0 -PropertyType "DWORD" -Force
New-ItemProperty -Path $RegPath -Name "LocalAccountTokenFilterPolicy" -Value 1 -PropertyType "DWORD" -Force
```
> [!IMPORTANT]
> È necessario riavviare il nodo al termine dell'esecuzione dello script.

#### <a name="add-prerequisite-software-to-vms"></a>Aggiungere il software necessario alle macchine virtuali

Nella seguente tabella sono elencati i software necessari che devono essere applicati ai computer per ogni tipo di nodo.

> [!NOTE]
> Sarà necessario riavviare il computer dopo l'installazione dei componenti.

| Tipo nodo | Componente | Comandi |
|-----------|-----------|---------|
| AOS       | SNAC – Driver ODBC | Vedere [Microsoft ODBC Driver 13.1 per SQL Server - Windows + Linux](https://www.microsoft.com/en-us/download/details.aspx?id=53339). |
| AOS       | Microsoft .NET Framework versione 2.0–3.5 (CLR 2.0) | `Add-WindowsFeature -Name NET-Framework-Features, NET-Framework-Core, NET-HTTP-Activation, NET-Non-HTTP-Activ` |
| AOS       | Microsoft .NET Framework versione 4.0–4.6 (CLR 4.0) | `Add-WindowsFeature -Name NET-Framework-45-Features, NET-Framework-45-Core, NET-Framework-45-ASPNET, NET-WCF-Services45, NET-WCF-TCP-PortSharing45` |
| AOS       | Internet Information Services (IIS) | `Add-WindowsFeature WAS, WAS-Process-Model, WAS-NET-Environment, WAS-Config-APIs`<br>`# Windows Process Activation Service`<br>`Add-WindowsFeature Web-Server, Web-WebServer, Web-Security, Web-Filtering, Web-App-Dev, Web-Net-Ext, Web-Mgmt-Tools, Web-Mgmt-Console` |
| AOS       | Microsoft SQL Server Management Studio 2016 | |
| AOS       | Microsoft Visual C++ Redistributable Packages per Microsoft Visual Studio 2013 | Vedere [Microsoft Visual C++ Redistributable Packages per Visual Studio 2013](https://support.microsoft.com/en-us/help/3179560). |
| AOS       | Motore di database di Microsoft Access 2010 ridistribuibile | Vedere [Motore di database di Microsoft Access 2010 ridistribuibile](https://www.microsoft.com/en-us/download/details.aspx?id=13255) |
| BI        | .NET Framework versione 2.0–3.5 (CLR 2.0) | `Add-WindowsFeature -Name NET-Framework-Features, NET-Framework-Core, NET-HTTP-Activation, NET-Non-HTTP-Activ` |
| BI        | .NET Framework versione 4.0–4.6 (CLR 4.0) | `Add-WindowsFeature -Name NET-Framework-45-Features, NET-Framework-45-Core, NET-Framework-45-ASPNET, NET-WCF-Services45, NET-WCF-TCP-PortSharing45` |
| BI        | Microsoft SQL Server 2016 SP1 | |
| BI        | Management Studio 2016 | |
| BI        | SQL Server Reporting Services 2016 in modalità **nativa** | |
| MR        | .NET Framework versione 2.0–3.5 (CLR 2.0) | `Add-WindowsFeature -Name NET-Framework-Features, NET-Framework-Core, NET-HTTP-Activation, NET-Non-HTTP-Activ` |
| MR        | .NET Framework versione 4.0–4.6 (CLR 4.0) | `Add-WindowsFeature -Name NET-Framework-45-Features, NET-Framework-45-Core, NET-Framework-45-ASPNET, NET-WCF-Services45, NET-WCF-TCP-PortSharing45` |
| MR        | Visual C++ Redistributable Packages per Visual Studio 2013 | Vedere [Microsoft Visual C++ Redistributable Packages per Visual Studio 2013](https://support.microsoft.com/en-us/help/3179560). |

#### <a name="download-setup-scripts-from-lcs"></a>Scaricare gli script di impostazione da LCS

Sono disponibili diversi script per migliorare per l'esperienza di impostazione. Seguire questi passaggi per scaricare gli script di impostazione da LCS.

1. Accedere a LCS (<https://lcs.dynamics.com/v2>).
2. Nel dashboard, fare clic sul riquadro **Raccolta di risorse condivise**.
3. Fare clic sulla scheda **Modello**.
4. Nella griglia, selezionare la riga **Dynamics 365 for Operations - Script di distribuzione locale**.
5. Fare clic su  **Versioni** e scaricare l'ultima versione degli script.

### <a name="describe-your-configuration"></a>Descrivere la configurazione

In questa sezione vengono fornite informazioni sugli script che è necessario eseguire. Gli script vengono discussi nell'ordine in cui devono essere eseguiti. Per eseguire gli script, compilare il file di modello in $(downloadPath)\\ConfigTemplate.xml. Il file ConfigTemplate.xml descrive i cluster Service Fabric, certificati utilizzati per configurarli e gli account a cui deve essere concesso l'accesso ai certificati pertinenti. Nell'esempio fornito, i valori vengono compilati per l'infrastruttura di esempio descritta in questo argomento. Il file di modello verrà utilizzato nella prossima sezione.

#### <a name="create-the-domain-account-for-a-service-user"></a>Creare l'account di dominio per un utente del servizio

Eseguire il seguente comando per creare l'account utente di dominio, contoso\\AXServiceUser.

```
New-ADUser -Name 'AXServiceUser' `
    -AccountPassword (Read-Host -Prompt 'Specify User Password' -AsSecureString) `
    -PasswordNeverExpires $true -ChangePasswordAtLogon $false `
    -Enabled $true -UserPrincipalName 'AXServiceUser@contoso.com'
```

#### <a name="create-gmsas"></a>Creare gli account del servizio gestito di gruppo (gMSA)

1. Cambiare la directory in **$(DownloadPath)** ed eseguire il seguente comando di Windows PowerShell.

    > [!NOTE]
    > Questo script non crea gli utenti. In alternativa, stampa i comandi che devono essere eseguiti manualmente nel computer del controller di dominio.

    ```
    # Generate gMSA account creation script (shows in console):
    .\Get-NewGMSAInDomainScript.ps1 -InputXml .\ConfigTemplate.xml
    ```

2. Copiare l'output del comando in una finestra di Windows PowerShell. Verificare che le interruzioni di riga siano state rimosse ed eseguire le righe nel computer del controller di dominio Active Directory utilizzando i privilegi elevati (fare clic con il pulsante destro del mouse su **Esegui come amministratore**).
3. Eseguire il seguente script nel computer del controller di dominio Active Directory per verificare che gli account siano stati creati correttamente. Assicurarsi di eseguire lo script dopo aver sostituito il criterio corrispondente alla convenzione di denominazione degli account del servizio.

    ```
    #Use this command to validate the gMSA accounts are added to AD.
    #Ensure to replace the Filter parameter with the pattern used to create your accounts.
    Get-ADServiceAccount -Filter { samAccountName -like "svc-*" }
    ```

4. Eseguire lo script Export-AddGMSAsONVMScript.ps1 sul computer client. Questo script genera gli script che vengono eseguiti in ogni VM Service Fabric e li aggiunge in una cartella corrispondente a ciascun nome di macchina virtuale.

    ```
    # Exports a script for installing gMSA on VM nodes into a directory VMs\<VMName>, again feed from XML
    .\Export-AddGMSAsOnVMScript.ps1 -InputXml .\ConfigTemplate.xml
    ```

#### <a name="stop-iis"></a>Arrestare IIS

Utilizzare il Remote Desktop Protocol (RDP) per collegare ogni VM Service Fabric e completare i passaggi manuali in [Avviare o arrestare il server Web (IIS 7)](https://technet.microsoft.com/en-us/library/cc732317(v=ws.10).aspx). In alternativa, utilizzare il seguente script Windows PowerShell usando il RDP per collegare ogni VM Service Fabric.

```
$ServiceName = "WAS"
$wasService = Get-Service $ServiceName -ErrorAction SilentlyContinue
if($wasService)
{
    $wasService.DependentServices | Stop-Service -Force -ErrorAction Continue
    $wasService | Stop-Service -ErrorAction Continue
    Set-Service $ServiceName -StartupType Disabled
}

$ServiceName = 'W3SVC'
$w3svc = Get-Service $ServiceName -ErrorAction SilentlyContinue
if($w3svc)
{
    $w3svc.DependentServices | Stop-Service -Force -ErrorAction Continue
    $w3svc | Stop-Service -ErrorAction Continue
    Set-Service $ServiceName -StartupType Disabled
}
```
La funzionalità _IIS deve essere installata, ma disabilitata poiché esistono alcune dipendenze alle DLL IIS nel prodotto._

### <a name="install-certificates"></a>Installare i certificati

1. Qualora i certificati elencati in precedenza in questo argomento siano stati acquistati da un'autorità di certificazione valida, immettere l'identificazione digitale e il nome del file PFX per i certificati nel file ConfigTemplate.xml. Impostare l'attributo **generateSelfSignedCert** su **False** e l'attributo **exportable** su **False**. Copiare i file PFX nella cartella $(DownloadPath)\\InfrastructureScripts\\Certs.
2. Se si utilizzano i certificati autofirmati (solo a scopo di verifica), eseguire il seguente script. Per creare certificati autofirmati, nel file ConfigTemplate.xml, verificare che **generateSelfSignedCert** stato impostato su **True** e **exportable** sia impostato su **True**. Lo script aggiornerà il codice XML con l'identificazione digitale per i certificati.

    ```
    # Create self-signed certs (optionally, use -Display if you only want to see commands):
    # Note: this script is completely driven off ConfigTemplate.xml
    .\New-SelfSignedCertificates.ps1 -InputXml .\ConfigTemplate.xml
    ```

3. Esportare i nuovi certificati con la chiave privata (il file PFX). Utilizzare il seguente script per generare ed eseguire i comandi di esportazione in Windows PowerShell. I file PFX verranno immessi nella cartella Certs.

    ```
    # Exports Pfx files into a directory VMs\<VMName>, all the certs will reside in a folder named Certs\
    # Feeds from XML, if certs don't have passwords then you are prompted to enter one
    .\Export-PfxFiles.ps1 -InputXml .\ConfigTemplate.xml
    ```

    > [!NOTE]
    > I certificati devono essere installati e devono essere presenti in cert:\\CurrentUser\\My. I certificati devono anche essere esportabili.

    Se si utilizzano i certificati autofirmati, ignorare la prossima sezione. Non è necessario completare questa procedura.

4. Dopo aver esportano o copiato i file PFX nella cartella $(DownloadPath)\\InfrastructureScripts\\Certs, eseguire i comandi seguenti per generare gli script che verranno inseriti nelle cartelle che corrispondono alle macchine virtuali.

    ```
    # Exports script for adding ACLs to certs into a directory VMs\<VMName>
    .\Export-CertificateAclsForVMs.ps1 -InputXml .\ConfigTemplate.xml
    
    # Exports Import-PfxFiles.ps1 script for importing PFXs on VM nodes into a directory VMS\<VMname>:
    .\Export-ImportPfxFilesScript.ps1 -InputXml .\ConfigTemplate.xml
    
    .\Export-UnblockStrongNameScript.ps1 -InputXml .\ConfigTemplate.xml
    ```

5. Copiare gli script in ciascuna cartella delle VM corrispondenti al nome della cartella.
6. In ciascuna macchina virtuale, eseguire gli script seguenti nell'ordine in cui sono visualizzati.

    ```
    #Run this script only if it exists
    .\Add-GMSAOnVM.ps1
    
    .\Import-PfxFiles.ps1
    
    .\Set-CertificateAcls.ps1
    
    #Run this script only if it exists
    .\Unblock-StrongName.ps1
    ```

### <a name="set-up-a-standalone-service-fabric-cluster"></a>Impostare un cluster Service Fabric autonomo

1. Eseguire il comando riportato di seguito per generare il file ClusterConfig.json.

    ```
    .\New-SFClusterConfig.ps1 -InputXml .\ConfigTemplate.xml
    ```

    Per ulteriori informazioni, vedere [Passaggio 1B: Creare un cluster per più computer](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-cluster-creation-for-windows-server#create-the-cluster) [Proteggere un cluster autonomo in Windows utilizzando i certificati X.509](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-windows-cluster-x509-security) e [Creare un cluster autonomo in esecuzione in Windows Server](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-cluster-creation-for-windows-server#create-the-cluster).

2. Scaricare il [pacchetto di installazione autonoma di Service Fabric](https://docs.microsoft.com/en-us/azure/service-fabric/service-fabric-cluster-creation-for-windows-server#download-the-service-fabric-standalone-package) su uno dei nodi Service Fabric. Dopo aver scaricato il file ZIP, sbloccarlo facendo clic con il pulsante destro del mouse sul file e scegliendo **Proprietà**. Nella finestra di dialogo, selezionare la casella di controllo **Sblocca** nella parte inferiore destra.
3. Copiare il file ZIP in uno dei nodi del cluster Service Fabric e decomprimerlo.
4. Eseguire i comandi seguenti per creare una regola firewall in entrata sulle porte 443 e 445 in tutti i nodi.

    ```
    #Create inbound Rule
    New-NetFirewallRule -DisplayName "SFInbound443445" -LocalPort 135, 137, 138, 139, 445, 443 -Direction Inbound -Enabled True -Protocol TCP
    
    #Test inbound Rule
    Get-NetFirewallRule -DisplayName "SFInbound443445"
    ```

5. Eseguire i comandi seguenti per creare una regola firewall in entrata sulla porta 80 solo per il nodo SSRS.

    ```
    #Create inbound Rule
    New-NetFirewallRule -DisplayName "Reporting80" -LocalPort 80 -Direction Inbound -Enabled True -Protocol TCP
    
    #Test inbound Rule
    Get-NetFirewallRule -DisplayName "Reporting80"
    ```

6. Copiare il file ClusterConfig.json nel percorso dell'installazione decompressa di Service Fabric autonomo.
7. Passare al percorso dell'installazione decompressa in Windows PowerShell utilizzando i privilegi elevati ed eseguire il comando riportato di seguito per verificare ClusterConfig.

    ```
    .\TestConfiguration.ps1 -ClusterConfigFilePath .\clusterConfig.json
    ```

8. Se il test viene superato, eseguire il seguente comando per distribuire il cluster.

    ```
    .\CreateServiceFabricCluster.ps1 -ClusterConfigFilePath .\ClusterConfig.json
    ```

9. Dopo che il cluster viene creato, aprire la funzionalità di esplorazione di Service Fabric in un computer client per convalidare l'installazione:

    1. Installare il certificato client Service Fabric in CurrentUser\\My se non è già stato installato.
    2. Andare a **Impostazioni IE** \> **Modalità compatibilità** e deselezionare la casella di controllo **Visualizza i siti intranet in modalità compatibilità**.
    3. Passare a `https://sf.d365ffo.onprem.contoso.com:19080`, dove sf.d365ffo.onprem.contoso.com è il nome host del cluster Service Fabric specificato nella zona. Se la risoluzione nome DNS non è configurata, utilizzare l'indirizzo IP del computer.
    4. Selezionare il certificato del client. Viene visualizzata la pagina **Esplora Service Fabric**.

### <a name="configure-lcs-connectivity-for-the-tenant"></a>Configurare la connettività LCS per il tenant

La distribuzione e l'assistenza di Finance and Operations sono gestite tramite LCS utilizzando un agente locale ospitato in locale. Per stabilire la connettività da LCS al tenant Finance and Operations, è necessario configurare un certificato che consente all'agente locale di agire per conto del tenant Azure AD, ad esempio Contoso.Onmicrosoft.com.

Utilizzare il certificato agente locale acquistato da un'autorità di certificazione o il certificato autofirmato generato tramite gli script.

Solo gli account utente con il ruolo della directory Amministratore globale possono aggiungere certificati per autorizzare LCS. Per impostazione predefinita, la persona che esegue l'accesso a Microsoft Office 365 per l'organizzazione sarà l'amministratore globale della directory.

> [!NOTE]
> È necessario configurare il certificato esattamente una volta per tenant. Tutti gli ambienti locali possono utilizzare lo stesso certificato per la connessione a LCS.

1. Scaricare e installare l'ultima versione di Azure PowerShell su un computer client. Per ulteriori informazioni, vedere [Installare e configurare Azure PowerShell](https://docs.microsoft.com/en-us/powershell/azure/install-azurerm-ps?view=azurermps-4.1.0&viewFallbackFrom=azurermps-4.0.0).
2. Accedere al [portale di Azure del cliente](https://portal.azure.com) per verificare di disporre del ruolo della directory Amministratore globale.
3. Eseguire il seguente script da $(DownloadPath)\\InfrastructureScripts.

   ```
   .\AddCertToServicePrincipal.ps1 -CertificateThumbprint <OnPremLocalAgent Certificate Thumbprint>
   ```

### <a name="set-up-file-storage"></a>Impostare l'archiviazione file

È necessario impostare due condivisioni file SMB 3.0 a disponibilità elevata. Per ulteriori informazioni su come abilitare SMB 3.0, vedere[Miglioramenti alla sicurezza di SMB](https://technet.microsoft.com/en-us/library/dn551363(v=ws.11).aspx#BKMK_disablesmb1).
La negoziazione dialetto protetta non è in grado di individuare o impedire i downgrade da SMB 2.0 o 3.0 a SMB 1.0. Per questo e per utilizzare totalmente le capacità della crittografia SMB, si consiglia di disabilitare il server SMB 1.0

> [!NOTE]
> Per contribuire a garantire che i dati siano protetti nell'ambiente durante l'inattività, la crittografia unità BitLocker deve essere abilitata in ogni computer. Per informazioni su come abilitare BitLocker, vedere [BitLocker: Come distribuire in Windows Server 2012 e versioni successive](https://docs.microsoft.com/en-us/windows/device-security/bitlocker/bitlocker-how-to-deploy-on-windows-server).

- Una condivisione file in cui vengono archiviati i documenti dell'utente che vengono caricati in AOS (ad esempio, \\\\DAX7SQLAOFILE1\\aos-storage).
- Una condivisione file in cui vengono archiviati gli ultimi file di configurazione e build per gestire la distribuzione (ad esempio, \\\\DAX7SQLAOFILE1\\agent)

    > [!NOTE]
    > Mantenere questo percorso della condivisione file il più breve possibile per evitare di superare la lunghezza massima del percorso dei file che verranno inseriti nella condivisione.

1. Sul computer della condivisione file, eseguire il seguente comando.

    ```
    Install-WindowsFeature -Name FS-FileServer -IncludeAllSubFeature -IncludeManagementTools
    ```
#### <a name="set-up-the-dax7sqlaofile1aos-storage-file-share"></a>Impostare la condivisione file \\\\DAX7SQLAOFILE1\\aos-storage

2. In Server Manager, selezionare **Servizi file e archiviazione** \> **Condivisioni**.
3. Fare clic su **Attività** \> **Nuova condivisione** per creare una nuova condivisione denominata **aos-storage**.
4. Concedere le autorizzazioni **Modifica** per ogni computer nel cluster Service Fabric, ad eccezione di **OrchestratorNodeType**.
5. Concedere le autorizzazioni **Modifica** per l'utente del dominio AOS (contoso\\AXServiceUser) e l'utente gMSA (contoso\\svc-AXSF).

#### <a name="set-up-the-dax7sqlaofile1agent-file-share"></a>Impostare la condivisione file \\\\DAX7SQLAOFILE1\\agent

6. Tornare in Server Manager, selezionare **Servizi file e archiviazione** \> **Condivisioni**.
7. Fare clic su **Attività** \> **Nuova condivisione** per creare una nuova condivisione denominata **agent**.
8. Concedere le autorizzazioni **Controllo completo** all'utente gMSA per l'agente di distribuzione locale (contoso\\svc-LocalAgent$).

### <a name="set-up-sql-server"></a>Impostare SQL Server

1. Installare SQL Server 2016 SP1 con disponibilità elevata, come cluster SQL che includono Storage Area Network (SAN) o in una configurazione Always-On.  Verificare che **Motore di database, Reporting Services, Ricerca full-text** e **Strumenti di gestione** siano già installati.
> [!NOTE]
> Verificare che SQL Always On sia installato secondo [Selezionare la pagina iniziale della sincronizzazione dei dati (procedure guidate per gruppo di disponibilità Always On)](https://docs.microsoft.com/en-us/sql/database-engine/availability-groups/windows/select-initial-data-synchronization-page-always-on-availability-group-wizards) e seguire [Per creare manualmente i database secondari](https://docs.microsoft.com/en-us/sql/database-engine/availability-groups/windows/select-initial-data-synchronization-page-always-on-availability-group-wizards#PrepareSecondaryDbs)
2. Eseguire il servizio SQL come utente di dominio.
3. Ottenere un certificato SSL da un'autorità di certificazione per configurare Finance and Operations. Per scopi di test, è possibile creare e usare un certificato autofirmato.

**Certificato autofirmato per l'istanza di SQL di cluster**
   ```
   New-SelfSignedCertificate -CertStoreLocation "cert:\CurrentUser\My" -DnsName "DAX7SQLAOSQLA.contososqlao.com" -Provider "Microsoft Enhanced RSA and AES Cryptographic Provider" -Subject "DAX7SQLAOSQLA.contososqlao.com"
   ```
**Certificato autofirmato per l'istanza di SQL Always-On**
```
#https://www.derekseaman.com/2014/11/sql-2014-alwayson-ag-pt-13-ssl.html

# Create certificate for each SQL Node (i.e. 2 nodes = 2 certificates)
# Run script on each node
$computerName = $env:COMPUTERNAME.ToLower() 
$domain = $env:USERDNSDOMAIN.ToLower()
$listenerName = 'dax7sqlaosqla' 
$cert = New-SelfSignedCertificate -Subject "$computerName.$domain" -DnsName "$listenerName.$domain", $listenerName, $computerName -Provider 'Microsoft Enhanced RSA and AES Cryptographic Provider'

```
4. Utilizzando il certificato, completare i passaggi in [Come abilitare la crittografia SSL per un'istanza di SQL Server utilizzando Microsoft Management Console](https://support.microsoft.com/en-us/help/316898/how-to-enable-ssl-encryption-for-an-instance-of-sql-server-by-using-microsoft-management-console) per configurare SSL in SQL Server.
5. Per ogni nodo del cluster, effettuare le seguenti operazioni. Assicurarsi di apportare le modifiche nel nodo non attivo ed eseguire il failover una volta apportate le modifiche.

    1. Importare il certificato in LocalMachine\\My.
    2. Concedere le autorizzazioni del certificato all'account del servizio utilizzato per eseguire il servizio SQL. In Microsoft Management Console (MMC), fare clic con il pulsante destro del mouse sul certificato (certlm.msc) e fare clic su **Attività** \> **Gestisci chiavi private**.
    3. Aggiungere l'identificazione digitale del certificato a HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Microsoft SQL Server\\*MSSQL.x*\\MSSQLServer\\SuperSocketNetLib\\Certificate.
    4. In Microsoft SQL Server Configuration Manager, impostare **ForceEncryption** su **Sì**.

6. Esportare la chiave pubblica del certificato (il file CER) e installarla nella radice attendibile di ogni nodo Service Fabric.

### <a name="configure-the-orchestratordata-database"></a>Configurare il database OrchestratorData

1.  Creare un database vuoto e denominarlo **OrchestratorData**. Questo database è utilizzato da agente locale ospitato in locale per gestire le distribuzioni.
2.  Concedere all'agente locale le autorizzazioni locali gMSA (svc-LocalAgent$) **db\_owner** per il database:

    1. Nell'albero, espandere il nome del server, espandere **Sicurezza** \> **Accessi** e quindi fare clic con il pulsante destro del mouse e scegliere **Nuovo accesso**.

        ![Comando Nuovo accesso](./media/OPSetup_01_NewLogin.png)


    2. Cercare l'account del servizio **svc-LocalAgent$**. Fare clic su **Ubicazioni** e selezionare e **Directory completa**, fare clic su **Tipi di oggetti** e selezionare **Account servizio**.

        ![Selezionare la finestra di dialogo Utente, Account del servizio o Gruppo](./media/OPSetup_02_SelectUserServiceAccountOrGroupDialogBox.png)

    3. Impostare **Assegna ServerRole** su **Pubblico**.
    4. Assegnare l'autorizzazione ruolo di database **db\_owner** al database OrchestratorData.

### <a name="configure-the-finance-and-operations-database"></a>Configurare il database di Finance and Operations

1. Accedere a LCS (<https://lcs.dynamics.com/v2>).
2. Nel dashboard, fare clic sul riquadro **Raccolta di risorse condivise**.
3. Fare clic sulla scheda **Modello** 
4. Nella griglia, fare clic sulla riga **Dynamics 365 for Operations locale, Enterprise Edition - Dati dimostrativi** per scaricare lo ZIP.
5. Lo ZIP contiene file BAK con dati dimostrativi e vuoti. A seconda delle esigenze selezionare il file BAK appropriato. Ad esempio, se sono necessari i dati dimostrativi, ripristinare il file AxBootstrapDB_Demodata.bak. 
6. Ripristinare il database AxBootstrapDB_DemoData.bak.
7. Rinominare il database **AXDBRAIN**.
8. Effettuare le seguenti query sul database ripristinato.

    ```
    ALTER DATABASE AXDBRAIN
    SET READ_COMMITTED_SNAPSHOT ON
    GO
    
    ALTER DATABASE AXDBRAIN
    SET ALLOW_SNAPSHOT_ISOLATION ON
    GO
    ```

4. Aggiornare i file del database:

    1. Fare clic con il pulsante destro del mouse sul database, quindi selezionare **Proprietà**.
    2. Fare clic su **File** per modificare le proprietà file del database.
    3. Nel campo **Dimensioni iniziali (MB)**, immettere un valore maggiore di 5.120.

        ![Finestra di dialogo Proprietà del database](./media/OPSetup_03_DatabasePropertiesDialogBox.png)

    4. Per **AXDBBuild\_Data**, impostare il campo **Aumento automatico/Ingrandisci** su **200** megabyte (MB).
    5. Per **AXDBBuild\_Log**, impostare il campo **Aumento automatico/Ingrandisci** su **500** MB.

        ![Modificare la finestra di dialogo Aumento automatico](./media/OPSetup_04_ChangeAutogrowthDialogBox.png)

5. Creare un nuovo utente con l'autenticazione SQL abilitata (axdbadmin).
6. Utilizzare le informazioni nella tabella seguente per mappare gli utenti e i ruoli di database.

    | Utente             | Tipo    | Ruolo di database |
    |------------------|---------|---------------|
    | svc-AXSF$        | gMSA    | db\_owner     |
    | svc-LocalAgent$  | gMSA    | db\_owner     |
    | svc-FRPS$        | gMSA    | db\_owner     |
    | svc-FRAS$        | gMSA    | db\_owner     |
    | axdbadmin        | SqlUser | db\_owner     |

7. Concedere all'utente svc-AXSF$ e all'utente axdbadmin SQL l'accesso ai seguenti ruoli del database tempdb:

    - db\_datareader
    - db\_datawriter
    - db\_ddladmin

8. In Management Studio, eseguire i seguenti comandi Transact SQL (T-SQL):

    ```
    GRANT VIEW SERVER STATE TO axdbadmin
    GRANT VIEW SERVER STATE TO [contososqlao\svc-AXSF$]
    ```
9. Eseguire il seguente comando:
```
.\Reset-DatabaseUsers.ps1 -DatabaseServer ‘<FQDN of the SQL server>’ -DatabaseName '<AX database name>'
```

### <a name="configure-the-financial-reporting-database"></a>Configurare il database di report finanziari

1.  Creare un database vuoto e denominarlo **FinancialReporting**.
2.  Utilizzare le informazioni nella tabella seguente per mappare gli utenti e i ruoli di database.

    | Utente             | Tipo | Ruolo di database |
    |------------------|------|---------------|
    | svc-LocalAgent$  | gMSA | db\_owner     |
    | svc-FRPS$        | gMSA | db\_owner     |
    | svc-FRAS$        | gMSA | db\_owner     |

### <a name="encrypt-credentials"></a>Crittografare le credenziali

1. In qualsiasi computer client, installare il certificato di crittografia nell'archivio certificati LocalMachine\\My.
2. Concedere l'accesso in lettura dell'utente corrente alla chiave privata del certificato.
3. Creare il file Credentials.json come indicato di seguito.

    ```
    {
        "AosPrincipal": {
            "AccountPassword": "<encryptedDomainUserPassword>"
        },
        "AosSqlAuth": {
            "SqlUser": "<encryptedSqlUser>",
            "SqlPwd": "<encryptedSqlPassword>"
        }
    }
    ```

    - **AccountPassword** è la password crittografata dell'utente di dominio per l'utente di dominio AOS (contoso\\axserviceuser).
    - **SqlUser** è l'utente crittografato di SQL (axdbadmin) con accesso al database Finance and Operations (AXDBRAIN) e **SqlPassword** è la password SQL crittografata.

4. Copiare il file JSON nella condivisione file SMB, \\\\AX7SQLAOFILE1\\agent\\Credentials\\Credentials.json.
5. Aggiornare il file Credentials.json con i valori crittografati.

    ```
    # Service fabric API to encrypt text and copy it to the clipboard.
    Invoke-ServiceFabricEncryptText -Text '<textToEncrypt>' -CertThumbprint '<DataEncipherment Thumbprint>' -CertStore -StoreLocation LocalMachine -StoreName My | clip
    ```

    1. In Credentials.json sostituire **\<encryptedDomainUserPassword\>** con la password crittografata del dominio.
    2. Sostituire **\<encryptedSqlUser\>** con l'utente SQL crittografato di Finance and Operations.
    3. Sostituire **\<encryptedSqlPassword\>** con la password SQL crittografata di Finance and Operations.
    
### <a name="set-up-ssrs"></a>Imposta SSRS

1.  Prima di iniziare, assicurarsi che i prerequisiti elencati all'inizio di questo argomento siano installati.
2.  Seguire i passaggi per [Configurare SQL Server Reporting Services per una distribuzione locale](../analytics/configure-ssrs-on-premises.md).

### <a name="configure-ad-fs"></a>Configurare AD FS

Prima di poter eseguire la procedura, AD FS deve essere distribuito in Windows Server 2016. Per informazioni sulla distribuzione di AD FS, vedere [Guida alla distribuzione di AD FS in Windows Server 2016 e 2012 R2](https://docs.microsoft.com/en-us/windows-server/identity/ad-fs/deployment/windows-server-2012-r2-ad-fs-deployment-guide).

Finance and Operations richiede la configurazione aggiuntiva oltre alla configurazione predefinita di fabbrica di AD FS. Per i seguenti passaggi, Windows PowerShell viene eseguito in un computer in cui è installato il servizio ruolo AD FS. L'account utente deve disporre delle autorizzazioni sufficienti per amministrare AD FS. Ad esempio, l'utente deve disporre di un account amministratore di dominio.

1. Configurare l'identificatore AD FS in modo che corrisponda all'emittente di token AD FS.

    ```
    $adfsProperties = Get-AdfsProperties
    Set-AdfsProperties -Identifier $adfsProperties.IdTokenIssuer
    ```

2. Disattivare l'autenticazione integrata di Windows (WIA) per le connessioni di autenticazione intranet a meno che AD FS non sia configurato per gli ambienti misti. Per ulteriori informazioni su come configurare WIA in modo da poterlo utilizzare con AD FS, vedere [Configurare i browser per usare l'autenticazione integrata di Windows con AD FS](https://docs.microsoft.com/en-us/windows-server/identity/ad-fs/operations/configure-ad-fs-browser-wia).

   ```
   Set-AdfsGlobalAuthenticationPolicy -PrimaryIntranetAuthenticationProvider FormsAuthentication, MicrosoftPassportAuthentication
   ```

3. Per accedere, l'indirizzo di posta elettronica dell'utente deve essere un input di autenticazione accettabile.

   ```
   Add-Type -AssemblyName System.Net
   $fdqn = ([System.Net.Dns]::GetHostEntry('localhost').HostName).ToLower()
   $domainName = $fdqn.Substring($fdqn.IndexOf('.')+1)
   Set-AdfsClaimsProviderTrust -TargetIdentifier 'AD AUTHORITY' -AlternateLoginID mail -LookupForests $domainName
   ```

Per consentire ad AD FS di considerare attendibile Finance and Operations per lo scambio di autenticazione, le diverse voci dell'applicazione devono essere registrate in AD FS con un gruppo per l'applicazione AD FS. Per velocizzare il processo di impostazione e contribuire a ridurre gli errori, è possibile utilizzare il seguente script per la registrazione. Copiar lo script Publish-ADFSApplicationGroup.ps1 e la directory D365FO-OP in un computer in cui è installato il servizio ruolo AD FS. Eseguire quindi lo script utilizzando un account utente, ad esempio un account amministratore, con le autorizzazioni sufficienti per amministrare AD FS. Per ulteriori informazioni sull'utilizzo dello script, vedere la documentazione riportata nello script. Annotare gli ID client specificati nell'output poiché verranno richiesti in LCS in un passaggio successivo.

```
# Host URL is your DNS record\host name for accessing the AOS
.\Publish-ADFSApplicationGroup.ps1 -HostUrl 'ax.d365ffo.onprem.contoso.com'
```

La console di gestione di AD FS deve essere simile alla figura seguente. Per aprire Server Manager, fare clic su **Strumenti** \> **Gestione AD FS**, quindi nella parte inferiore della visualizzazione ad albero sulla sinistra fare clic su **Gruppi di applicazioni**. Fare doppio clic sul gruppo di applicazioni per visualizzare ulteriori dettagli.

![Proprietà del gruppo di applicazioni](./media/OPSetup_05_ApplicatioGroupProperties.png)

Infine, per una verifica dell'integrità, assicurarsi che sia possibile l'accesso all'URL della configurazione OpenID di AD FS su un nodo Service Fabric di tipo **AOSNodeType** andando in `https://<adfs-dns-name>/adfs/.well-known/openid-configuration` in un Web browser. Se si riceve un messaggio indicante che il sito non è protetto, non è stato aggiunto il certificato SSL di AD FS all'archivio dell'autorità di certificazione radice attendibile. Questo passaggio è descritto nella Guida alla distribuzione di AD FS. Se si accede correttamente all'URL, viene restituito un file JavaScript Object Notation (JSON) contenente la configurazione AD FS e l'indicazione che l'URL di AD FS è attendibile.

Con questo l'impostazione dell'infrastruttura è completata. Nelle sezioni seguenti viene descritto come passare a [LCS](https://lcs.dynamics.com) per impostare il connettore e distribuire l'ambiente Dynamics 365 for Finance and Operations.

## <a name="configure-connector-and-install-on-premises-local-agent"></a>Configurare il connettore e installare l'agente locale ospitato in locale

1. Accedere a [LCS](https://lcs.dynamics.com/) e aprire il progetto di implementazione locale.
2. Nel menu a forma di hamburger, fare clic su **Impostazioni progetto**.

    ![Comando Impostazioni progetto](./media/OPSetup_06_ProjectSettings.png)

3. Fare clic su **Connettori locali**.
4. Fare clic su **Aggiungi** per creare un nuovo connettore.
5. Nella scheda **Imposta infrastruttura host** scaricare il programma di installazione dell'agente.

    ![Pulsante Scarica programma di installazione dell'agente nella scheda Imposta infrastruttura host](./media/OPSetup_07_DownloadAgentInstaller.png)

6. Verificare che il file ZIP sia sbloccato. Fare clic con il pulsante destro del mouse sul file selezionare **Proprietà** e quindi **Sblocca**.
7. Decomprimere il programma di installazione dell'agente in uno dei nodi Service Fabric di tipo **OrchestratorType**.
8. Nella scheda **Configurazione agente**, immettere le impostazioni di configurazione.
9. Salvare la configurazione e fare clic su **Scarica configurazioni** per scaricare il file di configurazione localagent-config.json.

    ![Pulsante Scarica configurazioni nella scheda Configura agente](./media/OPSetup_08_DownloadConfigurations.png)

10. Copiare il file localagent-config.json nel computer in cui si trova il pacchetto del programma di installazione dell'agente.
11. In una finestra del prompt dei comandi, eseguire il seguente comando accedendo alla cartella che contiene il programma di installazione dell'agente.

    ```
    LocalAgentCLI.exe Install <path to config.json>
    ```

    > [!NOTE]
    > L'utente che esegue questo comando deve disporre delle autorizzazioni **db\_owner** nel database OrchestratorData.
    
12. Al termine dell'installazione dell'agente locale, spostarsi di nuovo al connettore locale in LCS.
13. Nella scheda **Convalida impostazione** fare clic sul pulsante **Agente messaggio**. In tal modo si testa la connettività LCS con l'agente locale. Quando la connessione viene stabilita correttamente la pagina assomiglierà al grafico riportato di seguito.

     ![Convalidare l'agente](./media/ValidateAgent.PNG)

## <a name="deploy-your-dynamics-365-for-finance-and-operations-on-premises-environment"></a>Distribuire l'ambiente Dynamics 365 for Finance and Operations (locale)

1. Passare al progetto locale in LCS, selezionare **Ambiente**, **Sandbox** e fare clic su **Configura**
2. Selezionare la **Topologia ambiente** e usare la procedura guidata per inizializzare la distribuzione.
3. L'agente locale preleverà la richiesta di distribuzione, avvierà la distribuzione e comunicherà ad LCS quando è pronta.

