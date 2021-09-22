---
title: Un numero di giustificativo di entrata prodotti viene utilizzato anche quando non si genera un giustificativo
description: Un numero di giustificativo di entrata prodotti viene utilizzato anche se non viene generato alcun giustificativo finanziario durante l'entrata prodotti
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 0556969950c45e80d177a0e96096c4157d690ae3
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7476762"
---
# <a name="a-product-receipt-voucher-number-is-consumed-even-when-not-generating-a-voucher"></a>Un numero di giustificativo di entrata prodotti viene utilizzato anche quando non si genera un giustificativo

## <a name="symptoms"></a>Sintomi

Un numero di giustificativo di entrata prodotti viene utilizzato anche se non viene generato alcun giustificativo finanziario durante l'entrata prodotti.

## <a name="resolution"></a>Risoluzione

Se l'opzione **Passività ratei all'entrata prodotti** è impostata su *No* per il gruppo di modelli di articoli, non verranno effettuate registrazioni nella contabilità generale. Tuttavia, un evento fisico verrà registrato ai fini della contabilità in un giornale di registrazione secondario e tale evento richiede un numero di giustificativo. Questo numero di giustificativo è il numero di giustificativo a cui si fa riferimento nelle transazioni di magazzino.

Ti consigliamo di impostare l'opzione **Passività ratei all'entrata prodotti** su *Sì*, come descritto nel seguente post del blog: [Registrare le spese varie al momento dell'entrata del prodotto](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).
