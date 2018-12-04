--- 
title: Definire i criteri di controllo per i documenti di origine
description: In questa procedura viene illustrato come impostare ed eseguire le regole dei criteri di controllo di esecuzione.
author: ryansandness
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SysPolicySourceDocumentRuleType, SysFieldLookUp, SysPolicyListPage, SysPolicy, AuditPolicyRule, SysQueryForm, SysQueryFieldLookUp, AuditPolicyDateSelection, AuditPolicyAdditionalOption, BatchJob, CaseDetail
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 4b05f744120e940bfea3e92b8aac3e41fc8151d9
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="define-audit-policies-for-source-documents"></a>Definire i criteri di controllo per i documenti di origine

[!include [task guide banner](../../includes/task-guide-banner.md)]

In questa procedura viene illustrato come impostare ed eseguire le regole dei criteri di controllo di esecuzione. Nell'esempio vengono utilizzate le note spese con il tipo di spesa di hotel. Questa procedura utilizza la società dimostrativa USMF. Il ruolo del revisore contiene le autorizzazioni corrette per eseguire queste attività.

1. Fare clic su Controllo workbench > Impostazione > Tipo di regola dei criteri.
2. Fare clic su Nuovo.
3. Digitare un valore nel campo Regola.
4. Nel campo Descrizione digitare un valore.
5. Nel campo Nome query selezionare Riga nota spese.
6. Nel campo Tipo di query selezionare Aggrega
7. Nel campo Persona giuridica selezionare Persona giuridica.
8. Nel campo Riferimento alla data del documento selezionare Data e ora modifica
9. Fare clic su Salva.
10. Fare clic su Controllo workbench > Impostazione > Criteri di controllo.
11. Fare clic su Nuovo.
12. Digitare un valore nel campo Nome.
13. Espandere la sezione Organizzazioni criteri.
14. Nella struttura selezionare "Contoso Entertainment Systems USA"
15. Scegliere Aggiungi.
16. Nella struttura selezionare "Contoso Consulting USA".
17. Scegliere Aggiungi.
18. Nella struttura selezionare "Contoso Retail USA".
19. Scegliere Aggiungi.
20. Comprimere la sezione Organizzazioni criteri.
21. Espandere la sezione Regole dei criteri.
22. Nell'elenco, individuare e selezionare la regola dei criteri creata in precedenza.
23. Fare clic su Crea regola dei criteri.
24. Nel campo Data di validità immettere una data e un'ora.
25. Fare clic su Filtro.
26. Nell'elenco, selezionare la riga per la categoria di spesa e impostare i dettagli su Hotel
27. Nel campo Criteri immettere o selezionare un valore.
28. Fare clic sulla scheda Aggrega.
29. Scegliere Aggiungi.
30. Nell'elenco, selezionare un valore del campo Importo transazione:
31. Nel campo Campo immettere o selezionare un valore.
32. Nel campo AggregateFunction selezionare "Somma".
33. Fare clic sulla scheda Raggruppa per.
34. Scegliere Aggiungi.
35. Nell'elenco selezionare un valore di Dipendente  
36. Scegliere Aggiungi.
37. Nell'elenco selezionare un valore di Categoria di spesa
38. Nel campo Campo immettere o selezionare un valore.
39. Fare clic sulla scheda Avere.
40. Scegliere Aggiungi.
41. Selezionare Importo transazione
42. Nel campo Campo immettere o selezionare un valore.
43. Nel campo AggregateFunction selezionare "Somma".
44. Nel campo Criteri digitare '>2000'.
45. Fare clic su OK.
46. Test di clic su Test.
47. Nel campo Data iniziale di selezione documenti immettere una data e un'ora.
48. Nel campo Data finale di selezione documenti immettere una data e un'ora.
49. Fare clic su Esegui test.
50. Nel riquadro azioni, fare clic su Criteri di controllo.
51. Fare clic su Opzioni aggiuntive.
52. Nel campo Data di inizio immettere una data e un'ora.
53. Nel campo Data di fine immettere una data e un'ora.
54. Fare clic su Batch.
55. Espandere la sezione Esecuzione in background.
56. Selezionare Sì nel campo Elaborazione batch.
57. Fare clic su OK.
58. Fare clic su Controllo workbench > Casi di controllo.
59. Nell'elenco trovare e selezionare il record desiderato.
60. Nell'elenco fare clic sul collegamento nella riga selezionata.
61. Espandere la sezione Associazioni.
62. Nell'elenco trovare e selezionare il record desiderato.
63. Nell'elenco fare clic sul collegamento nella riga selezionata.


