---
title: Gestire i tipi di codice a barre
description: "Questa procedura mostra come impostare una nuova definizione di codice a barre che potrà quindi essere utilizzata come parte del report distinta di prelievo."
author: perlynne
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 45323206550d1b0ed66d89f4be7b995c60af63fc
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="maintain-bar-code-types"></a>Gestire i tipi di codice a barre

[!include[task guide banner](../../includes/task-guide-banner.md)]

Questa procedura mostra come impostare una nuova definizione di codice a barre che potrà quindi essere utilizzata come parte del report distinta di prelievo. È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure utilizzando i propri dati. Se si utilizza USMF è possibile utilizzare i valori di esempio visualizzati. Queste attività verranno in genere svolte da un responsabile del magazzino.

1. Passare ai codici a barre.
2. Fare clic su Nuovo.
3. Digitare un valore nel campo Impostazione codice a barre.
4. Nel campo Descrizione digitare un valore.
5. Nel campo Tipo di codice a barre selezionare un'opzione.
    * Se si utilizza USMF, è possibile selezionare 'Code 39'.  
6. Nel campo Dimensioni immettere un numero.
7. Nel campo Lunghezza massima immettere un numero.
8. Fare clic su Salva.
9. Chiudere la pagina.
10. Passare a Parametri di gestione articoli e magazzino.
11. Nel campo Impostazione codice a barre immettere o selezionare un valore.
    * Selezionare l'impostazione codice a barre creata prima, ma tenere presente che il formato di codice a barre deve corrispondere al formato dell'identificatore univoco per il tipo di record utilizzato nel processo. Ad esempio, per i cicli di prelievo, il formato di codice a barre deve corrispondere al formato di riferimento del ciclo di prelievo, che è in genere una sequenza numerica.  
12. Fare clic su Salva.
13. Chiudere la pagina.

