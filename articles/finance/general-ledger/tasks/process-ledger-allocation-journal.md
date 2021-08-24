---
title: Elaborare giornale di registrazione allocazioni contabili
description: In questo argomento viene illustrato come elaborare una richiesta di allocazione in Dynamics 365 Finance.
author: aprilolson
ms.date: 07/26/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerAllocationRequest, LedgerJournalTable, LedgerJournalTransAllocation
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7d37b1a9869cc130786d0e8fde68184e04c881bad1f64c86943174213025db82
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6765670"
---
# <a name="process-ledger-allocation-journal"></a>Elaborare giornale di registrazione allocazioni contabili

[!include [banner](../../includes/banner.md)]

In questo argomento viene illustrato come elaborare una richiesta di allocazione. Utilizzare la pagina Elabora richiesta di allocazione per creare un giornale di registrazione allocazione che è possibile rivedere e approvare prima della registrazione in contabilità generale o registrare direttamente in contabilità generale. Prima di creare un giornale di registrazione allocazioni, è necessario che esista almeno una regola di allocazione contabile attiva. In questa attività viene utilizzata la società dimostrativa USMF.

1. Nel pannello di navigazione, andare a **Moduli > Contabilità generale > Allocazioni > Elabora richiesta di allocazione**.
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