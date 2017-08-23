--- 
title: Impostare la separazione dei compiti
description: "È possibile impostare le regole per separare le attività che devono essere eseguite da utenti diversi."
author: maertenm
manager: AnnBe
ms.date: 11/15/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 2ab30f4326b627406f9a39d6c3203b181b67d68f
ms.contentlocale: it-it
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-segregation-of-duties"></a>Impostare la separazione dei compiti

[!include[task guide banner](../../includes/task-guide-banner.md)]

È possibile impostare le regole per separare le attività che devono essere eseguite da utenti diversi. Questo concetto è denominato separazione dei compiti. Ad esempio, non è possibile che la stessa persona confermi l'entrata delle merci ed elabori il pagamento al fornitore. La separazione dei compiti consente di ridurre il rischio di frode e aiuta anche a rilevare errori o irregolarità. È inoltre possibile utilizzare la separazione dei compiti per applicare i criteri di controllo interno. Completare la procedura indicata di seguito per creare una regola. È necessario essere un amministratore di sistema per completare la procedura. La società di dati dimostrativi utilizzata per creare questa procedura è DAT. 

1. Scegliere Amministrazione sistema > Sicurezza > Separazione dei compiti > Regole di separazione dei compiti.
2. Fare clic su Nuovo.
3. Digitare un valore nel campo Nome.
    * Immettere un nome per la regola.  
4. Nel campo Primo compito fare clic sul pulsante a discesa per aprire la ricerca.
5. Nell'elenco trovare e selezionare il record desiderato.
    * Selezionare il primo compito che è controllato dalla regola.  
6. Nell'elenco fare clic sul collegamento nella riga selezionata.
7. Nel campo Secondo compito fare clic sul pulsante a discesa per aprire la ricerca.
8. Nell'elenco trovare e selezionare il record desiderato.
    * Selezionare il secondo compito che è controllato dalla regola.  
9. Nell'elenco fare clic sul collegamento nella riga selezionata.
10. Selezionare un'opzione nel campo Gravità.
    * Selezionare la gravità del rischio che si verifica quando entrambi i compiti vengono eseguiti dallo stesso utente o ruolo.  
11. Digitare un valore nel campo Rischio di sicurezza.
    * Immettere una descrizione del rischio di sicurezza.  
12. Digitare un valore nel campo Riduzione dei rischi di sicurezza.
    * Immettere una descrizione delle azioni prese per attenuare il rischio di sicurezza. Ad esempio, è possibile attenuare il rischio effettuando revisioni più dettagliati del processo, svolgendo una revisione manageriale mensile o condividendo le risorse con altri reparti.  
13. Fare clic su Salva.


