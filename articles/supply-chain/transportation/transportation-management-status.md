---
title: Stati della gestione trasporto
description: Questo articolo spiega come creare uno stato di trasporto e mappare tale stato a uno stato di vettore.
author: Weijiesa
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2020-09-08
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 9b20570a87a9f8969ca6dcf898176fd40f88eeca
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8897373"
---
# <a name="transportation-management-statuses"></a>Stati della gestione trasporto

[!include [banner](../includes/banner.md)]

Impostare codici principali per gli stati di trasporto per interpretare i codici che sono forniti dai vettori di spedizione. Ciò consente l'integrazione con i vettori di spedizione per fornire uno stato. Lo stato del trasporto che si fornisce per un codice dello stato di trasporto principale consente di tenere traccia dello stato di un carico, una spedizione o un contenitore. Lo stato di trasporto specifico per un carico, una spedizione o un contenitore può essere aggiornato solo tramite l'integrazione dei dati e non manualmente tramite l'interfaccia utente.

## <a name="create-a-transportation-status"></a>Creare uno stato di trasporto

Per creare uno stato di trasporto, effettuare le seguenti operazioni:

1. Andare a **Gestione trasporto \> Impostazione \> Stato trasporto principale**.
1. Selezionare **Nuovo** per creare uno stato di trasporto principale.
1. Nel campo **Stato trasporto principale** immettere un codice univoco per lo stato del trasporto.
1. Nel campo **Tipo di trasporto** selezionare *Vettore di spedizione* o *Hub* come il tipo di trasporto.
1. Immettere un nome e lo stato del trasporto.
1. Chiudere la pagina.

## <a name="map-a-transportation-status-to-a-carrier-status"></a>Associare uno stato di trasporto a uno stato di vettore

Per associare uno stato di trasporto a uno stato di vettore, effettuare quanto segue:

1. Andare a **Gestione trasporto \> Impostazione \> Vettori \> Stato trasporto vettore**.
1. Selezionare **Nuovo** per mappare un vettore di spedizione a un codice dello stato di trasporto principale.
1. Selezionare l'ID univoco del vettore di spedizione e il servizio di trasporto.
1. Selezionare il codice dello stato di trasporto che si desidera mappare al codice del vettore di spedizione selezionato.
1. Immettere il codice esterno utilizzato dal vettore di spedizione.
1. Chiudere la pagina.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]