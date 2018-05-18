---
title: Integrazione dei cespiti
description: "È possibile integrare Cespiti con Contabilità generale, Gestione articoli, Contabilità clienti e Contabilità fornitori. È inoltre possibile impostare i cespiti per l'integrazione con gli ordini fornitore."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 3501
ms.assetid: f0639053-d99c-432a-8ead-5c26e0d4eaec
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: a598a562b35a8bb1e0ede6bb8f3dc0515c162a06
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="fixed-assets-integration"></a>Integrazione dei cespiti

[!include [banner](../includes/banner.md)]

È possibile integrare Cespiti con Contabilità generale, Gestione articoli, Contabilità clienti e Contabilità fornitori. È inoltre possibile impostare i cespiti per l'integrazione con gli ordini fornitore.

<a name="general-ledger"></a>Contabilità generale
--------------

In Contabilità generale il valore di tutti i cespiti viene di solito riepilogato in più conti principali necessari per i report finanziari. Tuttavia, nella pagina **Cespiti** è possibile creare più record relativi ai cespiti. Questi record possono includere le informazioni, ad esempio il prezzo di acquisizione, l'ammortamento e la valutazione. Ogni volta che si registra una transazione per un cespite, vengono aggiornati i conti principali appropriati. Nei conti principali per i cespiti viene sempre riportato il valore aggiornato dei cespiti.

Nella pagina **Profili registrazione cespiti** si definiscono i conti principali in cui vengono registrate le transazioni del libro cespiti. Vengono inoltre specificati i tipi di transazioni cespiti registrati in ciascun conto principale. È possibile creare varie combinazioni di conti principali per i cespiti, a seconda del livello di dettaglio desiderato per i cespiti nella contabilità generale. I conti principali possono essere basati su tipi di transazioni, libri e altri conti principali.

## <a name="inventory-management"></a>Gestione inventario
Nel giornale di registrazione magazzino per i cespiti, è possibile immettere i dati relativi all'acquisizione di cespiti che la persona giuridica ha prodotto o costruito per proprio uso. È possibile quindi trasferire gli articoli di magazzino ai cespiti sotto forma di acquisizione o di parte di un'acquisizione. 

È inoltre possibile acquisire cespiti utilizzando ordini fornitore. Quando in tali ordini sono presenti articoli di magazzino designati come cespiti, l'impostazione di **Consenti acquisizione cespiti da Acquisto** nella pagina **Parametri cespiti** determina se per il cespite viene registrata un'acquisizione al momento della registrazione della fattura. L'effetto dell'acquisizione dei cespiti sulle scorte dipende dall'impostazione della persona giuridica. 

Quando un articolo di magazzino diventa un'acquisizione cespiti, mediante il giornale di registrazione magazzino, un ordine fornitore o una proposta di acquisizione, viene creata una transazione di acquisizione del libro cespiti. Se l'acquisizione di un libro include un libro derivato, viene creata anche una transazione di acquisizione relativa al libro derivato. 

La riduzione delle scorte durante la registrazione di un'acquisizione è controllata dalle regole di registrazione impostate nella pagina **Registrazione** di Gestione articoli. Non accade tuttavia sempre che le scorte si riducano quando si registrano le fatture relative ai cespiti. In alcuni casi, i cespiti potrebbero venire acquistati per uso interno. Ad esempio un computer portatile acquistato per il reparto vendite. Quando si gestiscono gli ordini fornitore, è possibile utilizzare articoli impostati sia per la rivendita sia per uso interno. 

Se si utilizzano conti entrate e conti uscite specifici in gruppi di articoli per i cespiti, è possibile utilizzare lo stesso articolo di magazzino tanto per acquisti interni quanto come scorta per la rivendita. 

I cespiti per uso interno vengono impostati con un tipo di conto **Entrata cespite**. Questo tipo di conto viene utilizzato per tenere traccia dell'entrata del cespite. Quando si registra una fattura fornitore, utilizzare il conto di entrata cespite se si verifica una delle seguenti condizioni:

-   La riga di fattura contiene un cespite esistente per scopi interni.
-   La casella di controllo **Nuovo cespite?** è selezionata per la riga dell'entrata prodotti registrata.
-   La casella di controllo **Crea un nuovo cespite** è selezionata per la riga fattura fornitore.

Si tratta di solito di un conto spese. Il tipo di conto **Entrata cespite** può essere impostato per un gruppo di articoli o per un singolo articolo utilizzando la scheda **Ordine fornitore** delle pagine **Gruppo di articoli** o **Registrazione**.

Analogamente, i cespiti per uso interno possono essere impostati con un tipo di conto **Uscita cespite**. Questo tipo di conto viene utilizzato per tenere traccia dell'invio del cespite al destinatario. Quando un cespite viene acquisito mediante un ordine fornitore, il conto di uscita cespite è a compensazione del conto in Dare. L'acquisizione cespiti può essere registrata contestualmente a una fattura fornitore o alla registrazione dell'acquisizione cespiti nel giornale di registrazione cespiti, eventualmente mediante una proposta di acquisizione. Il tipo di conto **Uscita cespite** può essere impostato per un gruppo di articoli o per un singolo articolo utilizzando la scheda **Inventario** delle pagine **Gruppo di articoli** o **Registrazione articoli**. 

