---
title: Creare un piano materiali per co-prodotti
description: Il pianificatore della produzione pianifica i fabbisogni di materiali per gli articoli che sono co-prodotti della formula.
author: ChristianRytt
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: deae0d7e0295aa02f5ad512f67e9e3d2148c2e33
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7578298"
---
# <a name="create-a-material-plan-for-co-products"></a>Creare un piano materiali per co-prodotti

[!include [banner](../../includes/banner.md)]

Il pianificatore della produzione pianifica i fabbisogni di materiali per gli articoli che sono co-prodotti della formula. La società di dati dimostrativi utilizzata per creare questa procedura è USP2.

## <a name="create-requirement-for-a-co-product"></a>Creare il fabbisogno per un co-prodotto

1. Vai a **Vendite e marketing \> Aree di lavoro \> Elaborazione e richiesta di informazioni ordini cliente**.
1. Selezionare **Nuovo**.
1. Selezionare **Ordine cliente**.
1. Digitare un valore nel campo **Conto cliente**.
    * Esempio: US-001  
1. Selezionare **OK**.
1. Nel campo **Numero articolo**, digitare un valore.
    * Esempio: P6003  
1. Nel campo **Quantità** immettere un numero.
    * Esempio: 50000  
1. Selezionare **Salva**.

## <a name="create-a-material-plan-for-co-products"></a>Creare un piano materiali per co-prodotti

1. Chiudere la pagina.
1. Chiudere la pagina.
1. Selezionare **Pianificazione generale**.
1. Nel campo **Piano** selezionare il pulsante a discesa per aprire la ricerca.
1. Nell'elenco fare clic sul collegamento nella riga selezionata.
    * Esempio: MasterPlan  
1. Selezionare **Esegui**.
1. Espandere o comprimere la sezione **Record da includere**.
1. Seleziona **Filtro**.
1. Nell'elenco selezionare la riga per **Campo** = *Numero articolo*.
1. Digitare un valore nel campo **Criteri**.
    * Esempio: P6003  
1. Selezionare **OK**.
1. Selezionare **OK**.
1. Selezionare **Ordini pianificati**.
1. Utilizzare il filtro rapido per trovare i record. Ad esempio, filtrare il campo **Numero articolo** con un valore "P6000".
    * Applicare un filtro in base all'articolo formula con co-prodotto dell'articolo per cui è stato creato un ordine cliente.  
1. Nell'elenco contrassegnare la riga selezionata.
    * Selezionare una delle righe restituite dal filtro.  
1. Nell'elenco fare clic sul collegamento nella riga selezionata.
1. Espandere la sezione **Pegging**.
1. Nell'elenco fare clic sul collegamento nella riga selezionata.
    * L'ordine pianificato viene sottoposto all'ordine cliente per il co-prodotto.  
1. Chiudere la pagina.

## <a name="create-a-second-requirement-for-a-co-product"></a>Creare un secondo fabbisogno per un co-prodotto

1. Vai a **Vendite e marketing \> Aree di lavoro \> Elaborazione e richiesta di informazioni ordini cliente**.
1. Selezionare **Nuovo**.
1. Selezionare **Ordine cliente**.
1. Digitare un valore nel campo **Conto cliente**.
    * Esempio: US-001  
1. Selezionare **OK**.
1. Nel campo **Numero articolo**, digitare un valore.
    * Esempio: P6003  
1. Nel campo **Quantità** immettere un numero.
    * Esempio: 50000  
1. Selezionare **Salva**.

## <a name="create-a-second-material-plan-for-co-products"></a>Creare un secondo piano materiali per co-prodotti

1. Nel campo **Piano** selezionare il pulsante a discesa per aprire la ricerca.
2. Nell'elenco fare clic sul collegamento nella riga selezionata.
    * Esempio: MasterPlan  
3. Selezionare **Esegui**.
4. Espandere o comprimere la sezione **Record da includere**.
5. Seleziona **Filtro**.
6. Nell'elenco selezionare la riga per **Campo** = *Numero articolo*.
7. Digitare un valore nel campo *Criteri*.
    * Esempio: P6003  
8. Selezionare **OK**.
9. Selezionare **OK**.
10. Selezionare **Ordini pianificati**.
11. Utilizzare il filtro rapido per trovare i record. Ad esempio, filtrare il campo **Numero articolo** con un valore "P6000".
    * Applicare un filtro in base all'articolo formula con co-prodotto dell'articolo per cui è stato creato un ordine cliente.  
12. Nell'elenco contrassegnare la riga selezionata.
    * Selezionare una delle righe restituite dal filtro.  
13. Nell'elenco fare clic sul collegamento nella riga selezionata.
14. Espandere o comprimere la sezione **Pegging**.
15. Nell'elenco fare clic sul collegamento nella riga selezionata.
    * L'ordine pianificato viene sottoposto all'ordine cliente per il co-prodotto.  
16. Chiudere la pagina.
17. Selezionare **Pianificazione generale**.
18. Andare a **Pianificazione generale \> Impostazioni \>Parametri di pianificazione generale**.
19. Selezionare *No* nel campo **Disattiva tutti i processi di pianificazione**.
20. Chiudere la pagina.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]