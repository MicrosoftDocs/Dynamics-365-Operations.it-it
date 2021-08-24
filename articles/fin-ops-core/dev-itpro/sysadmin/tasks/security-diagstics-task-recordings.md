---
title: Diagnostica di sicurezza per registrazioni attività
description: Questo argomento fornisce informazioni su come analizzare e gestire i requisiti delle autorizzazione di sicurezza in base a una registrazione attività.
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
ms.openlocfilehash: 44af35f16f6e9ff89b30bc10eef3f16ecdfaf907c4c6e22aa5775d1941fb6a5d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6745122"
---
# <a name="security-diagnostics-for-task-recordings"></a>Diagnostica di sicurezza per registrazioni attività

[!include [banner](../../includes/banner.md)]

## <a name="before-you-begin"></a>Prima di iniziare

Questo argomento fornisce informazioni su come analizzare e gestire i requisiti delle autorizzazione di sicurezza in base a una registrazione attività. Prima di completare i passaggi in questo argomento, è necessario disporre di una registrazione attività del processo aziendale che si desidera analizzare. Per registrare un processo aziendale, vedere [Risorse registrazione attività](../../user-interface/task-recorder.md). 

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