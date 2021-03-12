---
title: Creare richieste articoli per gli ordini di assistenza
description: Se è necessario prenotare articoli specifici per un ordine di assistenza, è possibile creare le richieste articolo di magazzino.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7ae44088a1b53ac5e7e9ba09ed7ff611a08d2ed0
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996701"
---
# <a name="create-item-requirements-for-service-orders"></a>Creare richieste articoli per gli ordini di assistenza 

[!include [banner](../includes/banner.md)]


È possibile creare un ordine di assistenza per tenere traccia dei e gestire i servizi forniti ai clienti. Se è necessario prenotare articoli specifici per un ordine di assistenza, è possibile creare le richieste articolo di magazzino. Una richiesta articolo può essere immediatamente utilizzata dal magazzino oppure può avviare un ordine di produzione per l'articolo.

Le richieste articoli consentono, rispetto alle transazioni articolo, di pianificare la consegna per il momento immediatamente precedente l'utilizzo effettivo dell'articolo, di creare un ordine fornitore, di includere l'articolo all'interno di un accordo commerciale e di includere la richiesta articolo nella pianificazione della produzione.

Le richieste articoli per gli ordini di assistenza vengono elaborati nel corso di un progetto. Per creare una richiesta articolo in un ordine di assistenza, è necessario che l'ordine di assistenza sia assegnato a un progetto. Una volta creata una richiesta articolo per un ordine di assistenza, è possibile visualizzare la richiesta articolo nel modulo **Progetti** per il progetto selezionato.

## <a name="create-an-item-requirement-for-a-service-order"></a>Creare una richiesta articoli per un ordine di assistenza

1.  Fare clic su **Gestione assistenza** \> **Comune** \> **Ordini di assistenza** \> **Ordini di assistenza**.

2.  Selezionare l'ordine di assistenza per cui si desidera creare una richiesta di articoli.

3.  Nel **riquadro azioni** fare clic su **Richiesta articolo** nella scheda **Spedisci**.

4.  Nel modulo **Richieste articoli** immettere le informazioni relative all'articolo richiesto. Per ulteriori informazioni su specifici campi, consultare [Richieste articoli (modulo)](https://technet.microsoft.com/library/aa552021\(v=ax.60\)).

## <a name="create-an-item-requirement-for-a-service-agreement"></a>Creare una richiesta di articoli per un contratto di assistenza

1.  Fare clic su **Gestione assistenza** \> **Comune** \> **Contratti di assistenza** \> **Contratti di assistenza**.

2.  Aprire il contratto di assistenza per cui si desidera creare una richiesta di articoli.

3.  Nella Scheda dettaglio **Righe** fare clic su **Aggiungi** per creare una nuova riga.

4.  Nel campo **Tipo di transazione**, selezionare **Articolo**.

5.  Nel campo **Impostazioni articolo**, selezionare **Richiesta articolo**.

6.  Nel campo **Numero articolo** selezionare l'articolo necessario per il contratto di assistenza.

7.  Nella Scheda dettaglio **Dettagli riga**, nel campo **Sito** della scheda **Dimensioni prodotto**, selezionare il sito di magazzino per l'articolo.

8.  Per creare un ordine di assistenza dalla riga contratto, nella Scheda dettaglio **Righe** fare clic su **Crea ordini di assistenza**, quindi immettere le informazioni rilevanti nel modulo **Crea ordini di assistenza**. 


## <a name="see-also"></a>Vedere anche

[Creare ordini di assistenza automaticamente](create-service-orders-automatically.md).

  


