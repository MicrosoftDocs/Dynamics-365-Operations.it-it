--- 
title: Gestire DBA per un modello di configurazione prodotto
description: L'esecuzione di questa procedura richiede un modello di configurazione prodotto esistente.
author: YuyuScheller
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: c017d7719ac6af43b0c8a162080bb753587df030
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="maintain-bom-for-a-product-configuration-model"></a>Gestire DBA per un modello di configurazione prodotto

[!include[task guide banner](../../includes/task-guide-banner.md)]

L'esecuzione di questa procedura richiede un modello di configurazione prodotto esistente. Il modello High end speaker della società di dati dimostrativi USMF è utilizzato per creare questa procedura.


## <a name="add-a-bom-line"></a>Aggiungere una riga DBA
1. Fare clic su Definizione modello di variante prodotto.
2. Fare clic su Modelli di configurazione prodotto.
3. Nell'elenco trovare e selezionare il record desiderato.
    * Selezionare High end speaker per questa procedura.  
4. Nell'elenco fare clic sul collegamento nella riga selezionata.
5. Espandere la sezione Righe DBA.
6. Scegliere Aggiungi.
7. Digitare un valore nel campo Nome.
8. Nel campo Descrizione digitare un valore.
9. Fare clic su Salva.

## <a name="add-bom-line-details"></a>Aggiungere i dettagli riga DBA
1. Fare clic su Dettagli riga DBA.
2. Nel campo Numero di articoli immettere o selezionare un valore.
    * Ad esempio, è possibile selezionare l'articolo M0055.  
    * Per ogni proprietà di riga DBA, è possibile scegliere se prende un valore fisso o viene sottoposta al mapping a un attributo.  
3. Selezionare la casella di controllo Imposta.
4. Selezionare Sì nel campo Calcolo.
    * Impostando la proprietà Calcolo su Sì, si garantisce che la riga DBA venga inclusa nei calcoli dei costi.  
5. Fare clic sulla scheda Impostazioni.
6. Selezionare la casella di controllo Imposta.
7. Nel campo Quantità immettere un numero.
    * Il campo Quantità determina la quantità dell'articolo che verrà incluso nella DBA. Ovviamente può essere utilizzato per il mapping di attributo.  
8. Fare clic sulla scheda Dimensione.
    * Verificare se le dimensioni prodotto sono attive e nel qual caso è necessario assegnare un valore o un attributo.  
9. Fare clic su OK.


