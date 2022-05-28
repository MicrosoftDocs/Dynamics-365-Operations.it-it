---
title: Fatture di pagamento anticipato e pagamenti anticipati a confronto
description: Questo argomento descrive e contrappone i due metodi utilizzati dalle organizzazioni per i pagamenti anticipati.
author: abruer
ms.date: 10/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, PurchTable
audience: Application User
ms.reviewer: twheeloc
ms.custom: 15871
ms.assetid: a0bb5220-73d4-48ae-84d0-46a171c224fa
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f05f1d8d2a1fb454f3f227d2cc8138f2b779ff87
ms.sourcegitcommit: 1d2eeacad11c28889681504cdc509c90e3e8ea86
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2022
ms.locfileid: "8716327"
---
# <a name="prepayment-invoices-vs-prepayments"></a>Fatture di pagamento anticipato e pagamenti anticipati a confronto

[!include [banner](../includes/banner.md)]

Questo argomento descrive e contrappone i due metodi utilizzati dalle organizzazioni per i pagamenti anticipati. Un metodo crea una fattura di pagamento anticipato che è associata a un ordine fornitore. L'altro metodo crea i giustificativi del giornale di registrazione per pagamento anticipato mediante la creazione di scritture contabili e contrassegnando tali voci come giustificativi del giornale di registrazione per pagamento anticipato.

Le organizzazioni possono emettere pagamenti anticipati in favore dei fornitori di merci o servizi prima che la fornitura di tali merci o servizi sia stata completata. Due metodi possono essere utilizzati per emettere pagamenti anticipati ai fornitori. Per ridurre al minimo i rischi, è possibile tenere traccia dei pagamenti definendo il pagamento anticipato in relazione a un ordine fornitore. Per questo metodo è necessario creare una fattura di pagamento anticipato associata a un ordine fornitore. Questo metodo è denominato fatturazione di pagamento anticipato. Le organizzazioni che non desiderano tenere traccia dei pagamenti anticipati in modo sistematico o che non ricevono una fattura di pagamento anticipato dal proprio fornitore possono utilizzare i giustificativi giornale di registrazione per pagamento anticipato anziché il metodo di fatturazione di pagamento anticipato. È possibile creare i giustificativi del giornale di registrazione per pagamento anticipato mediante la creazione di inserimenti nel giornale di registrazione e contrassegnando tali voci come giustificativi del giornale di registrazione per pagamento anticipato. Con questo metodo non è possibile verificare quali pagamenti anticipati vengono effettuati a favore di un fornitore in relazione a un determinato ordine fornitore. Tuttavia, è possibile contrassegnare un pagamento anticipato registrato per la liquidazione in base a un ordine fornitore.

## <a name="when-to-use-prepayment-invoicing-vs-prepayments"></a>Quando utilizzare una fatturazione di pagamento anticipato rispetto ai pagamenti anticipati

| Fatturazione di pagamento anticipato                                                                | Pagamenti anticipati                                                              |
|-------------------------------------------------------------------------------------|--------------------------------------------------------------------------|
| Definire un valore di pagamento anticipato per un ordine fornitore.                                    | Nessun valore di pagamento anticipato è stato definito per un ordine fornitore.                    |
| Una fattura di pagamento anticipato e una fattura finale devono essere registrate.                       | Nessuna fattura di pagamento anticipato deve essere registrata.                                    |
| La passività per il pagamento anticipato viene registrata nel conto di pagamento anticipato, non nel conto della contabilità fornitori. | La passività per il pagamento anticipato viene registrata nel conto della contabilità fornitori.                  |
| Il saldo fornitore non corrisponde al valore di pagamento anticipato in tutto il processo.     | Il saldo fornitore corrisponde al valore di pagamento anticipato in tutto il processo. |
| La fatturazione di pagamento anticipato è disponibile solo in Contabilità fornitori.                         | I pagamenti anticipati sono disponibili in Contabilità fornitori e Contabilità clienti.    |

