---
title: Configurare le impostazioni di posta elettronica in Microsoft Dynamics 365 for Talent - Attract
description: In questo argomento viene descritto come configurare le impostazioni di posta elettronica inviata da Microsoft Dynamics 365 for Talent - Attract.
author: andreabichsel
manager: AnnBe
ms.date: 06/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.search.industry: ''
ms.author: anbichse
ms.search.validFrom: 2019-06-04
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 360937b807ea149edb2f16ad6799d74791d599b5
ms.sourcegitcommit: a6b32be10b6eb6340f8f68261bf62d0202c03dd1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/05/2019
ms.locfileid: "1729787"
---
# <a name="configure-email-settings-in-microsoft-dynamics-365-for-talent---attract"></a>Configurare le impostazioni di posta elettronica in Microsoft Dynamics 365 for Talent - Attract
[!include[banner](../includes/banner.md)]

Il proprio marchio è sinonimo di fiducia e consente di costruire una relazione con i candidati ancor prima che questi inviino la loro candidatura. Una percezione positiva del marchio attira i migliori talenti e aumenta la fedeltà dei dipendenti esistenti. Microsoft Dynamics 365 for Talent: Attract consente di configurare i messaggi di posta elettronica di modo che riflettano il marchio della società. Di conseguenza, è possibile fornire un'esperienza coerente ai candidati durante il processo di candidatura.

Attract consente di eseguire queste operazioni:

- Configurare le impostazioni di posta elettronica in modo da utilizzare l'account del servizio di posta elettronica Microsoft Exchange della società. In questo modo, i candidati sanno che i messaggi di posta elettronica provengono dalla società. Ad esempio, è possibile configurare le impostazioni di modo che i candidati ricevano messaggi di posta elettronica da `recruiting@contoso.com` anziché `contoso@microsoft.com`.
- Creare un marchio coerente per tutte le comunicazioni tramite posta elettronica impostando un'intestazione e un piè di pagina globali per i modelli di messaggio di posta elettronica. 

> [!NOTE]
> Per configurare Attract affinché utilizzi l'account del servizio di posta elettronica della società per inviare messaggi di posta elettronica, è necessario disporre del componente aggiuntivo per l'assunzione a livello globale.

## <a name="connect-an-email-service-account"></a>Connettere un account del servizio di posta elettronica

Mediante la connessione dell'account del servizio di posta elettronica della società, è possibile creare un'esperienza di posta elettronica contraddistinta dal marchio della società per i candidati. Se non si connette l'account della società, Attract utilizza l'account predefinito, ovvero quello del servizio di posta elettronica con marchio Microsoft.

1. Selezionare **Impostazioni** (il simbolo dell'ingranaggio) nell'angolo superiore destro, quindi selezionare **Interfaccia di amministrazione**.
2. Nella scheda **Impostazioni posta elettronica**, sotto **Account del servizio di posta elettronica**, selezionare **Connetti un account società**.

    ![Connessione dell'account del servizio di posta elettronica della società in Attract](./media/attract-admin-email-service-accounts.png)

    Per ulteriori informazioni sulla creazione di un account di posta elettronica condiviso, vedere [Cassette postali condivise in Exchange Online](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes).

3. Nella finestra di accesso di Microsoft, accedere utilizzando le credenziali aziendali.
4. Se non è ancora stato configurato un account del servizio di posta elettronica, o se si desidera aggiungerne uno, selezionare **Aggiungi nuovo account del servizio**, quindi immettere le informazioni di posta elettronica. Se si è già configurato l'account del servizio di posta elettronica da utilizzare, selezionarlo.

Dopo la configurazione dell'account del servizio di posta elettronica, l'account sarà visualizzato in **Account del servizio di posta elettronica**.

## <a name="disconnect-an-email-service-account"></a>Disconnettere un account del servizio di posta elettronica

Se non si intende più utilizzare il dominio della società nelle comunicazioni tramite posta elettronica con Attract, è possibile disconnettere un account del servizio di posta elettronica.

1. Selezionare **Impostazioni** (il simbolo dell'ingranaggio) nell'angolo superiore destro, quindi selezionare **Interfaccia di amministrazione**.
2. Nella scheda **Impostazioni posta elettronica**, sotto **Account del servizio di posta elettronica**, selezionare il pulsante **Ulteriori informazioni** (tre punti verticali) accanto all'account del servizio di posta elettronica che si desidera disconnettere.
3. Selezionare **Disconnetti account di posta elettronica**.

    ![Disconnessione dell'account del servizio di posta elettronica della società](./media/attract-admin-disconnect-email-account.png)

4. Quando viene richiesto di confermare l'operazione, selezionare **Disconnetti**.

    ![Conferma della disconnessione dell'account del servizio di posta elettronica della società](./media/attract-admin-email-confirm-disconnect.png)

Se non si connette un altro account del servizio di posta elettronica, per i messaggi di posta elettronica inviati da Attract si utilizzerà l'account del servizio di posta elettronica con marchio Microsoft.

## <a name="configure-email-template-settings"></a>Configurare le impostazioni del modello di messaggio di posta elettronica

È possibile caricare un'immagine del logo della società e altre informazioni come intestazione con marchio per i messaggi di posta elettronica. È inoltre possibile fornire collegamenti all'informativa sulla privacy e alle condizioni per l'utilizzo nei piè di pagina dei messaggi di posta elettronica.

> [!NOTE]
> È necessario rispettare tutte le leggi applicabili del proprio paese o zona geografica e le leggi del paese o della zona geografica a cui è soggetto il destinatario del messaggio di posta elettronica. Queste leggi includono le normative relative alla posta indesiderata.

1. Selezionare **Impostazioni** (il simbolo dell'ingranaggio) nell'angolo superiore destro, quindi selezionare **Interfaccia di amministrazione**.
2. Nella scheda **Impostazioni posta elettronica**, sotto **Impostazioni del modello di messaggio di posta elettronica**, trascinare l'immagine che si desidera utilizzare come intestazione dei messaggi nella casella dell'immagine, oppure fare clic sulla casella dell'immagine per cercare il file. Per sostituire un'immagine esistente, è necessario dapprima selezionare **Rimuovi** accanto all'immagine. L'immagine deve essere un file JPEG, JPG, PNG o SVG. La dimensione consigliata per le immagini è compresa tra 25 e 800 pixel (larghezza) e 25 e 150 pixel (altezza). La dimensione di file massima per l'intestazione è 1 megabyte (MB).

    ![Aggiunta di un'immagine per l'intestazione di posta elettronica della società](./media/attract-admin-email-header.png)

3. Sotto **Informativa sulla privacy per le comunicazioni**, immettere un collegamento all'informativa sulla privacy della società. Sotto **Condizioni per le comunicazioni**, immettere un collegamento alle condizioni per l'utilizzo della società.

    ![Aggiunta di collegamenti all'informativa sulla privacy e alle condizioni per l'utilizzo della società per il piè di pagina dei messaggi di posta elettronica](./media/attract-admin-email-footer.png)

4. Selezionare **Salva** per salvare le impostazioni del modello di messaggio di posta elettronica.
