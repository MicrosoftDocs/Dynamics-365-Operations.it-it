---
title: Metodi di pagamento nei servizi clienti
description: In questo argomento vengono descritti i diversi metodi di pagamento che è possibile utilizzare in un servizio clienti Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 03/28/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: MCRSalesTableOrderHistory, MCRCCAuthManagement
audience: Application User
ms.reviewer: josaw
ms.custom: 92163
ms.assetid: 8e738907-870b-466c-ab0c-07f4a4aa47f3
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 8fede81aa8c61eddba72b9ba2e780d61731f8253
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4989254"
---
# <a name="payment-methods-in-call-centers"></a>Metodi di pagamento nei servizi clienti

[!include [banner](includes/banner.md)]

In Dynamics 365 Commerce, la configurazione di un canale servizio clienti include un'impostazione **Attiva completamento ordine**. Questa impostazione consente di garantire che tutti gli ordini creati dagli utenti del canale vengano rilasciati per l'elaborazione degli ordini solo se dispongono di un pagamento prepagato o pre-autorizzato che rientra nelle tolleranze approvate. Se l'impostazione **Attiva completamento ordine** è abilitata, gli utenti del servizio clienti possono inserire pagamenti per ordini cliente per i clienti utilizzando le funzionalità di elaborazione dei pagamenti del servizio clienti. Se l'impostazione è disattivata, gli utenti del servizio clienti non possono utilizzare le funzionalità di elaborazione dei pagamenti tramite il servizio clienti, ma possono comunque applicare i pagamenti anticipati agli ordini cliente utilizzando la funzionalità di contabilità clienti standard.

Durante la configurazione di un canale, una società può definire i metodi di pagamento consentiti per un canale servizio clienti. Il canale servizio clienti utilizza gli stessi metodi di pagamento definiti per i canali del punto vendita.

Per configurare i metodi di pagamento per un canale servizio clienti, passare a **Retail e Commerce** \> **Canali** \> **Servizi clienti** \> **Tutti i servizi clienti** e quindi nel menu **Impostazione** selezionare l'opzione **Metodi di pagamento**.

Quando si crea un metodo di pagamento, sono disponibili cinque funzioni del metodo di pagamento che è possibile assegnare.

