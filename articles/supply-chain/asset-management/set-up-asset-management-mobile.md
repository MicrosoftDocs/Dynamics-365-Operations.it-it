---
title: Configurare l'area di lavoro per dispositivi mobili Gestione cespiti
description: Questo articolo descrive come configurare Microsoft Dynamics 365 Supply Chain Management e l'app per dispositivi mobili per la finanza e le operazioni (Dynamics 365) per eseguire un'area di lavoro per dispositivi mobili Gestione dispositivi che i lavoratori possono utilizzare per eseguire attività di gestione dei cespiti.
author: johanhoffmann
ms.date: 01/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-12-22
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: ef4e6bf2ae59adb05c7d4aacc3f5675a5adcafc9
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9070055"
---
# <a name="set-up-the-asset-management-mobile-workspace"></a>Configurare l'area di lavoro per dispositivi mobili Gestione cespiti

[!include [banner](../includes/banner.md)]

Questo articolo descrive come configurare Microsoft Dynamics 365 Supply Chain Management e l'app per dispositivi mobili per la finanza e le operazioni (Dynamics 365) per eseguire un'area di lavoro per dispositivi mobili **Gestione dispositivi** che i lavoratori possono utilizzare per eseguire attività di gestione dei cespiti.

## <a name="set-up-maintenance-worker-users-in-supply-chain-management"></a>Configurare gli utenti addetto alla manutenzione in Supply Chain Management

Per ogni utente che richiede l'accesso all'area di lavoro per dispositivi mobili **Gestione cespiti**, segui questi passaggi.

1. In Supply Chain Management, vai a **Human resources \> Lavoratori** e assicurati che esista un record di lavoro per l'utente che desideri configurare. Crea un nuovo record del lavoratore in base alle esigenze.
1. Vai a **Gestione cespiti \> Imposta \> Lavoratori \> Lavoratori** e assicurati che il record del lavoratore identificato (o creato) nel passaggio precedente sia mappato a un record dell'addetto alla manutenzione. Crea un nuovo record di addetto alla manutenzione come richiesto e imposta il campo **Lavoratore** su record del lavoratore dal passaggio precedente.
1. Vai a **Gestione cespiti \> Imposta \> Lavoratori \> gruppi Addetto alla manutenzione** e assicurati che il record di addetto alla manutenzione identificato (o creato) nel passaggio precedente appartenga a un gruppo addetto alla manutenzione.
1. Vai ad **Amministrazione sistema \> Utenti**.
1. Seleziona il relativo utente nella griglia.
1. Nella Scheda dettaglio **Dettagli utente**, imposta il campo **Utente tipo** sull'account del lavoratore che vuoi associare all'account utente corrente. Questo account lavoratore dovrebbe essere il record lavoratore identificato (o creato) nel passaggio 1 e mappato a un record addetto alla manutenzione nel passaggio 2.

> [!NOTE]
> Le autorizzazioni utente e i ruoli di sicurezza si applicano alle funzionalità dell'area di lavoro per dispositivi mobili **Gestione cespiti** proprio come si applicano alle funzionalità dell'interfaccia utente di Supply Chain Management. Pertanto, ogni utente configurato per accedere all'area di lavoro per dispositivi mobili **Gestione cespiti** deve avere i ruoli di sicurezza necessari per eseguire operazioni simili direttamente in Supply Chain Management.

## <a name="publish-the-asset-management-mobile-workspace"></a>Pubblicare l'area di lavoro per dispositivi mobili Gestione cespiti

Per rendere disponibili le funzionalità di gestione dei cespiti nell'app per dispositivi mobili per la finanza e le operazioni (Dynamics 365), devi pubblicare l'area di lavoro per dispositivi mobili **Gestione cespiti**.

1. In Supply Chain Management, seleziona il pulsante **Impostazioni** (il simbolo dell'ingranaggio nell'angolo in alto a destra), quindi seleziona **App per dispositivi mobili** sul menu.
1. Nella finestra di dialogo **Gestisci app per dispositivi mobili**, trova il riquadro **Gestione cespiti**. Se contiene il testo "Nei metadati - non pubblicato", l'area di lavoro non è stata ancora pubblicata. Se contiene il testo "Nei metadata - pubblicato", l'area di lavoro è già stata pubblicata e puoi saltare il resto di questa procedura.

    ![Gestire la finestra di dialogo dell'app per dispositivi mobili.](media/mobile-workspaces.png "Gestire la finestra di dialogo dell'app per dispositivi mobili")

1. Seleziona il riquadro **Gestione cespiti**, quindi seleziona **Pubblica** sulla barra degli strumenti. Dopo alcuni secondi, dovresti ricevere una notifica che informa che l'area di lavoro è stata pubblicata correttamente. Inoltre, il testo sul riquadro dovrebbe cambiare in "Nei metadati - pubblicato".

## <a name="install-and-set-up-the-finance-and-operations-dynamics-365-mobile-app"></a>Installare e configurare l'app per dispositivi mobili per la finanza e le operazioni (Dynamics 365)

1. Vai a uno dei seguenti app store per installare l'app **Microsoft per la finanza e le operazioni (Dynamics 365)** sul tuo dispositivo mobile:

    - [Per dispositivi Google Android](https://go.microsoft.com/fwlink/?linkid=850662)
    - [Per dispositivi Apple iOS](https://go.microsoft.com/fwlink/?linkid=850663)

1. Aprire l'app per la finanza e le operazioni (Dynamics 365). Dovrebbe essere visualizzata la pagina di accesso. Nel campo **Accedi**, immetti il tuo URL di Supply Chain Management o seleziona un URL recente nell'elenco **Ambienti recenti**, quindi tocca **Connetti**.

    ![Pagina di accesso.](media/mobile-app-sign-in.png "Pagina di accesso")

1. Se viene richiesto di confermare la connessione, seleziona la casella di controllo **Ho capito**, quindi tocca **Connetti**.
1. Nella pagina **Scegli un account**, usa il tuo account Microsoft per accedere all'applicazione per dispositivi mobili.

    Viene visualizzata la pagina **Aree di lavoro**. Elenca ogni area di lavoro per dispositivi mobili che è stata pubblicata dall'istanza di Supply Chain Management.

    ![Elenco delle aree di lavoro.](media/mobile-app-workspaces.png "Elenco delle aree di lavoro")

1. Se è necessario modificare la persona giuridica (azienda), toccar il pulsante Menu (a volte indicato come hamburger o pulsante hamburger) nell'angolo in alto a sinistra, quindi tocca **Cambia azienda**.

    ![Modifica della persona giuridica.](media/mobile-app-change-comp.png "Modifica della persona giuridica")

1. Nella pagina **Aree di lavoro**, seleziona l'area di lavoro con cui desideri lavorare per aprirla.

    ![Area di lavoro mobile di gestione cespiti.](media/mobile-app-asset-workspace.png "Area di lavoro mobile di gestione cespiti")

## <a name="work-with-the-asset-management-mobile-workspace"></a>Utilizzare l'area di lavoro per dispositivi mobili Gestione cespiti

Per ulteriori informazioni su come lavorare con l'area di lavoro per dispositivi mobili **Gestione cespiti**, vedi [Utilizzare l'area di lavoro per dispositivi mobili per la gestione dei cespiti](asset-management-mobile-workspace.md).

Per ulteriori informazioni sull'app per dispositivi mobili per la finanza e le operazioni (Dynamics 365), vedi la [Home page dell'app per dispositivi mobili](../../fin-ops-core/dev-itpro/mobile-apps/Mobile-app-home-page.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
