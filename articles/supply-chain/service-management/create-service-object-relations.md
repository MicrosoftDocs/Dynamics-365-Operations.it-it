---
title: Creare relazioni di oggetti assistenza
description: In questo articolo viene descritto come creare relazioni di oggetti assistenza per un contratto di assistenza e un ordine di assistenza.
author: sorenva
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b4d9424b5678a6f37d46203e5d4e359b020fda7a
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2022
ms.locfileid: "9016972"
---
# <a name="create-service-object-relations"></a>Creare relazioni di oggetti assistenza 

[!include [banner](../includes/banner.md)]


In questo articolo viene descritto come creare relazioni di oggetti assistenza per un contratto di assistenza e un ordine di assistenza. Per creare una relazione dell'oggetto di assistenza, associare l'oggetto assistenza a un contratto o all'ordine di assistenza. Quando un cliente richiede il servizio per un articolo che è un oggetto assistenza, è possibile selezionare l'oggetto assistenza dall'elenco delle relazioni di oggetti assistenza.

## <a name="create-a-service-object-relation-for-a-service-agreement"></a>Creare una relazione dell'oggetto di assistenza per un contratto di assistenza

Utilizzare i seguenti passaggi per creare una relazione dell'oggetto di assistenza per un contratto di assistenza:

1.  Fai clic su **Gestione assistenza** \> **Contratti di assistenza** \> **Contratti di assistenza**.

2.  Nell'elenco **Contratti di assistenza** selezionare un contratto di assistenza esistente, fare clic su **Nuovo** per creare un nuovo contratto di assistenza.

3.  Nel **riquadro azioni** del modulo **Contratti di assistenza**, nel gruppo **Relazioni** della scheda **Contratto di assistenza** fare clic su **Oggetti assistenza**.

4.  Nel modulo **Oggetti assistenza** fare clic su **Nuovo**, quindi selezionare un oggetto di assistenza per questo contratto di assistenza.

5.  Per assegnare una distinta base (DBA) modello al contratto di assistenza fare clic su **Funzioni**, quindi selezionare **Collega DBA modello**. Nel modulo **Seleziona DBA modello**, selezionare un modello nel campo **DBA modello**. 

## <a name="create-a-service-object-relation-for-a-service-order"></a>Creare una relazione dell'oggetto di assistenza per un ordine di assistenza

Utilizzare i seguenti passaggi per creare una relazione dell'oggetto di assistenza per un ordine di assistenza:

1.  Fai clic su **Gestione assistenza** \> **Ordini di assistenza** \> **Ordini di assistenza**.

2.  Nell'elenco **Ordini di assistenza** selezionare un ordine di assistenza esistente o crearne uno nuovo.

3.  Nel **riquadro azioni** del modulo **Ordini di assistenza**, nel gruppo **Relazioni** della scheda **Ordine di assistenza** fare clic su **Oggetti assistenza**.

4.  Nel modulo **Oggetti assistenza** fare clic su **Nuovo**, quindi selezionare un oggetto di assistenza per questo ordine di assistenza.

5.  Per assegnare una DBA modello al contratto di assistenza fare clic su **Funzioni**, quindi selezionare **Collega DBA modello**. Nel modulo **Seleziona DBA modello**, selezionare un modello nel campo **DBA modello**. 


## <a name="see-also"></a>Vedere anche

[Panoramica oggetti di servizio](service-objects.md)

[Relazioni oggetti assistenza](service-object-relations.md)

[DBA modello](template-boms.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]