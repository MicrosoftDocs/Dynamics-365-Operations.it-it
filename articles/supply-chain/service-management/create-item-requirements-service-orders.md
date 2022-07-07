---
title: Creare richieste articoli per gli ordini di assistenza
description: In questo articolo viene descritto come creare richieste articoli per gli ordini di assistenza.
author: sorenva
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f21cda0abb334432d22cc7e0ccfdab724253d91e
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2022
ms.locfileid: "9016951"
---
# <a name="create-item-requirements-for-service-orders"></a>Creare richieste articoli per gli ordini di assistenza

[!include [banner](../includes/banner.md)]

È possibile creare un ordine di assistenza per tenere traccia dei e gestire i servizi forniti ai clienti. Se è necessario prenotare articoli specifici per un ordine di assistenza, è possibile creare le richieste articolo di magazzino. Una richiesta articolo può essere immediatamente utilizzata dal magazzino oppure può avviare un ordine di produzione per l'articolo.

Le richieste articoli consentono, rispetto alle transazioni articolo, di pianificare la consegna per il momento immediatamente precedente l'utilizzo effettivo dell'articolo, di creare un ordine fornitore, di includere l'articolo all'interno di un accordo commerciale e di includere la richiesta articolo nella pianificazione della produzione.

Le richieste articoli per gli ordini di assistenza vengono elaborati nel corso di un progetto. Per creare una richiesta articolo in un ordine di assistenza, è necessario che l'ordine di assistenza sia assegnato a un progetto. Una volta creata una richiesta articolo per un ordine di assistenza, è possibile visualizzare la richiesta articolo nel modulo **Progetti** per il progetto selezionato.

## <a name="create-an-item-requirement-for-a-service-order"></a>Creare una richiesta articoli per un ordine di assistenza

1. Vai a **Gestione assistenza** \> **Ordini di assistenza** \> **Ordini di assistenza**.
1. Selezionare l'ordine di assistenza per cui si desidera creare una richiesta di articoli.
1. Nel **riquadro Azioni**, sulla scheda **Spedisci**, selezionare **Richiesta articolo**.
1. Nel modulo **Richieste articoli** immettere le informazioni relative all'articolo richiesto. Per ulteriori informazioni su specifici campi, consultare [Richieste articoli (modulo)](https://technet.microsoft.com/library/aa552021\(v=ax.60\)).

## <a name="create-an-item-requirement-for-a-service-agreement"></a>Creare una richiesta di articoli per un contratto di assistenza

1. Seleziona **Gestione assistenza** \> **Contratti di assistenza** \> **Contratti di assistenza**.
1. Aprire il contratto di assistenza per cui si desidera creare una richiesta di articoli.
1. Nella Scheda dettaglio **Righe** selezionare **Aggiungi** per creare una nuova riga.
1. Nel campo **Tipo di transazione**, selezionare **Articolo**.
1. Nel campo **Impostazioni articolo**, selezionare **Richiesta articolo**.
1. Nel campo **Numero articolo** selezionare l'articolo necessario per il contratto di assistenza.
1. Nella Scheda dettaglio **Dettagli riga**, nel campo **Sito** della scheda **Dimensioni prodotto**, selezionare il sito di magazzino per l'articolo.
1. Per creare un ordine di assistenza dalla riga contratto, nella Scheda dettaglio **Righe**, selezionare **Crea ordini di assistenza**, quindi immettere le informazioni rilevanti nel modulo **Crea ordini di assistenza**.

## <a name="see-also"></a>Vedere anche

[Creare ordini di assistenza automaticamente](create-service-orders-automatically.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
