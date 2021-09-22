---
title: Non è possibile aggiungere il campo Unità di prezzo alla pagina Contratto di acquisto
description: Quando si apre la pagina "Contratto di acquisto" in modalità di visualizzazione riga, non è possibile personalizzarla aggiungendo il campo Unità di prezzo nella panoramica della riga.
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart, PurchRFQTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 56d2ce94fb4b74d982cb6a052cca71c18190cd04
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476740"
---
# <a name="you-cant-add-the-price-unit-field-to-the-purchase-agreement-page"></a>Non è possibile aggiungere il campo Unità di prezzo alla pagina Contratto di acquisto

## <a name="symptoms"></a>Sintomi

Quando si apre la pagina **Contratto di acquisto** in modalità di visualizzazione riga, non è possibile personalizzarla aggiungendo il campo **Unità di prezzo** nella panoramica della riga.

## <a name="resolution"></a>Risoluzione

Alcuni campi condivisi nel framework dell'accordo non possono essere inclusi nelle personalizzazioni. Questa limitazione si verifica a causa del modello di dati implementato. Pertanto, non è possibile personalizzare il campo **Unità di prezzo**.
