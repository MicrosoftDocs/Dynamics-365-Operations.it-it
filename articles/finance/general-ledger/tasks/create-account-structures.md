---
title: Creare strutture dei conti
description: In questa procedura verrà illustrata la creazione di una struttura dei conti.
author: aprilolson
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DimensionConfigureAccountStructure, DimensionCreateAccountStructure, DimensionHierarchyAddLevel, DimensionHierarchyConstraintActivate
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 04c22fce0c6b510e7e02036d9bf84f33d3c71e8c
ms.sourcegitcommit: 1d2eeacad11c28889681504cdc509c90e3e8ea86
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2022
ms.locfileid: "8716833"
---
# <a name="create-account-structures"></a>Creare strutture dei conti

[!include [banner](../../includes/banner.md)]

In questa procedura verrà illustrata la creazione di una struttura dei conti. I passaggi utilizzano la società di dati dimostrativi USMF.

1. Andare a **Pannello di navigazione > Moduli > Contabilità generale > Piano dei conti > Strutture > Configura strutture dei conti**.
2. Nel **Riquadro azioni**, fare clic su **Nuovo** per aprire la finestra di dialogo.
3. Nel campo **Struttura dei conti**, immettere un nome per descrivere lo scopo della struttura dei conti.
4. Nel campo **Descrizione**, immettere una descrizione per specificare lo scopo della struttura dei conti.
5. Fare clic su **Crea**.
6. In **Segmenti e valori consentiti**, fare clic su **Aggiungi segmento**.
7. Nell'elenco Dimensioni, selezionare la dimensione da aggiungere alla struttura dei conti.
8. Alla fine dell'elenco, fare clic su **Aggiungi segmento**.
9. Ripetere i passaggi da 6 a 9 come necessario.
10. Nella sezione **Dettagli valori consentiti**, selezionare il segmento per modificare i valori consentiti.
    Ad esempio, fare clic su **Conto principale**.  
11. Nel campo **Operatore**, selezionare un'opzione, ad esempio è compreso in e include.
12. Digitare un valore nel campo **Valore**. Ad esempio, 600000.  
13. Digitare un valore nel campo **attraverso**. Ad esempio, 699999.  
14. Nella sezione **Dettagli valori consentiti**, fare clic su **Applica**.
15. Ripetere i passaggi da 10 a 15 come necessario.  
16. Nella sezione **Dettagli valori consentiti**, fare clic su **Aggiungi nuovi criteri**.
17. Nel campo Operatore, selezionare un'opzione, ad esempio è compreso in e include.
18. Digitare un valore nel campo **Valore**. Ad esempio, 033.  
19. Digitare un valore nel campo **attraverso**. Ad esempio, 034.  
20. Fare clic su **Applica**.
21. Nella griglia, selezionare il segmento per modificare i valori consentiti. Ad esempio, Centro di costo.  
22. Digitare un valore nel campo **CostCenter**. Ad esempio, 007..021.  
23. In **Segmenti e valori consentiti**, fare clic su **Aggiungi**.
24. Digitare un valore nel campo **MainAccount**. Ad esempio, 600000..699999  
25. Nella griglia, selezionare il segmento per modificare i valori consentiti. Ad esempio, Reparto.  
26. Digitare un valore nel campo Reparto. Ad esempio, 032.  
27. Digitare un valore nel campo CostCenter. Ad esempio, 086.  
28. Nel **riquadro azioni** fare clic su **Convalida**.
29. Nel **riquadro azioni** fare clic su **Attiva**.
30. Fare clic su **Attiva**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
