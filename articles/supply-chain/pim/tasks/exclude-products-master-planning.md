---
title: Creare uno stato del ciclo di vita del prodotto per escludere i prodotti dalla pianificazione principale
description: In questa procedura viene illustrato come creare un nuovo stato del ciclo di vita del prodotto che esclude i prodotti dal calcolo del livello DBA e dalla pianificazione generale.
author: cvocph
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cadf1d812e737309dbe8ca26d04ffb1ee88ef16a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5818039"
---
# <a name="create-a-product-lifecycle-state-to-exclude-products-from-master-planning"></a>Creare uno stato del ciclo di vita del prodotto per escludere i prodotti dalla pianificazione principale

[!include [banner](../../includes/banner.md)]

In questa procedura viene illustrato come creare un nuovo stato del ciclo di vita del prodotto che esclude i prodotti dal calcolo del livello DBA e dalla pianificazione generale.


## <a name="create-an-obsolete-state"></a>Creare uno stato obsoleto
1. Fare clic su Gestione informazioni sul prodotto > Impostazioni > Stato del ciclo di vita prodotto.
2. Fare clic su Nuovo.
3. Nel campo Stato digitare un valore.
4. Selezionare No nel campo Attivo per pianificazione.
5. Nel campo Descrizione digitare un valore.

## <a name="associate-the-obsolete-state-to-a-released-product"></a>Associare lo stato obsoleto a un prodotto rilasciato
1. Chiudere la pagina.
2. Fare clic su Gestione informazioni sul prodotto > Prodotti > Prodotti rilasciati.
3. Utilizzare il filtro rapido per trovare i record. Ad esempio, applicare un filtro al campo Nome di ricerca con il valore 'M00'.
4. Fare clic su Modifica.
5. Nell'elenco contrassegnare la riga selezionata.
6. Nel campo Stato del ciclo di vita prodotto immettere o selezionare un valore.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]