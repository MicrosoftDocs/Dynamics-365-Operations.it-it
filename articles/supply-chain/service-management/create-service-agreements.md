---
title: Creare contratti di assistenza
description: In questo argomento viene descritto come utilizzare le funzionalità dei moduli Gestione assistenza e Gestione progetti e contabilità per creare i contratti di assistenza.
author: sorenva
ms.date: 02/19/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0a8a139d1a11cca036ace2540cba59bf2cace0db
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2022
ms.locfileid: "8677256"
---
# <a name="create-service-agreements"></a>Creare contratti di assistenza

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto come utilizzare le funzionalità dei moduli Gestione assistenza e Gestione progetti e contabilità per creare i contratti di assistenza.

## <a name="create-a-service-agreement-from-service-management"></a>Creare un contratto di assistenza da Gestione assistenza

1. Passare a **Gestione assistenza**.
2. Selezionare **Contratti di assistenza** per creare una nuova riga del contratto di assistenza nell'intestazione della pagina. 
3. Selezionare **Nuovo**. Immettere una descrizione, selezionare un riferimento a un progetto nel campo **ID progetto** e completare i campi e le righe relativi al contratto di assistenza rimanenti. Selezionare **Salva**.
4. Fare clic sulla scheda **Relazioni** e selezionare **Oggetti assistenza** o **Attività di assistenza tecnica** per creare relazioni di oggetti assistenza o di attività di assistenza tecnica per il contratto di assistenza. Gli oggetti assistenza e le attività di assistenza tecnica per cui sono state create relazioni possono essere collegati alle righe del contratto di assistenza.
5. Nella metà inferiore della pagina creare le righe del contratto di assistenza procedendo manualmente oppure copiandole da un modello di assistenza o da un altro contratto di assistenza.

> [!NOTE]
> Se le righe vengono copiate da un altro contratto di assistenza, è possibile indicare se si desidera copiare anche le relazioni di oggetti assistenza e di attività di assistenza tecnica. In caso affermativo, le relazioni copiate verranno aggiunte a quelle esistenti nel contratto di assistenza. Se invece si copiano le righe del contratto di assistenza da un modello di assistenza, nelle righe del nuovo contratto le relazioni di oggetti assistenza e di attività di assistenza tecnica verranno copiate automaticamente.

## <a name="create-service-agreement-lines-manually"></a>Creare manualmente righe di contratto di assistenza

1. Dalla pagina **Contratti di assistenza** aggiungere una riga del contratto di assistenza nella griglia di righe. 
2. Immettere le informazioni appropriate per la riga del contratto di assistenza. 
3. Selezionare **Salva** per salvare la riga, quindi chiudere la pagina.

## <a name="create-a-service-agreement-from-project"></a>Creare un contratto di assistenza mediante Gestione progetti

1. Selezionare **Gestione progetti e contabilità**.
2. Selezionare **Tutti i progetti**.
3. Selezionare il progetto dall'elenco.
4. Nel **riquadro azioni**, selezionare **Gestisci**. Nel gruppo azioni **Nuovo**, selezionare **Assistenza** e **Contratto di assistenza**.
5. Completare i passaggi della sezione **Creare un contratto di assistenza** descritta in precedenza in questo argomento, per inserire il riferimento del progetto.


## <a name="related-topics"></a>Argomenti correlati

[Panoramica sviluppo e definizione dei contratti di assistenza](service-agreements.md)




[!INCLUDE[footer-include](../../includes/footer-banner.md)]