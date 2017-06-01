---
title: Installare e configurare Microsoft Dynamics 365 for Operations &#8211; Magazzino
description: In questo argomento viene descritto come installare e configurare Microsoft Dynamics 365 for Operations - Magazzino.
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 46b4809ae89f90295766e95ce78a8f019de0cdae
ms.contentlocale: it-it
ms.lasthandoff: 05/25/2017


---

# <a name="install-and-configure-microsoft-dynamics-365-for-operations-8211-warehousing"></a>Installare e configurare Microsoft Dynamics 365 for Operations &#8211; Magazzino

[!include[banner](../includes/banner.md)]


In questo argomento viene descritto come installare e configurare Microsoft Dynamics 365 for Operations - Magazzino.

Dynamics 365 for Operations - Magazzino è un'applicazione disponibile in Google Play Store e Windows Store. Per la versione corrente di Microsoft Dynamics 365 for Operations, questa app viene fornita come componente autonomo, ovvero con auto-distribuzione sui dispositivi utilizzati per le attività di magazzino. Per utilizzare l'app nell'ambiente Dynamics 365 for Operations, è necessario scaricarla su ciascun dispositivo e configurarla per connettersi all'ambiente Dynamics 365 for Operations. In questo argomento viene descritto come installare l'app sui dispositivi. Viene inoltre illustrato come configurare l'app per connettersi all'ambiente Dynamics 365 for Operations.

## <a name="prerequisites"></a>Prerequisiti
L'app è disponibile sui sistemi operativi Android e Windows. Per utilizzare questo app, è necessario avere uno dei sistemi operativi supportati installati sulle unità. È inoltre necessario avere una delle seguenti versioni supportate di Dynamics 365 for Operations. Utilizzare le informazioni nella tabella seguente per valutare se l'ambiente software e hardware è pronto a supportare l'installazione.

| Piattaforma                    | Versione                                                                                                                                                                     |
|-----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Android                     | 4.4, 5.0, 6.0                                                                                                                                                               |
| Windows (UWP)               | Windows 10 (tutte le versioni)                                                                                                                                                   |
| Dynamics 365 for Operations | Microsoft Dynamics 365 for Operations versione 1611 -o- Microsoft Dynamics Dynamics AX versione 7.0/7.0.1 e aggiornamento 2 alla piattaforma Microsoft Dynamics AX con aggiornamento rapido KB 3210014 |

