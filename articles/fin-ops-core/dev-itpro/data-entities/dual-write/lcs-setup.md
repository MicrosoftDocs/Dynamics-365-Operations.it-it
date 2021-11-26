---
title: Configurazione a doppia scrittura da Lifecycle Services
description: Questo argomento spiega come configurare una connessione a doppia scrittura da Microsoft Dynamics Lifecycle Services (LCS).
author: laneswenka
ms.date: 08/03/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 1fd15b5d664fead10949750678a2d3eab967af22
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/10/2021
ms.locfileid: "7781394"
---
# <a name="dual-write-setup-from-lifecycle-services"></a>Configurazione a doppia scrittura da Lifecycle Services

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Questo argomento spiega come abilitare la doppia scrittura da Microsoft Dynamics Lifecycle Services (LCS).

## <a name="prerequisites"></a>Prerequisiti

Devi completare l'integrazione di Power Platform come descritto nei seguenti argomenti:

+ [Integrazione di Power Platform: abilita durante la distribuzione dell'ambiente](../../power-platform/enable-power-platform-integration.md#enable-during-deploy)
+ [Integrazione di Power Platform: abilita dopo la distribuzione dell'ambiente](../../power-platform/enable-power-platform-integration.md#enable-after-deploy)

## <a name="set-up-dual-write-for-new-dataverse-environments"></a>Configurare la doppia scrittura per i nuovi ambienti Dataverse

Segui questi passaggi per configurare la doppia scrittura dalla pagina **Dettagli ambiente** di LCS:

1. Nella pagina **Dettagli ambiente**, espandi la sezione **Integrazione Power Platform**.

2. Seleziona il pulsante **Applicazione a doppia scrittura**.

    ![Integrazione di Power Platform.](media/powerplat_integration_step2.png)

3. Esamina i termini e le condizioni e quindi seleziona **Configura**.

4. Selezionare **OK** per continuare.

5. Puoi monitorare l'avanzamento aggiornando periodicamente la pagina dei dettagli dell'ambiente. La configurazione richiede in genere 30 minuti o meno.  

6. Quando la configurazione è completa, un messaggio ti informerà se il processo è andato a buon fine o se si è verificato un errore. Se la configurazione non è riuscita, viene visualizzato un messaggio di errore correlato. È necessario correggere eventuali errori prima di passare alla fase successiva.

7. Seleziona **Collegamento all'ambiente Power Platform** per creare un collegamento tra Dataverse e i database dell'ambiente corrente. La configurazione richiede in genere 5 minuti o meno.

    :::image type="content" source="media/powerplat_integration_step3.png" alt-text="Collegamento all'ambiente Power Platform.":::

8. Quando il collegamento è completo, viene visualizzato un collegamento ipertestuale. Utilizza il collegamento per accedere all'area di amministrazione a doppia scrittura nell'ambiente Finance and Operations. Da lì, puoi configurare le mappature delle entità.

## <a name="set-up-dual-write-for-an-existing-dataverse-environment"></a>Configurare la doppia scrittura per un ambiente Dataverse esistente

Per configurare la doppia scrittura per un ambiente Dataverse, è necessario creare un [ticket di supporto](../../lifecycle-services/lcs-support.md) Microsoft. Il ticket deve includere:

+ L'ID ambiente Finance and Operations.
+ Il nome del tuo ambiente da Lifecycle Services.
+ L'ID organizzazione Dataverse o ID ambiente Power Platform dall'interfaccia di amministrazione di Power Platform. Nel tuo ticket, richiedi che l'ID sia l'istanza utilizzata per l'integrazione Power Platform.

> [!NOTE]
> Non è possibile scollegare gli ambienti utilizzando LCS. Per scollegare un ambiente, aprire l'area di lavoro **Integrazione dei dati** nell'ambiente Finance and Operations, quindi selezionare **Scollega**.

## <a name="linking-mismatch"></a>Collegamenti non corrispondenti

È possibile che il tuo ambiente LCS sia collegato a un'istanza Dataverse e che il tuo ambiente a doppia scrittura sia collegato a un'altra istanza Dataverse. Questi collegamenti non corrispondenti possono causare un comportamento imprevisto e potrebbero inviare dati all'ambiente sbagliato. L'ambiente raccomandato da usare per la doppia scrittura è quello che viene creato come parte dell'integrazione di Power Platform , e a lungo termine, questo sarà l'unico modo per stabilire un collegamento tra gli ambienti.

Se il tuo ambiente presenta collegamenti non corrispondenti, LCS visualizza un avviso nella pagina dei dettagli dell'ambiente simile a "Microsoft ha rilevato che l'ambiente è collegato tramite la doppia scrittura a una destinazione diversa da quella specificata nell'integrazione di Power Platform e ciò è sconsigliato":

:::image type="content" source="media/powerplat_integration_mismatchLink.png" alt-text="Collegamenti non corrispondenti nell'integrazione di Power Platform.":::

Se vedi questo errore ci sono due opzioni, in base alle tue esigenze:

+ [Scollega e ricollega gli ambienti a doppia scrittura (ripristina o modifica il collegamento)](relink-environments.md#scenario-reset-or-change-linking) come specificato nella pagina dei dettagli dell'ambiente LCS. Questa è l'opzione ideale, perché puoi eseguirla senza il supporto Microsoft.  
+ Se volete mantenere il vostro collegamento in dual-write, potete chiedere aiuto al supporto Microsoft per cambiare l'integrazione di Power Platform per usare il vostro ambiente esistente Dataverse come documentato nella sezione precedente.  

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
