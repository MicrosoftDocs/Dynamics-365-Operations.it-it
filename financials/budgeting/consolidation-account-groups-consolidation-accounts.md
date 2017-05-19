---
title: Gruppi di conti di consolidamento e conti di consolidamento aggiuntivi
description: In questo argomento vengono fornite informazioni sui gruppi di conti di consolidamento e sui conti di consolidamento aggiuntivi e viene illustrato come vengono utilizzati in Microsoft Dynamics 365 for Operations.
author: RobinARH
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 265544
ms.assetid: 71c31df7-b655-46a8-8844-4f92a8bd71b0
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: eeba79c99f6eb730a2e5cb14aeeceaa2f5894434
ms.contentlocale: it-it
ms.lasthandoff: 04/25/2017


---

# <a name="consolidation-account-groups-and-additional-consolidation-accounts"></a>Gruppi di conti di consolidamento e conti di consolidamento aggiuntivi

[!include[banner](../includes/banner.md)]


In questo argomento vengono fornite informazioni sui gruppi di conti di consolidamento e sui conti di consolidamento aggiuntivi e viene illustrato come vengono utilizzati in Microsoft Dynamics 365 for Operations.

<a name="consolidation-account-groups"></a>Gruppi di conti di consolidamento
----------------------------

I gruppi di conti di consolidamento consentono di creare gruppi di conti da utilizzare per consolidare i dati. In genere, un gruppo di conti di consolidamento rappresenta un piano dei conti definito dal Governo o mappa i conti a un gruppo definito dalla sede centrale della società. I gruppi di conti di consolidamento sono disponibili nell'area **Impostazioni** del modulo **Consolidamenti**. Quando si aggiunge un nuovo gruppo, si immette un identificatore univoco per il gruppo di conti e un nome.

## <a name="additional-consolidation-accounts"></a>Conti di consolidamento aggiuntivi
I conti di consolidamento aggiuntivi consentono di assegnare un conto da un piano dei conti esistente a un gruppo di conti di consolidamento. Successivamente è possibile specificare un valore e un nome di conto di consolidamento. 

I conti di consolidamento aggiuntivi sono disponibili nell'area **Impostazioni** del modulo **Consolidamenti**. Quando si crea un nuovo conto di consolidamento, è necessario specificare le informazioni seguenti:

-   **Conto principale**: si tratta di un campo di ricerca che mostra tutti i conti principali basati sul piano dei conti selezionato nella pagina. Quando si seleziona un conto, il relativo nome viene automaticamente inserito nel campo **Nome conto principale**.
-   **Gruppo di conti di consolidamento**: utilizzare questo campo per specificare il gruppo a cui assegnare il conto. Se si esegue il consolidamento in due modi diversi, è necessario aggiungere lo stesso conto a tutti e quattro i gruppi di conti di consolidamento.
-   **Conto di consolidamento**: immettere il valore del conto di consolidamento. Questo valore non deve essere un conto di un piano dei conti. È possibile immettere qualsiasi valore desiderato.
-   **Nome conto di consolidamento**: immettere il nome del conto che si desidera visualizzare le richieste di informazioni e nei report.
-   **Livello SAT**: questo campo viene utilizzato per segnalare gli estratti conto agli uffici tributari messicani. 

Dopo aver creato i gruppi di conti di consolidamento e i conti di consolidamento aggiuntivi, è possibile selezionare il gruppo nel processo di consolidamento online.





