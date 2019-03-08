---
title: Salvare le guide attività in LCS e riprodurle nuovamente
description: In questo argomento viene descritto come salvare guide attività in Microsoft Dynamics Lifecycle Services(LCS) e riprodurle.
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 40b4c3154a04a557b8a670e1f1ae3722c71122fe
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "305018"
---
# <a name="save-task-guides-to-lcs-and-replay-them"></a>Salvare le guide attività in LCS e riprodurle nuovamente

[!include [banner](includes/banner.md)]

**Dettagli ambiente** 

Microsoft Dynamics 365 for Talent, distribuito tramite Microsoft Dynamics Lifecycle Services (LCS)

**Uscita**

Il cliente desidera salvare nuove registrazioni attività nel progetto LCS e quindi riprodurre le guide attività salvate.

**Risoluzione**

Seguire la procedura seguente per salvare una registrazione attività in LCS.

1. Accedere a LCS e selezionare il progetto.
2. Selezionare il riquadro **Modellatore di processi aziendali**.
3. Visualizzare la pagina nell'"Esperienza BPM aggiornata".
4. Selezionare una libreria, quindi **Copia**.
5. Immettere un nome per il modello Modellatore di processi aziendali (BPM).
6. Accedere a Talent da LCS.
7. Nel campo **Cerca**, immettere **guida**. Viene aperta la Guida di Lifecycle Services
8. Selezionare il pulsante **Aggiorna** per la configurazione della Guida di Lifecycle Services.

    La nuova libreria BPM viene visualizzata e dovrebbe essere attiva.

9. Chiudere la pagina.
10. Creare una registrazione attività.
11. Al termine, selezionare **Salvare in Lifecycle Services**.

    ![Salvare in Lifecycle Services](media/task-guides.png)

12. Selezionare il nodo e la libreria BPM in cui salvare la registrazione attività.

Seguire questi passaggi per riprodurre una guida attività da LCS.

1. Avviare Registrazione attività.
2. Selezionare **Apri da LCS**.
3. Selezionare la libreria e il nodo BPM con la guida attività salvata.
4. Aprire la guida attività.
