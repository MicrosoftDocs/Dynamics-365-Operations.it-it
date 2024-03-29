---
title: Libri derivati
description: Questo articolo fornisce una panoramica delle funzionalità dei libri derivati.
author: moaamer
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetBookTable
audience: Application User
ms.reviewer: kfend
ms.custom: 3401
ms.assetid: 862d6450-187b-497f-9822-cce45f2c65a9
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 81abb1b16069adb3cdcc73bdf6b963463cc88938
ms.sourcegitcommit: d1683d033fc74adbc4465dd26f7b0055e7639753
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2022
ms.locfileid: "8714091"
---
# <a name="derived-books"></a>Libri derivati

[!include [banner](../includes/banner.md)]

Questo articolo fornisce una panoramica delle funzionalità dei libri derivati.

Lo scopo dei libri derivati è semplificare la registrazione delle transazioni relative ai libri di cespiti pianificate a intervalli regolari.  È possibile selezionare un libro come primario. Di solito si tratta del libro utilizzato per l'ammortamento contabile. Quindi lo si collega ad altri libri impostati per la registrazione di transazioni negli stessi intervalli del libro principale. I libri di ammortamento fiscale sono spesso impostati come libri derivati. 

Le transazioni più comuni da impostare per la registrazione in libri derivati sono le acquisizioni, le rettifiche di acquisizioni e le dismissioni. 

## <a name="example"></a>Esempio

Il libro B e il libro C vengono impostati come libri derivati per il libro A per il tipo di transazione di acquisizione. Nel libro A immettere una transazione di acquisizione per il cespite 123 di 1.500,00. 

Quando la transazione viene registrata, una transazione di acquisizione viene generata e registrata nel cespite 123 per il libro B e nel cespite 123 per il libro C per 1.500,00. Quando si preparano le transazioni del libro principale per la registrazione nel giornale di registrazione cespiti, è possibile visualizzare e modificare anche le transazioni dei libri derivati. Quando si preparano le transazioni del libro principale per la registrazione in un altro giornale di registrazione, le transazioni del valore derivato non vengono visualizzate. Queste vengono comunque registrate nei conti e nei livelli di registrazione appropriati quando si registrano le transazioni del libro principale.

> [!NOTE]                                                                                                                               
> I libri impostati per la registrazione di transazioni a intervalli diversi da quelli del libro principale devono essere collegati al cespite come libri separati, non come libri derivati.  

Per ulteriori informazioni, vedere [Registrare con i libri derivati](post-derived-value-models.md).





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