## <a name="get-the-app"></a>Ottenere l'app
-   Windows (UWP) - [Dynamics 365 for Operations - Magazzino in Windows Store](https://www.microsoft.com/store/apps/9p1bffd5tstm)
-   Android - [Dynamics 365 for Operations - Magazzino in Google Play Store](https://play.google.com/store/apps/details?id=com.Microsoft.Dynamics365forOperationsWarehousing)

## <a name="create-a-web-service-application-in-active-directory"></a>Creare un'applicazione servizio Web in Active Directory
Per abilitare l'app a interagire con un server Dynamics 365 for Operations specifico, è necessario registrare un'applicazione servizio Web in Azure Active Directory per il tenant di Dynamics 365 for Operations. Per motivi di sicurezza, si consiglia di creare un'applicazione servizio Web per ogni dispositivo utilizzato. Per creare un'applicazione servizio Web in Azure Active Directory (Azure AD), effettuare le seguenti operazioni:

1.  In un Web browser, passare a <https://manage.windowsazure.com>.
2.  Immettere il nome e la password dell'utente che ha accesso alla sottoscrizione Azure.
3.  Nel portale di Azure, nel riquadro di spostamento sinistro, fare clic su **Active Directory**.[](./media/wh-01-active-directory-example.png)[![wh-01-active-directory-example](./media/wh-01-active-directory-example.png)](./media/wh-01-active-directory-example.png)
4.  Nella griglia, selezionare l'istanza di Active Directory utilizzata da Dynamics 365 for Operations.
5.  Nella barra degli strumenti superiore, fare clic su **Applicazioni**. [![wh-02-active-directory-applications](./media/wh-02-active-directory-applications-1024x197.png)](./media/wh-02-active-directory-applications.png)
6.  Nel riquadro inferiore fare clic su **Aggiungi**. Viene avviata la procedura guidata **Aggiungi applicazione**.
7.  Immettere un nome per l'applicazione e selezionare **Applicazione Web e/o API Web**. [![wh-03-active-directory-add-application](./media/wh-03-active-directory-add-application.png)](./media/wh-03-active-directory-add-application.png)
8.  Immettere l'URL di accesso, ovvero l'URL dell'applicazione nel tenant, l'URL radice di Operations. L'URL di accesso non è attivamente attualmente utilizzata per autenticare l'app, ma il campo è obbligatorio. Immettere lo stesso URL nel campo URI ID app. [![wh-04-ad-add-properties](./media/wh-04-ad-add-properties.png)](./media/wh-04-ad-add-properties.png)
9.  Andare alla scheda **Configura**. [![wh-05-ad-configure-app](./media/wh-05-ad-configure-app.png)](./media/wh-05-ad-configure-app.png)
10. Scorrere in basso fino a visualizzare la sezione **Autorizzazioni per altre applicazioni**. Fare clic su **Aggiungi applicazione**. [![wh-06-ad-app-add-permissions](./media/wh-06-ad-app-add-permissions.png)](./media/wh-06-ad-app-add-permissions.png)
11. Selezionare **Microsoft Dynamics ERP** nell'elenco. Fare clic sul pulsante **Verifica completa** nell'angolo in alto a destra della pagina. [![wh-07-ad-select-permissions](./media/wh-07-ad-select-permissions.png)](./media/wh-07-ad-select-permissions.png)
12. Nell'elenco **Delega autorizzazioni**, selezionare tutte le caselle di controllo. Fare clic su **Salva**. [![wh-08-ad-delegate-permissions](./media/wh-08-ad-delegate-permissions.png)](./media/wh-08-ad-delegate-permissions.png)
13. Prendere nota delle informazioni seguenti.
    -   **ID client** - scorrendo in alto la pagina si vedrà l'**ID client**.
    -   **Chiave** - nella sezione **Chiavi** creare una chiave selezionando la durata e copiare la chiave. Questa chiave successivamente verrà detta **Segreto client**.

## <a name="create-and-configure-a-user-account-in-dynamics-365-for-operations"></a>Creare e configurare un account utente in Dynamics 365 for Operations
Per abilitare Dynamics 365 for Operations a utilizzare l'applicazione Azure AD, è necessario completare i seguenti passaggi di configurazione:

1.  Creare un nuovo account utente in Azure Active Directory per il tenant Dynamics 365 for Operations. Lo scopo di questo account utente è di accedere al servizio personalizzato specifico dell'app Magazzino, esposta dal server Dynamics 365 for Operations. Al termine di questo passaggio, si disporrà delle credenziali utente WMDP, costituite da un indirizzo di posta elettronica WMDP e una password WMDP. Per informazioni sui passaggi di base per aggiungere utenti a Azure AD e Dynamics 365 for Operations, fare riferimento a questa esercitazione: [Iscriversi per una sottoscrizione di Microsoft Dynamics 365 for Operations](/dynamics365/operations/dev-itpro/dev-tools/sign-up-preview-subscription).
2.  Creare un utente di Dynamics 365 for Operations che corrisponde alle credenziali dell'utente dell'app per il magazzino.
    1.  In Dynamics 365 for Operations, andare a **Amministrazione sistema** &gt; **Comune** &gt; **Utenti**.
    2.  Creare un nuovo utente.
    3.  Assegnare l'utente del dispositivo mobile di magazzino, come illustrato nella schermata. [![wh-09-add-user-security-role](./media/wh-09-add-user-security-role.png)](./media/wh-09-add-user-security-role.png)

3.  Associare l'applicazione Azure Active Directory all'utente dell'app del magazzino.
    1.  In Dynamics 365 for Operations, andare a **Amministrazione sistema** &gt; **Impostazione** &gt; **Applicazioni di Azure Active Directory**.
    2.  Creare una nuova riga.
    3.  Immettere il ***Client ID** (ottenuto nell'ultima sezione), assegnare un nome e selezionare l'utente creato in precedenza. Si consiglia di etichettare tutti i dispositivi in modo che sia possibile rimuovere facilmente l'accesso a Dynamics 365 for Operations da questa pagina nel caso vengano persi. [![wh-10-ad-applications-form](./media/wh-10-ad-applications-form.png)](./media/wh-10-ad-applications-form.png)

## <a name="configure-the-application"></a>Configurare l'applicazione
È necessario configurare 'app sul dispositivo per connettersi al server Dynamics 365 for Operations tramite l'applicazione Azure AD. Per effettuare questa operazione, attenersi alla seguente procedura:

1.  Nel'app, andare a **Impostazioni di connessione**.
2.  Cancellare il campo **Modalità demo**. [![wh-11-app-connection-settings-demo-mode](./media/wh-11-app-connection-settings-demo-mode-169x300.png)](./media/wh-11-app-connection-settings-demo-mode.png)
3.  Immettere le seguenti informazioni: **ID client Azure Active Directory** - L'ID client ottenuto nel passaggio 13 in "Creare un'applicazione servizio Web in Active Directory". -**Segreto client Azure Active Directory** - il segreto client ottenuto nel passaggio 13 in "Creare un'applicazione servizio Web in Active Directory". - **Risorsa Azure Active Directory** - La risorsa Azure AD Directory mostra l'URL radice di Dynamics 365 for Operations. **Nota**: non terminare questo campo con un carattere di barra (/). - **Tenant Azure Active Directory** - Il tenant Azure AD usato con il server Dynamics 365 for Operations: https://login.windows.net/&lt;ID-tenant-AD&gt;. Ad esempio: https://login.windows.net/contosooperations.onmicrosoft.com. 
**Nota**: non terminare questo campo con un carattere di barra (/). - **Società***- Immettere la persona giuridica in Dynamics 365 for Operations a cui si desidera connettere l'applicazione. [![wh-12-app-connection-settings](./media/wh-12-app-connection-settings-169x300.png)](./media/wh-12-app-connection-settings.png)
4.  Selezionare il pulsante **Indietro** nell'angolo superiore sinistro dell'applicazione. L'applicazione si connetterà al server Dynamics 365 for Operations e apparirà la schermata di accesso per il lavoratore di magazzino. [![wh-13-log-in-screen](./media/wh-13-log-in-screen-180x300.png)](./media/wh-13-log-in-screen.png)

## <a name="remove-access-for-a-device"></a>Rimuovere l'accesso per un dispositivo
In caso di un dispositivo perso o compromesso, è necessario rimuovere l'accesso a Dynamics 365 for Operations del dispositivo. Nei passaggi seguenti viene descritto il processo consigliato per rimuovere l'accesso.

1.  In Dynamics 365 for Operations, andare a **Amministrazione sistema** &gt; **Impostazione** &gt; **Applicazioni di Azure Active Directory**.
2.  Eliminare la riga corrispondente al dispositivo a cui si desidera rimuovere l'accesso. Annotare l'**ID client** utilizzato per il dispositivo rimosso.
3.  Accedere al portale classico di Azure all'indirizzo <https://manage.windowsazure.com>.
4.  Fare clic sull'icona ** **Active Directory** *nel menu sinistro e fare clic sulla directory desiderata.
5.  Nel menu superiore, fare clic su **Applicazioni** quindi fare clic sull'applicazione da configurare. La pagina **Avvio rapido** verrà visualizzata con il punto di accesso singolo e altre informazioni di configurazione.
6.  Fare clic sulla scheda **Configura**, scorrere verso il basso e verificare che l'**ID client ID** dell'applicazione sia lo stesso di nel passaggio 2 di questa sezione.
7.  Fare clic sul pulsante **Elimina** sulla barra dei comandi.
8.  Nel messaggio di conferma, fare clic su **Sì**.





