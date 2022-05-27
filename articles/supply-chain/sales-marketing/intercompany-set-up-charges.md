---
title: Impostare addebiti sugli ordini interaziendali
description: In questo argomento viene illustrato come impostare addebiti sugli ordini interaziendali
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
ms.openlocfilehash: 27633e09bfcf41fbbe5449b0d3b5f283eaf7ee13
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2022
ms.locfileid: "8673664"
---
# <a name="set-up-charges-on-intercompany-orders"></a>Impostare addebiti sugli ordini interaziendali

[!include [banner](../../includes/banner.md)]

È possibile impostare gli addebiti da aggiungere agli ordini interaziendali. Quando un addebito viene aggiunto a un ordine cliente interaziendale, viene anche sincronizzato automaticamente con l'ordine fornitore interaziendale. In modo analogo se l'addebito viene aggiunto a un ordine fornitore interaziendale, viene automaticamente sincronizzato con l'ordine cliente interaziendale.

È inoltre possibile utilizzare gli addebiti per aggiungere un profitto a un ordine cliente interaziendale definendoli come percentuale interaziendale.

Quando si impostano gli addebiti da applicare agli ordini interaziendali, si attiva il calcolo del profitto interno per un ordine cliente interaziendale dall'importo netto dell'ordine cliente originario. Questo può essere utile se il fornitore interaziendale vende gli articoli al prezzo di costo. Nella seguente procedura viene descritto come impostare questa opzione per i clienti interaziendali. È possibile utilizzare la stessa procedura per i fornitori.

1. Andare a **Contabilità clienti \> Impostazione \> Addebiti \> Gruppi di addebiti cliente**.
1. Creare un gruppo di addebiti.
1. Andare a **Contabilità clienti \> Clienti \> Tutti i clienti**. Selezionare un collegamento conto cliente. Sul riquadro Azioni, selezionare la scheda **Cliente**, quindi la Scheda dettaglio **Ordine cliente**.
1. Selezionare **Modifica** nel riquadro azioni per consentire le modifiche al campo. Nel campo **Gruppo addebiti**, selezionare il gruppo di addebiti interaziendali impostato nel passaggio 2.
1. Accedere a **Contabilità clienti \> Impostazione \> Addebiti \> Addebiti automatici**.
1. Impostare gli addebiti completando i campi appropriati.
1. Nel campo **Relazione cliente**, selezionare il gruppo di addebiti interaziendali impostato nel passaggio 2.
1. Nella Scheda dettaglio **Righe**, nel campo **Categoria**, selezionare **Percentuale interaziendale**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
