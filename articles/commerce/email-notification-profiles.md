---
title: Impostare un profilo di notifica tramite posta elettronica
description: In questo articolo viene descritto come creare un profilo di notifica tramite posta elettronica in Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 02/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: db6c46d471e3b54982132df3e4819236833cf4a8
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9292137"
---
# <a name="set-up-an-email-notification-profile"></a>Impostare un profilo di notifica tramite posta elettronica

[!include [banner](includes/banner.md)]

In questo articolo viene descritto come creare un profilo di notifica tramite posta elettronica in Microsoft Dynamics 365 Commerce.

Quando si creano canali, è possibile impostare un profilo di notifica tramite posta elettronica. Il profilo di notifica tramite posta elettronica definisce gli eventi di una transazione di vendita (come gli eventi ordine creato, ordine imballato e ordine fatturato) per i quali invierai notifiche ai tuoi clienti. 

Per ulteriori informazioni di configurazione della posta elettronica, vedere [Configurare e inviare messaggi di posta elettronica](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).



## <a name="create-an-email-template"></a>Crea un modello di messaggio di posta elettronica

Prima di poter abilitare un tipo di notifica tramite posta elettronica, è necessario creare un modello di messaggio di posta elettronica dell'organizzazione in Commerce Headquarters per ogni tipo di notifica che vuoi supportare. Questo modello definisce l'oggetto, il mittente, la lingua predefinita e il corpo del messaggio di posta elettronica per ciascuna lingua supportata.

Per creare un modello di messaggio di posta elettronica attenersi alla procedura seguente.

1. Nel pannello di navigazione, selezionare **Moduli \> Vendita al dettaglio e commercio \> Impostazione sedi centrali \> Parametri \> Modelli di posta elettronica a livello di organizzazione**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nel campo **ID posta elettronica**, immettere un ID per facilitare l'identificazione di questo modello.
1. Nel campo **Nome mittente** immettere il nome del mittente.
1. Nel campo **Descrizione messaggio di posta elettronica** immettere una descrizione pertinente.
1. Nel campo **Indirizzo di posta elettronica del mittente** immettere l'indirizzo di posta elettronica del mittente.
1. Nella sezione **Generale**, selezionare una lingua predefinita per il modello di messaggio di posta elettronica. La lingua predefinita verrà utilizzata quando non esiste alcun modello localizzato per la lingua specificata.
1. Espandere la sezione **Contenuto messaggio posta elettronica** e selezionare **Nuovo** per creare il contenuto del modello. Per ogni elemento di contenuto, selezionare la lingua e fornire la riga dell'oggetto del messaggio di posta elettronica. Se il messaggio di posta elettronica avrà un corpo, assicurarsi che la casella **Con corpo** è selezionata.
1. Nel riquadro azioni, selezionare **Messaggio di posta elettronica** per fornire un modello di corpo dell'email.

L'immagine seguente mostra alcune impostazioni di esempio del modello di messaggio di posta elettronica.

![Impostazioni del modello di messaggio di posta elettronica.](media/email-template.png)

Per altre informazioni sulla creazione di modelli di messaggio di posta elettronica, vedere [Creare modelli di posta elettronica per eventi transazionali](email-templates-transactions.md). 

## <a name="create-an-email-notification-profile"></a>Creare un profilo di notifica tramite posta elettronica

Per creare un profilo di notifica tramite posta elettronica in Headquarters, attenersi alla seguente procedura.

1. Nel pannello di navigazione, andare a **Moduli \> Vendita al dettaglio e commercio \> Impostazione sedi centrali \> Profilo di notifica tramite posta elettronica per Commerce**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nel campo **Profilo di notifica tramite posta elettronica**, immettere un nome per identificare il profilo.
1. Nel campo **Descrizione** immettere una descrizione pertinente.
1. Impostare **Attivo** su **Sì**.

## <a name="add-a-notification-type"></a>Aggiungere un tipo di notifica

Per creare un evento di posta elettronica attenersi alla procedura seguente.

1. Nel pannello di navigazione, andare a **Moduli \> Vendita al dettaglio e commercio \> Impostazione sedi centrali \> Profilo di notifica tramite posta elettronica per Commerce**.
1. Sotto **Impostazioni di notifica tramite posta elettronica per vendita al dettaglio**, seleziona **Nuovo**.
1. Selezionare il **Tipo di notifica tramite posta elettronica** appropriato dall'elenco a discesa.
1. Seleziona il modello di messaggio di posta elettronica creato sopra dall'elenco a discesa **ID posta elettronica**.
1. Selezionare la casella di controllo **Attiva**.
1. Nel riquadro azioni selezionare **Salva**.

L'immagine seguente mostra alcune impostazioni di esempio della notifica di evento.

![Impostazioni notifica di eventi.](media/email-notification-profile.png)


## <a name="schedule-a-recurring-email-notification-process-job"></a>Pianificare un processo di notifica tramite posta elettronica ricorrente

Per inviare notifiche tramite posta elettronica, il processo **Elabora notifica tramite posta elettronica di ordine di vendita al dettaglio** deve essere in esecuzione.

Per impostare un processo batch in Headquarters per l'invio di messaggi di posta elettronica transazionale, attenersi alla seguente procedura.

1. Andare a **Vendita al dettaglio e commercio \> Vendita al dettaglio e commercio IT \> Posta elettronica e notifiche \> Invia notifica tramite posta elettronica**.
1. Nella finestra di dialogo **Elabora notifica tramite posta elettronica di ordine di vendita al dettaglio**, selezionare **Ricorrenza**.
1. Nella finestra di dialogo **Definisci ricorrenza**, selezionare **Nessuna data di fine**.
1. In **Criterio di ricorrenza**, selezionare **Minuti** e impostare il campo **Conteggio** su **1**. Queste impostazioni garantiranno l'elaborazione più rapida possibile delle notifiche tramite posta elettronica.
1. Selezionare **OK** per ritornare alla finestra di dialogo **Elabora notifica tramite posta elettronica di ordine di vendita al dettaglio**.
1. Per completare l'impostazione del processo, selezionare **OK**.

## <a name="next-steps"></a>Passaggi successivi

Prima di poter inviare messaggi di posta elettronica, è necessario configurare il servizio di posta in uscita. Per ulteriori informazioni, vedere [Configurare e inviare messaggi di posta elettronica](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).

## <a name="additional-resources"></a>Risorse aggiuntive

[Configurare e inviare messaggi di posta elettronica](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json)

[Panoramica dei canali](channels-overview.md)

[Prerequisiti di impostazione dei canali](channels-prerequisites.md)

[Panoramica organizzazioni e gerarchie organizzative](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
