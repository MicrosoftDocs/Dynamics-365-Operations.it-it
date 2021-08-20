---
title: Gli ordini di acquisto ricevuti fisicamente non sono visualizzati nel report Chiusura inventario
description: Gli ordini di acquisto ricevuti fisicamente non sono visualizzati nel report di chiusura inventario Verifica quantità aperte.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventOpenQtyCritical
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 49faa2c68d496c5c0d8c7e4abfd93d9a917857220dd23c09a050fa3436e1d49a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6746869"
---
# <a name="physically-received-purchase-orders-dont-appear-on-the-inventory-closing-report"></a>Gli ordini di acquisto ricevuti fisicamente non sono visualizzati nel report Chiusura inventario

Numero KB: 4612595

## <a name="symptoms"></a>Sintomi

Gli ordini di acquisto ricevuti fisicamente non sono visualizzati nel report di chiusura dell'inventario **Verifica quantità aperte**.

## <a name="resolution"></a>Risoluzione

Il report **Verifica quantità aperte** mostra le transazioni in uscita che non possono essere liquidate in base alle entrate in magazzino aggiornate finanziariamente alla data di chiusura selezionata. Puoi scegliere di includere le entrate fisiche nel report. In tal caso, le entrate fisiche verranno visualizzate se possono coprire le transazioni in uscita che non possono essere liquidate. Per ulteriori informazioni, vedi [Operazioni preliminari alla chiusura inventario](/dynamicsax-2012/appuser-itpro/preparing-to-run-inventory-close).
