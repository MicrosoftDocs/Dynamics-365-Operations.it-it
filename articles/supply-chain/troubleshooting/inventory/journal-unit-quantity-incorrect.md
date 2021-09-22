---
title: L'unità e la quantità unitaria non funzionano correttamente nel giornale di registrazione dell'inventario
description: L'unità e la quantità unitaria non funzionano correttamente nel giornale di registrazione dell'inventario
author: sherry-zheng
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 39f462ae325aa1104a25a8290daed70388e624ec
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476749"
---
# <a name="the-unit-and-unit-quantity-arent-working-correctly-in-the-inventory-journal"></a>L'unità e la quantità unitaria non funzionano correttamente nel giornale di registrazione dell'inventario

## <a name="symptoms"></a>Sintomi

Potresti riscontrare uno o entrambi i seguenti problemi quando lavori con unità e quantità in un giornale di registrazione magazzino:

- Non vengono visualizzate le unità o le quantità unitarie nel giornale di registrazione magazzino mentre è impostata un'unità di conversione per il prodotto rilasciato e non è possibile modificare l'unità nel giornale di registrazione magazzino.
- Vedi i campi **Quantità** e **Unità** nel giornale di registrazione magazzino, ma non vedi il campo **Quantità unitaria**. Se modifichi l'unità, immetti una quantità e registri il giornale di registrazione, il giornale di registrazione mostra ancora l'unità di misura originale per quella quantità.

## <a name="resolution"></a>Risoluzione

Per risolvere questo problema, procedere come segue.

1. Nell'area di lavoro **Gestione funzionalità**, assicurati che la funzionalità *Utilizzo di unità di misura e quantità unitaria nei giornali di registrazione magazzino* sia attivata. Questa funzionalità aggiunge i campi **Unità** e **Quantità unitaria** al giornale di registrazione.
1. Dopo che la funzionalità è stata attivata, utilizza i campi **Quantità**, **Quantità unitaria** e **Unità** nel modo seguente:

    - **Quantità**: specifica la quantità utilizzando l'unità predefinita definita per il prodotto rilasciato. Tuttavia, l'unità predefinita stessa non viene mostrata qui. Se viene configurata una conversione tra l'unità predefinita e l'unità selezionata nel campo **Unità**, il campo **Quantità** viene aggiornato automaticamente, in base alle selezioni nei campi **Quantità unitaria** e **Unità**.
    - **Quantità unitaria**: specificare la quantità utilizzando l'unità selezionata nel campo **Unità**.
    - **Unità**: selezionare l'unità da applicare al valore nel campo **Quantità unitaria**.
