---
title: " Creare e associare una postazione hardware"
description: In questa procedura vengono descritti i passaggi per creare una nuova stazione hardware.
author: jashanno
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailHardwareStation, RetailStoreTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 80df4fa663d208e28f5c9b031b6610d29286171c
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1548395"
---
# <a name="create-and-associate-a-hardware-station"></a> Creare e associare una postazione hardware

[!include[task guide banner](../includes/task-guide-banner.md)]

In questa procedura vengono descritti i passaggi per creare una nuova stazione hardware. Un nuovo profilo hardware verrà creato e utilizzato per aggiungere le nuove stazioni hardware a un punto vendita predefinito (canale). Questa procedura utilizza i dati dimostrativi della società USRT.

1. Passare a Funzionalità fondamentali commercio > Canali  > .. > .. > Profili stazione hardware.
2. Fare clic su Nuovo.
3. Nel campo ID stazione hardware, immettere 'TestHWProfile'.
4. Digitare un valore nel campo Nome.
5. Immettere un numero nel campo Numero porta.
6. Nel campo Profilo hardware fare clic sul pulsante a discesa per aprire la ricerca.
7. Trovare e selezionare il record desiderato nell'elenco.
8. Nell'elenco fare clic sul collegamento nella riga selezionata.
9. Nel campo Nome pacchetto fare clic sul pulsante a discesa per aprire la ricerca.
10. Nell'elenco fare clic sul collegamento nella riga selezionata.
    * Si tratta del collo standard fornito con un nuovo ambiente. Il numero di versione può variare.  
11. Fare clic su Salva.
12. Chiudere la pagina.
13. Passare a Vendita al dettaglio e commercio > Canali > Tutti i punti vendita al dettaglio.
14. Nell'elenco selezionare la riga 17.
    * Se si utilizza la società di dati dimostrativi USRT, questo valore corrisponde al punto vendita Houston.  
15. Nell'elenco fare clic sul collegamento nella riga selezionata.
16. Attivare l'espansione della sezione Stazioni hardware.
17. Scegliere Aggiungi.
18. Nell'elenco contrassegnare la riga selezionata.
19. Nel campo ID profilo fare clic sul pulsante a discesa per aprire la ricerca.
20. Nell'elenco trovare e selezionare il record desiderato.
    * Deve essere il nuovo profilo di stazione hardware creato nei passaggi precedenti.  
21. Nell'elenco fare clic sul collegamento nella riga selezionata.
22. Digitare un valore nel campo Nome host.
23. Digitare un valore nel campo ID terminale EFT.
24. Fare clic su Salva.

