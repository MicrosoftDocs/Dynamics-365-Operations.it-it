---
title: Creare e assegnare strutture di regole avanzate
description: In questo argomento viene descritto come creare e assegnare una struttura di regole avanzate a una struttura dei conti.
author: aprilolson
manager: AnnBe
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DimensionConfigureAccountRuleStructure, DimensionCreateAccountRuleStructure, DimensionHierarchyAddLevel, DimensionHierarchyConstraintActivate, DimensionConfigureAccountStructure, DimensionConfigureAccountRule, DimensionCreateAccountRule, DimensionSelectAccountRuleStructure
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cff07c13553ea140f537160da7f93820d5e3f77a
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "1834896"
---
# <a name="create-and-assign-advanced-rule-structures"></a>Creare e assegnare strutture di regole avanzate

[!include [task guide banner](../../includes/task-guide-banner.md)]

In questo argomento viene descritto come creare e assegnare una struttura di regole avanzate a una struttura dei conti. Questa guida utilizza la società dimostrativa USMF.

## <a name="create-an-advanced-rule-structure"></a>Crea una struttura di regole avanzate
1. Passare a **Pannello di navigazione > Moduli > Contabilità generale > Piano dei conti > Strutture > Strutture regole avanzate**.
2. Selezionare **Nuovo** per aprire la finestra di dialogo a discesa.
3. Nel campo **Struttura regole avanzate**, digitare un nome per descrivere la struttura delle regole.
4. Selezionare **OK**.
5. Selezionare **Aggiungi segmento**.
6. Selezionare una dimensione finanziaria nell'elenco di segmenti. Ad esempio, **Punto vendita**.  
7. Selezionare **Aggiungi segmento**.
8. Selezionare **Attiva**.

## <a name="apply-an-advanced-rule-structure-to-an-account-structure"></a>Applicare una struttura di regole avanzate a una struttura dei conti
1. Passare a **Pannello di navigazione > Moduli > Contabilità generale > Piano dei conti > Strutture > Configura strutture dei conti**.
2. Nell'elenco, trovare e selezionare la struttura dei conti a cui applicare la regola avanzata.
3. Selezionare **Modifica**. È inoltre possibile fare clic su **Regole avanzate** e verrà richiesto di inserire la struttura dei conti in **modalità di bozza**.  
4. Selezionare **Regole avanzate**.
5. Selezionare **Nuovo** per aprire la finestra di dialogo a discesa.
6. Digitare un valore nel campo **Regola avanzata**.
7. Digitare un valore nel campo **Nome**.
8. Selezionare **Crea**.
9. Fare clic su **Aggiungi nuovi criteri**.
10. Nel campo **Percorso**, selezionare un conto principale o una dimensione finanziaria.
11. Nel campo **Operatore**, selezionare un'opzione, ad esempio **è compreso in** e **include**.
12. Digitare un valore nel campo **Valore**.
13. Digitare un valore nel campo **attraverso**.
14. Fare clic su **Aggiungi** per aprire la finestra di dialogo a discesa.
15. Nell'elenco, individuare la struttura di regole avanzate da utilizzare quando vengono soddisfatti i criteri immessi.
16. Selezionare **Aggiungi**.
17. Chiudere la pagina.
18. Selezionare **Attiva**.