Infine, i conti principali utilizzati per la registrazione vengono determinati dalle opzioni di integrazione contabile specificate per il gruppo di modelli di articoli. Inoltre, i conti principali che vengono utilizzati variano a seconda che un cespite venga assegnato o meno alla riga dell'ordine fornitore. I conti derivano dal profilo registrazione per ogni gruppo di articoli. 
**Nota:** Se è presente una prenotazione delle scorte quando le entrate prodotti vengono registrate, non sarà possibile assegnare un cespite o crearne uno dalla riga. 

I conti in cui vengono registrate le transazioni cespiti dipendono da due fattori: se i cespiti vengono acquistati o costruiti dalla persona giuridica e dal tipo di transazione del cespite. 

Il tipo di transazione collega la transazione di magazzino al profilo registrazione in Cespiti. Poiché tale profilo definisce quali conti saranno aggiornati, la selezione di un tipo di transazione per un cespite è indirettamente anche la selezione dei conti principali in cui viene registrata la transazione. Sia per i cespiti costruiti sia per quelli acquistati, il tipo di transazione è solitamente **Acquisizione** o **Rettifica acquisizione**.

## <a name="accounts-receivable"></a>Contabilità clienti
L'integrazione dei cespiti con la contabilità clienti utilizza i profili di registrazione impostati nei cespiti. Questi profili vengono attivati quando un cespite, un libro e un tipo di transazione cespiti vengono selezionati per una fattura cliente prima che venga registrata. Poiché i cespiti non fanno parte della gestione articoli, quando si vende un cespite, è necessario utilizzare la pagina **Fattura a testo libero**. 

Se un libro include un libro derivato, quando si registra la fattura cliente viene creata una transazione del libro derivato.

## <a name="accounts-payable"></a>Contabilità fornitori
I cespiti solitamente vengono acquisiti rivolgendosi a fornitori esterni. Utilizzando la pagina **Parametri cespiti** è possibile specificare se le acquisizioni cespiti devono essere sempre registrate quando si registrano le fatture fornitore o se tali acquisizioni possono essere registrate solo da Cespiti. Se si consente la registrazione delle acquisizioni cespiti da Contabilità fornitori, i conti cespiti verranno aggiornati ogni volta che viene registrata una fattura fornitore per un'acquisizione cespiti. 

Se il sistema è configurato per registrare un'acquisizione cespiti al momento della registrazione di una fattura, la transazione verrà registrata in base ai profili registrazione impostati in Cespiti secondo i vari tipi di transazione cespiti. La registrazione è controllata dal cespite, dal libro e dal tipo di transazione cespiti selezionati nella pagina **Ordine fornitore** prima della registrazione della fattura fornitore. 

Se un libro include un libro derivato, quando si registra la fattura fornitore viene creata una transazione del libro derivato.

L'integrazione per ciascuna riga ordine viene attivata nella scheda **Cespiti** della scheda dettaglio **Dettagli riga** nella pagina **Ordine fornitore**. È possibile inviare un ordine fornitore per un cespite al fornitore. Tuttavia, i cespiti e i conti principali vengono aggiornati solo quando si registra la fattura fornitore dopo che il cespite è stato ricevuto. Poiché negli ordini fornitore possono essere presenti solo articoli di magazzino, l'effetto dell'acquisizione di cespiti sulle scorte dipende dall'impostazione della persona giuridica.

## <a name="project-management-and-accounting"></a>Gestione progetti e contabilità
È possibile associare un progetto a un cespite interessato dal progetto. È inoltre possibile associare ogni fase, attività o sottoprogetto a un cespite diverso. Un cespite può essere associato a ogni record di progetto. È possibile creare l'associazione quando si immette un numero di cespite nel campo **Numero cespite** della pagina **Progetti**. Il tipo di progetto deve essere **Interno** o **Piano dei costi**. 

È possibile utilizzare la pagina **Progetti** anche per visualizzare i dettagli dei cespiti associati ai progetti. Per visualizzare il record cespite, fare clic sul collegamento al cespite nella scheda dettaglio **Impostazioni** per aprire la pagina **Cespiti**. Quindi fare clic su **Progetti** &gt; **Tutti i progetti** per visualizzare i progetti associati al cespite. 

I cespiti in genere vengono associati ai progetti quando questi sono relativi a lavoro, manutenzione o miglioramenti connessi al cespite. Quando il progetto è stato completato, non viene creata automaticamente una rettifica di rivalutazione per il cespite. Pertanto, sarà necessario crearla manualmente, se richiesta. 

Per eliminare l'associazione tra un progetto e un cespite, deselezionare il campo **Numero cespite** nella pagina **Progetti**. 

È inoltre possibile designare un cespite che si sta creando o producendo come parte di un progetto stima. Al termine di tale progetto, sarà possibile registrare automaticamente una transazione di acquisizione cespiti.

Per ulteriori informazioni, vedere [Acquisire cespiti tramite approvvigionamento](acquire-assets-procurement.md).




