---
title: Diagnostica di sicurezza per registrazioni attività
description: Questo articolo fornisce informazioni su come analizzare e gestire i requisiti delle autorizzazione di sicurezza in base a una registrazione attività.
author: Peakerbl
ms.date: 05/05/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: ''
ms.dyn365.ops.version: Version 10.0.9
ms.openlocfilehash: cb69bf997100f25cd0ad2b7e34139857199e5d00
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8880169"
---
# <a name="security-diagnostics-for-task-recordings"></a>Diagnostica di sicurezza per registrazioni attività

[!include [banner](../../includes/banner.md)]

## <a name="before-you-begin"></a>Prima di iniziare

Questo articolo fornisce informazioni su come analizzare e gestire i requisiti delle autorizzazione di sicurezza in base a una registrazione attività. Prima di completare i passaggi in questo articolo, è necessario disporre di una registrazione attività del processo aziendale che si desidera analizzare. Per registrare un processo aziendale, vedere [Risorse registrazione attività](../../user-interface/task-recorder.md). 

## <a name="manage-security-for-a-task-recording"></a>Gestire la sicurezza per una registrazione attività

1. Andare a **Amministrazione sistema** > **Sicurezza** > **Diagnostica sicurezza per registrazione attività**.
2. Aprire la registrazione attività dalla relativa posizione. Selezionare **Apri dal PC** o **Aprire da Lifecycle Services**, quindi selezionare **Chiudi**.
3. Verrà aperta la pagina dei **dettagli delle voci del menu Sicurezza** in cui è presente un elenco degli oggetti di sicurezza richiesti per il processo.

 > [!NOTE]
 > Le voci di menu **Azione** e **Output** sono incluse nell'elenco.

4. Nel campo **ID utente** selezionare un utente. Se l'utente non dispone delle autorizzazioni per alcune voci di menu, il campo **Autorizzazioni mancanti** verrà modificato in **Sì**.
  
  ![Pagina dei dettagli delle voci del menu Sicurezza.](../media/Security-Menu-Item-Details.png)

5. Selezionare **Aggiungi riferimento** per visualizzare un elenco degli oggetti di sicurezza, inclusi ruoli, compiti e privilegi che concedono l'autorizzazione mancante.
6. Selezionare un oggetto di sicurezza dall'elenco:

    - Se **Ruolo** è selezionato, selezionare **Aggiungi ruolo a utente**. Verrà aperta la pagina **Assegna utenti a ruoli**. Per ulteriori informazioni, vedere la pagina [Assegnare gli utenti ai ruoli di sicurezza](assign-users-security-roles.md).
    - Se **Compito** è selezionato, selezionare **Aggiungi compito a ruolo**, selezionare i ruoli a cui deve essere aggiunto il compito, quindi **OK**.
    - Se **Privilegio** è selezionato, selezionare **Aggiungi privilegio a compiti**, selezionare i ruoli a cui deve essere aggiunto il compito, quindi **OK**.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]