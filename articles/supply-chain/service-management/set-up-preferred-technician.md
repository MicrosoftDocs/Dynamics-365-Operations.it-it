---
title: Impostare un tecnico preferito
description: "È possibile selezionare qualsiasi lavoratore come tecnico preferito per un contratto o per un ordine di assistenza."
author: YuyuScheller
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAAgreementTable, SMADispatchBoard
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 390e436b63fdfe82e0b743e7f286cae3bb29be55
ms.contentlocale: it-it
ms.lasthandoff: 05/08/2018

---


# <a name="set-up-a-preferred-technician"></a>Impostare un tecnico preferito 

[!include [banner](../includes/banner.md)]


È possibile selezionare qualsiasi lavoratore come tecnico preferito per un contratto o per un ordine di assistenza. Tuttavia, è consigliabile aggiungere il lavoratore al team di intervento appropriato in modo che venga incluso nel **Prospetto interventi**.

## <a name="assign-employee-to-a-dispatch-team"></a>Assegnare un dipendente a un team di intervento

1.  Fare clic su **Risorse umane** \> **Comune** \> **Lavoratori** \> **Lavoratori**. Fare doppio clic su un lavoratore per aprire la pagina dei dettagli relativi al lavoratore. Nel **riquadro azioni**, fare clic su **Impostazione** \>**Team di intervento** per aprire il modulo **Lavoratori di intervento**.

2.  Nel campo **Team di intervento** selezionare il team a cui assegnare il lavoratore.

## <a name="assign-a-preferred-technician-to-a-service-agreement"></a>Assegnare un tecnico preferito a un contratto di assistenza

1.  Fare clic su **Gestione assistenza** \> **Comune** \> **Contratti di assistenza** \> **Contratti di assistenza**. Fare doppio clic su un contratto di assistenza per aprire il modulo dei dettagli.

2.  Nella scheda **Generale**, selezionare il campo **Tecnico preferito**, quindi selezionare un membro del team di intervento appropriato come tecnico preferito per il contratto di assistenza.

## <a name="assign-a-preferred-technician-to-a-service-order"></a>Assegnare un tecnico preferito a un ordine di assistenza

1.  Fare clic su **Gestione assistenza** \> **Periodico** \> **Prospetto interventi**.
    

    > [!NOTE]
    > <P>Nel modulo <STRONG>Prospetto interventi</STRONG> specificare l'intervallo di date in cui devono rientrare le attività di intervento da visualizzare. Indicare inoltre se si desidera visualizzare le attività chiuse e limitare l'elenco delle attività di intervento ai team dei quali si è membri o che si è autorizzati a monitorare. Scegliere <STRONG>OK</STRONG> per aprire il modulo <STRONG>Prospetto interventi</STRONG>.</P>



2.  Selezionare la riga dell'attività di assistenza tecnica da modificare.

3.  Nella scheda **Correlati** utilizzare l'elenco **Lavoratore** per impostare un membro del team di intervento appropriato come tecnico preferito per la chiamata di assistenza.

## <a name="see-also"></a>Vedere anche

[Contratti di assistenza ](service-agreements.md)

[Creare ordini di assistenza manualmente](create-service-orders-manually.md)

[Contratti di assistenza (modulo)](https://technet.microsoft.com/en-us/library/aa617823\(v=ax.60\))
  



