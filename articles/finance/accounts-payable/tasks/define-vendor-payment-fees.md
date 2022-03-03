---
title: Definire commissioni pagamento fornitore
description: Impostare commissione pagamento fornitore.
author: abruer
ms.date: 02/11/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendPaymFee, VendPaymModeFee, BankAccountTableLookUp
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c490bb4d15fa03742b12f337046f26976ab70d29
ms.sourcegitcommit: 3105642fca2392edef574b60b4748a82cda0a386
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2022
ms.locfileid: "8109833"
---
# <a name="define-vendor-payment-fees"></a>Definire commissioni pagamento fornitore

[!include [banner](../../includes/banner.md)]

Impostare commissione pagamento fornitore. In questa attività viene utilizzata la società dimostrativa USMF.

1. Andare a **Contabilità fornitori > Impostazione pagamenti > Commissione di pagamento**.
2. Fare clic su **Nuovo**.
3. Digitare un valore nel campo **ID commissione**.
    * L'**ID della commissione** deve descrivere quando la commissione verrà utilizzata, ad esempio "EFT_Fee.  
4. Digitare un valore nel campo **Nome**.
5. Digitare un valore nel campo **Descrizione commissione**.
    * Aggiungere una descrizione per fornire più dettagli riguardo a quando la commissione viene imposta.  
6. Nel campo **Spesa**, selezionare **Fornitore** o **Contabilità generale**.
    * L'opzione **Contabilità generale** è utilizzata quando la commissione verrà considerata per l'organizzazione. L'opzione **Fornitore** viene utilizzata quando la commissione verrà imposta al fornitore.  
7. Immettere un conto principale per dove la commissione verrà considerata come spesa.
    * Questa opzione è disponibile solo quando si seleziona **Contabilità generale** come opzione di **addebito**.  
8. Selezionare il giornale di registrazione in cui la commissione può essere utilizzata. 
    * Per una commissione di pagamento fornitore, verrà selezionato il giornale di registrazione "Esborso fornitore".  
9. Fare clic su **Salva**.
10. Fare clic su **Impostazione commissione pagamento**.
    * Procedere all'**impostazione della commissione di pagamento** per definire quando la commissione dovrà essere impostata come valore predefinito nel giornale di registrazione selezionato.  
11. Selezionare **Tabella**, **Gruppo** o **Tutti**.
    * L'opzione **Tabella** viene utilizzata per selezionare un singolo conto bancario, l'opzione **Gruppo** viene utilizzata per selezionare un gruppo bancario e **Tutti** per utilizzare l'impostazione della commissione per tutti i conti bancari.  
12. Selezionare un gruppo bancario o un conto bancario.
    * La ricerca indicherà il gruppo bancario se è stato selezionato **Gruppo** e indicherà i conti bancari se è stato selezionato **Tabella**.  
13. Selezionare il metodo di pagamento per quando verrà imposta la commissione.
14. Selezionare la **specifica di pagamento** per il metodo di pagamento selezionato.
    * La **specifica di pagamento** viene utilizzata con i metodi di trasferimento fondi attraverso sistemi di pagamento elettronici.  
15. Selezionare se la commissione è una percentuale, un importo o un intervallo.
16. Immettere la percentuale o l'importo della commissione.
    * Se la **commissione** è una percentuale, immettere la percentuale. Se la **commissione** è un importo, immettere l'importo della commissione. Se la **commissione** è un intervallo, utilizzare la scheda **Intervallo** per definire le commissioni a livelli.  
17. Nel campo **Valuta commissioni** selezionare la valuta in cui verrà imposta la commissione.
    * Questa valuta è per la commissione. La valuta di pagamento viene utilizzata per definire quando la regola della commissione deve essere imposta in base alla valuta del pagamento. Ad esempio, la banca può addebitare una commissione quando un pagamento viene effettuato in euro, ma a tutti gli altri pagamenti non viene imposta una commissione.  
18. Fare clic su **Salva**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
