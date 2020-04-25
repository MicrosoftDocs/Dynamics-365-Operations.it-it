---
title: Panoramica sull'installazione e sulla configurazione dell'app Magazzino
description: In questo argomento viene descritto come installare e configurare l'app Dynamics 365 for Finance and Operations - Magazzino.
author: MarkusFogelberg
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysAADClientTable, WHSMobileAppField, WHSMobileAppFieldPriority, WHSRFMenu, WHSRFMenuItem, WHSWorker
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 267694
ms.assetid: d95d43b2-13ff-4189-a71a-3a1fb57d55ed
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: mafoge
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 52882ef7542bfedebdae4a08de8404cddd01ed55
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3205600"
---
# <a name="install-and-configure-the-warehousing-app-overview"></a>Panoramica sull'installazione e sulla configurazione dell'app Magazzino

[!include [banner](../includes/banner.md)]

> [!NOTE]
> 
> In questo argomento viene descritto come configurare il magazzino per le distribuzioni cloud. Se si stanno cercando informazioni su come configurare il magazzino per distribuzioni locali, vedere [Magazzino per distribuzioni locali](../../dev-itpro/deployment/warehousing-for-on-premise-deployments.md).


In questo argomento viene descritto come installare e configurare l'app Dynamics 365 for Finance and Operations - Magazzino.

L'app Magazzino è disponibile in Google Play Store e Windows Store. Per la versione corrente di Dynamics 365 Supply Chain Management, questa app viene fornita come componente autonomo, ovvero con auto-distribuzione sui dispositivi utilizzati per le attività di magazzino. Per utilizzare l'app, è necessario scaricarla su ciascun dispositivo e configurarla per connettersi all'ambiente Supply Chain Management. In questo argomento viene descritto come installare l'app sui dispositivi. Viene inoltre illustrato come configurare l'app per connettersi all'ambiente Supply Chain Management.

## <a name="prerequisites"></a>Prerequisiti
L'app è disponibile sui sistemi operativi Android e Windows. Per utilizzare questo app, è necessario avere uno dei sistemi operativi supportati installati sulle unità. È necessario anche avere una delle versioni supportate seguenti. Utilizzare le informazioni nella tabella seguente per valutare se l'ambiente software e hardware è pronto a supportare l'installazione.

| Piattaforma                    | Versione                                                                                                                                                                     |
|-----------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Android                     | 4.4, 5.0, 6.0, 7.0, 8.0, 9.0                                                                                                                                                     |
| Windows (UWP)               | Windows 10 (tutte le versioni)                                                                                                                                                   |
| Finance and Operations | Microsoft Dynamics 365 for Operations versione 1611 <br>oppure <br>Microsoft Dynamics AX versione 7.0/7.0.1 e aggiornamento 2 della piattaforma Microsoft Dynamics AX con hotfix KB 3210014 |

