---
title: Definire i criteri di controllo per i documenti di origine
description: In questo argomento viene illustrato come impostare ed eseguire regole dei criteri di controllo.
author: ryansandness
manager: AnnBe
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicySourceDocumentRuleType, SysFieldLookUp, SysPolicyListPage, SysPolicy, AuditPolicyRule, SysQueryForm, SysQueryFieldLookUp, AuditPolicyDateSelection, AuditPolicyAdditionalOption, BatchJob, CaseDetail
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ba720fd1bbbbf8b4f3b936d65d9d7840432f291a
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3145031"
---
# <a name="define-audit-policies-for-source-documents"></a>Definire i criteri di controllo per i documenti di origine

[!include [banner](../../includes/banner.md)]

In questo argomento viene illustrato come impostare ed eseguire regole dei criteri di controllo. Nell'esempio vengono utilizzate le note spese con il tipo di spesa di hotel. Questa procedura utilizza la società dimostrativa USMF. Il ruolo del revisore contiene le autorizzazioni corrette per eseguire queste attività.

1. Nel pannello di navigazione, andare a **Moduli > Controllo workbench > Impostazione > Tipo di regola dei criteri**.
2. Selezionare **Nuovo**.
3. Nel campo **Nome regola** digitare un valore.
4. Digitare un valore nel campo **Descrizione**
5. Nel campo **Nome query** selezionare **Riga nota spese**.
6. Nel campo **Tipo di query** selezionare **Aggrega**.
7. Nel campo **Persona giuridica** selezionare **Persona giuridica**.
8. Nel campo **Riferimento alla data del documento** selezionare **Data e ora modifica**.
9. Selezionare **Salva**.
10. Nel pannello di navigazione, andare a **Moduli > Controllo workbench > Impostazione > Criteri di controllo**.
11. Selezionare **Nuovo**.
12. Digitare un valore nel campo **Nome**.
13. Espandere la sezione **Organizzazioni criteri**.
14. Nella struttura selezionare **Contoso Entertainment Systems USA**, quindi selezionare **Aggiungi**.
15. Nella struttura selezionare **Contoso Consulting USA**, quindi selezionare **Aggiungi**.
16. Nella struttura selezionare **Contoso Retail USA**, quindi selezionare **Aggiungi**.
17. Comprimere la sezione **Organizzazioni criteri**.
18. Espandere la sezione **Regole dei criteri**.
19. Nell'elenco, individuare e selezionare la regola dei criteri creata in precedenza.
20. Selezionare **Crea regola dei criteri**.
21. Nel campo **Data di validità** immettere una data e un'ora.
22. Selezionare **Filtro**.
23. Nell'elenco, selezionare la riga per **Categoria di spesa** e impostare i dettagli su **Hotel**.
24. Nel campo **Criteri** immettere o selezionare un valore.
25. Selezionare la scheda **Aggrega**.
26. Selezionare **Aggiungi**.
27. Nell'elenco, selezionare un valore di **Importo transazione**.
28. Nel campo **Campo** immettere o selezionare un valore.
29. Nel campo **AggregateFunction** selezionare **Somma**.
30. Selezionare la scheda **Raggruppa per**.
31. Selezionare **Aggiungi**.
32. Nell'elenco selezionare un valore di **Dipendente**.
33. Selezionare **Aggiungi**.
34. Nell'elenco selezionare un valore di **Categoria di spesa**.
35. Nel campo **Campo** immettere o selezionare un valore.
36. Selezionare la scheda **Avere**.
37. Selezionare **Aggiungi**.
38. Selezionare **Importo transazione**.
39. Nel campo **Campo** immettere o selezionare un valore.
40. Nel campo **AggregateFunction** selezionare **Somma**.
41. Nel campo **Criteri** digitare `>2000`.
42. Selezionare **OK**.
43. Selezionare **Test**.
44. Nel campo **Data iniziale di selezione documenti** immettere una data e un'ora.
45. Nel campo **Data finale di selezione documenti** immettere una data e un'ora.
46. Selezionare **Esegui test**.
47. Nel riquadro azioni, selezionare **Criteri di controllo**.
48. Selezionare **Opzioni aggiuntive**.
49. Nel campo **Data di inizio** immettere una data e un'ora.
50. Nel campo **Data di fine** immettere una data e un'ora.
51. Selezionare **Batch**.
52. Espandere la sezione **Esecuzione in background**.
53. Selezionare **Sì** nel campo **Elaborazione batch**.
54. Selezionare **OK**.
55. Nel pannello di navigazione, andare a **Moduli > Controllo workbench > Casi di controllo**.
56. Nell'elenco trovare e selezionare il record desiderato.
57. Espandere la sezione **Associazioni**.
58. Nell'elenco trovare e selezionare il record desiderato.

