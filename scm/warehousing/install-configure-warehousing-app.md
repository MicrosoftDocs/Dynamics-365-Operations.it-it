---
title: Installare e configurare Microsoft Dynamics 365 per le operazioni &#8211; Immagazzinamento
description: In questo argomento viene descritto come impostare e configurare Microsoft Dynamics 365 per le operazioni di immagazzinando.
author: YuyuScheller
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: SysAADClientTable, WHSMobileAppField, WHSMobileAppFieldPriority, WHSRFMenu, WHSRFMenuItem, WHSWorker
audience: Application User, IT Pro
ms.search.scope: Operations, Core
ms.custom: 267694
ms.assetid: d95d43b2-13ff-4189-a71a-3a1fb57d55ed
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mafoge
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: 231c087ddc976aa552fc9cd6c89188f82a0247d1
ms.lasthandoff: 03/31/2017


---

# <a name="install-and-configure-microsoft-dynamics-365-for-operations-8211-warehousing"></a>Installare e configurare Microsoft Dynamics 365 per le operazioni &#8211; Immagazzinamento

In questo argomento viene descritto come impostare e configurare Microsoft Dynamics 365 per le operazioni di immagazzinando.

Dynamics 365 per le operazioni di magazzino è un'applicazione disponibile nel Google e Play Store Connect in Windows. Per la versione corrente di Microsoft Dynamics 365 per le operazioni, questo app viene immesso come componente autonoma, ovvero automaticamente la distribuzione delle unità utilizzate per le attività di magazzino. Per utilizzare il nell'app Approvazioni Dynamics 365 per l'ambiente delle operazioni, è necessario scaricare il app per ciascuna unità e configurarla per connettersi a Dynamics il 365 per l'ambiente delle operazioni. In questo argomento viene descritto come impostare il app per le unità. E viene illustrato come configurare il app per connettersi a l Dynamics 365 per l'ambiente delle operazioni.

## <a name="prerequisites"></a>Prerequisiti
Il app è disponibile in Android e sui sistemi operativi Windows. Per utilizzare questo app, è necessario avere uno dei sistemi operativi supportati impostati per le unità. È inoltre necessario avere una delle seguenti versioni di Supporto tecnico Microsoft Dynamics 365 per le operazioni. Utilizzare le informazioni nella tabella seguente per valutare se l'ambiente di software e hardware è pronti a supportare l'installazione.

| Piattaforma                    | Versione                                                                                                                                                                     |
|-----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Android                     | 4.4, 5.0, 6.0                                                                                                                                                               |
| Windows (UWP)               | Windows 10 (tutte le versioni)                                                                                                                                                   |
| Dynamics 365 per le operazioni | Microsoft Dynamics 365 per la versione 1611 - di operazioni o versione 7.0/7.0.1 di Microsoft Dynamics Dynamics AX 2 e aggiornare la piattaforma di Microsoft Dynamics AX con il 3210014 KB di hotfix |

