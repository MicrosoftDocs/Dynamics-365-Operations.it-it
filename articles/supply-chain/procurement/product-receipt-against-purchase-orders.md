---
title: Entrata prodotti e ordini fornitore
description: In questo argomento vengono descritte le varie opzioni per la registrazione dei prodotti quando vengono ricevuti.
author: FrankDahl
manager: AnnBe
ms.date: 11/15/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 93113
ms.assetid: d4ec3e86-fce2-4546-911b-e0acf64c8887
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fea28da19c0aa1e9083091d0693404e0d8cb173c
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1554346"
---
# <a name="product-receipt-against-purchase-orders"></a>Entrata prodotti e ordini fornitore

[!include [banner](../includes/banner.md)]

[!include [retail name](../includes/retail-name.md)]

In questo argomento vengono descritte le varie opzioni per la registrazione dei prodotti quando vengono ricevuti.

L'entrata prodotti è il processo di registrazione che i prodotti ordinati sono stati ricevuti, in modo che le righe di ordine fornitore possono quindi essere elaborate per la fatturazione. In alcuni casi, i prodotti attraversano la preregistrazione, in cui informazioni aggiuntive da parte del fornitore vengono registrate prima del ricevimento dei prodotti. All'arrivo dei prodotti, sono prima contrassegnati come **Registrato**. I prodotti quindi prima possono attraversare processi aggiuntivi, quali la gestione della qualità, prima di essere contrassegnati come **Ricevuto**.

## <a name="preregistration-asn"></a>Preregistrazione (ASN)
I fornitori potrebbero condividere informazioni sui prodotti che verranno consegnati. In questo caso, è possibile "preregistrare" i prodotti per registrare queste informazioni prima che il ricevimento dei prodotti. Preregistrando i prodotti, si riduce la quantità di lavoro che viene richiesto durante l'entrata e la registrazione degli articoli. I fornitori possono fornire informazioni sul prodotto elettronicamente tramite un Advance Shipment Notice (ASN) che viene quindi automaticamente registrato nel sistema. Le informazioni nell'ASN includono la quantità di prodotti che verranno consegnati e la data di spedizione. L'ASN può anche includere informazioni quali numeri di serie o batch. Si verifica la registrazione dell'ASN nel modulo **Gestione trasporto**.

## <a name="registration"></a>Registrazione
La registrazione entrata prodotti si verifica spesso alle banchine di entrata di un magazzino. Viene eseguita utilizzando un dispositivo palmare o tramite giornali di registrazione arrivi. In alternativa, è possibile registrare manualmente l'entrata prodotti utilizzando l'azione **Registrazione** nella pagina **Ordine fornitore**. In entrambi i casi, i prodotti sono contrassegnati come **Registrato**. Si noti che i prodotti non sono ancora contrassegnati come **Ricevuto**.  

I prodotti che vengono ricevuti in magazzino possono essere sottoposti a ispezione di controllo qualità prima dello stoccaggio in magazzino. Ordini di controllo qualità o ordini di quarantena possono essere utilizzati per eseguire l'ispezione di controllo qualità. Se vengono utilizzati ordini di controllo qualità, è possibile configurare il processo per bloccare temporaneamente i prodotti mediante una prenotazione mentre ispezionati. Se vengono utilizzati gli ordini di quarantena, prodotti vengono spostati in un altro magazzino per l'ispezione. Questo magazzino è noto come magazzino di quarantena. In entrambi i processi di ispezione di controllo di qualità, alcune delle merci potrebbero essere scartate, perché non conformi alle aspettative di qualità o perché il controllo di qualità implica test distruttivi di un campione del prodotto.

## <a name="product-receipt"></a>Entrata prodotti
Molto spesso, l'azione **Entrata prodotti** della pagina **Ordini fornitore** viene utilizzata per contrassegnare i prodotti come **Ricevuto** nell'ordine fornitore. La pagina **Registrazione entrata prodotti** include diverse opzioni per la quantità che viene considerata come ricevuta. Ad esempio, è possibile impostare il campo **Quantità** su **Quantità ordinata** o **Quantità in Ricevi ora**. In alternativa, se è stato utilizzato un processo di arrivo in magazzino, spesso il campo viene impostato su **Quantità registrata**. È possibile modificare le quantità in ciascuna riga dell'ordine che verrà contrassegnata come **Ricevuto**, per tenere conto di eventuali discrepanze, come limite minimo e massimo di fornitura. Durante l'entrata prodotti, è necessario specificare un identificatore di entrata prodotti, che è in genere un riferimento al documento di trasporto del fornitore. Questo identificatore è necessario per la contabilità, poiché consente verifiche o controlli di documenti di trasporto rispetto a ciò che è stato ricevuto e le scorte o le spese contabilizzate.  

