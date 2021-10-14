---
title: Ordini interaziendali e ordini di reso
description: Questo argomento spiega gli ordini interaziendali e gli ordini di reso
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 103225595e82bdedec6d97e5ebe5b61498377065
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548363"
---
# <a name="intercompany-orders-and-return-orders"></a>Ordini interaziendali e ordini di reso

[!include [banner](../../includes/banner.md)]

In questo argomento viene descritto come vengono creati e aggiornati gli ordini fornitore interaziendali, gli ordini cliente, gli ordini di reso, i contratti di acquisto e i contratti di vendita.

## <a name="about-intercompany-orders"></a>Informazioni sugli ordini interaziendali

Quando si crea un ordine cliente interaziendale, Microsoft Dynamics 365 Supply Chain Management genera automaticamente un ordine fornitore corrispondente. Analogamente, quando si crea un ordine fornitore interaziendale, viene generato automaticamente un ordine cliente corrispondente.

Quanto appena esposto è valido sia per ordini basati su transazioni a due (transazioni tra due società correlate), sia per la maggior parte degli ordini basati su transazioni a tre (transazioni interaziendali generate da un ordine relativo a un cliente esterno).

## <a name="intercompany-order-example"></a>Esempio di ordine interaziendale

Le società A e B sono correlate. La prima è un'affiliata di vendita, mentre la seconda è un'unità di distribuzione. La creazione automatica degli ordini cliente e fornitore interaziendali viene eseguita nei seguenti scenari:

- Quando la società A crea un ordine fornitore e il fornitore in questione corrisponde alla società B, nella società B viene creato automaticamente un ordine cliente interaziendale. La catena degli ordini basati su transazioni a due consisterà in un ordine fornitore nella società A e in un ordine cliente interaziendale nella società B.
- Quando la società B crea un ordine clienti e il cliente in questione corrisponde alla società A, nella società A viene creato automaticamente un ordine fornitore interaziendale. La catena degli ordini basati su transazioni a due consisterà in un ordine fornitore nella società B e in un ordine cliente interaziendale nella società A.
- Quando la società A crea un ordine cliente per un cliente esterno, è possibile che nella stessa società venga creato automaticamente un ordine fornitore che, a sua volta, determinerà la creazione automatica di un ordine cliente interaziendale nella società B. La catena degli ordini basati su transazione a tre consisterà in un ordine cliente nella società A, in un ordine fornitore nella società A e in un ordine cliente interaziendale nella società B.

## <a name="about-intercompany-return-orders"></a>Informazioni sugli ordini di reso interaziendali

I resi di articoli interaziendali possono essere gestiti in modo analogo a quelli normali. Tuttavia, con gli articoli interaziendali l'ordine di reso di un cliente esterno comporta la creazione di un ordine fornitore interaziendale, che a sua volta determina la creazione automatica di un ordine di reso cliente interaziendale. È possibile restituire un articolo interaziendale anche senza l'ordine di reso di un cliente esterno.

Gli ordini di reso interaziendali, analogamente ai normali ordini di reso, vengono inizializzati nella pagina **Crea ordine di reso**.

In Microsoft Dynamics 365 Supply Chain Management, i contratti di vendita e di acquisto interaziendali vengono aggiornati automaticamente in modo da riflettere un articolo reso. L'impegno di contratto di acquisto o di vendita per tale articolo viene rettificato automaticamente per riflettere le modifiche di quantità o di importo quando viene eseguito il reso di un articolo.

## <a name="intercompany-return-order-example"></a>Esempio di ordine di reso interaziendale

La società A crea un ordine fornitore collegato a un contratto di acquisto per un articolo interaziendale. Un ordine cliente interaziendale viene automaticamente creato nella società B collegata al contratto di vendita corrispondente. Il contratto di acquisto e il contratto di vendita sono correlati come contratti interaziendali.

La società A esegue il resto di un articolo interaziendale alla società B. La società B crea un ordine di reso per l'articolo e l'ordine di reso acquisti viene creato automaticamente nella società A. Gli impegni nel contratto di acquisto e nel contratto di vendita che sono collegati agli ordini originali vengono automaticamente rettificati in modo da riflettere la modifica alla quantità o all'importo.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
