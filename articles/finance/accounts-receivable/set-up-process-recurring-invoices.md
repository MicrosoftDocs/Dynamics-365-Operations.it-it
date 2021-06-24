---
title: Impostare ed elaborare fatture ricorrenti
description: Questo articolo illustra come impostare ed elaborare le fatture ricorrenti. È possibile utilizzare le fatture ricorrenti se è necessario fatturare ai clienti lo stesso importo su base regolare.
author: ShivamPandey-msft
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustInvoiceTemplate
audience: Application User
ms.reviewer: roschlom
ms.custom: 14011
ms.assetid: 9cc37003-adf1-413d-b2b2-2badcf512e3b
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 834dc64ce531fb614bc7836e0def16f27ecf5e18
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "6188640"
---
# <a name="set-up-and-process-recurring-invoices"></a>Impostare ed elaborare fatture ricorrenti

[!include [banner](../includes/banner.md)]

Questo articolo illustra come impostare ed elaborare le fatture ricorrenti. È possibile utilizzare le fatture ricorrenti se è necessario fatturare ai clienti lo stesso importo su base regolare.

## <a name="create-a-recurring-free-text-invoice-template"></a>Creare un modello di fattura ricorrente a testo libero

Per fatturare a carico di clienti per gli stessi servizi a intervalli regolari, è necessario definire un modello di fattura a testo libero che può essere riutilizzato per creare le fatture. In questo modello sono incluse le seguenti informazioni:

-   Informazioni di intestazione, ad esempio gruppi di imposte, termini e metodo di pagamento
-   Informazioni sulle righe, ad esempio la descrizione del servizio, i conti ricavi, il prezzo unitario e l'importo della fattura
-   Spese per spedizione o gestione
-   Distribuzioni contabili insieme alle informazioni sulle dimensioni finanziarie, ad esempio i centri di costo e Business Unit

In pratica, si crea una fattura completa e la si salva come modello. È possibile impostare i modelli utilizzando la pagina **Fatture ricorrenti**.

## <a name="assign-a-free-text-invoice-template-to-a-customer-and-enter-recurrence-details"></a>Assegnare un modello di fattura a testo libero a un cliente e immettere i dettagli di ricorrenza
Una volta creato il modello, è necessario assegnarlo ai clienti per i quali si desidera emettere la fattura. Inoltre, è necessario specificare quando e con quale frequenza verrà utilizzata la fattura. È possibile assegnare i modelli sulla scheda **Fattura** della pagina **Clienti**. Aggiungere il modello all'elenco e aggiornare le informazioni seguenti:

-   La data di inizio e, facoltativamente, la data di fine per la fatturazione ricorrente
-   La frequenza della fatturazione ricorrente (ad esempio ogni giorno o una volta al mese)
-   L'importo massimo di fatturazione (se queste informazioni sono necessarie)

Un cliente può avere più modelli con frequenze diverse.

## <a name="generate-the-recurring-invoices"></a>Generare le fatture ricorrenti
Nella pagina **Fatture ricorrenti** è presente un'attività che elabora modelli di fattura ricorrente. Specificare la data della fattura e il modello da cui generare le fatture. Le fatture verranno generate e verrà assegnato un singolo numero ID ricorrenza per ciascun gruppo di fatture elaborato.

## <a name="post-recurring-free-text-invoices"></a>Registrare fatture a testo libero ricorrenti

Dopo la generazione delle fatture ricorrenti, gli ID ricorrenza delle fatture vengono visualizzati in un'attività di registrazione nella pagina **Fatture ricorrenti**. È possibile visualizzare tutte le fatture per un ID ricorrenza facendo clic sul collegamento. Durante la revisione delle fatture per ID ricorrenza, è possibile eliminare singole fatture. Le impostazioni di ricorrenza del cliente saranno reimpostate per il modello, in modo da poterlo rigenerare successivamente. È possibile registrare una, molte o tutte le fatture per un ID ricorrenza. Se i flussi di lavoro sono attivati, è necessario fare clic su **Invia** per poter registrare le fatture.

## <a name="print-recurring-free-text-invoices"></a>Stampare fatture a testo libero ricorrenti

Dopo la registrazione delle fatture ricorrenti, è possibile stampare le fatture dalla pagina elenco delle fatture a testo libero. È possibile stampare le fatture selezionate oppure selezionare un intervallo di fatture da stampare.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]