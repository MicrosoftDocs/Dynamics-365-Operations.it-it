---
title: Gruppi di conto di consolidamento e conti di consolidamento aggiuntivi
description: In questo argomento vengono fornite informazioni sui gruppi di conto di consolidamento e conti di consolidamento aggiuntive e viene illustrato come vengono utilizzate in Microsoft Dynamics 365 per le operazioni.
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
translationtype: Human Translation
ms.sourcegitcommit: 9f4d7fdd8cfa7a540fce219f6ae4792e57dfbe44
ms.openlocfilehash: f9c5aaa389c9c2f85d1ab91cbf3d2222cbebef55
ms.lasthandoff: 03/31/2017


---

# <a name="consolidation-account-groups-and-additional-consolidation-accounts"></a>Gruppi di conto di consolidamento e conti di consolidamento aggiuntivi

In questo argomento vengono fornite informazioni sui gruppi di conto di consolidamento e conti di consolidamento aggiuntive e viene illustrato come vengono utilizzate in Microsoft Dynamics 365 per le operazioni.

<a name="consolidation-account-groups"></a>Gruppi di conti di consolidamento
----------------------------

I gruppi di conto di consolidamento consentono di creare gruppi di conti da utilizzare per consolidare i dati. In genere, un gruppo di conti di consolidamento per un piano dei conti governo definito o abbinare i conti a un gruppo definito dalla sede della società. Per i gruppi di conto di consolidamento ** impostazione ** nell'area ** consolidamenti ** del modulo. Quando si aggiunge un nuovo gruppo, quindi immettere un identificatore univoco per il gruppo di conti e un nome.

## <a name="additional-consolidation-accounts"></a>Conti di consolidamento aggiuntivi
I conti di consolidamento aggiuntivi consentono di assegnare un conto da un piano dei conti esistente a un gruppo di conti di consolidamento. È quindi possibile specificare un valore e un nome di conto di consolidamento. 

Per i conti di consolidamento aggiuntive ** impostazione ** nell'area ** consolidamenti ** del modulo. Quando si crea un nuovo conto di consolidamento, sarà necessario specificare le informazioni seguenti:

-   ** Il conto principale ** il campo è una ricerca in cui vengono visualizzati tutti i conti principali basate sul piano dei conti selezionato nella pagina. Quando si seleziona un conto, il nome automaticamente ** nome del conto principale ** nel campo.
-   ** Gruppo di conti di consolidamento ** consente di utilizzare questo campo per specificare il gruppo per assegnare il conto. Se si consolidano in due modi diversi, è necessario aggiungere lo stesso conto per tutte e quattro i gruppi di conto di consolidamento.
-   ** Conto di consolidamento ** immettere il valore del conto di consolidamento. Questo valore non deve essere un account da un piano dei conti. È possibile immettere qualsiasi valore desiderato.
-   ** Nome conto di consolidamento ** il nome del conto che si desidera visualizzare le richieste di informazioni e nei report.
-   ** Il livello di servizio SAT ** in questo campo viene utilizzato per dichiarare gli estratti conto agli uffici tributari messicane. 

Al termine di creare i gruppi di conto di consolidamento e conti di consolidamento supplementari, è possibile selezionare il gruppo nel processo di consolidamento in linea.



