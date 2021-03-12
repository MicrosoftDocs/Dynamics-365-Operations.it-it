---
title: Conferma prodotto per prelievo cluster
description: Viene descritta la procedura per l'impostazione della verifica dell'articolo e del prelievo cluster.
author: Mirzaab
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFAutoConfirm
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c8f81d760e8c181891aeba92834577e8869fbdd8
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "5001126"
---
# <a name="product-confirmation-for-cluster-picking"></a>Conferma prodotto per prelievo cluster

[!include [banner](../includes/banner.md)]

Il prelievo cluster consente di selezionare gli articoli per più ordini contemporaneamente. Quando il prelievo cluster viene applicato, la conferma dell'articolo è essenziale per verificare che gli articoli vengano aggiunti ai cluster. È possibile verificare gli articoli nel prelievo cluster durante il processo di prelievo cluster.

## <a name="where-it-applies"></a>Dove si applica

La verifica dell'articolo per il prelievo cluster funziona nello stesso modo della verifica degli articoli nei processi di prelievo non cluster. L'impostazione dipende dall'impostazione dei codici a barre del prodotto.

## <a name="set-up-item-verification-with-cluster-picking"></a>Impostare la verifica dell'articolo con prelievo cluster

1. Su una voce di menu del dispositivo mobile, aprire il modulo di impostazione per la conferma di lavoro: **Gestione magazzino** > **Gestione magazzino** > **Impostazione** > **Dispositivo mobile** > **Voci di menu del dispositivo mobile**.
1. Dalle voci di menu del dispositivo mobile, aprire la **configurazione della conferma del lavoro**.

|        Opzione        |                                    descrizione                                    |
|----------------------|-----------------------------------------------------------------------------------|
| Conferma prodotto | Consente di verificare ogni pezzo di magazzino dal dispositivo mobile sottoposto a scansione. |
