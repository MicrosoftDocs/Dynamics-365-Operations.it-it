--- 
title: "Creare e acquisire cespiti dalla contabilità fornitori"
description: "In questa guida attività verrà illustrata la creazione e l'acquisizione di un cespite con il processo di acquisto."
author: saraschi2
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9149378047fc22efbd401b7af86df07c1403e4f5
ms.openlocfilehash: cfe920b2ef493ab3ae36a9557001086ed99c3e4e
ms.contentlocale: it-it
ms.lasthandoff: 10/05/2017

---
# <a name="create-and-acquire-assets-from-accounts-payable"></a>Creare e acquisire cespiti dalla contabilità fornitori

[!include [task guide banner](../../includes/task-guide-banner.md)]

In questa guida attività verrà illustrata la creazione e l'acquisizione di un cespite con il processo di acquisto. Vengono utilizzati l'addetto alla contabilità fornitori e il contabile e la società dimostrativa USMF.


## <a name="set-fixed-assets-parameters"></a>Impostare i parametri per i cespiti
1. Passare a Cespiti > Impostazione > Parametri cespiti.
2. Espandere o comprimere la sezione Ordini fornitore.
3. Selezionare la casella di controllo Consenti acquisizione cespiti da Acquisto.
4. Selezionare la casella di controllo Crea cespite durante la registrazione entrata prodotti o fattura.

## <a name="create-a-new-vendor-invoice"></a>Crea una nuova fattura fornitore
1. Andare a Contabilità fornitori > Aree di lavoro > Inserimento fatture fornitore.
2. Fare clic su Nuova fattura fornitore.
3. Nel campo Conto fattura fare clic sul pulsante a discesa per aprire la ricerca.
4. Nell'elenco fare clic sul collegamento nella riga selezionata.
5. Digitare un valore nel campo Numero.
6. Immettere una data nel campo Data registrazione.
7. Fare clic su Aggiungi riga.
8. Nel campo Numero articolo fare clic sul pulsante a discesa per aprire la ricerca.
    * Gli articoli non stoccati o le categorie di approvvigionamento possono essere utilizzati per l'acquisizione dei cespiti.  
9. Nell'elenco fare clic sul collegamento nella riga selezionata.
10. Nel campo Quantità immettere un numero.
    * Una riga della fattura creerà solo un cespite, indipendentemente dalla quantità.  Il valore del campo Quantità in fattura verrà trasferito in Quantità cespite.  
11. Nel campo Prezzo unitario immettere un numero.
12. Espandere o comprimere la sezione Dettagli riga.
13. Fare clic sulla scheda Cespiti.
14. Selezionare la casella di controllo Crea un nuovo cespite.
15. Nel campo Gruppo cespite fare clic sul pulsante a discesa per aprire la ricerca.
16. In questo elenco selezionare il gruppo cespite da utilizzare quando si crea il nuovo cespite.
17. Nell'elenco fare clic sul collegamento nella riga selezionata.
18. Fare clic su Registra.
    * Il cespite verrà creato e acquisito quando viene registrata la fattura.  


