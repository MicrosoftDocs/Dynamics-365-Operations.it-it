---
title: Creare un piano interaziendale
description: In questa procedura viene illustrato come creare un piano interaziendale.
author: ChristianRytt
ms.date: 08/13/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ReqIntercompanyPlanningGroupSetup,  ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7ef1484e6925427454f819a5effdc911f762b48b
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7578274"
---
# <a name="create-an-intercompany-plan"></a>Creare un piano interaziendale

[!include [banner](../../includes/banner.md)]

In questa procedura viene illustrato come creare un piano interaziendale. La società di dati dimostrativi utilizzata per creare questa procedura è USMF.

## <a name="set-up-an-intercompany-planning-group"></a>Impostare un gruppo di pianificazione interaziendale

1. Nel **pannello di navigazione**,andare a **Moduli > Pianificazione generale > Impostazioni > Gruppi di pianificazione interaziendale**.
2. Utilizzare il filtro rapido per trovare i record. Ad esempio, applicare un filtro nel campo Nome con un valore "10".
3. Nell'elenco contrassegnare la riga selezionata.
4. Selezionare **Elimina**. Questo passaggio è necessario per abbreviare per l'esecuzione di pianificazione interaziendale.   La pianificazione interaziendale eseguirà la pianificazione generale in tutte le società in un gruppo di pianificazione, a partire dalla sequenza di programmazione inferiore.  
5. Selezionare **Sì**.
6. Chiudere la pagina.

## <a name="create-an-intercompany-master-plan"></a>Creare un piano generale interaziendale

1. Nel **pannello di navigazione**, andare a **Moduli > Pianificazione generale > Aree di lavoro > Pianificazione generale**.
2. Selezionare **Pianificazione generale interaziendale**.  
3. Nel campo **Gruppo di pianificazione interaziendale** selezionare il pulsante a discesa per aprire la ricerca.
4. Nell'elenco fare clic sul collegamento nella riga selezionata. Selezionare il gruppo di pianificazione interaziendale 10.  
5. Nel campo **Numero di iterazioni di pianificazione interaziendale**, immettere '2'. Il gruppo di pianificazione interaziendale 10 ha due membri. Per propagare i ritardi dalla società di origine (USMF) alla società cliente (DEMF), sarà necessario eseguire la pianificazione interaziendale in entrambe le società due volte. La prima iterazione propagherà la domanda e identificherà i ritardi nella società di origine (USMF). La seconda iterazione propagherà i ritardi da USMF a DEMF.  
6. Nel campo **Prima iterazione** selezionare "Rigenerazione".
7. Nel campo **Iterazioni successive** selezionare "Rigenerazione".
8. Nel campo **Numero di thread** immettere un numero. Questo rappresenta il numero di thread paralleli utilizzati per la pianificazione.  
9. Selezionare **OK**.

## <a name="view-the-result-of-the-plan"></a>Visualizzare il risultato del piano

1. Nel campo **Piano** selezionare il pulsante a discesa per aprire la ricerca.
2. Nell'elenco fare clic sul collegamento nella riga selezionata. Selezionare il collegamento per StaticPlan. È necessario essere  nella società USMF.  
3. Selezionare **Ordini pianificati**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]