## <a name="overview-of-the-prepayment-process"></a>Panoramica del processo di pagamento anticipato
Le procedure contabili in molti paesi richiedono che i pagamenti anticipati da un cliente, o effettuati a favore di un fornitore, non vengano registrati nei conti riepilogativi abituali relativi al cliente o al fornitore. Tali pagamenti anticipati vanno invece registrati in conti CoGe specifici per i pagamenti anticipati. Quando si crea un ordine cliente o un ordine fornitore, viene emessa una fattura al cliente o dal fornitore. Una volta pagata la fattura, il pagamento anticipato e il giustificativo per il pagamento anticipato IVA vengono stornati dai conti CoGe per i pagamenti anticipati e gli importi in fattura vengono automaticamente registrati nei conti riepilogativi abituali. Per creare un pagamento anticipato, completare i passaggi che seguono.

1.  Impostare i profili di registrazione per i pagamenti anticipati.
2.  In Parametri contabilità clienti e Parametri contabilità fornitori di **Contabilità generale e IVA** selezionare il nuovo profilo di registrazione utilizzando il parametro **Profilo registrazione per giornale di registrazione pagamenti con pagamento anticipato**.
3.  Crea un giornale di registrazione pagamenti, quindi crea il nuovo pagamento.
4.  È possibile contrassegnare il pagamento come pagamento anticipato. Se un pagamento viene contrassegnato come pagamento anticipato, il pagamento viene registrato nei conti CoGe che vengono definiti nel profilo di registrazione impostato ai passaggi 1 e 2. Inoltre, se il pagamento viene contrassegnato come pagamento anticipato, le imposte vengono calcolate. Alcuni governi richiedono che le imposte siano pagate quando viene registrato un pagamento anticipato, anche in mancanza di fattura.
5.  Registrare il pagamento anticipato.
6.  Facoltativo: È possibile liquidare il pagamento anticipato a fronte dell'ordine fornitore o l'ordine cliente prima di creare la fattura. In un ordine cliente o un ordine fornitore, nel riquadro azioni, utilizza **Liquida transazioni**.
7.  Dopo che il fornitore avrà fornito le merci o i servizi, registrare la fattura. Se il pagamento anticipato è stato liquidato a fronte dell'ordine fornitore o dell'ordine cliente al passaggio 6, il pagamento anticipato viene automaticamente liquidato a fronte della fattura creata. Se il pagamento anticipato non è stato liquidato a fronte dell'ordine fornitore o dell'ordine cliente, è possibile liquidarlo manualmente a fronte della fattura utilizzando **Liquida transazioni** nella pagina cliente o fornitore. L'importo del pagamento anticipato verrà quindi temporaneamente stornato dal conto CoGe di AP/AR. Inoltre, se le imposte sono state calcolate, vengono stornate, poiché la fattura include le imposte effettive.

## <a name="overview-of-the-prepayment-invoicing-process"></a>Panoramica del processo di fatturazione del pagamento anticipato
Le fatture di pagamento anticipato sono una normale procedura commerciale. Un fornitore emette le fatture di pagamento anticipato per richiedere un deposito sull'acquisto prima che l'ordine fornitore sia stato completato. Ad esempio, alcuni fornitori richiedono un pagamento anticipato di merci o servizi personalizzati. Se un fornitore emette una fattura che richiede il pagamento anticipato, è possibile utilizzare la funzionalità di fatturazione del pagamento anticipato. Un valore di pagamento anticipato può essere definito nell'ordine fornitore, una fattura di pagamento anticipato viene registrata e pagata, quindi la fattura di pagamento anticipato viene applicata alla fattura finale. Per creare un pagamento anticipato, completare i passaggi che seguono.

1.  L'addetto acquisti crea, conferma e invia un ordine fornitore per il quale il fornitore ha richiesto un pagamento anticipato. Il valore di pagamento anticipato viene definito nell'ordine fornitore come parte del contratto.
2.  Il fornitore invia una fattura di pagamento anticipato.
3.  Il coordinatore della contabilità fornitori registra la fattura di pagamento anticipato a fronte dell'ordine fornitore, quindi viene pagata la fattura del pagamento anticipato.
4.  Il fornitore invia una richiesta di pagamento, denominata fattura fornitore standard. Dopo che il fornitore ha consegnato le merci o fornito i servizi e sono state ricevute le relative fatture fornitore standard, il coordinatore della contabilità fornitori applica l'importo di pagamento anticipato già pagato a fronte della fattura standard.
5.  Il coordinatore della contabilità fornitori effettua il pagamento e liquida l'importo rimanente della fattura standard.