## <a name="get-the-app"></a>Ottenere il app
-   Windows UWP () - 070- Dynamics 365 per le operazioni di immagazzinando in Windows Store (https://www.microsoft.com/store/apps/9p1bffd5tstm)]
-   Android - 070- Dynamics 365 per le operazioni e che disponibile nel Google Play Store (https://play.google.com/store/apps/details?id=com.Microsoft.Dynamics365forOperationsWarehousing)]

## <a name="create-a-web-service-application-in-active-directory"></a>Creare una richiesta di assistenza Web in Active Directory
Per abilitare le app di interagire con Dynamics 365 specifico per le operazioni server, è necessario registrare una richiesta di assistenza Web in un azzurrato Active Directory per Dynamics 365 del titolare delle operazioni. Per motivi di protezione, si consiglia di creare una domanda di un servizio Web di ogni unità utilizzato. Per creare una domanda di assistenza Web in Active Directory azzurrato (ANNUNCIO azzurrato), effettuare le seguenti operazioni:

1.  In una Web browser, passare all'> indirizzo https://manage.windowsazure.com.
2.  Immettere il nome e la password dell'utente che ha accesso alla sottoscrizione azzurrata.
3.  Nel portale azzurrato, nel riquadro di spostamento sinistro, fare clic su ** Active Directory **. [] (. /media/wh-01-active-directory-example.png![) [] (wh-01-active-directory-example. /media/wh-01-active-directory-example.png)](. /media/wh-01-active-directory-example.png)
4.  Nella griglia, selezionare l'istanza di Active Directory utilizzate da Dynamics 365 per le operazioni.
5.  Sulla barra degli strumenti superiore, fare clic su ** ** applicazioni. ![[] (wh-02-active-directory-applications. /media/wh-02-active-directory-applications-1024x197.png)](. /media/wh-02-active-directory-applications.png)
6.  Nel riquadro inferiore, fare clic su ** aggiungere **. ** Aggiunta dell'applicazione ** di inizio della procedura guidata.
7.  Immettere un nome per la domanda e selezionare ** API Web e/o di applicazione Web **. ![[] (wh-03-active-directory-add-application. /media/wh-03-active-directory-add-application.png)](. /media/wh-03-active-directory-add-application.png)
8.  Immettere il accesso nell'URL, ovvero l'applicazione URL nel, il titolare le operazioni l'URL principale. Segno- l'URL non attivamente attualmente utilizzato nell'app autenticare il, ma è obbligatorio. Immettere lo stesso URL nel campo URI ID App. ![[] (wh-04-ad-add-properties. /media/wh-04-ad-add-properties.png)](. /media/wh-04-ad-add-properties.png)
9.  Passare ** configurare ** nella scheda. ![[] (wh-05-ad-configure-app. /media/wh-05-ad-configure-app.png)](. /media/wh-05-ad-configure-app.png)
10. Scorrere fino a indicare ** autorizzazioni ad altre applicazioni ** la sezione. ** Fare clic su Aggiungi ** applicazione. ![[] (wh-06-ad-app-add-permissions. /media/wh-06-ad-app-add-permissions.png)](. /media/wh-06-ad-app-add-permissions.png)
11. Selezionare ** Microsoft Dynamics ERP ** nell'elenco. Fare clic su ** assegno completo ** viene subito nell'angolo destro della pagina. ![[] (wh-07-ad-select-permissions. /media/wh-07-ad-select-permissions.png)](. /media/wh-07-ad-select-permissions.png)
12. In ** autorizzazioni del delegato ** elenchi, selezionare tutte le caselle di controllo. Click **Save**. ![[] (wh-08-ad-delegate-permissions. /media/wh-08-ad-delegate-permissions.png)](. /media/wh-08-ad-delegate-permissions.png)
13. Annotare delle seguenti informazioni:
    -   ** Identificazione del client ** - poiché si sposta il contenuto della schermata verso l'alto la pagina, vedrete ** identificazione del client ** visualizzare.
    -   ** La chiave ** - ** chiavi ** nell'area, creare una chiave selezionando la durata e di copiare la chiave. Questa chiave successivamente verrà applicata a l ** segreto client **.

## <a name="create-and-configure-a-user-account-in-dynamics-365-for-operations"></a>Creare e configurare un account utente in Dynamics 365 per le operazioni
Per attivare Dynamics 365 per le operazioni utilizzare l'applicazione azzurrata AD, è necessario completare i seguenti passaggi di configurazione:

1.  Creare un nuovo account utente in Active Directory azzurrato per Dynamics 365 del titolare delle operazioni. Lo scopo di questo account utente consentono di accedere al servizio personalizzato specifico dell'app Approvazioni di immagazzinamento, che Dynamics 365 per il server di operazioni espone. Al termine di questo passaggio, sarà possibile credenziali utente di WMDP, costituita da un indirizzo di posta elettronica di WMDP e una password di WMDP. Per conoscere illustrati i passaggi di base per aggiungere gli utenti a ANNUNCIO azzurrato e di Dynamics 365 per le operazioni, fare riferimento a questa esercitazione: [Iscriversi a Microsoft Dynamics 365 per la sottoscrizione] di operazioni (/dynamics365/operations/dev-itpro/sign-up-preview-subscription).
2.  Creare Dynamics 365 per l'utente di operazioni che corrisponde alle credenziali di immagazzinamento utente dell'app Approvazioni.
    1.  In Dynamics 365 per le operazioni, spostarsi ** Amministrazione sistema ** &gt; ** il Ordinarie ** &gt; ** ** utenti.
    2.  Creare un nuovo utente.
    3.  Assegnare l'utente del dispositivo mobile di magazzino, come illustrato nella schermata. ![[] (wh-09-add-user-security-role. /media/wh-09-add-user-security-role.png)](. /media/wh-09-add-user-security-role.png)

3.  Associare la domanda di lavoro azzurrata di Active Directory all'utente di immagazzinamento dell'app Approvazioni.
    1.  In Dynamics 365 per le operazioni, spostarsi ** Amministrazione sistema ** &gt; ** l'impostazione ** &gt; ** applicazioni azzurrate di Active Directory **.
    2.  Creare una nuova riga.
    3.  Immettere il ** identificazione del client ** (verificato nell'ultima sezione), assegnarle un nome e selezionare l'utente creato in precedenza. Si consiglia di etichettiate tutte le unità in modo che sia possibile rimuovere facilmente il relativo accesso a Dynamics 365 per le operazioni della pagina nel caso vengano perse. ![[] (wh-10-ad-applications-form. /media/wh-10-ad-applications-form.png)](. /media/wh-10-ad-applications-form.png)

## <a name="configure-the-application"></a>Configurazione dell'applicazione
È necessario configurare il nell'app per connettersi a Dynamics 365 per il server delle operazioni con l'applicazione azzurrata AD. A tale scopo, effettuare le operazioni seguenti.

1.  Nel'app Approvazioni, passare ** impostazioni di connessione **.
2.  Rimuovere ** modalità dimostrativi ** il campo. ![[] (wh-11-app-connection-settings-demo-mode. /media/wh-11-app-connection-settings-demo-mode-169x300.png)](. /media/wh-11-app-connection-settings-demo-mode.png)
3.  Immettere le seguenti informazioni: ** - Identificazione azzurrata client di Active Directory ** - Identificazione del client è ottenuta al passaggio 13 in "crea una domanda di assistenza Web in Active Directory". - ** Il segreto azzurrato client di Active Directory ** il segreto client viene ottenuto nel passaggio 13 in "crea una domanda di assistenza Web in Active Directory". - ** La risorsa azzurrata di Active Directory ** la risorsa azzurrata di Rubrica AD viene descritto Dynamics 365 per la l'URL principale delle operazioni. ** ** Nota: Non terminare questo campo con un carattere in avanti di barra (/). - ** Inquilino azzurrato di Active Directory ** univoco del titolare della Rubrica azzurrato AD utilizzato con Dynamics 365 per il server di operazioni: https://login.windows.net/your-AD-tenant-ID&lt;&gt;. Se ad esempio: https://login.windows.net/contosooperations.onmicrosoft.com. 
** ** Nota: Non terminare questo campo con un carattere in avanti di barra (/). - ** Società ** consente della persona giuridica in Dynamics 365 per le operazioni in cui si desidera collegare la domanda. ![[] (wh-12-app-connection-settings. /media/wh-12-app-connection-settings-169x300.png)](. /media/wh-12-app-connection-settings.png)
4.  Selezionare ** posteriore ** viene subito nell'angolo superiore sinistro dell'applicazione. L'applicazione verrà collegherà Dynamics al 365 del server delle operazioni e la schermata di accesso per il lavoratore di magazzino. ![[] (wh-13-log-in-screen. /media/wh-13-log-in-screen-180x300.png)](. /media/wh-13-log-in-screen.png)

## <a name="remove-access-for-a-device"></a>Rimuovere l'accesso per un'unità
In caso di un'unità persa o compromessa, è necessario rimuovere l'accesso a Dynamics 365 per le operazioni dell'unità. Nei passaggi seguenti viene descritto il processo consiglia di rimuovere l'accesso.

1.  In Dynamics 365 per le operazioni, spostarsi ** Amministrazione sistema ** &gt; ** l'impostazione ** &gt; ** applicazioni azzurrate di Active Directory **.
2.  Consente di eliminare la riga corrispondente all'unità a cui si desidera rimuovere l'accesso. Rettifica ** identificazione del client ** utilizzato per l'unità deselezionata.
3.  Accesso il portale classico azzurrato< all'> indirizzo https://manage.windowsazure.com.
4.  Fare clic su ** Active Directory ** l'icona il menu sinistro e fare clic sulla directory desiderata.
5.  Nel menu superiore, quindi su ** applicazioni ** quindi fare clic sulla richiesta che si desidera configurare. ** Avvio veloce ** la pagina verrà publicata singolo con accesso in e altre informazioni di configurazione.
6.  Fare clic su ** configurare ** la scheda, fare scorrere l'elenco e verificare che ** identificazione del client ** dell'applicazione sia lo stesso di nel passaggio 2 di questa sezione.
7.  Fare clic su Elimina ** ** viene subito la barra di comando.
8.  Fare clic su Sì ** ** nel messaggio di conferma.



