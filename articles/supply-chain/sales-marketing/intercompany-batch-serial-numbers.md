---
title: Batch interaziendale e numeri di serie
description: Questo argomento spiega cosa accadrà quando si registrano i numeri di batch e i numeri di serie per gli ordini interaziendali
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 4da936263bb57c24eeb7021ac61b3945bb2777fb
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548366"
---
# <a name="intercompany-batch-and-serial-numbers"></a>Batch interaziendale e numeri di serie

[!include [banner](../../includes/banner.md)]

Le società che utilizzano numeri di serie o numeri di batch per monitorare gli articoli devono tenere traccia anche dei numeri di serie e dei numeri di batch degli articoli prelevati. La funzionalità interaziendale consente di automatizzare lo spostamento dei numeri di serie e dei numeri di batch da una società all'altra. Quando si registrano i numeri di batch e di serie per gli articoli in un ordine cliente interaziendale, è possibile impostare il programma per il trasferimento automatico di tali numeri all'ordine fornitore interaziendale e all'ordine cliente originario. È necessario impostare i parametri pertinenti nella pagina **Interaziendale** per l'ordine cliente:

- Se si seleziona il campo **Numero di batch** nella pagina **Criteri ordine cliente**, il numero di batch viene sincronizzato con le operazioni di inventario nelle righe dell'ordine fornitore interaziendale durante la registrazione del documento di trasporto dell'ordine cliente interaziendale.
- Se si seleziona il campo **Numero di serie**, i numeri di serie vengono sincronizzati con le operazioni di inventario nelle righe dell'ordine fornitore interaziendale durante la registrazione del documento di trasporto dell'ordine cliente interaziendale.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
