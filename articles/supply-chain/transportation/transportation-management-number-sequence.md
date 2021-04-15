---
title: Sequenza numerica della gestione trasporto
description: Questo argomento descrive come impostare le sequenze numeriche per la gestione del trasporto.
author: Henrikan
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-10-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: f3da757cbf47e0e1af781b720d17a673e19aeb3b
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5807682"
---
# <a name="transportation-management-number-sequence"></a>Sequenza numerica della gestione trasporto

[!include [banner](../includes/banner.md)]

Utilizzare la pagina **Sequenze numeriche** nel modulo di gestione dei trasporti per impostare vari numeri processo. I numeri processo vengono utilizzati dai corrieri per organizzare e monitorare lo stato di avanzamento di ogni spedizione.

## <a name="create-a-number-sequence-for-a-pro-number"></a>Creare una sequenza numerica per un numero prodotto

Per creare una sequenza numerica per un numero prodotto, procedere come segue:

1. Vai a **Gestione trasporto \> Impostazioni \> Vettori \> Sequenze numeriche**.
1. Selezionare **Nuovo** per creare una nuova sequenza numerica.
1. Immettere un ID univoco e un nome descrittivo per la sequenza numerica.
1. Nel campo **Tipo di sequenza numerica**, *Numero prodotto* è l'unica opzione.
1. Nel campo **Cifra di controllo**, *Cifra di controllo* è l'unica opzione ed è impostato come motore generico.
1. Nella scheda dettaglio **Sequenza** fornire informazioni sulla sequenza.
1. Chiudere la pagina.

## <a name="link-a-number-sequence-to-a-shipping-carrier"></a>Collegare una sequenza numerica a un vettore

Per collegare una sequenza numerica a un vettore, procedere come segue:

1. Vai a **Gestione trasporto \> Impostazioni \> Vettori \> Vettori spedizione**.
1. Selezionare un vettore di spedizione.
1. Seleziona **Modifica**.
1. Nella scheda dettaglio **Panoramica** selezionare un'opzione nel campo **Sequenza numerica prodotto**.
1. Chiudere la pagina.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]