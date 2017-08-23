--- 
title: Approvare i fornitori per categorie specifiche di approvvigionamento
description: "Quando una richiesta di acquisto viene creata, ci può essere un requisito di selezionare un fornitore approvato o preferito, in base all'impostazione dei criteri di acquisto."
author: mkirknel
manager: AnnBe
ms.date: 08/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bibis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 75486202c3fdcaff78a5592389c624d8e21fa969
ms.contentlocale: it-it
ms.lasthandoff: 07/27/2017

---
# <a name="approve-vendors-for-specific-procurement-categories"></a>Approvare i fornitori per categorie specifiche di approvvigionamento

[!include[task guide banner](../../includes/task-guide-banner.md)]

Quando una richiesta di acquisto viene creata, ci può essere un requisito di selezionare un fornitore approvato o preferito, in base all'impostazione dei criteri di acquisto. Questa procedura vi mostra come specificare che un fornitore è approvato o preferito per una categoria specifica di approvvigionamento. Questa attività in genere viene svolta da un responsabile degli approvvigionamenti. È possibile utilizzare questa procedura nella società di dati dimostrativi USMF.

1. Andare ad Approvvigionamento > Fornitori > Tutti i fornitori.
2. Selezionare il fornire da impostare come approvato o preferito per una categoria.
3. Nel riquadro azioni fare clic su Generale.
4. Fare clic su Categorie.
5. Fare clic su Aggiungi categoria.
6. Nel campo Categoria, selezionare OFFICE AND DESK ACCESSORIES (OFFICE AND DESK ACCESSORIES).
7. Selezionare 'Preferito' nel campo Stato categoria fornitore.
    * È possibile specificare più di un fornitore preferito per una categoria.  
8. Fare clic su Salva.
9. Passare a Approvvigionamento > Categorie di approvvigionamento.
10. Nella struttura selezionare 'CORP PROCUREMENT CATEGORIES\OFFICE AND DESK ACCESSORIES'.
11. Espandere la sezione Fornitori.
    * Controllare se il fornitore selezionato compare come fornitore preferito per la categoria degli accessori per ufficio. Se state eseguendo questa procedura come guida attività, potrebbe essere neecssario fare clic sul pulsante Sblocca per scorrere verso il basso l'elenco dei fornitori.  È inoltre possibile aggiungere i fornitori preferiti ed approvati a questa pagina.  
12. Nella struttura espandere 'OFFICE AND DESK ACCESSORIES'.
13. Nella struttura, selezionare 'Scissors'.
14. Selezionare No nel campo Eredita fornitori dalla categoria padre.
15. Selezionare Sì nel campo Eredita fornitori dalla categoria padre.


