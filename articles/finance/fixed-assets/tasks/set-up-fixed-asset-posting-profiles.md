---
title: Impostare i profili registrazione cespiti
description: Questa procedura mostra come impostare i profili di registrazione cespiti.
author: moaamer
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetPosting
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ee0006c9588a22d720687e7aceb49acc756b83e1
ms.sourcegitcommit: 62ca651c94e61aaa69cfa59e861f263f89d01c4a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2021
ms.locfileid: "7883770"
---
# <a name="set-up-fixed-asset-posting-profiles"></a>Impostare i profili registrazione cespiti

[!include [banner](../../includes/banner.md)]

Questa procedura mostra come impostare i profili di registrazione cespiti. Gli esempi forniti nell'argomento sono relativi a un profilo registrazione di base, anche se i profili registrazione devono essere creati per i requisiti specifici di report finanziari e piano dei conti.

1. Nel pannello di navigazione, passare a **Moduli > Cespiti > Impostazione > Profili registrazione cespiti**.
2. Fare clic su **Nuovo**.
3. Nel campo **Profilo registrazione** digitare un valore.
4. Digitare un valore nel campo **Descrizione** Sarà necessario creare un profilo di registrazione per ogni tipo di transazione cespiti che si utilizzerà quando si utilizzano i cespiti. Questa guida attività inizierà con il tipo di transazione Acquisizione.  
5. Fare clic su **Aggiungi** nella barra degli strumenti.
6. Nel campo **Libro** immettere o selezionare un valore. Il campo **Raggruppamenti** consente di definire il profilo di registrazione fino a Tabella (un'unica impostazione di conto per ciascun cespite) o a Gruppo (un'unica impostazione di conto per ciascun gruppo cespite). Per la guida attività si lasceranno i valori impostati su "Tutti" da applicare a tutti i cespiti con il libro specificato.  
7. Nel campo **Conto principale**, specificare i valori desiderati. Per le acquisizioni, è possibile immettere un conto di contropartita o lasciarlo vuoto perché venga compilato per la transazione specifica.    
8. Nel menu a discesa nel Scheda dettaglio **Conti CoGe**, selezionare 'Rettifica acquisizione'. Per le transazioni di rettifica acquisizione, verranno utilizzati gli stessi conti utilizzati per le transazioni di acquisizione.  
9. Scegliere **Aggiungi**.
10. Nel campo **Libro** immettere o selezionare un valore.
11. Nel campo **Conto principale**, specificare i valori desiderati. Per le rettifiche di acquisizione, è possibile immettere un conto di contropartita o lasciarlo vuoto perché venga compilato per la transazione specifica.    
12. Nel menu a discesa nel Scheda dettaglio **Conti CoGe**, selezionare 'Ammortamento'.
13. Scegliere **Aggiungi**.
14. Nel campo **Libro** immettere o selezionare un valore.
15. Nel campo **Conto principale**, specificare i valori desiderati.
16. Nel campo **Conto di contropartita**, specificare i valori desiderati.
17. Nel menu a discesa sotto la Scheda dettaglio **Conti CoGe**, selezionare 'Rettifica ammortamento'. Per le transazioni di rettifica ammortamento, verranno utilizzati gli stessi conti utilizzati per le transazioni di ammortamento.  
18. Scegliere **Aggiungi**.
19. Nel campo **Libro** immettere o selezionare un valore.
20. Nel campo **Conto principale**, specificare i valori desiderati.
21. Nel campo **Conto di contropartita**, specificare i valori desiderati.
22. Nel menu a discesa sotto la Scheda dettaglio **Conti CoGe**, selezionare 'Vendita di dismissione'.
23. Scegliere **Aggiungi**.
24. Nel campo **Libro** immettere o selezionare un valore.
25. Nel campo **Conto principale**, specificare i valori desiderati. Per le dismissioni, è possibile immettere un conto di contropartita o lasciarlo vuoto perché venga compilato per la transazione specifica.  
26. Nel menu a discesa sotto la Scheda dettaglio **Conti CoGe**, selezionare 'Dismissione - scarto'. Usare gli stessi conti per la vendita di dismissione e lo scarto di dismissione.  
27. Scegliere **Aggiungi**.
28. Nel campo **Libro** immettere o selezionare un valore.
29. Nel campo **Conto principale**, specificare i valori desiderati. Per le dismissioni, è possibile immettere un conto di contropartita o lasciarlo vuoto perché venga compilato per la transazione specifica.  
30. Espandere la Scheda dettaglio **Dismissione**. È necessario impostare i profili di registrazione dismissioni sia per la vendita che per lo scarto.  Si inizierà con le transazioni di vendita di dismissione.  
31. Scegliere **Aggiungi**.
32. Nel campo **Libro** immettere o selezionare un valore.
33. Nel campo **Valore registrato**, selezionare 'Valore di acquisizione'.
    * Il valore di acquisizione indirizzerà i valori di acquisizione e di rettifica acquisizione per tutti gli anni. È inoltre possibile definire i conti per questi tipi di transazione separatamente.  
    * È possibile impostare il processo di dismissione per utilizzare conti diversi a seconda se la dismissione determina una perdita o un profitto. Si imposterà Tipo valore di vendita su "Tutti" per utilizzare gli stessi conti per tutti i tipi di dismissioni.  
