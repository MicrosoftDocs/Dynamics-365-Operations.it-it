---
title: Definire le commissioni di pagamento cliente
description: Creare le commissioni di pagamento per i pagamenti cliente.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPaymFee, CustPaymModeFee, BankAccountTableLookUp
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 99201039c30cd9d8e900662cd9e33b0a5db8e55a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "5012116"
---
# <a name="establish-customer-payment-fees"></a>Definire le commissioni di pagamento cliente

[!include [banner](../../includes/banner.md)]

Creare le commissioni di pagamento per i pagamenti cliente.

In questa attività viene utilizzata la società dimostrativa USMF.

1. Nel **pannello di navigazione** andare a **Moduli > Crediti e riscossioni > Impostazione pagamenti > Commissione pagamento**.
2. Fare clic su **Nuovo**.
3. Nel campo **ID commissione**, immettere un ID della commissione. L'ID della commissione viene visualizzato nei giornali di registrazione pagamenti, quindi fare in modo che sia descrittivo per comprendere la commissione imposta.  
4. Nel campo **Nome** immettere un nome.
5. Nel campo **Descrizione commissione** immettere una descrizione per la commissione.
6. Nel campo **Addebito**, selezionare se la commissione verrà addebitata al cliente o a un conto CoGe. Se la commissione viene imposta al cliente, selezionare Cliente. Se la commissione verrà imposta all'organizzazione come spesa, selezionare Contabilità generale. Per l'attività, selezionare Cliente.  
7. Nel campo **Tipo giornale di registrazione**, selezionare il tipo di giornale di registrazione che può utilizzare questa commissione di pagamento. Se queste commissioni sono utilizzate per i pagamenti cliente, il tipo di giornale di registrazione sarà probabilmente Pagamento cliente.  
8. Fare clic su **Salva**.
9. Fare clic su **Impostazione commissione pagamento**. Impostazione commissione pagamento viene utilizzata per definire i criteri per quando la commissione di pagamento verrà imposta.  Ad esempio, è possibile definire che la commissione verrà calcolata se il conto bancario è USMF OPER e il metodo di pagamento è assegno.  
10. Nel campo **Raggruppamenti** selezionare Tabella, Gruppo o Tutti per definire i conti bancari a cui verrà imposta la commissione. Se si seleziona Tutti, la commissione potrà essere imposta a tutti i conti bancari.  Se si seleziona Tabella, la commissione potrà essere imposta solo al conto bancario selezionato. Se si seleziona Gruppo, la commissione potrà essere imposta solo ai conti bancari nel gruppo bancario selezionato.  
11. Nel campo **Relazione bancaria**, selezionare un gruppo bancario o un conto bancario. Se è stato selezionato Tabella, la ricerca consentirà di visualizzare i conti bancari. Se è stato selezionato Gruppo, la ricerca consentirà di visualizzare i gruppi bancari.  
12. Nell'elenco fare clic sul collegamento nella riga selezionata.
13. Nel campo **Metodo di pagamento**, selezionare il metodo di pagamento per il quale la commissione verrà valutata. Ad esempio, è possibile imporre una commissione ai clienti se inviano i pagamenti come assegno, anziché come pagamento elettronico.  
14. Nell'elenco trovare e selezionare il record desiderato.
15. Se pertinente, nel campo **Valuta pagamento**, immettere una valuta per il pagamento. La valuta del pagamento viene utilizzata come criterio aggiuntivo per indicare se la commissione verrà imposta.  Ad esempio, la banca può addebitare una commissione aggiuntiva per i pagamenti ricevuti nella valuta EUR, poiché trattano in genere solo nella valuta EUR.  
16. Selezionare se la commissione sarà una percentuale, un importo o un intervallo.
17. Nel campo **Percentuale/Importo**, immettere la percentuale o l'importo della commissione. Se il campo Percentuale/Importo è Percentuale, il valore immesso in questo campo sarà una percentuale. Se il campo Percentuale/Importo è Importo, il valore immesso in questo campo sarà un importo. Se il campo Percentuale/Importo è Intervallo, utilizzare la scheda Intervallo per definire i livelli.  
18. Nel campo **Valuta commissioni**, selezionare la valuta della commissione. Si tratta della valuta in cui la commissione verrà creata.  
19. Fare clic su **Salva**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]