| Funzione            | descrizione |
|---------------------|-------------|
| Normale              | Utilizzare la funzione **Normale** nel metodo di pagamento quando si definiscono i metodi di pagamento quali contanti o buoni. Quando questi tipi di pagamenti vengono applicati a un ordine cliente nel servizio clienti, il flag **Pagamento anticipato** è impostato per impostazione predefinita su **Sì**. In questo modo verrà registrato immediatamente un giustificativo di pagamento anticipato nel conto cliente quando l'ordine viene inviato. Gli utenti possono cambiare il flag **Pagamento anticipato** su **No** se lo desiderano in modo che il giustificativo di pagamento non venga creato fino alla registrazione della fattura. Il giustificativo di pagamento anticipato viene registrato nello storico delle transazioni del cliente, dove verrà compensato in modo sistematico nella fattura per l'ordine cliente. |
| Verifica               | Utilizzare la funzione **Assegno** quando si definisce uno strumento assegno bancario come forma di pagamento. Quando questo tipo di pagamento viene applicato a un ordine cliente, l'utente deve immettere il numero di assegno del cliente come parte dell'elaborazione dell'applicazione di pagamento. Anche i pagamenti con assegni vengono trattari come pagamenti anticipati quando vengono applicati e i giustificativi di pagamento vengono creati immediatamente al ricevimento dell'ordine. Questi giustificativi di pagamento anticipato verranno liquidati in modo sistematico in base alle fatture create per l'ordine. |
| Carte               | I tipi di pagamento con carta rappresentano qualsiasi tipo di pagamento che richiede l'immissione di un numero di carta che è stato definito per la carta di pagamento del cliente. Gli esempi includono carte di credito e carte regalo. Quando si configurano questi tipi di pagamenti, è necessario utilizzare il menu **Impostazione carta** per definire gli ID della carta associati a questo metodo di pagamento. Al momento della registrazione dell'ordine, gli utenti possono indicare se il pagamento con carta sarà anticipato, utilizzando il pagamento l'opzione **Pagamento anticipato** che appare sulla pagina di pagamento. A meno che l'azienda non richieda pagamenti anticipati, il flusso tipico di un vero pagamento con carta di credito è un processo in due fasi, in cui l'autorizzazione viene ottenuta al momento della registrazione ordine e il pagamento viene regolato e addebitato sulla carta del cliente al momento della fatturazione. Per i pagamenti con carta regalo, si raccomanda il pagamento anticipato, poiché il saldo della carta regalo deve essere ridotto immediatamente in modo che il cliente non possa applicare lo stesso valore da qualche altra parte. |
| Cliente            | La funzione **Cliente** in un metodo di pagamento implica che il pagamento verrà applicato al limite di credito del cliente o messo "in acconto". In Commerce, a un cliente può essere assegnato un limite di credito che può essere convalidato al momento della registrazione ordine. I pagamenti effettuati utilizzando un metodo di pagamento collegato alla funzione **Cliente** crea una passività nel conto del cliente. Quindi, quando l'ordine cliente viene fatturato, viene visualizzato un saldo dovuto. In queste situazioni, i clienti in genere inviano un pagamento, in base ai termini forniti. In alternativa, è possibile applicare un precedente buono di credito aperto sul conto del cliente per saldare il saldo dovuto. Tenere presente che anche se si definisce questo metodo di pagamento, non viene visualizzato tra le opzioni di selezione dei pagamenti nella registrazione ordine del servizio clienti a meno che il flag **Consenti in acconto** non sia impostato per il record del cliente per il cliente con cui si sta lavorando. Questo flag si trova nella scheda **Impostazioni predefinite pagamento** del record del cliente. |
| Rimuovi/sospendi metodo di pagamento | La funzione **Rimuovi/sospendi metodo di pagamento** non viene utilizzata dal servizio clienti. È applicabile solo quando si definiscono i metodi di pagamento utilizzati dall'applicazione POS in un canale punto vendita. |

Poiché i metodi di pagamento sono definiti, devono essere collegati a un conto di contabilità generale o a un conto bancario. Se si omette questo passaggio, gli utenti riceveranno errori quando tentano di salvare il tipo di pagamento.

## <a name="refund-payment-methods"></a>Metodi di pagamento per il rimborso

Per gli scenari di elaborazione del rimborso, il servizio clienti utilizza anche alcuni metodi di pagamento definiti in Contabilità clienti. Per configurare questi metodi di pagamento, andare a **Retail e Commerce** \> **Impostazione canale** \> **Impostazione servizio clienti** \> **Metodi di rimborso servizio clienti**. È necessario completare la configurazione per elaborare gli assegni di rimborso ai clienti. Ad esempio, se un cliente ha in origine pagato per un ordine utilizzando contanti o un assegno, l'utente potrebbe voler inviare al cliente un assegno di rimborso tramite la contabilità clienti. In questo caso, i tipi di pagamento in contanti e con assegno nel servizio clienti devono essere associati al metodo di pagamento corretto in Contabilità clienti per garantire che il rimborso venga correttamente elaborato.

Inoltre, se un utente sta elaborando un ordine di reso come utente di un servizio clienti in Commerce, ma non è in grado di collegare il reso a una vendita originale, il metodo di pagamento **Reso** deve essere definito nei parametri del servizio clienti. Passare a **Retail e Commerce** \> **Impostazione canale** \> **Impostazione servizio clienti** \> **Parametri servizio clienti** e quindi nella scheda **NAR/Reso** nel campo **Metodo di pagamento** assicurarsi che il metodo di pagamento sia definito. Il metodo di pagamento sarà il metodo di pagamento utilizzato per i rimborsi. In genere, verrà definito come metodo con assegno o metodo tramite conto cliente.
