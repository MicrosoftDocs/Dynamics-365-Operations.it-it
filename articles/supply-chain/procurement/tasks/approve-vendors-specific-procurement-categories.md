---
title: Approvare i fornitori per categorie specifiche di approvvigionamento
description: In questo argomento viene descritto come approvare i fornitori per categorie di approvvigionamento specifiche in Dynamics 365 Supply Chain Management.
author: RichardLuan
manager: tfehr
ms.date: 07/30/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, DirPartyEcoResCategory, EcoResCategorySingleLookup, ProcCategoryHierarchyManagement
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 159d918a4dd3b6502bc8ab411d0353545eb4fcba
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2021
ms.locfileid: "5016351"
---
# <a name="approve-vendors-for-specific-procurement-categories"></a>Approvare i fornitori per categorie specifiche di approvvigionamento

[!include [banner](../../includes/banner.md)]

In questo argomento viene descritto come approvare i fornitori per categorie di approvvigionamento specifiche in Dynamics 365 Supply Chain Management. Quando una richiesta di acquisto viene creata, ci può essere un requisito di selezionare un fornitore approvato o preferito, in base all'impostazione dei criteri di acquisto. Questa procedura vi mostra come specificare che un fornitore è approvato o preferito per una categoria specifica di approvvigionamento. Questa attività in genere viene svolta da un responsabile degli approvvigionamenti. È possibile utilizzare questa procedura nella società di dati dimostrativi USMF.

1. Nel pannello di navigazione, andare a **Moduli > Approvvigionamento > Fornitori > Tutti i fornitori**.
2. Selezionare il fornire da impostare come approvato o preferito per una categoria.
3. Nel riquadro azioni fare clic su **Generale**.
4. Selezionare **Categorie**.
5. Selezionare **Aggiungi categoria**.
6. Nel campo **Categoria**, selezionare **OFFICE AND DESK ACCESSORIES (OFFICE AND DESK ACCESSORIES)**.
7. Selezionare **Preferito** nel campo **Stato categoria fornitore**. È possibile specificare più di un fornitore preferito per una categoria.  
8. Selezionare **Salva**.
9. Nel pannello di navigazione, andare a **Moduli > Approvvigionamento > Categorie di approvvigionamento**.
10. Nella struttura selezionare **CORP PROCUREMENT CATEGORIES\OFFICE AND DESK ACCESSORIES**.
11. Espandere la sezione **Fornitori**. Controllare se il fornitore selezionato compare come fornitore preferito per la categoria degli accessori per ufficio. Se state eseguendo questa procedura come guida attività, potrebbe essere necessario selezionare il pulsante **Sblocca** per scorrere verso il basso l'elenco dei fornitori.  È inoltre possibile aggiungere i fornitori preferiti ed approvati a questa pagina.  
12. Nella struttura, espandere **OFFICE AND DESK ACCESSORIES** e selezionare **Scissors**.
13. Selezionare **No** nel campo **Eredita fornitori dalla categoria padre**.
14. Selezionare **Sì** nel campo **Eredita fornitori dalla categoria padre**.

