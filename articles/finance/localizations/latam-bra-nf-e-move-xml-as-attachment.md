---
title: Spostare i file XML NF-e come allegati
description: Questo argomento spiega come spostare i file XML NF-e fuori dai database Microsoft Dynamics 365 Finance o Dynamics 365 Supply Chain Management e renderli invece disponibili come allegati.
author: gionoder
ms.date: 11/11/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2022-01-27
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: c7b82d486cecf6b20f1283fa609c360b3003efca
ms.sourcegitcommit: ebf6546835e4d6a80aea1dfae81e119e294387f0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2021
ms.locfileid: "7799448"
---
# <a name="move-nf-e-xml-files-as-attachments"></a>Spostare i file XML NF-e come allegati

[!include [banner](../includes/banner.md)] 


Quando vengono emessi documenti fiscali elettronici (NF-e), i file XML vengono creati e archiviati nei database Microsoft Dynamics 365 Finance e Dynamics 365 Supply Chain Management. Nella localizzazione brasiliana, puoi utilizzare la funzionalità **Spostare i file XML NF-e come allegati** per liberare lo spazio del database utilizzato da quei file XML.

Per un intervallo di date e un'istituzione fiscale specifici, la funzionalità per spostare i file XML NF-e dal database Finance o Supply Chain Management all'archivio BLOB dalla sottoscrizione di Azure. Questo spostamento rende i file disponibili solo come allegati. Dopo che i file XML sono stati spostati correttamente nell'archivio BLOB, i file originali vengono eliminati dal database Finance o Supply Chain Management. Pertanto, viene rilasciato lo spazio del database utilizzato da quei file.

Segui questi passaggi per abilitare la funzionalità **Spostare i file XML NF-e come allegati**.

1. In Finance o Supply Chain Management, apri l'area di lavoro **Gestione funzionalità**.
2. Nella scheda **Tutto**, cercare e selezionare la funzionalità **Spostare i file XML NF-e come allegati**.
3. Selezionare **Abilita ora**.

Segui questi passaggi per spostare i file XML NF-e come allegati.

1. Vai a **Contabilità clienti** \> **Documenti fiscali** \> **Documenti fiscali elettronici** \> **Sposta NF-e XML come allegati**.
2. Nei campi **Dal** e **Al** seleziona le dati di inizio e fine.
3. Nel campo **ID sistema fiscale** selezionare un valore.
4. Seleziona **OK**.

> [!IMPORTANT]
> Il processo non è reversibile. Dopo aver spostato i file XML NF-e, gli utenti possono visualizzarli solo selezionando **Allegati** nella parte superiore della pagina **Documento fiscale**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
