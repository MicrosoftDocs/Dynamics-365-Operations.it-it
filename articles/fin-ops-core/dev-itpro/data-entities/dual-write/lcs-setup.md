---
title: Configurazione a doppia scrittura da Lifecycle Services
description: Questo articolo spiega come configurare una connessione a doppia scrittura da Microsoft Dynamics Lifecycle Services (LCS).
author: laneswenka
ms.date: 05/16/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 5cccba580d23c3a0e9aed62f76a305926a58585f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8879806"
---
# <a name="dual-write-setup-from-lifecycle-services"></a>Configurazione a doppia scrittura da Lifecycle Services

[!include [banner](../../includes/banner.md)]



Questo articolo spiega come abilitare la doppia scrittura da Microsoft Dynamics Lifecycle Services (LCS).

## <a name="prerequisites"></a>Prerequisiti

Il clienti devono completare l'integrazione di Power Platform come descritto nei seguenti argomenti:

- Se non lo usi ancora Microsoft Power Platform e desideri espandere i tuoi ambienti finanziari e operativi aggiungendo funzionalità della piattaforma, vedi [Integrazione di Power Platform - Abilitazione durante la distribuzione dell'ambiente](../../power-platform/enable-power-platform-integration.md#enable-during-deploy).
- Se hai già gli ambienti Dataverse e Power Platform e vuoi connetterli agli ambienti finanziari e operativi, vedi [Integrazione di Power Platform - Abilitazione dopo la distribuzione dell'ambiente](../../power-platform/enable-power-platform-integration.md#enable-after-deploy).

## <a name="set-up-dual-write-for-new-or-existing-dataverse-environments"></a>Configurare la doppia scrittura per un ambiente Dataverse nuovo o esistente

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

8. Quando il collegamento è completo, viene visualizzato un collegamento ipertestuale. Utilizza il collegamento per accedere all'area di amministrazione a doppia scrittura nell'ambiente Finanza e operazioni. Da lì, puoi configurare le mappature delle entità.

## <a name="linking-mismatch"></a>Collegamenti non corrispondenti

È possibile che il tuo ambiente di doppia scrittura sia collegato a un'istanza di Dataverse mentre LCS non è impostato per l'integrazione di Power Platform. Questa mancata corrispondenza di collegamento può causare un comportamento imprevisto. Si consiglia che i dettagli dell'ambiente LCS corrispondano a ciò a cui si è connessi in doppia scrittura in modo che la stessa connessione possa essere utilizzata da eventi aziendali, tabelle virtuali e componenti aggiuntivi.

Se il tuo ambiente presenta collegamenti non corrispondenti, LCS visualizza un avviso simile al seguente esempio nella pagina dei dettagli dell'ambiente simile a "Microsoft ha rilevato che l'ambiente è collegato tramite la doppia scrittura a una destinazione diversa da quella specificata nell'integrazione di Power Platform e ciò è sconsigliato".

:::image type="content" source="media/powerplat_integration_mismatchLink.png" alt-text="Collegamenti non corrispondenti nell'integrazione di Power Platform.":::

Se ricevi questo avviso, prova una delle seguenti soluzioni:

- Se il tuo ambiente LCS non è mai stato configurato per l'integrazione di Power Platform, è possibile connettersi all'istanza di Dataverse configurata in doppia scrittura seguendo le istruzioni in questo articolo.
- Se il tuo ambiente LCS è già configurato per l'integrazione di Power Platform, è necessario scollegare la doppia scrittura e ricollegarla a quella specificata da LCS utilizzando lo [Scenario: reimpostare o modificare il collegamento](relink-environments.md#scenario-reset-or-change-linking).

In passato era disponibile un'opzione di ticket di supporto manuale, ma prima che esistesse l'opzione 1 precedente.  Microsoft non supporta più le richieste di ricollegamento manuale tramite ticket di supporto.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
