---
title: Elaborare il giornale di registrazione allocazioni contabili
description: In questo articolo viene illustrato come elaborare una richiesta di allocazione in Dynamics 365 Finance.
author: aprilolson
ms.date: 07/26/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerAllocationRequest, LedgerJournalTable, LedgerJournalTransAllocation
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b86f8f5d090d624e812d9e7e6c0bc0212e5e9716
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8902431"
---
# <a name="process-ledger-allocation-journal"></a>Elaborare il giornale di registrazione allocazioni contabili

[!include [banner](../../includes/banner.md)]

In questo articolo viene illustrato come elaborare una richiesta di allocazione. Utilizzare la pagina Elabora richiesta di allocazione per creare un giornale di registrazione allocazione che è possibile rivedere e approvare prima della registrazione in contabilità generale o registrare direttamente in contabilità generale. Prima di creare un giornale di registrazione allocazioni, è necessario che esista almeno una regola di allocazione contabile attiva. In questa attività viene utilizzata la società dimostrativa USMF.

1. Nel pannello di navigazione, andare a **Contabilità generale > Allocazioni > Elabora richiesta di allocazione**.
2. Nel campo **Regola** selezionare il record desiderato nel menu a discesa.
3. Immettere una data nel campo **In data**.

    - Il valore di **In data** è molto importante quando la contabilità generale è l'origine dati per la regola. Questa data determina quali saldi contabili includere per l'allocazione.  
    - Nel campo **Origine zero** selezionare **Interrompi**. Questa operazione interromperà il processo di allocazione e visualizzerà un messaggio indicante che è selezionato un importo di origine pari a zero.  

4. Nel campo **Opzioni proposta**, selezionare **Solo proposta**. Selezionare **Solo proposta** per esaminare e facoltativamente approvare il risultato nei giornali di registrazione allocazioni prima della registrazione dell'allocazione nella contabilità generale.  
5. Immettere una data nel campo Data registrazione CoGe.
6. Selezionare **OK**.
7. Nel pannello di navigazione, andare a **Moduli > Contabilità generale > Allocazioni > Giornali di registrazione allocazioni**.
8. Selezionare **Righe**.
9. Selezionare **Registra**.
10. Selezionare **Registra**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
