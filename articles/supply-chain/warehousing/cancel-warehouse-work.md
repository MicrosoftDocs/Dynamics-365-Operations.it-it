---
title: Annullare il lavoro di magazzino per la gestione delle eccezioni
description: In questo articolo viene descritta la funzionalità di annullamento del lavoro che consente ai supervisori del magazzino di gestire il lavoro bloccato.
author: Mirzaab
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSTroubIeshootingSeIfService, WHSTroubleshootingSelfService
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2019-10-1
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: b1e2036e4e7a8a47d6df029f285df7aca0fa74e6
ms.sourcegitcommit: 0220be95c007c77ba3b73fed8ac68a3d72dc2884
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2022
ms.locfileid: "9403677"
---
# <a name="cancel-warehouse-work-for-exception-handling"></a>Annullare il lavoro di magazzino per la gestione delle eccezioni

[!include [banner](../includes/banner.md)]

La funzionalità Annulla lavoro in Microsoft Dynamics 365 Supply Chain Management consente all'utente amministratore di annullare il lavoro magazzino specifico attualmente in corso, ma che è bloccato dal sistema o non può essere completato a causa di circostanze eccezionali. Questa funzionalità è un'alternativa conveniente e sicura agli script correttivi SQL che correggono i dati incoerenti. Tuttavia, mentre questi script sono in genere richiesti ai professionisti IT, la funzionalità Annulla lavoro può essere utilizzata dagli utenti dell'azienda che dispongono dei diritti di amministratore.

È possibile accedere alla funzionalità Annulla lavoro selezionando **Gestione magazzino** \> **Attività periodiche** \> **Pulitura \> Annulla lavoro**. Nella finestra di dialogo **Annulla lavoro**, specificare l'ID del lavoro da annullare, quindi selezionare **OK**.

## <a name="warehouse-work-that-can-be-canceled"></a>Lavori di magazzino che possono essere annullati

Durante le operazioni di prelievo del magazzino, un lavoratore potrebbe riscontrare situazioni in cui ha registrato le quantità come prelevate da un'ubicazione di immagazzinamento nell'ubicazione dell'utente, ma non può registrare l'operazione di inserimento. Dati di magazzino incoerenti sono spesso, ma non sempre, il motivo per cui il lavoro viene bloccato.

Diversamente dalla normale funzionalità Annulla a cui è possibile accedere utilizzando il pulsante **Annulla** nell'intestazione del lavoro, la funzionalità Annulla lavoro non richiede che l'ultima riga di lavoro completata sia una riga di lavoro di tipo **stoccaggio**. In altre parole, per la funzionalità Annulla lavoro, la logica di annullamento può essere eseguita anche se la quantità di articoli su una riga di lavoro si trova in un'ubicazione dell'utente.

> [!NOTE]
> Per lavori che devono essere annullati per motivi operativi, gli utenti del magazzino devono continuare a utilizzare la normale funzionalità Annulla nella pagina di lavoro.

Solo i lavori di tipo **Vendite**, **Uscita di trasferimento**, **Prelievo materie prime** oppure **Rifornimento** possono essere annullati utilizzando la funzionalità Annulla lavoro. La logica di annullamento non verrà eseguita per i lavori di prelievo materie prime bloccati o lavori che possono essere annullati utilizzando la normale funzionalità Annulla (vedere la nota precedente).

Per sbloccare il lavoro, il sistema annulla le eventuali righe di lavoro rimanenti e corregge i dati di magazzino associati all'ID lavoro specificato dall'utente. Sarà quindi possibile riprendere le normali operazioni di gestione del magazzino che riguardano la quantità dell'articolo interessata.

Per stoccare l'articolo interessato in un'ubicazione specifica dopo che il lavoro è stato annullato, l'utente deve utilizzare un'operazione di movimento scorte o rettifica della quantità su un dispositivo mobile.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]