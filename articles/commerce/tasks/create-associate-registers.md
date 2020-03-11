---
title: " Creare e associare registri di cassa"
description: Questa procedura dimostra come creare un registratore di cassa POS.
author: rubencdelgado
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailTerminalTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0ac75d390b8bbb94c6e039b374b51462d348e355
ms.sourcegitcommit: 12b9d6f2dd24e52e46487748c848864909af6967
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "3057169"
---
# <a name="create-and-associate-registers"></a> Creare e associare registri di cassa

[!include[task guide banner](../includes/task-guide-banner.md)]

Questa procedura dimostra come creare un registratore di cassa POS. Questa procedura utilizza la società di dati dimostrativi USRT.

1. Passare a Retail e Commerce > Impostazione canale > Impostazione POS > Registri.
2. Fare clic su Nuovo.
3. Nel campo Numero registratore di cassa, digitare l'ID relativo al nuovo registratore.
    * L'ID registratore comprende tipicamente i codici che contribuiscono a mappare il registratore al punto vendita a cui appartiene ed alla posizione all'interno del punto vendita.  
4. Nel campo Nome digitare un nome descrittivo per il registratore di cassa.
5. Nel campo Numero punto vendita immettere o selezionare un valore.
6. Nel campo Profilo hardware immettere o selezionare un valore.
    * I profili hardware sono usati per specificare le periferiche che saranno collegate al registratore, quali il cassetto della cassa e la stampante delle ricevute.  
7. Nel campo Profilo visivo immettere o selezionare un valore.
    * I profili visivi sono usati per specificare le immagini utilizzate nello sfondo POS e nella pagina di accesso come pure i temi per il POS.  
8. Nel campo Numero di registratore di cassa POS EFT, digitare un valore.
    * Il numero di registratore di cassa POS EFT è usato per indicare all'unità di elaborazione di pagamento quale terminale di pagamento sta inviando le richieste di autorizzazione. Questo valore spesso è chiamato "ID terminale" o “TID”. Il TID può essere trovato generalmente su un autoadesivo sul dispositivo di pagamento.  
9. Fare clic su Salva.

