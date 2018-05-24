---
title: Creare una DBA modello
description: "È possibile creare una DBA modello utilizzando vari metodi."
author: YuyuScheller
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMATemplateBOMTable
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
ms.openlocfilehash: a80cf596a3e7c7f08d493a0fb7350fad62d38c3e
ms.contentlocale: it-it
ms.lasthandoff: 05/08/2018

---

# <a name="create-a-template-bom"></a>Creare una DBA modello   

[!include [banner](../includes/banner.md)]


È possibile creare una DBA modello utilizzando uno dei metodi descritti di seguito. Per tutti i metodi, i campi **Dal** e **Al** sono facoltativi ed esclusivamente informativi.

## <a name="create-a-template-bom-manually"></a>Creare manualmente una DBA modello

1.  Fare clic su **Gestione assistenza** \> **Impostazione** \> **Oggetti assistenza** \> **DBA modello**.

2.  Premere CTRL+N per aprire il modulo **Crea DBA modello**.

3.  In **Copia righe DBA da riferimento**, selezionare l'opzione **Manuale**.

4.  Nel campo **Numero articolo** immettere un articolo di tipo **DBA**.

5.  Nel campo **Nome** immettere un nome per il modello.

6.  Nei campi **Dal** e **Al** immettere un intervallo di date in cui la DBA modello è attiva.

7.  Fare clic su **OK**.

Verrà creata una nuova DBA modello vuota.

## <a name="create-a-template-bom-based-on-another-template-bom"></a>Creare una DBA modello basata su un'altra DBA modello

1.  Fare clic su **Gestione assistenza** \> **Impostazione** \> **Oggetti assistenza** \> **DBA modello**.

2.  Premere CTRL+N per aprire il modulo **Crea DBA modello**.

3.  In **Copia righe DBA da riferimento**, selezionare l'opzione **DBA modello**.

4.  Nel campo **Numero di riferimento** selezionare una DBA modello esistente da copiare nella nuova DBA modello.

5.  Nel campo **Nome** immettere un nome per il modello.

6.  Nei campi **Dal** e **Al** immettere un intervallo di date in cui la DBA modello è attiva.

7.  Fare clic su **OK**.

Verrà creata una nuova DBA modello mediante le righe che corrispondono a quelle della DBA modello originaria.

## <a name="create-a-template-bom-based-on-an-item-bom"></a>Creare una DBA modello basata su una DBA articolo

1.  Fare clic su **Gestione assistenza** \> **Impostazione** \> **Oggetti assistenza** \> **DBA modello**.

2.  Premere CTRL+N per aprire il modulo **Crea DBA modello**.

3.  In **Copia righe DBA da riferimento**, selezionare **DBA**.

4.  Nel campo **Numero di riferimento**, selezionare una versione DBA. Un articolo di tipo DBA verrà copiato nel campo **Numero articolo**.

5.  Nel campo **Nome** immettere un nome per il modello.

6.  Nei campi **Dal** e **Al** immettere un intervallo di date in cui la DBA modello è attiva.

7.  Fare clic su **OK**.

Verrà creata una nuova DBA modello con le righe corrispondenti a quelle della DBA elencata in **Distinte base**.

## <a name="create-a-template-bom-based-on-a-production-bom"></a>Creare una DBA modello basata su una DBA di produzione

1.  Fare clic su **Gestione assistenza** \> **Impostazione** \> **Oggetti assistenza** \> **DBA modello**.

2.  Premere CTRL+N per aprire il modulo **Crea DBA modello**.

3.  In **Copia righe DBA da riferimento**, selezionare **Produzione**.

4.  Nel campo **Numero di riferimento**, selezionare una DBA di produzione.

5.  Nel campo **Nome** immettere un nome per il modello.

6.  Nei campi **Dal** e **Al** immettere un intervallo di date in cui la DBA modello è attiva.

7.  Fare clic su **OK**.

Verrà creata una nuova DBA modello con le righe corrispondenti a quelle della DBA elencata in **DBA**.

## <a name="see-also"></a>Vedere anche

[DBA modello ](template-boms.md)

  



