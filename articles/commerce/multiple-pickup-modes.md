---
title: Abilitare più modalità di consegna ritiro per gli ordini cliente
description: Questo argomento spiega la funzionalità in Microsoft Dynamics 365 Commerce che consente di creare ordini cliente per il ritiro in un negozio.
author: hhainesms
ms.date: 11/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: c32ffc8435c05c644bf836bb184400d067269208
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5796880"
---
# <a name="enable-multiple-pickup-delivery-modes-for-customer-orders"></a>Abilitare più modalità di consegna ritiro per gli ordini cliente

[!include [banner](includes/banner.md)]


In Microsoft Dynamics 365 Commerce versione 10.0.16 e successive, le organizzazioni possono definire più modalità di consegna tra le quali gli acquirenti o gli addetti alle vendite possono scegliere quando creano un ordine che verrà ritirato in un negozio. In questo modo, le organizzazioni possono fornire più opzioni di ritiro ai propri acquirenti. Ad esempio, molti rivenditori ora offrono agli acquirenti la possibilità di scegliere tra il ritiro in negozio o il ritiro al piano strada per i loro ordini. Commerce supporta la configurazione di queste diverse modalità di consegna ritiro. Gli utenti possono quindi trarne vantaggio quando creano ordini cliente in qualsiasi canale di Commerce supportato (e-commerce, call center o negozio).

## <a name="enable-and-configure-pickup-delivery-modes"></a>Abilitare e configurare le modalità di consegna ritiro

Per utilizzare questa funzionalità, attivare la funzionalità **Supporto per più modalità di consegna ritiro** nell'area di lavoro **Gestione funzionalità** in Commerce headquarters. Dopo aver attivato la funzionalità, è necessaria una configurazione aggiuntiva.

In Commerce versione 10.0.15 e precedenti, le organizzazioni possono definire solo una modalità di consegna come modalità di consegna ritiro designata. Questa definizione viene eseguita nella pagina **Parametri di commercio**. Nella versione 10.0.16 e successive, quando si attiva la funzionalità **Supporto per più modalità di consegna ritiro**, la modalità di consegna precedentemente definita come modalità di consegna ritiro nella pagina **Parametri di commercio** viene automaticamente copiata nella nuova configurazione per le modalità di consegna ritiro.

![Modalità di consegna ritiro nella pagina dei parametri di Commerce](media/multiplepickupparameter.png)

Dopo aver attivato la funzionalità **Supporto per più modalità di consegna ritiro**, è possibile definire più modalità di consegna ritiro nella griglia **Modalità di consegna ritiro** nella scheda dettaglio **Modalità di consegna** della scheda **Ordini cliente** della pagina **Parametri di commercio**.

I campi **Modalità di consegna trasporto** e **Modalità di consegna elettronica** e l'opzione **Mostra solo le opzioni della modalità corriere per gli ordini di spedizione**, sono state riposizionate in questa scheda dettaglio.

Prima di configurare modalità di consegna ritiro aggiuntive, è necessario definire le modalità di consegna. Nella pagina **Modalità di consegna** di Commerce headquarters, aggiungere le modalità di consegna da considerare modalità di consegna ritiro. Assicurarsi che tutta la configurazione sia stata completata. Ad esempio, assicurarsi che la modalità di consegna sia collegata ai canali e agli articoli appropriati. Al termine, eseguire il processo **Esegui modalità di consegna** per creare le relazioni tra la modalità di consegna, i canali e gli articoli. Al termine dell'esecuzione del processo, aprire la pagina **Programma di distribuzione** in Commerce headquarters ed eseguire il processo di distribuzione **1120** per garantire che i database dei canali di Commerce pertinenti siano aggiornati con la nuova configurazione della modalità di consegna.

![Esempio di configurazione della modalità di consegna per il ritiro al piano strada](media/pickupmodes.png)

Dopo aver definito le modalità di consegna ritiro aggiuntive, aggiungerle alla griglia **Modalità di consegna ritiro** nella pagina **Parametri di commercio**. Quindi eseguire i processi di distribuzione appropriati per aggiornare i database dei canali di Commerce pertinenti con la modifica della configurazione.

> [!NOTE]
> A parte la modalità di consegna ritiro esistente che viene copiata nella griglia **Modalità di consegna ritiro** quando si attiva la funzionalità **Supporto per più modalità di consegna ritiro**, per ogni configurazione aggiuntiva della modalità di consegna ritiro che viene creata è necessario configurare nuove modalità di consegna. Quando si aggiungono modalità di consegna alla griglia **Modalità di consegna ritiro**, Commerce convalida se righe di vendita aperte attive già le utilizzano. Se vengono trovate righe di vendita aperte, viene visualizzato un messaggio di errore. Le modalità di consegna non sono considerate modalità di consegna ritiro fino a quando tutte le righe di vendita aperte che le utilizzano non sono state chiuse (fatturate o annullate).

