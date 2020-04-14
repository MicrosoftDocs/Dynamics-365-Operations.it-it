---
title: Configurazione della doppia scrittura da Lifecycle Services
description: Questo argomento spiega come impostare una connessione a doppia scrittura tra un nuovo ambiente Finance and Operations e un nuovo ambiente Common Data Service da Microsoft Dynamics Lifecycle Services (LCS).
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: c78752aa1544b12f61071fa06617af4ac2809233
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172994"
---
# <a name="dual-write-setup-from-lifecycle-services"></a>Configurazione della doppia scrittura da Lifecycle Services

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

Questo argomento spiega come impostare una connessione a doppia scrittura tra un nuovo ambiente Finance and Operations e un nuovo ambiente Common Data Service da Microsoft Dynamics Lifecycle Services (LCS).

## <a name="prerequisites"></a>Prerequisiti

È necessario essere un amministratore per impostare una connessione a doppia scrittura.

+ È necessario disporre dell'accesso al tenant.
+ È necessario essere un amministratore in entrambi gli ambienti Finance and Operations e Common Data Service.

## <a name="set-up-a-dual-write-connection"></a>Configurare una connessione a doppia scrittura

Per impostare una connessione a doppia scrittura effettuare le seguenti operazioni.

1. In LCS, andare al progetto.
2. Selezionare **Configura** per distribuire un nuovo ambiente.
3. Selezionare la versione. 
4. Selezionare la topologia. Se è disponibile solo una topologia, viene selezionata automaticamente.
5. Completare i primi passaggi nella procedura guidata **Impostazioni di distribuzione**.
6. Nella scheda **Common Data Service**, eseguire uno dei passaggi seguenti:

    - Se un ambiente Common Data Service è già predisposto per il tenant, è possibile selezionarlo.

        1. Impostare l'opzione **Configura Common Data Service** su **Sì**.
        2. Nel campo **Ambienti disponibili**, selezionare l'ambiente da integrare con i dati Finance and Operations. L'elenco include tutti gli ambienti per cui si dispone dei privilegi di amministratore.
        3. Selezionare la casella di controllo **Accetto** per indicare che si accettano le condizioni.

        ![Scheda Common Data Service quando un ambiente Common Data Service è già predisposto per il tenant](../dual-write/media/lcs_setup_1.png)

    - Se il tenant non dispone già di un ambiente Common Data Service, verrà fornito un nuovo ambiente.

        1. Impostare l'opzione **Configura Common Data Service** su **Sì**.
        2. Immettere un nome per l'ambiente Common Data Service.
        3. Seleziona l'area geografica in cui distribuire l'ambiente.
        4. Seleziona la lingua e la valuta predefinite per l'ambiente.

            > [!NOTE]
            > Non è possibile cambiare la lingua e la valuta in un secondo momento.

        5. Selezionare la casella di controllo **Accetto** per indicare che si accettano le condizioni.

        ![Scheda Common Data Service quando il tenant non dispone già si un ambiente Common Data Service](../dual-write/media/lcs_setup_2.png)

7. Completare i rimanenti passaggi nella procedura guidata **Impostazioni di distribuzione**.
8. Dopo che l'ambiente ha lo stato **Distribuito**, aprire la pagina dei dettagli dell'ambiente. La sezioni **Informazioni sull'ambiente Common Data Service** mostra i nomi dell'ambiente Finance and Operations e dell'ambiente Common Data Service collegati.

    ![Sezione informazioni sull'ambiente Common Data Service](../dual-write/media/lcs_setup_3.png)

9. Un amministratore dell'ambiente Finance and Operations deve accedere a LCS e selezionare **Collega a CDS per app** per completare il collegamento. La pagina dei dettagli dell'ambiente mostra le informazioni di contatto dell'amministratore.

    Una volta completato il collegamento, lo stato viene aggiornato su **Collegamento ambiente completato**.

10. Per aprire l'area di lavoro **Integrazione dei dati** nell'ambiente Finance and Operations e controllare i modelli disponibili, selezionare **Collega a CDS per app**.

    ![Pulsante Collega a CDS per app nella sezione informazioni sull'ambiente Common Data Service](../dual-write/media/lcs_setup_4.png)

> [!NOTE]
> Non è possibile scollegare gli ambienti utilizzando LCS. Per scollegare un ambiente, aprire l'area di lavoro **Integrazione dei dati** nell'ambiente Finance and Operations, quindi selezionare **Scollega**.
