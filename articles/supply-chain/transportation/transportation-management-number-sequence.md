---
title: Sequenza numerica della gestione trasporto
description: Questo articolo descrive come impostare le sequenze numeriche per la gestione del trasporto.
author: Weijiesa
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2020-10-16
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 2a1d3e1a36164215b70d88b10beb35748be2e23b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8847819"
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