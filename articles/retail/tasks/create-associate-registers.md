--- 
title: " Creare e associare registri di cassa"
description: Questa procedura dimostra come creare un registratore di cassa POS.
author: rubencdelgado
manager: AnnBe
ms.date: 10/05/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: 1de4e71fd554ba0486a5d2f65803f0806df37fe4
ms.contentlocale: it-it
ms.lasthandoff: 02/07/2018

---
# <a name="create-and-associate-registers"></a> Creare e associare registri di cassa

[!INCLUDE [task guide banner](../includes/task-guide-banner.md)]

Questa procedura dimostra come creare un registratore di cassa POS. Questa procedura utilizza la società di dati dimostrativi USRT.

1. Passare a Vendita al dettaglio e commercio > Impostazione canale > Impostazione POS > Registri.
2. Fare clic su Nuovo.
3. Nel campo Numero registratore di cassa, digitare l'ID relativo al nuovo registratore.
    * L'ID registratore comprende tipicamente i codici che contribuiscono a mappare il registratore al punto vendita a cui appartiene ed alla posizione all'interno del punto vendita.  
4. Nel campo Nome digitare un nome descrittivo per il registratore di cassa.
5. Nel campo Numero punto vendita immettere o selezionare un valore.
6. Nel campo Profilo hardware immettere o selezionare un valore.
    * I profili hardware sono usati per specificare le periferiche di vendita al dettaglio che saranno collegate al registratore, quali il cassetto della cassa e la stampante delle ricevute.  
7. Nel campo Profilo visivo immettere o selezionare un valore.
    * I profili visivi sono usati per specificare le immagini utilizzate nello sfondo POS e nella pagina di accesso come pure i temi per il POS.  
8. Nel campo Numero di registratore di cassa POS EFT, digitare un valore.
    * Il numero di registratore di cassa POS EFT è usato per indicare all'unità di elaborazione di pagamento quale terminale di pagamento sta inviando le richieste di autorizzazione. Questo valore spesso è chiamato "ID terminale" o “TID”. Il TID può essere trovato generalmente su un autoadesivo sul dispositivo di pagamento.  
9. Fare clic su Salva.