## <a name="set-up-parameters-to-enable-the-prepayment-invoicing-process"></a>Impostare i parametri per abilitare il processo di fatturazione del pagamento anticipato
È necessario definire un conto di pagamento anticipato nella scheda **Ordine fornitore** della pagina **Registrazione inventario** (**Gestione inventario \> Impostazioni \> Registrazione \> Registrazione**). Il conto per il pagamento anticipato verrà aggiornato, in genere addebitato, quando viene registrata la fattura del pagamento anticipato. Il saldo del conto pagamento anticipato verrà stornato quando viene registrata la fattura standard applicata alla fattura pagamento anticipato. Se non si salda la fattura di pagamento anticipato con un pagamento prima di applicare la fattura di pagamento anticipato alla fattura standard, le voci contabili della fattura di pagamento anticipato registrata verranno stornate quando la fattura standard viene registrata.

Il conto di contabilità fornitori riepilogo contropartita è definito nel profilo **Registrazione fornitore**. Per definire il profilo di registrazione predefinito, fai clic su **Contabilità fornitori \>Impsotazioni \> Parametri contabilità fornitori \> Scheda libro mastro e IVA \> Profilo di registrazione con fattura fornitore pagamento anticipato**.

Il **Criterio applicazione pagamento anticipato** indica se il sistema applicherà automaticamente le fatture di pagamento anticipato liquidate alla fattura finale creata manualmente. Le fatture create utilizzando un'entità di dati non faranno riferimento al **Criterio applicazione pagamento anticipato**. Sarà necessario applicare manualmente le fatture di pagamento anticipato liquidate alle fatture create utilizzando un'entità di dati. Per definire il criterio, vai a **Contabilità fornitori \>Impostazioni \> Parametri contabilità fornitori \> Scheda libro mastro e IVA \> Criterio applicazione pagamento anticipato**. Se il campo **Criterio applicazione pagamento anticipato** è impostato su **Automatico**, la fattura di pagamento anticipato verrà automaticamente contrassegnata per la liquidazione con la fattura finale. Se il campo è impostato su **Notifica**, al momento della creazione della fattura finale verrà visualizzata un'indicazione visiva che una fattura di pagamento anticipato è disponibile per l'applicazione.

## <a name="create-a-purchase-order-that-contains-prepayment-invoice-information"></a>Creare un ordine fornitore contenente informazioni sulla fattura di pagamento anticipato
Quando un fornitore comunica che richiede il pagamento anticipato per beni e servizi contenuti in un ordine fornitore, è necessario definire il valore di pagamento anticipato per l'ordine fornitore associato. Vai a **Contabilità fornitori \> Comune \> Ordini fornitore \> Tutti gli ordini fornitore** e trova l'ordine del fornitore. Nel riquadro azioni, seleziona la scheda **Acquisto** e quindi seleziona **Pagamento anticipato**. Immetti le informazioni per il pagamento anticipato, inclusa la descrizione, il valore, l'indicazione di importo fisso di percentuale e un ID categoria di pagamento anticipato. 

Non sono consentite più definizioni di pagamenti anticipati in un ordine fornitore. Se è necessario consentire più pagamenti anticipati in un ordine fornitore, registra i pagamenti utilizzando le registrazioni pagamenti anziché una fattura di pagamento anticipato.

Il pagamento anticipato può essere rimosso dall'ordine fornitore a meno che non sia già stato liquidato un pagamento rispetto alla fattura di pagamento anticipato registrata o non sia stata registrata la fattura standard. Per rimuovere le informazioni di pagamento anticipato dall'ordine fornitore, seleziona **Contabilità fornitori \> Comune \> Ordini fornitore \> Tutti gli ordini fornitore** e trova l'ordine del fornitore. Nel riquadro azioni, seleziona la scheda **Acquisto** e quindi seleziona **Rimuovi pagamento anticipato**.

