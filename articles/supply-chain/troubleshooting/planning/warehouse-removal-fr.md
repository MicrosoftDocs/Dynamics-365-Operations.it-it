---
title: Impossibile rimuovere la dimensione di previsione della domanda di magazzino dalle righe di previsione
description: Impossibile rimuovere la dimensione di previsione della domanda di magazzino dalle righe di previsione.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ForecastSales
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 6b643c4fe51ae6ce73b34ab81d4e458dcd5032df
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026646"
---
# <a name="you-cant-remove-the-warehouse-demand-forecast-dimension-from-forecast-lines"></a>Impossibile rimuovere la dimensione di previsione della domanda di magazzino dalle righe di previsione

Numero KB: 4614408

## <a name="symptoms"></a>Sintomi

Questo problema si verifica quando la dimensione **Magazzino** non è assegnata nella scheda **Dimensioni previsione** della pagina **Parametri di previsione della domanda**. Tuttavia, la colonna **Magazzino** è visualizzata nella **Previsione della domanda** (**Pianificazione generale \> Previsioni \> Voce di previsione \> Righe di previsione della domanda**).

## <a name="resolution"></a>Risoluzione

Le impostazioni nella scheda **Dimensioni previsione** della pagina **Parametri di previsione della domanda** non influiscono sulla pagina **Previsione della domanda**. Controllano la previsione di base generata e mostrata nella previsione della domanda modificata. Tuttavia, non controllano le dimensioni necessarie per la previsione della domanda "reale". Autorizzando i record visualizzati nella pagina **Previsione della domanda modificata** è possibile convertirli in voci di previsione "reali" per un modello di previsione. Quel modello può quindi essere utilizzato per la pianificazione generale.

Nella pagina **Previsione della domanda**, le dimensioni per la previsione "reale" visualizzate nelle righe di previsione della domanda fanno parte delle dimensioni inventariali (questo comportamento è simile a quello delle righe di ordine cliente). Se il sistema non è configurato per utilizzare **Magazzino** come dimensione inventariale obbligatoria, puoi personalizzare la pagina per nascondere la colonna.
