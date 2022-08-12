---
title: Impostare il delimitatore del piano dei conti come univoco
description: In questo articolo viene descritto perché non è possibile avere lo stesso delimitatore per il piano dei conti e i valori delle dimensioni. Dopo l'aggiornamento, è necessario cambiare i valori del delimitatore.
author: panolte
ms.date: 04/13/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: 8
ms.openlocfilehash: 2fd29d747c7141b051e6c7c68db94abfd849f947
ms.sourcegitcommit: 873d66c03a51ecb7082e269f30f5f980ccd9307f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/06/2022
ms.locfileid: "9123498"
---
# <a name="make-the-chart-of-accounts-delimiter-unique"></a>Impostare il delimitatore del piano dei conti come univoco

[!include [banner](../includes/banner.md)]

In Microsoft Dynamics AX 2012, è possibile utilizzare lo stesso delimitatore per il piano dei conti e i valori delle dimensioni. Nelle versioni correnti delle app per la finanza e le operazioni, non è possibile avere lo stesso delimitatore per il piano dei conti e i valori o i nomi delle dimensioni. L'eventuale delimitatore duplicato può essere sostituito dopo l'aggiornamento. 

## <a name="update-delimiter"></a>Aggiornare il delimitatore
In presenza di un conflitto con il piano dei conti, è possibile cambiare il delimitatore del piano dei conti e il formato ID del progetto/sottoprogetto. Non è possibile cambiare alcun altro delimitatore delle dimensioni. 
- È possibile cambiare il delimitatore del piano dei conti dopo l'aggiornamento in **Parametri di contabilità generale** > **Piano dei conti e dimensioni** > **Modifica delimitatore**. 
- Se il conflitto è presente solo con il formato ID del progetto/sottoprogetto, è possibile modificare il valore in **Parametri Gestione progetti e contabilità** > **Generale** > **Modifica formato sottoprogetto**. 

### <a name="other-considerations"></a>Altre considerazioni
Analogamente all'ID progetto/sottoprogetto, qualsiasi altro record di dati master utilizzato come dimensioni finanziarie, ad esempio fornitori o clienti, non deve avere valori ID conto che utilizzano lo stesso carattere del delimitatore del piano dei conti. 

## <a name="how-to-determine-if-your-environment-requires-updated-delimiters"></a>Come determinare se l'ambiente richiede delimitatori aggiornati 
Se i delimitatori nell'ambiente aggiornato sono in conflitto, è possibile avvertire l'instabilità quando si immettono i valori in un controllo di immissione segmentato o in un controllo di immissione delle dimensioni. Ciò significa che è sempre necessario utilizzare le ricerche o un menu a comparsa quando si immettono combinazioni di piano dei conti e dimensioni.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

