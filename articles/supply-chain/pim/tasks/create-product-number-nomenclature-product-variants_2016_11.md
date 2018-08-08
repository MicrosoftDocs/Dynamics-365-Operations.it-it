--- 
title: Creare un numero di prodotto per le varianti prodotto configurate
description: "In questa procedura viene illustrato come impostare una nomenclatura di numero prodotto per le varianti prodotto configurate e come può essere collegata a una rappresentazione generale prodotto configurabile."
author: ShylaThompson
manager: AnnBe
ms.date: 10/25/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: e70a5f28635e75a69811085637f7e7431c0f1d40
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-product-number-for-configured-product-variants"></a>Creare un numero di prodotto per le varianti prodotto configurate

[!include [task guide banner](../../includes/task-guide-banner.md)]

In questa procedura viene illustrato come impostare una nomenclatura di numero prodotto per le varianti prodotto configurate e come può essere collegata a una rappresentazione generale prodotto configurabile. Questa procedura dimostra anche come è possibile creare una nomenclatura di configurazione per un componente del modello di configurazione prodotto. La società di dati dimostrativi utilizzata per creare questa procedura è USMF. La nuova nomenclatura di numero prodotto è assegnata alla rappresentazione generale prodotto D0004. Questa attività viene in genere effettuata da un responsabile del design del prodotto.


## <a name="create-a-product-number-nomenclature"></a>Creare una nomenclatura di numero prodotto
1. Fare clic su Definizione modello di variante prodotto.
2. Fare clic su Nomenclatura di prodotto.
3. Fare clic su Nuovo.
4. Digitare un valore nel campo Nome.
5. Nel campo Descrizione digitare un valore.
6. Scegliere Aggiungi.
7. Fare clic su Numero rappresentazione generale prodotto.
8. Scegliere Aggiungi.
9. Fare clic su Costante testo.
10. Nell'elenco contrassegnare la riga selezionata.
11. Digitare un valore nel campo Testo.
12. Scegliere Aggiungi.
13. Fare clic su Configurazione.
14. Chiudere la pagina.

## <a name="assign-the-product-number-nomenclature-to-a-product-master"></a>Assegnare la nomenclatura di un numero prodotto a una rappresentazione generale prodotto
1. Fare clic su Rappresentazioni generali prodotto.
2. Utilizzare il filtro rapido per trovare i record. Ad esempio, filtrare in base al campo Numero prodotto con un valore di 'D'.
3. Nell'elenco fare clic sul collegamento nella riga selezionata.
4. Fare clic su Modifica.
5. Selezionare Sì nel campo Utilizza nomenclatura.
6. Nel campo Nomenclatura di numero di variante prodotto immettere o selezionare un valore.
7. Chiudere la pagina.
8. Chiudere la pagina.

## <a name="create-nomenclature-for-a-product-configuration-model-component"></a>Creare una nomenclatura per un componente di modello di configurazione prodotto
1. Fare clic su Modelli di configurazione prodotto.
2. Nell'elenco trovare e selezionare il record desiderato.
3. Nell'elenco fare clic sul collegamento nella riga selezionata.
4. Fare clic su Modifica.
5. Selezionare Sì nel campo Utilizza nomenclatura di configurazione.
6. Scegliere Aggiungi.
7. Fare clic su Valore attributo.
8. Nell'elenco contrassegnare la riga selezionata.
9. Nel campo Attributo immettere o selezionare un valore.
10. Scegliere Aggiungi.
11. Fare clic su Costante testo.
12. Nell'elenco contrassegnare la riga selezionata.
13. Digitare un valore nel campo Testo.
14. Scegliere Aggiungi.
15. Fare clic su Valore attributo.
16. Nell'elenco contrassegnare la riga selezionata.
17. Nel campo Attributo immettere o selezionare un valore.
18. Scegliere Aggiungi.
19. Fare clic su Costante testo.
20. Nell'elenco contrassegnare la riga selezionata.
21. Digitare un valore nel campo Testo.
22. Scegliere Aggiungi.
23. Fare clic su Valore attributo.
24. Nell'elenco contrassegnare la riga selezionata.
25. Nel campo Attributo immettere o selezionare un valore.
26. Scegliere Aggiungi.
27. Fare clic su Costante testo.
28. Nell'elenco contrassegnare la riga selezionata.
29. Digitare un valore nel campo Testo.
30. Scegliere Aggiungi.
31. Fare clic su Valore attributo.
32. Nell'elenco contrassegnare la riga selezionata.
33. Nel campo Attributo immettere o selezionare un valore.
34. Scegliere Aggiungi.
35. Fare clic su Costante testo.
36. Nell'elenco contrassegnare la riga selezionata.
37. Digitare un valore nel campo Testo.
38. Scegliere Aggiungi.
39. Fare clic su Valore sequenza numerica.
40. Nell'elenco contrassegnare la riga selezionata.
41. Nel campo Sequenza numerica immettere o selezionare un valore.
42. Chiudere la pagina.
43. Chiudere la pagina.
44. Chiudere la pagina.


