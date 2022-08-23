---
title: Mappare negozi e team se ci sono team preesistenti in Microsoft Teams
description: In questo articolo viene illustrato come mappare i negozi e i team corrispondenti in Dynamics 365 Commerce headquarters se la tua organizzazione ha già creato team in Microsoft Teams prima dell'integrazione di Commerce.
author: gvrmohanreddy
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 67a1a79dd74d411aa7e21000c8baaa8a069cede7
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9279121"
---
# <a name="map-stores-and-teams-if-there-are-pre-existing-teams-in-microsoft-teams"></a>Mappare negozi e team se ci sono team preesistenti in Microsoft Teams

[!include [banner](includes/banner.md)]

In questo articolo viene illustrato come mappare i negozi e i team corrispondenti in Dynamics 365 Commerce headquarters se la tua organizzazione ha già creato team in Microsoft Teams prima dell'integrazione di Commerce.

La tua organizzazione potrebbe avere creato dei team per alcuni o tutti i tuoi negozi prima dell'integrazione di Dynamics 365 Commerce e Microsoft Teams. In questo caso, per stabilire la sincronizzazione delle attività tra Commerce POS e Microsoft Teams devi fornire la mappatura dei negozi e del team corrispondente in Commerce headquarters.

## <a name="map-stores-and-corresponding-teams-in-commerce-headquarters"></a>Mappare i negozi e i team corrispondenti in Commerce headquarters 

Per mappare i negozi e i team corrispondenti in Commerce headquarters, segui questi passaggi.

1. Vai ad **Amministrazione sistema \> Area di lavoro \> Gestione dati**.
1. Selezionare **Esporta**. 
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Sotto **Nome gruppo**, immetti "Esporta mappatura Teams".
1. Nella scheda dettaglio **Entità selezionate**, seleziona **Aggiungi entità**. Viene visualizzata la finestra di dialogo **Aggiungi entità**.  
1. Nell'elenco a discesa **Nome entità** seleziona **Mapping di Teams tra origine e team**.
1. Nell'elenco a discesa **Formato dati di destinazione** seleziona **CSV**.
1. Seleziona **Aggiungi** e quindi seleziona **Chiudi**.
1. In alto a sinistra, sotto il riquadro azioni, seleziona **Esporta ora**.
1. Sotto **Stato elaborazione entità**, seleziona **Scarica file**.
1. Nel file CSV esportato, inserisci i valori per **SOURCETYPE**, **SOURCEID**, e **TEAMID** come segue:
    - Per **SOURCETYPE**, inserisci "RetailStore". 
    - Per **SOURCEID**, inserisci il numero del negozio (ad esempio, "000135" per il negozio di San Francisco). Puoi trovare i numeri dei negozi in **Retail e Commerce \> Canali \> Negozi**.
    - Per **TEAMID**, inserisci l'ID team corrispondente da Microsoft Teams (per esempio, "5f8bc92b-6aa8-451e-85d1-3949c01ddc6c"). Puoi trovare le informazioni sull'ID del team all'indirizzo [admin.teams.microsoft.com](https://admin.teams.microsoft.com).
1. Salva il file CSV sul tuo computer locale.
1. Vai ad **Amministrazione sistema \> Area di lavoro \> Gestione dati** e seleziona **Importa**.
1. Nella scheda dettaglio **Entità selezionate**, seleziona **Aggiungi file**. Viene visualizzata la finestra di dialogo **Aggiungi file**.
1. Nell'elenco a discesa **Nome entità** seleziona **Mapping di Teams tra origine e team**.
1. Nell'elenco a discesa **Formato dati di origine** seleziona **CSV**.
1. Seleziona **Carica e aggiungi**, seleziona il file CSV salvato in precedenza, quindi seleziona **Apri**.
1. Nella finestra di dialogo **Aggiungi file** seleziona **Chiudi**.
1. Nel riquadro azioni seleziona **Salva** e quindi **Importa**.

L'immagine di esempio seguente mostra il gruppo **Esporta mapping di Teams** in Commerce con gli elementi **Aggiungi entità** e le intestazioni del file CSV esportato evidenziate.

![Gruppo Esporta mapping di Teams in Commerce con gli elementi Aggiungi entità e le intestazioni del file CSV esportato evidenziate.](media/d365-commerce-data-mgmt-export-entity.png)

> [!NOTE]
> Dopo aver completato i passaggi precedenti, segui i passaggi in [Sincronizzare la gestione delle attività tra Microsoft Teams e POS](synchronize-tasks-teams-pos.md) per sincronizzare la gestione delle attività. 

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica dell'integrazione di Dynamics 365 Commerce e Microsoft Teams](commerce-teams-integration.md)

[Abilitare l'integrazione di Dynamics 365 Commerce e Microsoft Teams](enable-teams-integration.md)

[Provisioning di Microsoft Teams da Dynamics 365 Commerce](provision-teams-from-commerce.md)

[Sincronizzare la gestione delle attività tra POS di Microsoft Teams e Dynamics 365 Commerce](synchronize-tasks-teams-pos.md)

[Gestire i ruoli utente in Microsoft Teams](manage-user-roles-teams.md)

[Domande frequenti sull'integrazione di Dynamics 365 Commerce e Microsoft Teams](teams-integration-faq.md)
