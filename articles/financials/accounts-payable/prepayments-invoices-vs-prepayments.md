---
title: Fatture di pagamento anticipato e pagamenti anticipati a confronto
description: Questo argomento descrive e contrappone i due metodi utilizzati dalle organizzazioni per i pagamenti anticipati. Con un metodo si crea una fattura di pagamento anticipato associata a un ordine fornitore. Con l'altro metodo si creano i giustificativi del giornale di registrazione per pagamento anticipato mediante la creazione di scritture contabili e contrassegnando tali voci come giustificativi del giornale di registrazione per pagamento anticipato.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 10/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, PurchTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 15871
ms.assetid: a0bb5220-73d4-48ae-84d0-46a171c224fa
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c81045b72d15f4474d82040d7725740cff5eba91
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "310141"
---
# <a name="prepayment-invoices-vs-prepayments"></a>Fatture di pagamento anticipato e pagamenti anticipati a confronto

[!include [banner](../includes/banner.md)]

Questo argomento descrive e contrappone i due metodi utilizzati dalle organizzazioni per i pagamenti anticipati. Con un metodo si crea una fattura di pagamento anticipato associata a un ordine fornitore. Con l'altro metodo si creano i giustificativi del giornale di registrazione per pagamento anticipato mediante la creazione di scritture contabili e contrassegnando tali voci come giustificativi del giornale di registrazione per pagamento anticipato.

Le organizzazioni possono emettere pagamenti anticipati in favore dei fornitori di merci o servizi prima che la fornitura di tali merci o servizi sia stata completata. Due metodi possono essere utilizzati per emettere pagamenti anticipati ai fornitori. Per ridurre al minimo i rischi, è possibile tenere traccia dei pagamenti definendo il pagamento anticipato in relazione a un ordine fornitore. Per questo metodo è necessario creare una fattura di pagamento anticipato associata a un ordine fornitore. Questo metodo è denominato fatturazione di pagamento anticipato. Le organizzazioni che non desiderano tenere traccia dei pagamenti anticipati in modo sistematico o che non ricevono una fattura di pagamento anticipato dal proprio fornitore possono utilizzare i giustificativi giornale di registrazione per pagamento anticipato anziché il metodo di fatturazione di pagamento anticipato. È possibile creare i giustificativi del giornale di registrazione per pagamento anticipato mediante la creazione di inserimenti nel giornale di registrazione e contrassegnando tali voci come giustificativi del giornale di registrazione per pagamento anticipato. Con questo metodo non è possibile verificare quali pagamenti anticipati vengono effettuati a favore di un fornitore in relazione a un determinato ordine fornitore. Tuttavia, è possibile contrassegnare un pagamento anticipato registrato per la liquidazione in base a un ordine fornitore.

## <a name="when-to-use-prepayment-invoicing-vs-prepayments"></a>Quando utilizzare una fatturazione di pagamento anticipato rispetto ai pagamenti anticipati

| Fatturazione di pagamento anticipato                                                                | Pagamenti anticipati                                                              |
|-------------------------------------------------------------------------------------|--------------------------------------------------------------------------|
| Definire un valore di pagamento anticipato per un ordine fornitore.                                    | Nessun valore di pagamento anticipato è stato definito per un ordine fornitore.                    |
| Chiave: una fattura di pagamento anticipato e una fattura finale devono essere registrate.                       | Nessuna fattura di pagamento anticipato deve essere registrata.                                    |
| La passività per il pagamento anticipato viene registrata nel conto di pagamento anticipato, non nel conto della contabilità fornitori. | La passività per il pagamento anticipato viene registrata nel conto della contabilità fornitori.                  |
| Il saldo fornitore non corrisponde al valore di pagamento anticipato in tutto il processo.     | Il saldo fornitore corrisponde al valore di pagamento anticipato in tutto il processo. |
| La fatturazione di pagamento anticipato è disponibile solo in Contabilità fornitori.                         | I pagamenti anticipati sono disponibili in Contabilità fornitori e Contabilità clienti.    |