È possibile creare PO per prodotti non destinati come magazzino ma che sono considerati una spesa. Questa categoria include le righe dell'ordine in cui i prodotti sono contrassegnati come **Non stoccati** dal relativo gruppo di modelli inventariali e anche le righe che utilizzano le categorie di approvvigionamento. In questo caso, gli articoli potrebbero non essere sottoposti a registrazione degli arrivi e l'entrata in magazzino. Invece, l'azione **Entrata prodotti** viene utilizzata per registrare l'entrata direttamente nell'ordine fornitore e l'entrata dipende dalla quantità ordinata, non una quantità registrata.  

È possibile creare righe di ordine fornitore dove l'opzione **Nuovo cespite** è attivata. Questa opzione indica che l'acquisto deve essere considerato un cespite invece di magazzino. In questo caso, le regole di determinazione dei cespiti che sono state configurate determinano se l'acquisto del prodotto o categoria supera le soglie specifiche, pertanto deve essere conteggiato come un cespite e essere sottposto alla gestione cespiti. Gli acquisti possono anche essere effettuati rispetto a un cespite esistente. In questo caso, l'importo viene rettificato in base alle esigenze.  

È possibile selezionare più ordini ed elaborare l'entrata per tutti gli ordini contemporaneamente. Questo approccio non viene utilizzato molto spesso, ma si consiglia di utilizzarlo se un fornitore ha consolidato le spedizioni in un singolo carico. Durante l'entrata prodotti sugli acquisti, vi è una funzione per eseguire gli aggiornamenti riepilogativi. Gli aggiornamenti riepilogativi consentono di registrare un singolo documento di trasporto del fornitore per più di un ordine fornitore.  

I PO potrebbero essere creati da un ordine cliente dove l'opzione **Consegna diretta** è stata selezionata. Quando si utilizza la consegna diretta, i prodotti non arrivano in magazzino ma vengono spediti direttamente dal fornitore al cliente. In questo caso, l'entrata è in genere registrata direttamente nell'ordine fornitore. L'entrata può essere eseguita automaticamente, ad esempio mediante EDI (electronic data interchange) con il fornitore. In alternativa, se l'ordine fornitore è interaziendale, Microsoft Dynamics 365 for Finance and Operations consente di automatizzare l'entrata sull'ordine cliente interaziendale quando si verifica la spedizione. Quando si utilizza la consegna diretta, pi rodotti sono ancora contabilizzati come magazzino, anche se non arrivano fisicamente nel magazzino. Pertanto, quando l'entrata prodotti è registrata nell'ordine fornitore, l'ordine cliente viene automaticamente aggiornato con un documento di trasporto, in modo che la variazione generale nel magazzino è 0 (zero). In scenari di consegna diretta, è opportuno non utilizzare la preregistrazione. Se si utilizzano magazzini che sono abilitati per la gestione magazzino, è possibile evitare il requisito per la registrazione di targa specificando invece un magazzino virtuale. Specificare il magazzino nel campo **Magazzino consegna diretta** sul prodotto. 

Dopo che l'entrata prodotti è stato elaborata nell'ordine fornitore, lo stato dell'ordine è impostato su **Ricevuto** per indicare che la fattura può essere elaborata per l'ordine. È possibile esaminare i dettagli sui prodotti che sono già stati ricevuti utilizzando la pagina **Giornali di registrazione entrata prodotti**.  

È possibile accedere a questa pagina dal gruppo di azioni **Ricevuta** nella pagina **Ordine fornitore**. Le informazioni nei giornali di registrazione includono informazioni dettagliate sulle dimensioni, quantità e date.

<a name="additional-resources"></a>Risorse aggiuntive
--------

[Panoramica dell'ordine fornitore](purchase-order-overview.md)

[Creazione ordine fornitore](purchase-order-creation.md)

[Approvazione e conferma di un ordine fornitore](purchase-order-approval-confirmation.md)

[Panoramica delle fatture fornitore](../../financials/accounts-payable/vendor-invoices-overview.md)



