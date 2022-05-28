---
title: Creare e assegnare strutture di regole avanzate
description: In questo argomento viene descritto come creare e assegnare una struttura di regole avanzate a una struttura dei conti.
author: aprilolson
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DimensionConfigureAccountRuleStructure, DimensionCreateAccountRuleStructure, DimensionHierarchyAddLevel, DimensionHierarchyConstraintActivate, DimensionConfigureAccountStructure, DimensionConfigureAccountRule, DimensionCreateAccountRule, DimensionSelectAccountRuleStructure
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ea0a31eeac9593051916d44113459f4b6ad70a92
ms.sourcegitcommit: 602a319f4720b39a56b7660b530236912d484391
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2022
ms.locfileid: "8723053"
---
# <a name="create-and-assign-advanced-rule-structures"></a>Creare e assegnare strutture di regole avanzate

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
