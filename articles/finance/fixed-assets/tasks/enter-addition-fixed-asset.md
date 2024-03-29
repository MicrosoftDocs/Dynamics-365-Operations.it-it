---
title: Immettere un cespite aggiuntivo
description: In questa procedura viene illustrato come aggiungere un componente aggiuntivo a un cespite esistente.
author: moaamer
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable, AssetAddition
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2d23f60963466249b332b759ee72ebc8387aee4b
ms.sourcegitcommit: d1683d033fc74adbc4465dd26f7b0055e7639753
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2022
ms.locfileid: "8713024"
---
# <a name="enter-an-addition-to-a-fixed-asset"></a>Immettere un cespite aggiuntivo

[!include [banner](../../includes/banner.md)]

In questa procedura viene illustrato come aggiungere un componente aggiuntivo a un cespite esistente. Lo scopo di Componenti cespite aggiuntivi è di tenere traccia dei componenti articolo aggiuntivi, di manutenzione o di miglioramenti per un cespite ed è solo informativo. Tutte le modifiche al valore o alla vita utile del cespite devono essere effettuate separatamente.   

Nella procedura viene utilizzato il ruolo Ragioniere e i dati dimostrativi per la persona giuridica USMF.

1. Nel pannello di navigazione, passare a **Moduli > Cespiti > Cespiti > Cespiti**.
2. Nell'elenco, individuare e selezionare il cespite per il componente aggiuntivo.
3. Nell'elenco fare clic sul collegamento nella riga selezionata.
4. Nel riquadro azioni fare clic su **Cespite**.
5. Fare clic su **Componenti cespite aggiuntivi**.
6. Fare clic su **Nuovo**.
7. Digitare un valore nel campo **Nome**.
8. Nel campo **Data di acquisizione**, impostare la data di acquisto o di manutenzione del componente.
9. Nel campo **Costo unitario** Immettere il costo dell'articolo, della manutenzione o di un altro miglioramento per il cespite.
10. Nel campo **Quantità** immettere un numero. Il costo totale non avrà impatto sul valore del cespite e viene fornito solo per tenere traccia e per scopi informativi. Se il costo verrà capitalizzato, una transazione di rettifica di rivalutazione deve essere registrata separatamente.  
11. Fare clic sulla scheda **Generale**.

    * Impostare **Aumenta la vita utile** su **Sì** se il componente aggiuntivo aumenta la vita utile del cespite.  
    * Questo campo viene visualizzato solo a scopo informativo. Per aumentare la vita utile, modificare la vita utile nei modelli di valore e/o nei registri beni ammortizzabili per il cespite.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