34. Nel campo **Conto principale**, specificare i valori desiderati.
35. Nel campo **Conto di contropartita**, specificare i valori desiderati.
36. Scegliere **Aggiungi**.
37. Nel campo **Libro** immettere o selezionare un valore.
38. Nel campo **Valore registrato**, selezionare 'Ammortamento (anni precedenti)'.  
38. Nel campo **Conto principale**, specificare i valori desiderati.
39. Nel campo **Conto di contropartita**, specificare i valori desiderati.
40. Scegliere **Aggiungi**.
41. Nel campo **Libro** immettere o selezionare un valore.
42. Nel campo **Valore registrato**, selezionare 'Ammortamento (anno in corso)'.
43. Nel campo **Conto principale**, specificare i valori desiderati.
44. Nel campo **Conto di contropartita**, specificare i valori desiderati.
45. Scegliere **Aggiungi**.
46. Nel campo **Libro** immettere o selezionare un valore.
47. Nel campo **Valore registrato**, selezionare 'Rettifiche all'ammortamento (anni precedenti)'.
48. Nel campo **Conto principale**, specificare i valori desiderati.
49. Nel campo **Conto di contropartita**, specificare i valori desiderati.
50. Scegliere **Aggiungi**.
51. Nel campo **Libro** immettere o selezionare un valore.
52. Nel campo **Valore registrato**, selezionare 'Rettifiche all'ammortamento (anno in corso)'.
53. Nel campo **Conto principale**, specificare i valori desiderati.
54. Nel campo **Conto di contropartita**, specificare i valori desiderati.
55. Scegliere **Aggiungi**.
56. Nel campo **Libro** immettere o selezionare un valore.
57. Nel campo **Valore registrato**, selezionare 'Valore contabile netto'.
58. Nel campo **Conto principale**, specificare i valori desiderati.
59. Nel campo **Conto di contropartita**, specificare i valori desiderati.
60. Nel campo **Vendita o scarto** selezionare 'Scarto'.
61. Scegliere **Aggiungi**.
62. Nel campo **Libro** immettere o selezionare un valore.
63. Nel campo **Valore registrato**, selezionare 'Valore di acquisizione'.
64. Nel campo **Conto principale**, specificare i valori desiderati.
65. Nel campo **Conto di contropartita**, specificare i valori desiderati.
66. Scegliere **Aggiungi**.
67. Nel campo **Libro** immettere o selezionare un valore.
67. Nel campo **Valore registrato**, selezionare 'Ammortamento (anni precedenti)'.  
68. Nel campo **Conto principale**, specificare i valori desiderati.
69. Nel campo **Conto di contropartita**, specificare i valori desiderati.
70. Scegliere **Aggiungi**.
71. Nel campo **Libro** immettere o selezionare un valore.
72. Nel campo **Valore registrato**, selezionare 'Ammortamento (anno in corso)'.
73. Nel campo **Conto principale**, specificare i valori desiderati.
74. Nel campo **Conto di contropartita**, specificare i valori desiderati.
75. Scegliere **Aggiungi**.
76. Nel campo **Libro** immettere o selezionare un valore.
77. Nel campo **Valore registrato**, selezionare 'Rettifiche all'ammortamento (anni precedenti)'.
78. Nel campo **Conto principale**, specificare i valori desiderati.
79. Nel campo **Conto di contropartita**, specificare i valori desiderati.
80. Scegliere **Aggiungi**.
81. Nel campo **Libro** immettere o selezionare un valore.
82. Nel campo **Valore registrato**, selezionare 'Rettifiche all'ammortamento (anno in corso)'.
83. Nel campo **Conto principale**, specificare i valori desiderati.
84. Nel campo **Conto di contropartita**, specificare i valori desiderati.
85. Scegliere **Aggiungi**.
86. Nel campo **Libro** immettere o selezionare un valore.
87. Nel campo **Valore registrato**, selezionare 'Valore contabile netto'.
88. Nel campo **Conto principale**, specificare i valori desiderati.
89. Nel campo **Conto di contropartita**, specificare i valori desiderati.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
