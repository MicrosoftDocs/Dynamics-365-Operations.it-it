--- 
title: Creare un nuovo conto bancario fornitore
description: Questa procedura mostra come creare un conto bancario per un fornitore.
author: mkirknel
manager: AnnBe
ms.date: 08/25/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: adb759c59d7275e7323dbb760de56acdef2e3cff
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-vendor-bank-account"></a>Creare un nuovo conto bancario fornitore

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Questa procedura mostra come creare un conto bancario per un fornitore. È possibile utilizzare questa procedura nella società di dati dimostrativi USMF.

1. Andare ad Approvvigionamento > Fornitori > Tutti i fornitori.
2. Selezionare il fornitore per cui volete creare un conto bancario e poi fate clic sul collegamento nell'ID conto fornitore.
3. Nel riquadro azioni, fare clic su Fornitore.
4. Fare clic su Conti bancari.
5. Fare clic su Nuovo.
6. Digitare un valore nel campo Conto bancario.
    * Questo ID sarà usato per identificare il conto bancario nel record fornitore.  
7. Digitare un valore nel campo Nome.
8. Nel campo gruppi bancari immettere o selezionare un valore.
9. Nel campo Tipo di numero di registrazione selezionare un'opzione.
    * Questo è il tipo di numero di registrazione utilizzato per i pagamenti internazionali.  
10. Digitare un valore nel campo Numero conto bancario.
11. Digitare un valore nel campo Codice SWIFT.
12. Digitare un valore nel campo IBAN.
    * Il numero IBAN deve essere nel formato corretto. È ad esempio possibile utilizzare DE89370400440532013000.  
    * Lo stato del conto bancario è attivo se la data di attivazione è stata raggiunta e la data di scadenza non è stata oltrepassata. È inoltre attivo se entrambi i campi Data di attivazione e Data di scadenza sono vuoti. Se le date incluse nei campi Data di attivazione e Data di scadenza sono entrambe successive alla data corrente, non è possibile effettuare pagamenti elettronici. Sono disponibili altri tipi di pagamento e il conto bancario è attivo.  
13. Espandere la sezione Impostazione.
14. Digitare un valore nel campo Codice di testo.
    * Questo campo specifica un codice che comparirà sul rendiconto bancario del destinatario.  
15. Digitare un valore nel campo Messaggio alla banca.
16. Digitare un valore nel campo Riferimento cambio.
    * Questo è il numero di riferimento dell'eventuale tasso di cambio a termine o fisso.  
17. Nel campo Valuta immettere o selezionare un valore.
    * Quando le notifiche anticipate sono pubblicate, questa sezione fornisce una panoramica del loro stato (in sospeso o approvato).  
18. Espandere la sezione Indirizzo.
19. Espandere la sezione Notifiche anticipate.
20. Espandere la sezione Informazioni sul contatto.
21. Digitare un valore nel campo Telefono.
22. Chiudere la pagina.
23. Fare clic su Modifica.
24. Espandere la sezione Pagamento.
25. Nel campo Conto bancario, selezionare il conto che avete creato appena.
26. Fare clic su Salva.
    * L'indirizzo può essere ereditato dal gruppo di banche, se è specificato, o potete aggiungerlo qui.  


