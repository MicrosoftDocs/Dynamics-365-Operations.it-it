---
title: Inserire dati fattura nella contabilità fornitori tramite un giornale di approvazione
description: In questo argomento viene descritto come utilizzare il registro fatture per creare fatture e quindi per utilizzare il giornale di approvazione per aggiornare i conti spese.
author: abruer
ms.date: 02/11/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransInvoiceRegister, HcmWorkerLookUp, LedgerJournalTransApprove, LedgerJournalTransApproveFetchVouchers, LedgerTransVoucher
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0ce66a4b92f26bcec0849accad3878aef2b2f658
ms.sourcegitcommit: 3105642fca2392edef574b60b4748a82cda0a386
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2022
ms.locfileid: "8109660"
---
# <a name="key-invoice-data-into-accounts-payable-using-an-approval-journal"></a>Inserire dati fattura nella contabilità fornitori tramite un giornale di approvazione

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
