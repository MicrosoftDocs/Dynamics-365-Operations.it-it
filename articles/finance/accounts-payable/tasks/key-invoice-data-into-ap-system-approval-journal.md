---
title: Inserire dati fattura nella contabilità fornitori tramite un giornale di approvazione
description: In questo argomento viene descritto come utilizzare il registro fatture per creare fatture e quindi per utilizzare il giornale di approvazione per aggiornare i conti spese.
author: abruer
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransInvoiceRegister, HcmWorkerLookUp, LedgerJournalTransApprove, LedgerJournalTransApproveFetchVouchers, LedgerTransVoucher
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fb690769a33f88e63ab8f54cec69a5e927fd324c
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2178534"
---
# <a name="key-invoice-data-into-accounts-payable-using-an-approval-journal"></a>Inserire dati fattura nella contabilità fornitori tramite un giornale di approvazione

[!include [task guide banner](../../includes/task-guide-banner.md)]

In questo argomento viene descritto come utilizzare il registro fatture per creare fatture e quindi per utilizzare il giornale di approvazione per aggiornare i conti spese.

## <a name="create-and-post-and-invoice"></a>Creare e registrare una fattura
1. Nel pannello di navigazione andare a **Moduli > Contabilità fornitori > Fatture > Registro fatture**.
2. Selezionare **Nuovo**.
3. Selezionare il nome del registro fatture che si desidera utilizzare.
4. Selezionare **Righe** per aprire il registro e immettere le righe di spesa.
5. Selezionare un fornitore. Ad esempio, immettere o selezionare `US-104`.
6. Digitare un valore nel campo **Fattura**.
7. Digitare un valore nel campo **Descrizione**
8. Nel campo **Credito** immettere un numero.
9. Nel campo **Approvato da**, selezionare un approvatore dal menu a discesa.
10. Selezionare **Registra**.

## <a name="approve-an-invoice"></a>Approvare una fattura
1. Nel pannello di navigazione andare a **Moduli > Contabilità fornitori > Fatture > Approvazione fattura**.
2. Selezionare **Nuovo**.
3. Selezionare il nome del giornale di approvazione fatture che si desidera utilizzare.
4. Selezionare **Righe** per visualizzare una pagina in cui sarà possibile selezionare le fatture che si desidera approvare.
5. Selezionare **Trova giustificativi** per visualizzare tutte le fatture pronte per l'approvazione.
6. Contrassegnare la fattura creata, quindi fare clic su **Seleziona**. I giustificativi selezionati in precedenza vengono spostati in questo elenco dopo che sono stati selezionati.  
7. Selezionare **OK**.
8. Selezionare il campo **Numero di conto** per aggiungere un conto spese alla fattura.
9. Immettere un numero di conto e uscire dal campo. Ad esempio, immettere `600120`.
10. Selezionare **Registra**.
11. Selezionare **Giustificativo** per visualizzare le voci registrate. Il conto di approvazione fatture in sospeso viene stornato e sostituito con il conto spese effettivo.  