## <a name="create-and-post-a-prepayment-invoice"></a>Creare e registrare una fattura di pagamento anticipato
Per registrare la fattura di pagamento anticipato del fornitore, vai alla pagina **Fattura fornitore** selezionando l'opzione **Fattura pagamento anticipato** nella pagina **Ordini fornitore** (**Contabilità fornitore \> Comune \> Ordini fornitore \> Tutti gli ordini fornitore \> scheda Fattura \> Fattura pagamento anticipato**). Immetti le informazioni relative alla fattura di pagamento anticipato, compreso il numero della stessa. Non è possibile modificare le quantità per una fattura di pagamento anticipato. Se il fornitore ha fatturato un importo parziale del valore di pagamento anticipato definito nell'ordine fornitore, è possibile aggiornare il prezzo unitario in modo che rifletta il valore parziale.

Quando la fattura di pagamento anticipato viene registrata, il saldo fornitore e il conto pagamento anticipato verranno aggiornati. Verrà inoltre aggiornato il valore dell'**applicazione di pagamento anticipato** nella definizione di pagamento anticipato contenuta nell'ordine fornitore. I movimenti di dimensione finanziaria predefiniti per il giustificativo di pagamento anticipato registrato verranno prelevati dalle informazioni di intestazione nell'ordine fornitore.

## <a name="post-and-settle-payments-for-the-prepayment-invoice"></a>Registrare e liquidare i pagamenti per la fattura di pagamento anticipato
Successivamente, la fattura di pagamento anticipato verrà pagata dalla pagina **Giornale di registrazione pagamenti**. Per accedere ai giornali di registrazione pagamenti, fai clic su **Contabilità fornitori \> Giornali di registrazione \> Pagamenti \> Giornale di registrazione pagamenti**. Dopo aver contabilizzato la liquidazione del pagamento nella fattura di pagamento anticipato, il valore **rimanente dell'applicazione di pagamento anticipato** dell'ordine fornitore verrà aggiornato.

Prima di registrare la fattura standard per la fattura di pagamento anticipato, è possibile stornare la liquidazione del pagamento dalla fattura di pagamento anticipato. Tuttavia dopo l'applicazione di una fattura standard alla fattura di pagamento anticipato, non è possibile stornare la liquidazione del pagamento dalla fattura di pagamento anticipato.

## <a name="post-the-standard-vendor-invoice-for-the-purchase-order-and-apply-the-prepayment-invoice-to-the-standard-invoice"></a>Registrare la fattura fornitore standard per l'ordine fornitore e applicare la fattura di pagamento anticipato alla fattura standard
Registra la fattura standard ricevuta dal fornitore. Come parte di questo processo, puoi applicare la fattura di pagamento anticipato liquidata alla fattura fornitore in modo che il valore della fattura sia ridotto dell'importo già pagato. L'applicazione della fattura di pagamento anticipato alla fattura fornitore garantirà che i movimenti contabili della fattura di pagamento anticipato vengano stornati.

## <a name="application-of-the-prepayment-invoice-after-posting-the-standard-invoice"></a>Applicazione della fattura di pagamento anticipato dopo la registrazione della fattura standard
Se dimentichi di applicare il pagamento anticipato alla fattura fornitore standard al momento della registrazione della fattura fornitore, il pagamento anticipato liquidato sarà disponibile per l'applicazione ad altre fatture di questo fornitore dalla pagina **Fornitori** (**Contabilità fornitori \> Comune \> Fornitori \> Tutti i fornitori \> scheda Fattura \> Applica**).

## <a name="reversal-of-the-prepayment-application-process"></a>Storno del processo di applicazione di pagamento anticipato
Se è necessario annullare la liquidazione o stornare l'applicazione di una fattura di pagamento anticipato da una fattura standard, seleziona l'azione **Storna** dalla pagina **Fornitori** (**Contabilità fornitori \> Comune \> Fornitori \> Tutti i fornitori \> scheda Fattura \> Storna**). Dopo lo storno dell'applicazione di pagamento anticipato, è possibile applicare il pagamento anticipato a un'altra fattura standard. 



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
