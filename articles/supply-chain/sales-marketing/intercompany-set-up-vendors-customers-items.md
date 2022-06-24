---
title: Impostare fornitori, clienti e articoli per il commercio interaziendale
description: In questo articolo viene illustrato come impostare fornitori, clienti e articoli per il commercio interaziendale
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: CustTable, VendTable, EcoResProductListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 4c928435a4e66832b09dbc805664934cfb1236be
ms.sourcegitcommit: b666289f5113d0a3fa2220fe337d5aacf07cbd92
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2022
ms.locfileid: "8945757"
---
# <a name="set-up-vendors-customers-and-items-for-intercompany-trade"></a>Impostare fornitori, clienti e articoli per il commercio interaziendale

[!include [banner](../../includes/banner.md)]

Per preparare l'organizzazione per il commercio interaziendale, è necessario definire i fornitori e clienti con cui si effettueranno scambi commerciali internamente. È quindi necessario associare questi fornitori e clienti con gli articoli che saranno acquistati o venduti.

1. Andare ad **Approvvigionamento \> Fornitori \> Tutti i fornitori**.
1. Selezionare il fornitore da definire come fornitore interaziendale.
1. Nel riquadro azioni, sella scheda **Generale**, selezionare **Interaziendale**.
1. Specificare i parametri interaziendali di impostazione per il conto fornitore. Questi parametri includono la persona giuridica del cliente e il conto, i criteri ordine cliente, i criteri ordine fornitore, il mapping di valore e criteri del contratto di vendita e di acquisto. È inoltre necessario specificare se utilizzare i valori di dati di base dal conto fornitore o dal conto cliente in un'altra persona giuridica.
1. Fai clic su **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.
1. Nella pagina elenco **Prodotti rilasciati** selezionare gli articoli da assegnare al fornitore, in modo che gli articoli sono disponibili per il commercio interaziendale. Per ogni articolo, aprire la pagina **Dettagli prodotto rilasciato**. Nella scheda **Acquisto** nel campo **Fornitore**, digitare il numero del fornitore.
1. Andare a **Contabilità clienti \> Clienti \> Tutti i clienti**.
1. Selezionare il cliente da definire come cliente interaziendale.
1. Nel riquadro azioni, sella scheda **Generale**, selezionare **Interaziendale**.
1. Specificare i parametri interaziendali di impostazione per il conto cliente. Questi parametri includono la persona giuridica del fornitore e il conto, i criteri ordine fornitore, i criteri ordine vendita, il mapping di valore e criteri del contratto di vendita e di acquisto. È inoltre necessario specificare se utilizzare i valori di dati di base dal conto cliente o dal conto fornitore in un'altra persona giuridica.
1. Al termine della configurazione dei parametri interaziendali, chiudi la pagina **Interaziendale** per tornare ai dettagli del cliente selezionato.
1. Espandi la Scheda dettaglio **Dettagli vari** e imposta **Crea ordini interaziendali** su *Sì*. Se vuoi consegnare gli ordini direttamente ai clienti, imposta **Consegna diretta** su *Sì*.

    > [!NOTE]
    > Se alcuni articoli vengono immagazzinati e consegnati dall'organizzazione ai clienti, potrebbe non essere opportuno creare ordini interaziendali in modo automatico indipendentemente dalla presenza di tali articoli in magazzino. Per disattivare la generazione automatica di ordini per articoli disponibili saltuariamente in magazzino, imposta **Crea ordini interaziendali** su *No*.

1. Se si desidera consentire la creazione indiretta di righe aggiuntive in un ordine cliente, imposta **Crea righe ordine indiretto** su *Sì*. In questo modo un utente potrà aggiungere righe all'ordine cliente originario dall'ordine cliente interaziendale.

> [!WARNING]
> Se si consente la creazione indiretta delle righe ordine, sarà automaticamente autorizzata qualsiasi aggiunta all'ordine cliente originario dall'ordine cliente interaziendale, che verrà quindi elaborata per il cliente e aggiunta all'ordine e alla fattura. Ciascun componente verrà elaborato tramite il cliente e aggiunto all'ordine e alla fattura. Inoltre, ogni documento incluso nella vendita viene stampato e registrato automaticamente. Gli utenti non vengono informati del componente aggiuntivo.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
