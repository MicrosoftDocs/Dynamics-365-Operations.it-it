---
title: Salvare le guide attività in LCS e riprodurle nuovamente
description: In questo articolo viene descritto come salvare guide attività in Microsoft Dynamics Lifecycle Services(LCS) e riprodurle.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e8cf6338e17c9d4f0f50e5c36291ce4f81800f76951e873f2e0cf435cc3cc97e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6713080"
---
# <a name="save-task-guides-to-lcs-and-replay-them"></a>Salvare le guide attività in LCS e riprodurle nuovamente

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Dettagli ambiente** 

Microsoft Dynamics 365 Human Resources, distribuito tramite Microsoft Dynamics Lifecycle Services (LCS)

**Uscita**

Il cliente desidera salvare nuove registrazioni attività nel progetto LCS e quindi riprodurre le guide attività salvate.

**Risoluzione**

Seguire la procedura seguente per salvare una registrazione attività in LCS.

1. Accedere a LCS e selezionare il progetto.
2. Selezionare il riquadro **Modellatore di processi aziendali**.
3. Visualizzare la pagina nell'"Esperienza BPM aggiornata".
4. Selezionare una libreria, quindi **Copia**.
5. Immettere un nome per il modello Modellatore di processi aziendali (BPM).
6. Accedi a Human Resources da LCS.
7. Nel campo **Cerca**, immettere **guida**. Viene aperta la Guida di Lifecycle Services
8. Selezionare il pulsante **Aggiorna** per la configurazione della Guida di Lifecycle Services.

    La nuova libreria BPM viene visualizzata e dovrebbe essere attiva.

9. Chiudere la pagina.
10. Creare una registrazione attività.
11. Al termine, selezionare **Salvare in Lifecycle Services**.

    ![Salvare in Lifecycle Services.](media/task-guides.png)

12. Selezionare il nodo e la libreria BPM in cui salvare la registrazione attività.

Seguire questi passaggi per riprodurre una guida attività da LCS.

1. Avviare Registrazione attività.
2. Selezionare **Apri da LCS**.
3. Selezionare la libreria e il nodo BPM con la guida attività salvata.
4. Aprire la guida attività.


[!INCLUDE[footer-include](../includes/footer-banner.md)]