> [!IMPORTANT]
> Dopo aver definito più di una modalità di consegna ritiro nella pagina **Parametri di commercio**, la funzionalità **Supporto per più modalità di consegna ritiro** diventa obbligatoria e non può più essere disattivata. Se è necessario disattivare la funzione, rimuovere tutte le modalità di consegna ritiro tranne una dalla griglia **Modalità di consegna ritiro**. Quando viene definita una sola modalità di consegna ritiro, la funzione non è più considerata obbligatoria e può essere disattivata.

### <a name="e-commerce-site-configurations"></a>Configurazioni del sito di e-commerce

Quando la funzionalità **Supporto per più modalità di consegna ritiro** è attivata, i seguenti moduli sulle pagine di e-commerce mostrano le nuove modalità di consegna ritiro come configurate:

- Casella acquisti
- Selettore punto vendita
- Carrello
- Informazioni di prelievo
- Conferma dell'ordine
- Dettagli ordine

Non sono necessari passaggi aggiuntivi sulle pagine di e-commerce per rendere disponibili le modalità di consegna ritiro.

## <a name="work-with-multiple-pickup-delivery-modes"></a>Utilizzare più modalità di consegna ritiro

Quando sono disponibili più modalità di consegna ritiro per un canale, viene fornita un'esperienza migliorata ai clienti quando acquistano i prodotti che verranno ritirati. 

- Nei canali di e-commerce, gli acquirenti possono selezionare qualsiasi modalità di consegna ritiro valida disponibile. Ad esempio, un rivenditore definisce due modalità di consegna ritiro (ritiro in negozio e ritiro a piano strada), entrambe sono configurate nella griglia **Modalità di consegna ritiro** ed entrambe sono valide per il canale di evasione degli ordini e per il prodotto che un acquirente sta attualmente acquistando. In questo caso, l'acquirente può selezionare la modalità di consegna ritiro preferita. La modalità di consegna ritiro selezionata diventa quindi la modalità di consegna collegata alla riga dell'ordine di vendita quando l'ordine viene creato in Commerce headquarters.

    ![Selezione di un'opzione di ritiro in e-commerce](media/pickupecommerce.png)

- Nei canali del punto vendita, se viene creato un ordine cliente per il ritiro tramite l'applicazione del punto vendita (POS), all'addetto alle vendite viene richiesto di scegliere tra le modalità di consegna ritiro disponibili, se sono state configurate. Se è disponibile una sola modalità di consegna ritiro valida per il canale e l'articolo, all'addetto alle vendite non viene chiesto di selezionarla. La modalità di consegna ritiro disponibile viene invece applicata automaticamente alle righe dell'ordine.

    ![Selezione di un'opzione di ritiro nell'applicazione POS](media/pickuppos.png)

- Nei canali del call center, quando gli utenti creano ordini di ritiro, possono selezionare manualmente qualsiasi modalità di consegna ritiro definita collegata al canale del call center. Il sistema quindi convalida che la modalità di consegna ritiro selezionata possa essere utilizzata quando l'articolo a cui è stato collegato viene ordinato. Quando si seleziona una modalità di consegna ritiro nei canali del call center, le righe dell'ordine cliente devono essere collegate a un magazzino del punto vendita valido. Se un magazzino non del punto vendita è definito in una riga di vendita del call center, non è possibile impostare una modalità di consegna ritiro su quella riga di vendita.
- Gli addetti alle vendite possono utilizzare l'operazione **Richiama ordine** o **Evasione ordine** nell'applicazione POS per recuperare un elenco di ordini o righe di ordine per il ritiro. Se un addetto alle vendite utilizza un filtro di ricerca predefinito per mostrare tutti gli ordini che verranno ritirati nel negozio corrente, le query vengono modificate per garantire che i risultati della ricerca includano tutti gli ordini idonei che utilizzano qualsiasi modalità di consegna ritiro. Gli utenti POS possono anche utilizzare i filtri esistenti per limitare l'elenco degli ordini a una specifica modalità di consegna ritiro. Ad esempio, possono mostrare solo gli ordini per il ritiro dal piano strada.

    ![Filtro per modalità di consegna ritiro applicato a un elenco di ordini di richiamo](media/pickuprecallorder.png)

## <a name="considerations-for-distributed-order-management"></a>Considerazioni per la gestione di ordini distribuiti

Le funzioni di [gestione ordini distribuiti (DOM)](https://docs.microsoft.com/dynamics365/commerce/dom) in Commerce ignorano le righe di vendita contrassegnate per il ritiro in negozio. Queste funzionalità sono state aggiornate per garantire che le righe di vendita collegate alle modalità di consegna ritiro configurate ignorino la logica DOM e non vengano riallocate a un nuovo magazzino di evasione ordini.


[!INCLUDE[footer-include](../includes/footer-banner.md)]