---
title: Impostare codici di smaltimento
description: Questa procedura riguarda l'impostazione di un codice smaltimento che può essere utilizzato in un dispositivo mobile per il processo di ricezione dell'ordine di reso.
author: ShylaThompson
manager: tfehr
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSDispositionTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6d84699e8e4323792ac67b69236d264e33eeaf28
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "4431535"
---
# <a name="set-up-dispositions-codes"></a>Impostare codici di smaltimento

[!include [banner](../../includes/banner.md)]

Questa procedura riguarda l'impostazione di un codice smaltimento che può essere utilizzato in un dispositivo mobile per il processo di ricezione dell'ordine di reso. I codici smaltimento sono una raccolta di regole che possono essere utilizzate quando gli articoli vengono ricevuti. Ad esempio, quando un utente di lavoro utilizza un dispositivo mobile per ricevere articoli danneggiati, l'utente deve digitalizzare un codice smaltimento per gli articoli danneggiati. Lo stato di inventario delle merci ricevute, il modello di lavoro e la direttiva ubicazione possono essere determinate dal codice smaltimento digitalizzato. Per il processo di ricezione dell'ordine fornitore e il processo di dichiarazione di finito degli ordini di produzione, l'utilizzo di un codice smaltimento è facoltativo. Per il processo di ricevimento reso dell'ordine cliente, se gli articoli vengono registrati tramite un dispositivo mobile, l'utilizzo del codice smaltimento è obbligatorio.  Questa guida è stata creata utilizzando la società di dati dimostrativi USMF. Questa procedura è destinata al responsabile del magazzino. 

1. Andare a Gestione magazzino > Impostazioni > Dispositivo mobile > Codici smaltimento.
2. Fare clic su Nuovo.
    * Creare un nuovo codice smaltimento da utilizzare per i resi dei clienti.  
3. Nel campo Codice smaltimento digitare un valore.
4. Nel campo Stato inventario selezionare uno stato in cui sia presente il blocco scorte.
    * Se si utilizza USMF, selezionare l'opzione di bloccaggio. È possibile aggiungere lo stato delle scorte al codice smaltimento per sostituire lo stato predefinito sulle righe ordine.  
5. Digitare un valore nel campo Modello di lavoro.
    * Facoltativo: selezionare un codice del modello di lavoro associato a un ordine di reso. Se nessun valore viene specificato, il modello di lavoro verrà risolto utilizzando le regole standard configurate nel sistema. La selezione di un modello di lavoro limiterà i processi con cui il codice smaltimento specifico può essere utilizzato. Ad esempio, se un codice smaltimento ha un modello di lavoro con un ordine di lavoro di tipo ordine fornitore, non può essere utilizzato per registrare gli articoli restituiti dai clienti.  
6. Nel campo Codice smaltimento reso digitare un valore.
    * Il codice smaltimento di reso determina il resto del processo di ordine di reso per gli articoli registrati. In questo esempio, il cliente deve ricevere una nota di accredito. Aggiungere un codice smaltimento di reso contenente un'azione di tipo Avere.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]