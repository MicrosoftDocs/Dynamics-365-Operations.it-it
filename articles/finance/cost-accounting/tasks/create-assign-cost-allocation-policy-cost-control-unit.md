---
title: Creare e assegnare i criteri di allocazione costi a un'unità di controllo costi
description: Utilizzare questa procedura per creare e assegnare i criteri di allocazione costi e le regole corrispondenti a un'unità di controllo costi.
author: ShylaThompson
ms.date: 06/28/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CAMCostAccountingLedgerPolicyAssignment
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1cff10132e8007be885e9c69d97cf96c30d69f50
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5822857"
---
# <a name="create-and-assign-a-cost-allocation-policy-to-a-cost-control-unit"></a>Creare e assegnare i criteri di allocazione costi a un'unità di controllo costi

[!include [banner](../../includes/banner.md)]

Utilizzare questa procedura per creare e assegnare i criteri di allocazione costi e le regole corrispondenti a un'unità di controllo costi. Questa registrazione utilizza i dati dimostrativi della società USP2.


## <a name="create-a-policy"></a>Creare un criterio
1. Andare a Contabilità industriale > Criteri > Criteri di allocazione costi.
2. Fare clic su Nuovo.
3. Digitare un valore nel campo Nome criteri.
4. Nel campo Gerarchia dimensioni di oggetto di costo immettere o selezionare un valore.
    * Selezionare Organizzazione.  
5. Nel campo Dimensione statistica immettere o selezionare un valore.
6. Fare clic su Salva.

## <a name="create-allocation-rules"></a>Creare regole di allocazione
1. Fare clic su Nuovo.
2. Nell'elenco contrassegnare la riga selezionata.
3. Nel campo Nodo gerarchia dimensioni di oggetto di costo immettere o selezionare un valore.
4. Nel campo Comportamento costo selezionare "Totale".
5. Nel campo Base di allocazione immettere o selezionare un valore.
6. Fare clic su Nuovo.
7. Nell'elenco contrassegnare la riga selezionata.
8. Nel campo Nodo gerarchia dimensioni di oggetto di costo immettere o selezionare un valore.
9. Nel campo Comportamento costo selezionare "Totale".
10. Nel campo Base di allocazione immettere o selezionare un valore.
11. Fare clic su Nuovo.
12. Nell'elenco contrassegnare la riga selezionata.
13. Nel campo Nodo gerarchia dimensioni di oggetto di costo immettere o selezionare un valore.
14. Nel campo Comportamento costo selezionare "Totale".
15. Nel campo Base di allocazione immettere o selezionare un valore.
    * Continuare fino a quando non sono state create tutte le regole.  
16. Fare clic su Salva.

## <a name="assign-the-policy-to-a-cost-control-unit"></a>Assegnare i criteri a un'unità di controllo costi
1. Fare clic su Assegnazioni criteri per unità di controllo costi.
2. Fare clic su Nuovo.
3. Nell'elenco contrassegnare la riga selezionata.
4. Immettere una data nel campo Valido dalla data di registrazione.
    * Le regole hanno una data di validità. Un utente o il sistema può farle scadere se ne viene creata una nuova versione.  
5. Nel campo Unità di controllo costi immettere o selezionare un valore.
6. Fare clic su Salva.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]