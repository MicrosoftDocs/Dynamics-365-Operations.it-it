---
title: Regulatory Configuration Service (RCS) - Eliminare un ambiente RCS
description: Questo articolo spiega come un amministratore di sistema Regulatory Configuration Service (RCS) può eliminare un ambiente RCS e i relativi dati.
author: JaneA07
ms.date: 06/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization, Global
audience: Application User, System Admin
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2021-01-01
ms.dyn365.ops.version: AX 10.0.15
ms.openlocfilehash: 21e7ee546bb2b712d9424c6bd95e9f9227831bd1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8908892"
---
# <a name="regulatory-configuration-service-rcs---delete-an-rcs-environment"></a>Regulatory Configuration Service (RCS) - Eliminare un ambiente RCS

[!include [banner](../includes/banner.md)]

Questo articolo spiega come un amministratore di sistema Regulatory Configuration Service (RCS) può eliminare un ambiente RCS e i relativi dati.

Prima di poter completare le procedure in questo articolo, è necessario soddisfare i seguenti prerequisiti:

- Devi avere il ruolo **Amministratore di sistema** assegnato per l'ambiente RCS.
- Il ruolo **Amministratore di sistema** deve avere il ruolo **RCSDeleteEnvironmentDuty** assegnato.

## <a name="delete-an-rcs-environment"></a>Eliminare un ambiente RCS

1. Apri RCS e seleziona l'area di lavoro **Creazione di report elettronici**.
2. Nella sezione **Collegamenti correlati** seleziona **Elimina ambiente RCS**.

    ![Collegamento Elimina ambiente RCS nella sezione Collegamenti correlati.](media/01_RCS-Delete-Environ-Related-Link.PNG)

3. Nella finestra di dialogo visualizzata, esamina i messaggi sull'ambito dell'eliminazione dell'ambiente.

    ![Messaggi nella finestra di dialogo Elimina ambiente RCS.](media/01_RCS-Delete-Environ-Msg_noGUID.PNG)

    > [!IMPORTANT]
    > L'eliminazione di un ambiente RCS non può essere annullata.
    >
    > L'operazione elimina l'ambiente RCS selezionato e tutti i dati correlati, comprese le funzionalità e le configurazioni archiviate nel repository globale. Le funzionalità e le configurazioni condivise con altre organizzazioni verranno annullate ed eliminate se non hanno dipendenze. Le funzionalità e le configurazioni con dipendenze verranno contrassegnate come interrotte.

4. Nel campo fornito, inserisci il GUID dell'ambiente RCS per confermare che desideri eliminarlo. Il GUID dell'ambiente è incluso nel messaggio di eliminazione.
5. Seleziona **Elimina ambiente**.
    
Il tuo ambiente RCS e tutti i dati correlati sono ora eliminati.

> [!IMPORTANT]
> Dopo aver eliminato un ambiente RCS, non è possibile recuperare i dati. È possibile creare un nuovo ambiente RCS in qualsiasi area RCS disponibile.
