---
title: Batch interaziendale e numeri di serie
description: Questo articolo spiega cosa accadrà quando si registrano i numeri di batch e i numeri di serie per gli ordini interaziendali
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 5c743c8eee8d27a2c2357523a11236eb247ec5be
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8851509"
---
# <a name="intercompany-batch-and-serial-numbers"></a>Batch interaziendale e numeri di serie

[!include [banner](../../includes/banner.md)]

Le società che utilizzano numeri di serie o numeri di batch per monitorare gli articoli devono tenere traccia anche dei numeri di serie e dei numeri di batch degli articoli prelevati. La funzionalità interaziendale consente di automatizzare lo spostamento dei numeri di serie e dei numeri di batch da una società all'altra. Quando si registrano i numeri di batch e di serie per gli articoli in un ordine cliente interaziendale, è possibile impostare il programma per il trasferimento automatico di tali numeri all'ordine fornitore interaziendale e all'ordine cliente originario. È necessario impostare i parametri pertinenti nella pagina **Interaziendale** per l'ordine cliente:

- Se si seleziona il campo **Numero di batch** nella pagina **Criteri ordine cliente**, il numero di batch viene sincronizzato con le operazioni di inventario nelle righe dell'ordine fornitore interaziendale durante la registrazione del documento di trasporto dell'ordine cliente interaziendale.
- Se si seleziona il campo **Numero di serie**, i numeri di serie vengono sincronizzati con le operazioni di inventario nelle righe dell'ordine fornitore interaziendale durante la registrazione del documento di trasporto dell'ordine cliente interaziendale.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
