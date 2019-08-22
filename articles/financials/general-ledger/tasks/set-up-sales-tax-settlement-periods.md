---
title: Imposta i periodi di liquidazione IVA
description: I periodi di liquidazione IVA contengono informazioni sugli intervalli periodici in cui l'IVA deve essere dichiarata e pagata.
author: twheeloc
manager: AnnBe
ms.date: 08/05/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxPeriod
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8304d9e8997a5d31740ee1203aa4bf0603014056
ms.sourcegitcommit: d0fa8d0140fa81029527edb317623c1a7737c593
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2019
ms.locfileid: "1862990"
---
# <a name="set-up-sales-tax-settlement-periods"></a>Imposta i periodi di liquidazione IVA

[!include [task guide banner](../../includes/task-guide-banner.md)]

I periodi di liquidazione IVA contengono informazioni sugli intervalli periodici in cui l'IVA deve essere dichiarata e pagata. Un processo di liquidazione può essere eseguito per un periodo di liquidazione per un intervallo di date specifico. Tutti i codici IVA associati al periodo di liquidazione verranno liquidati. A seconda dell'impostazione dell'ufficio IVA correlato, la soggettività tributaria viene registrata in un conto fornitore o CoGe.



In questa attività viene utilizzata la società dimostrativa USMF.



1. Andare a Imposta > Imposte indirette > IVA > Periodi liquidazione IVA.
2. Fare clic su Nuovo.
3. Nel campo Periodo di liquidazione digitare un calore.
4. Nel campo Descrizione digitare un valore.
5. Nel campo Ufficio selezionare l'ufficio IVA che riceve i report e i pagamenti creati per il periodo di liquidazione.
6. Trovare e selezionare il record desiderato nell'elenco.
7. Nell'elenco fare clic sul collegamento nella riga selezionata.
8. Nel campo Termini di pagamento fare clic sul pulsante a discesa per aprire la ricerca.
    * L'ufficio IVA relativo può essere impostato come fornitore e la liquidazione VAT creerà una fattura fornitore aperta. Termini di pagamento definisce la data di scadenza della fattura fornitore aperta.  
9. Nell'elenco trovare e selezionare il record desiderato.
10. Nell'elenco fare clic sul collegamento nella riga selezionata.
11. Selezionare un tipo per gli intervalli del periodo di liquidazione.
12. Immettere il numero di unità dell'intervallo periodico per periodo. Ad esempio, un trimestre ha 3 mesi.
13. Selezionare o deselezionare la casella di controllo Utilizza elaborazione batch per liquidazione IVA.
    * Il processo di liquidazione per il periodo di liquidazione può essere elaborato come processo batch in background. Si consigliano tantissime transazioni IVA all'interno di un intervallo periodico.  
    > [!NOTE]
    > Attualmente questo non è supportato in Austria, in Belgio, Spagna, in Italia, in Giappone e nei Paesi Bassi.
14. Selezionare o deselezionare la casella di controllo Impedisci generazione transazioni contropartita fiscale.
    * Per impostazione predefinita, il sistema genera transazioni di contropartita fiscale durante il processo di liquidazione, la cui causa può creare problemi in caso di un numero elevato di transazioni fiscali in un determinato intervallo periodico. Selezionare questa casella di controllo per impedire la generazione di transazioni di contropartita fiscale.
15. Espandere la scheda Intervalli periodici.
16. Scegliere Aggiungi.
17. Nell'elenco contrassegnare la riga selezionata.
18. Immettere una data nel campo Dal.
19. Nel campo Data finale immettere una data.
20. Fare clic su Nuovo intervallo periodico.
    * Una volta che il primo intervallo periodico è stato immesso, i nuovi periodi possono essere creati automaticamente. È possibile tornare e aggiungere nuovi intervalli periodici in base alle esigenze.  
21. Chiudere la pagina.

