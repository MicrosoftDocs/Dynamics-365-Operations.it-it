---
title: Creare una DBA modello
description: È possibile creare una DBA modello utilizzando vari metodi.
author: ShylaThompson
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMATemplateBOMTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 781df7611ec1e3ee9d3013f971232700df38ada0
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5836304"
---
# <a name="create-a-template-bom"></a>Creare una DBA modello   

[!include [banner](../includes/banner.md)]


È possibile creare una DBA modello utilizzando uno dei metodi descritti di seguito. Per tutti i metodi, i campi **Dal** e **Al** sono facoltativi ed esclusivamente informativi.

## <a name="create-a-template-bom-manually"></a>Creare manualmente una DBA modello

1.  Seleziona **Gestione assistenza** \> **Impostazione** \> **Oggetti assistenza** \> **DBA modello**.

2.  Seleziona **Nuovo** per aprire il modulo **Crea DBA modello**.

3.  In **Copia righe DBA da riferimento**, selezionare l'opzione **Manuale**.

4.  Nel campo **Numero articolo** immettere un articolo di tipo **DBA**.

5.  Nel campo **Nome** immettere un nome per il modello.

6.  Nei campi **Dal** e **Al** immettere un intervallo di date in cui la DBA modello è attiva.

7.  Selezionare **OK**.

Verrà creata una nuova DBA modello vuota.

## <a name="create-a-template-bom-based-on-another-template-bom"></a>Creare una DBA modello basata su un'altra DBA modello

1.  Seleziona **Gestione assistenza** \> **Impostazione** \> **Oggetti assistenza** \> **DBA modello**.

2.  Seleziona **Nuovo** per aprire il modulo **Crea DBA modello**.

3.  In **Copia righe DBA da riferimento**, selezionare l'opzione **DBA modello**.

4.  Nel campo **Numero di riferimento** selezionare una DBA modello esistente da copiare nella nuova DBA modello.

5.  Nel campo **Nome** immettere un nome per il modello.

6.  Nei campi **Dal** e **Al** immettere un intervallo di date in cui la DBA modello è attiva.

7.  Selezionare **OK**.

Verrà creata una nuova DBA modello mediante le righe che corrispondono a quelle della DBA modello originaria.

## <a name="create-a-template-bom-based-on-an-item-bom"></a>Creare una DBA modello basata su una DBA articolo

1.  Seleziona **Gestione assistenza** \> **Impostazione** \> **Oggetti assistenza** \> **DBA modello**.

2.  Seleziona **Nuovo** per aprire il modulo **Crea DBA modello**.

3.  In **Copia righe DBA da riferimento**, selezionare **DBA**.

4.  Nel campo **Numero di riferimento**, selezionare una versione DBA. Un articolo di tipo DBA verrà copiato nel campo **Numero articolo**.

5.  Nel campo **Nome** immettere un nome per il modello.

6.  Nei campi **Dal** e **Al** immettere un intervallo di date in cui la DBA modello è attiva.

7.  Selezionare **OK**.

Verrà creata una nuova DBA modello con le righe corrispondenti a quelle della DBA elencata in **Distinte base**.

## <a name="create-a-template-bom-based-on-a-production-bom"></a>Creare una DBA modello basata su una DBA di produzione

1.  Seleziona **Gestione assistenza** \> **Impostazione** \> **Oggetti assistenza** \> **DBA modello**.

2.  Seleziona **Nuovo** per aprire il modulo **Crea DBA modello**.

3.  In **Copia righe DBA da riferimento**, selezionare **Produzione**.

4.  Nel campo **Numero di riferimento**, selezionare una DBA di produzione.

5.  Nel campo **Nome** immettere un nome per il modello.

6.  Nei campi **Dal** e **Al** immettere un intervallo di date in cui la DBA modello è attiva.

7.  Selezionare **OK**.

Verrà creata una nuova DBA modello con le righe corrispondenti a quelle della DBA elencata in **DBA**.

## <a name="see-also"></a>Vedere anche

[DBA modello ](template-boms.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]