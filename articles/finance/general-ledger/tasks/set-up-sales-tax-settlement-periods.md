---
title: Impostare i periodi di liquidazione IVA
description: In questo argomento viene illustrato come impostare periodi di liquidazione IVA in Dynamics 365 Finance.
author: twheeloc
ms.date: 08/05/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxPeriod
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1f57cd2b5b0f8f86d67500086403c5f484a263f76601453c00f59ede901b01a8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6732959"
---
# <a name="set-up-sales-tax-settlement-periods"></a>Impostare i periodi di liquidazione IVA

[!include [banner](../../includes/banner.md)]

In questo argomento viene illustrato come impostare periodi di liquidazione IVA. I periodi di liquidazione IVA contengono informazioni sugli intervalli periodici in cui l'IVA deve essere dichiarata e pagata. Un processo di liquidazione può essere eseguito per un periodo di liquidazione per un intervallo di date specifico. Tutti i codici IVA associati al periodo di liquidazione verranno liquidati. A seconda dell'impostazione dell'ufficio IVA correlato, la soggettività tributaria viene registrata in un conto fornitore o CoGe.

In questa attività viene utilizzata la società dimostrativa USMF.

1. Nel pannello di navigazione andare a **Moduli > Imposta > Imposte indirette > IVA > Periodi liquidazione IVA**.
2. Selezionare **Nuovo**.
3. Nel campo **Periodo di liquidazione** digitare un calore.
4. Digitare un valore nel campo **Descrizione**
5. Nel campo **Ufficio** selezionare l'ufficio IVA che riceve i report e i pagamenti creati per il periodo di liquidazione.
6. Nell'elenco trovare e selezionare il record desiderato.
7. Nel campo **Termini di pagamento** fare clic sul record desiderato del menu a discesa. L'ufficio IVA relativo può essere impostato come fornitore e la liquidazione VAT creerà una fattura fornitore aperta. Termini di pagamento definisce la data di scadenza della fattura fornitore aperta.  
8. Selezionare un tipo per gli intervalli del periodo di liquidazione.
9. Immettere il numero di unità dell'intervallo periodico per periodo. Ad esempio, un trimestre ha 3 mesi.
10. Selezionare o deselezionare la casella di controllo **Utilizza elaborazione batch per liquidazione IVA**. Il processo di liquidazione per il periodo di liquidazione può essere elaborato come processo batch in background. Si consigliano tantissime transazioni IVA all'interno di un intervallo periodico.
11. Selezionare o deselezionare la casella di controllo **Impedisci generazione transazioni contropartita fiscale**. Per impostazione predefinita, il sistema genera transazioni di contropartita fiscale durante il processo di liquidazione, la cui causa può creare problemi in caso di un numero elevato di transazioni fiscali in un determinato intervallo periodico. Selezionare questa casella di controllo per impedire la generazione di transazioni di contropartita fiscale.
12. Espandere la scheda **Intervalli periodici**.
13. Selezionare **Aggiungi**.
14. Immettere una data nella nuova riga del campo **Dal**.
15. Nel campo **Al** immettere una data.
16. Selezionare **Nuovo intervallo periodico**. Una volta che il primo intervallo periodico è stato immesso, i nuovi periodi possono essere creati automaticamente. È possibile tornare e aggiungere nuovi intervalli periodici in base alle esigenze.  
17. Chiudere la pagina.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