## <a name="overview-of-the-prepayment-process"></a>Panoramica del processo di pagamento anticipato
Le procedure contabili in molti paesi richiedono che i pagamenti anticipati da un cliente, o effettuati a favore di un fornitore, non vengano registrati nei conti riepilogativi abituali relativi al cliente o al fornitore. Tali pagamenti anticipati vanno invece registrati in conti CoGe specifici per i pagamenti anticipati. Quando si crea un ordine cliente o un ordine fornitore, viene emessa una fattura al cliente o dal fornitore. Una volta pagata la fattura, il pagamento anticipato e il giustificativo per il pagamento anticipato IVA vengono stornati dai conti CoGe per i pagamenti anticipati e gli importi in fattura vengono automaticamente registrati nei conti riepilogativi abituali. Per creare un pagamento anticipato, completare i passaggi che seguono.

1.  Impostare i profili di registrazione per i pagamenti anticipati.
2.  In Parametri contabilità clienti e Parametri contabilità fornitori di **Contabilità generale e IVA** selezionare il nuovo profilo di registrazione utilizzando il parametro **Profilo registrazione per giornale di registrazione pagamenti con pagamento anticipato**.
3.  Creare un giornale di registrazione pagamenti, quindi creare il nuovo pagamento.
4.  È possibile contrassegnare il pagamento come pagamento anticipato. Se un pagamento viene contrassegnato come pagamento anticipato, il pagamento viene registrato nei conti CoGe che vengono definiti nel profilo di registrazione impostato ai passaggi 1 e 2. Inoltre, se il pagamento viene contrassegnato come pagamento anticipato, le imposte vengono calcolate. Alcuni governi richiedono che le imposte siano pagate quando viene registrato un pagamento anticipato, anche in mancanza di fattura.
5.  Registrare il pagamento anticipato.
6.  Facoltativo: È possibile liquidare il pagamento anticipato a fronte dell'ordine fornitore o l'ordine cliente prima di creare la fattura. In un ordine cliente o un ordine fornitore, nel riquadro azioni, utilizzare **Liquida transazioni**.
7.  Dopo che il fornitore avrà fornito le merci o i servizi, registrare la fattura. Se il pagamento anticipato è stato liquidato a fronte dell'ordine fornitore o dell'ordine cliente al passaggio 6, il pagamento anticipato viene automaticamente liquidato a fronte della fattura creata. Se il pagamento anticipato non è stato liquidato a fronte dell'ordine fornitore o dell'ordine cliente, è possibile liquidarlo manualmente a fronte della fattura utilizzando **Liquida transazioni** nella pagina cliente o fornitore. L'importo del pagamento anticipato verrà quindi temporaneamente stornato dal conto CoGe di AP/AR. Inoltre, se le imposte sono state calcolate, vengono stornate, poiché la fattura include le imposte effettive.

## <a name="overview-of-the-prepayment-invoicing-process"></a>Panoramica del processo di fatturazione del pagamento anticipato
Le fatture di pagamento anticipato sono una normale procedura commerciale. Un fornitore emette le fatture di pagamento anticipato per richiedere un deposito sull'acquisto prima che l'ordine fornitore sia stato completato. Ad esempio, alcuni fornitori richiedono un pagamento anticipato di merci o servizi personalizzati. Se un fornitore emette una fattura che richiede il pagamento anticipato, è possibile utilizzare la funzionalità di fatturazione del pagamento anticipato. Un valore di pagamento anticipato può essere definito nell'ordine fornitore, una fattura di pagamento anticipato viene registrata e pagata, quindi la fattura di pagamento anticipato viene applicata alla fattura finale. Per creare un pagamento anticipato, completare i passaggi che seguono.

1.  L'addetto acquisti crea, conferma e invia un ordine fornitore per il quale il fornitore ha richiesto un pagamento anticipato. Il valore di pagamento anticipato viene definito nell'ordine fornitore come parte del contratto.
2.  Il fornitore invia una fattura di pagamento anticipato.
3.  Il coordinatore della contabilità fornitori registra la fattura di pagamento anticipato a fronte dell'ordine fornitore, quindi viene pagata la fattura del pagamento anticipato.
4.  Dopo che il fornitore ha consegnato le merci o fornito i servizi e sono state ricevute le relative fatture fornitore, il coordinatore della contabilità fornitori applica l'importo di pagamento anticipato già pagato a fronte della fattura.
5.  Il coordinatore della contabilità fornitori effettua il pagamento e liquida l'importo rimanente della fattura.




