--- 
title: " Utilizzare un programma di continuità"
description: "Questa procedura descrive la vendita di un programma di continuità e l'elaborazione degli ordini cliente correlati."
author: scott-tucker
manager: AnnBe
ms.date: 11/14/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: d2642d922fc1fa03644be8195a8c9dd3edfc3483
ms.contentlocale: it-it
ms.lasthandoff: 02/07/2018

---
# <a name="use-a-continuity-program"></a> Utilizzare un programma di continuità

[!include[task guide banner](../includes/task-guide-banner.md)]

Questa procedura descrive la vendita di un programma di continuità e l'elaborazione degli ordini cliente correlati. Per eseguire questa procedura, l'utente deve essere impostato come utente di servizio clienti. Questa procedura utilizza la società di dati dimostrativi USRT.

1. Passare a Vendita al dettaglio e commercio > Clienti > Servizio clienti.
2. Nel campo Cerca testo, digitare 'Karen' quindi premere il tasto TAB.
    * La finestra di dialogo di ricerca avanzata dovrebbe apparire. In caso contrario, fare clic su Cerca a destra del campo.  
3. Nell'elenco contrassegnare la riga selezionata.
    * Deve essere presente un'unica riga che mostra Karen Berg. Selezionare la riga facendo clic su nella colonna di segno di spunta all'estrema sinistra della griglia.  
4. Fare clic su Seleziona.
5. Fare clic su Nuovo ordine cliente.
    * È consigliabile prendere nota del numero di ordine cliente. Sarà necessario più avanti in questa procedura.  
6. Nel campo Numero articolo, digitare '88000' quindi premere il tasto TAB.
    * Si tratta di un articolo continuità nei dati dimostrativi USRT.  
7. Fare clic su Completa.
8. Nel campo Metodo di pagamento, immettere 'Visa'.
9. Fare clic su Aggiungi carta di credito.
    * Immettere le informazioni necessarie su carta di credito in questa pagina.  
10. Fare clic su OK.
11. Espandere la sezione Pagamento.
    * Per inviare un ordine servizio clienti, i pagamenti devono essere immessi per l'ordine.  
12. Fare clic su OK.
13. Fare clic su Invia.
    * È terminata la creazione di un nuovo ordine di continuità. A questo punto, eseguirete due processi batch utilizzati per elaborare gli ordini di continuità.  
14. Chiudere la pagina.
15. Passare a Vendita al dettaglio e commercio > Continuità > Elabora pagamenti di continuità.
16. Nel campo Articolo di continuità, digitare '88000' quindi premere il tasto TAB.
17. Fare clic su OK.
18. Passare a Vendita al dettaglio e commercio > Continuità > Crea ordini di continuità figlio.
    * Questo processo consente di creare nuovi ordini cliente in base alle impostazioni dei programmi di continuità.  
19. Nel campo Articolo di continuità, digitare '88000' quindi premere il tasto TAB.
    * Articolo '88000' è un articolo di continuità nei dati dimostrativi USRT.  
20. Nel campo Ordine cliente immettere o selezionare un valore.
    * Immettere il numero di ordine cliente annotato in precedenza nella procedura. Questo terrà il tempo di elaborazione a un minimo per questa procedura. Il campo Ordine cliente è facoltativo: si potrebbero elaborare tutti gli ordini per qualsiasi dato programma.  
21. Fare clic su OK.


