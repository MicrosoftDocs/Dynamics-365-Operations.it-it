--- 
title: " Creare gruppi di autorizzazioni POS"
description: In questa procedura vengono descritti i passaggi per creare un gruppo di autorizzazioni POS.
author: scott-tucker
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: e924dc59c3e4cb9b6979014852512453dd3d70db
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="create-pos-permission-groups"></a> Creare gruppi di autorizzazioni POS

[!include[task guide banner](../includes/task-guide-banner.md)]

In questa procedura vengono descritti i passaggi per creare un gruppo di autorizzazioni POS. La società di dati dimostrativi utilizzata per creare questa attività è USRT. Questa attività è destinata al ruolo Responsabile operativo vendita al dettaglio.

1. Passare a Gruppi di autorizzazioni.
2. Fare clic su Nuovo.
3. Digitare un valore nel campo ID gruppo di autorizzazioni POS.
4. Nel campo Descrizione digitare un valore.
5. Selezionare Sì nel campo Visualizza voci orologio.
    * È ora possibile abilitare o disabilitare le varie autorizzazioni per il gruppo di autorizzazioni POS. Per alcune autorizzazioni è possibile impostare un valore che verrà utilizzato per valutare se l'utente POS può eseguire l'azione.  Questa guida attività abilita l'autorizzazione che può essere assegnata al cassiere.  
6. Selezionare Sì nel campo Consenti creazione ordine.
7. Selezionare Sì nel campo Consenti modifica ordine.
8. Selezionare Sì nel campo Consenti recupero ordine.
9. Selezionare Sì nel campo Consenti modifica password.
10. Selezionare Sì nel campo Consenti chiusura forzata.
11. Fare clic su Salva.
    * Dopo aver salvato le modifiche, è necessario eseguire la programmazione di distribuzione del personale per applicare le modifiche ai canali di vendita al dettaglio.  
12. Chiudere la pagina.
13. Passare a Processi.
    * Quindi, verrà assegnato il gruppo di autorizzazioni POS a un processo.  
14. Nell'elenco trovare e selezionare il record desiderato.
15. Nell'elenco fare clic sul collegamento nella riga selezionata.
16. Fare clic su Modifica.
17. Espandere la sezione Classificazione mansione.
18. Nel campo Gruppo di autorizzazioni POS immettere o selezionare un valore.
    * Tutti i lavoratori nelle posizioni per questo processo utilizzeranno le impostazioni del gruppo di autorizzazioni POS a meno che le autorizzazioni POS del lavoratore siano state ignorate a livello di posizione.  
19. Fare clic su Salva.
    * Dopo aver salvato le modifiche, è necessario eseguire la programmazione di distribuzione del personale per applicare le modifiche ai canali di vendita al dettaglio.  