## <a name="get-the-app"></a>Ottenere l'app
-   Windows (UWP)
     - [Finance and Operations- Magazzino su Windows Store](https://www.microsoft.com/store/apps/9p1bffd5tstm)
-   Android
    - [Finance and Operations- Magazzino su Google Play Store](https://play.google.com/store/apps/details?id=com.Microsoft.Dynamics365forOperationsWarehousing)

> [!NOTE]
> Zebra App Gallery è stato ritirato, di conseguenza l'app Magazzino non sarà più disponibile per il download da tale posizione.

## <a name="create-a-web-service-application-in-azure-active-directory"></a>Creare un'applicazione servizio Web in Azure Active Directory
Per abilitare l'app a interagire con un server Supply Chain Management specifico, è necessario registrare un'applicazione servizio Web in Azure Active Directory per il tenant di Supply Chain Management. Per motivi di sicurezza, si consiglia di creare un'applicazione servizio Web per ogni dispositivo utilizzato. Per creare un'applicazione servizio Web in Azure Active Directory (Azure AD), effettuare le seguenti operazioni:

1.  In un Web browser, passare a <https://portal.azure.com>.
2.  Immettere il nome e la password dell'utente che ha accesso alla sottoscrizione Azure.
3.  Nel portale di Azure, nel riquadro di spostamento a sinistra, fare clic su **Azure Active Directory**.

    [![WMA-01-active-directory-example](./media/WMA-01-active-directory-example.png )](./media/WMA-01-active-directory-example.png)

4.  Assicurarsi che l'istanza di Active Directory corrisponda a quella utilizzata da Supply Chain Management.
5.  Nell'elenco, fare clic su **Registrazioni app**. 

    [![WMA-02-active-directory-app-registrations](./media/WMA-02-active-directory-app-registrations.png)](./media/WMA-02-active-directory-app-registrations.png)

6.  Nel riquadro superiore, fare clic su **Nuova registrazione**. Viene avviata la procedura guidata per **registrare un'applicazione**.
7.  Immettere un nome per l'applicazione e selezionare **Solo account nella directory organizzativa**. Fare clic su **Registra**.  

    [![WMA-03-active-directory-add-application](./media/WMA-03-active-directory-add-application.png)](./media/WMA-03-active-directory-add-application.png)

8.  La nuova registrazione dell'app viene aperta. 

    [![WMA-04-active-directory-configure-app](./media/WMA-04-active-directory-configure-app.png)](./media/WMA-04-active-directory-configure-app.png)

9.  Ricordare l'**ID applicazione**, sarà necessario in seguito. In seguito, verrà fatto riferimento all'**ID applicazione** come a **ID client**.
10. Fare clic su **Certificato e segreti** nel riquadro **Gestisci**. Fare clic su **Nuovo segreto client**. 

    [![WMA-05-active-directory-create-key](./media/WMA-05-active-directory-create-key.png)](./media/WMA-05-active-directory-create-key.png)

11. Creare una chiave immettendo una descrizione per la chiave e una durata nella sezione **Password**. Fare clic su **Aggiungi** e copiare la chiave. Questa chiave successivamente verrà detta **Segreto client**. 

    [![WMA-06-active-directory-save-key](./media/WMA-06-active-directory-save-key.png)](./media/WMA-06-active-directory-save-key.png)

## <a name="create-and-configure-a-user-account-in-supply-chain-management"></a>Creare e configurare un account utente in Supply Chain Management
Per abilitare Supply Chain Management a utilizzare l'applicazione Azure AD, è necessario completare i seguenti passaggi di configurazione:

1.  Creare un utente che corrisponde alle credenziali dell'utente dell'app per il magazzino.
    1.  Scegliere **Amministrazione sistema** &gt; **Comune** &gt; **Utenti**.
    2.  Creare un nuovo utente.
    3.  Assegnare l'utente del dispositivo mobile di magazzino, come illustrato nella schermata. 
    
        [![wh-09-add-user-security-role](./media/wh-09-add-user-security-role.png)](./media/wh-09-add-user-security-role.png)

2.  Associare l'applicazione Azure Active Directory all'utente dell'app del magazzino.
    1.  In Supply Chain Management, andare a **Amministrazione sistema** &gt; **Impostazione** &gt; **Applicazioni di Azure Active Directory**.
    2.  Creare una nuova riga.
    3.  Immettere il **Client ID** (ottenuto nell'ultima sezione), assegnare un nome e selezionare l'utente creato in precedenza. Si consiglia di etichettare tutti i dispositivi in modo che sia possibile rimuovere facilmente l'accesso a Supply Chain Management da questa pagina nel caso vengano persi. 
    
        [![wh-10-ad-applications-form](./media/wh-10-ad-applications-form.png)](./media/wh-10-ad-applications-form.png)

## <a name="configure-the-application"></a>Configurare l'applicazione
È necessario configurare 'app sul dispositivo per connettersi al server Supply Chain Management tramite l'applicazione Azure AD. Per effettuare questa operazione, attenersi alla seguente procedura:

1.  Nel'app, andare a **Impostazioni di connessione**.
2.  Cancellare il campo **Modalità demo**. <br>

    [![wh-11-app-connection-settings-demo-mode](./media/wh-11-app-connection-settings-demo-mode-169x300.png)](./media/wh-11-app-connection-settings-demo-mode.png)

3.  Immettere le seguenti informazioni: 
    + -**ID client Azure Active Directory** - L'ID client viene ottenuto nel passaggio 9 in "Creare un'applicazione servizio Web in Active Directory". 
    + **Segreto client Azure Active Directory** - Il segreto client ottenuto nel passaggio 11 in "Creare un'applicazione servizio Web in Active Directory". 
    + **Risorsa Azure Active Directory** - La risorsa Azure AD Directory mostra l'URL di Supply Chain Management. 
    
        > [!NOTE]
        > Non terminare questo campo con un carattere di barra (/). 

    + **Azure Active directory tenant**: il tenant Azure AD usato con il server Supply Chain Management: `https://login.windows.net/your-AD-tenant-ID`. Ad esempio: `https://login.windows.net/contosooperations.onmicrosoft.com.` 
    
        > [!NOTE]
        > Non terminare questo campo con un carattere di barra (/). 
    
    + **Società** - Immettere la persona giuridica in Supply Chain Management a cui si desidera connettere l'applicazione. <br>
    
    [![wh-12-app-connection-settings](./media/wh-12-app-connection-settings-169x300.png)](./media/wh-12-app-connection-settings.png)

4.  Selezionare il pulsante **Indietro** nell'angolo superiore sinistro dell'applicazione. L'applicazione si connetterà al server Supply Chain Management e apparirà la schermata di accesso per il lavoratore di magazzino.

    [![wh-13-log-in-screen](./media/wh-13-log-in-screen-180x300.png)](./media/wh-13-log-in-screen.png)

Per informazioni su come impostare l'app Magazzino per eseguire la scansione dei codici a barre utilizzando una fotocamera su un dispositivo mobile, vedere [Eseguire la scansione dei codici a barre utilizzando una fotocamera in Dynamics 365 for Finance and Operations - Magazzino](scan-bar-codes-using-a-camera.md).

## <a name="remove-access-for-a-device"></a>Rimuovere l'accesso per un dispositivo
In caso di un dispositivo perso o compromesso, è necessario rimuovere l'accesso a Supply Chain Management del dispositivo. Nei passaggi seguenti viene descritto il processo consigliato per rimuovere l'accesso.

1.  Scegliere **Amministrazione sistema** &gt; **Impostazioni** &gt; **Applicazioni Azure Active Directory**.
2.  Eliminare la riga corrispondente al dispositivo a cui si desidera rimuovere l'accesso. Ricordare l'**ID client** utilizzato per il dispositivo rimosso, sarà necessario in seguito.
3.  Accedere al portale Azure all'indirizzo <https://portal.azure.com>.
4.  Fare clic sull'icona **Active Directory** nel menu sinistro e verificare di trovarsi nella directory corretta.
5.  Nell'elenco fare clic su **Registrazioni app** quindi fare clic sull'applicazione da configurare. Verrà visualizzata la pagina **Impostazioni** con informazioni di configurazione.
6.  Assicurarsi che l'**ID client** dell'applicazione sia lo stesso dell'ID nel passaggio 2 di questa sezione.
7.  Fare clic sul pulsante **Elimina** nel riquadro superiore.
8.  Nel messaggio di conferma, fare clic su **Sì**.
