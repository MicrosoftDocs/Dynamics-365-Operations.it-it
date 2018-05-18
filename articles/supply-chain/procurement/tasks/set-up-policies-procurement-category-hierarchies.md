--- 
title: Impostare criteri per le gerarchie di categorie di approvvigionamento
description: Utilizzare questa procedura per impostare le regole per ordinare prodotti in una categoria.
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
ms.openlocfilehash: 50764f99be04d27e04047824f870e724336cb452
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-policies-for-procurement-category-hierarchies"></a>Impostare criteri per le gerarchie di categorie di approvvigionamento

[!include [task guide banner](../../includes/task-guide-banner.md)]

Utilizzare questa procedura per impostare le regole per ordinare prodotti in una categoria. Le regole vengono definite per criteri di acquisto specifici. La regola di accesso alle categorie determina le categorie di approvvigionamento a cui i dipendenti hanno accesso quando creano una richiesta. Quando viene creata una richiesta, i criteri di acquisto e la regola di accesso alle categorie da applicare vengono determinati dalla persona giuridica e dall'unità operativa a cui il dipendente appartiene. È possibile utilizzare questa procedura nella società di dati dimostrativi USMF. In genere questa attività sarà svolta da un responsabile acquisti.


## <a name="find-the-procurement-policy"></a>Trovare i criteri di approvvigionamento
1. Andare a Approvvigionamento > Impostazioni > Criteri > Criteri di acquisto.
2. Fare clic sul collegamento sui criteri di approvvigionamento USMF.
    * Questi sono i criteri a cui aggiungerete una regola. Devono essere criteri attivi.  

## <a name="create-a-category-access-rule"></a>Creare una regola di accesso alla categoria
1. Selezionare la regola dei criteri di accesso alle categorie.
    * Se il pulsante Crea regola dei criteri è disattivato, è perché c'è già una regola dei criteri attiva per l'accesso alle categorie. Controllare i campi Data di validità e Data di scadenza per determinare quale è, quindi selezionarla e fare clic su Ritira regola dei criteri. Se il pulsante Crea regola dei criteri è disponibile, non dovete fare nulla.  
2. Fare clic su Crea regola dei criteri.
3. Nel campo Data di validità immettere una data e un'ora.
    * Il tempo non deve sovrapporsi con un'altra regola che è già attiva.  
    * Selezionare una categoria a cui la regola si applicherà. Prendere nota di quale categoria questa è – l'informazione sarà necessaria successivamente. Quando si seleziona una categoria, anche le relative categorie padre verranno aggiunte all'elenco Categorie selezionate.  
    * Selezionare la casella di controllo Includi sottocategorie per applicare la regola a tutte le sottocategorie della categoria selezionata.  
4. Scegliere Aggiungi.
    * Se si imposta l'opzione Includi regola padre su Sì, la regola dei criteri definiti per una categoria padre verrà assegnata anche alle categorie figlio se non è stata definita una regola dei criteri per le categorie figlio.  
5. Fare clic su OK.

## <a name="create-a-category-policy-rule"></a>Crea una regola dei criteri categorie
1. Selezionare la regola dei criteri di accesso.
    * Se il pulsante Crea regola dei criteri è disattivato, selezionare la regola dei criteri attiva e poi fare clic su Ritira regola dei criteri.  
2. Fare clic su Crea regola dei criteri.
3. Nel campo Data di validità immettere una data e un'ora.
4. Scegliere Aggiungi.
5. Selezionare la stessa categoria che avete usato per la regola di accesso alle categorie.
6. Selezionare un'opzione nel campo Selezione fornitore.
    * Selezionare una regola per controllare il tipo di fornitori che può essere selezionato per la categoria quando le richieste vengono create.  
7. Fare clic su Chiudi.
    * Le regole dei criteri definite sono state per le richieste di tipo Consumo. Se voleste definire criteri per le richieste di tipo Rifornimento, dovreste creare una regola per Tipo di regola dei criteri chiamata "Regola dei criteri di accesso alle categorie di rifornimento".  


