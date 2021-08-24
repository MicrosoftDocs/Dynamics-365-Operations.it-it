---
title: Fatturazione progetto
description: Questo argomento fornisce una panoramica della fatturazione per i progetti di tempistica e materiali e a prezzo fisso. Sono riportate informazioni sulle proposte di fatturazione (fatture preliminari), controllo della fattura, fatturazione acconti, fatturazione fornitori e note di credito.
author: TaylorVH
ms.date: 07/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProjInvoiceCashFlow, ProjInvoiceControl, ProjInvoiceListPage, ProjInvoiceProposalDetail, ProjInvoiceProposalListPage
audience: Application User, IT Pro
ms.reviewer: roschlom
ms.custom: 23111
ms.assetid: 1812d6f2-8b34-4258-8f5f-dcf12281547f
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2020-07-06
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: d8f0e027761a42871f9fc543319ba47fe457f23b8b7f937b8f847cc16922610e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6737261"
---
# <a name="project-invoicing"></a>Fatturazione progetto

[!include [banner](../includes/banner.md)]

Questo argomento fornisce una panoramica della fatturazione per i progetti di tempistica e materiali e a prezzo fisso. Sono riportate informazioni sulle proposte di fatturazione (fatture preliminari), controllo della fattura, fatturazione acconti, fatturazione fornitori e note di credito.

La procedura di fatturazione da applicare è determinata dal tipo di progetto. È possibile fatturare solo i due tipi di progetto esterni, ovvero i progetti di tempistica e materiali e quelli a prezzo fisso. I progetti di tempistica e materiali e quelli a prezzo fisso sono sempre collegati a un contratto di progetto.

-   **Progetti a prezzo fisso**: l'importo della fattura cliente si basa su programmi di fatturazione. La fatturazione viene effettuata mediante un'impostazione in acconto, denominata anche programma di fatturazione. È possibile fatturare i progetti a prezzo fisso per progetto o per contratto di progetto.
-   **Progetti di tempistica e materiali**: l'importo della fattura cliente è basato sulle righe di transazione immesse nei progetti. Le transazioni possono essere fatturate per progetto o per contratto di progetto.

Sono disponibili tre modi per collegare i progetti di tempistica e materiali e quelli a prezzo fisso ai progetti di fatturazione:

-   **Fatturazione in acconto**: è possibile fatturare i progetti a prezzo fisso e quelli di tempistica e materiali in acconto. Sono necessari due diversi tipi di impostazione in acconto, uno per ciascun tipo di progetto.
-   **Fatturazione nell'area Periodico**: mediante le funzioni periodiche è possibile fatturare transazioni all'interno di progetti. Le funzioni periodiche forniscono una panoramica delle transazioni da fatturare.
-   **Note di accredito nella fatturazione**: è possibile creare una nota di accredito sia per i progetti di tempistica e materiali sia per i progetti a prezzo fisso.

## <a name="invoice-proposals"></a>Proposte di fatturazione
Prima di creare una fattura cliente per un progetto, è possibile creare una fattura preliminare o una proposta di fatturazione. In una proposta di fatturazione, è possibile selezionare le transazioni di progetto da includere in una fattura di progetto. È quindi possibile esaminare i dettagli della fattura prima di registrare la fattura di progetto e inviarla al cliente o a un'altra fonte di finanziamento.

### <a name="creating-invoice-proposals"></a>Creazione di proposte di fatturazione

È possibile creare proposte di fatturazione selezionando manualmente una transazione da un elenco di transazioni disponibili per un progetto specificato. È inoltre possibile impostare le regole di fatturazione che specificano quando creare automaticamente una proposta di fatturazione. È ad esempio possibile creare una regola di fatturazione per creare una proposta di fatturazione quando il lavoro su un progetto è stato completato per il 25%, il 50%, il 75% e il 100%. 

Le proposte di fatturazione possono essere create per le seguenti transazioni:

-   ore, spese e altre transazioni di progetto
-   Importi trattenuti dai clienti nelle fatture di progetto precedenti.
-   Note di accredito
-   Importi pagati da un cliente prima dell'avvio di un progetto.

> [!NOTE]
> La funzionalità **Abilita l'ordinamento per risorsa durante la creazione della proposta di fattura del progetto** consente al contabile del progetto di ordinare le transazioni del progetto disponibili per la fatturazione dalla risorsa durante la creazione di una nuova proposta di fatturazione del progetto. La griglia che visualizza le transazioni di progetto disponibili avrà campi separati per **ID risorsa** e **Risorsa**. Questi campi consentono di filtrare e ordinare il nome della risorsa. Per impostazione predefinita, questa funzionalità è disattivata. Può essere abilitato usando la pagina **Gestione funzionalità** (**Aree di lavoro> Gestione funzionalità**). Contatta l'amministratore di sistema per assistenza nell'abilitazione di questa funzionalità.

È possibile creare transazioni sbilanciate in una proposta di fatturazione. È inoltre possibile modificare il prezzo di vendita per le transazioni orarie, di spesa, articolo e per le transazioni sbilanciate. Quando si registra una proposta di fatturazione, i prezzi aggiornati e le transazioni vengono aggiunti ai report di progetto e allo storico delle transazioni. 

Per creare più fatture cliente per un progetto, è necessario creare una proposta di fatturazione per ciascuna fattura. È ad esempio possibile creare fatture basate sul tipo di transazione. Per specificare le ore in una fattura cliente e gli articoli in un'altra, è necessario creare proposte di fatturazione separate per le transazioni orarie e per le transazioni sbilanciate. 

Se un progetto presenta più di una fonte di finanziamento, è possibile creare una proposta di fatturazione separata per ciascuna fonte di finanziamento. Nella pagina **Allocazioni regole di finanziamento** è possibile definire la percentuale dell'importo della transazione da allocare a ciascuna fonte di finanziamento e la fonte per la registrazione delle differenze di arrotondamento.

### <a name="creating-customer-invoices-from-invoice-proposals"></a>Creazione di fatture cliente in base alle proposte di fatturazione

Dopo aver creato e registrato una proposta di fatturazione, viene automaticamente creata una fattura cliente per le transazioni incluse nella proposta di fatturazione. 

Prima di registrare una proposta di fatturazione è possibile aggiungervi o eliminare transazioni. È ad esempio possibile rimuovere le transazioni di spesa registrate in un progetto ma non addebitabili al cliente. 

Se l'organizzazione richiede che le proposte di fatturazione vengano riviste prima della registrazione, è consigliabile approvare la proposta di fatturazione tramite il flusso di lavoro "Rivedi proposte di fatturazione progetto" prima che venga registrata.

### <a name="view-grant-information-on-project-invoice-list-pages"></a>Visualizzare le informazioni sulla concessione nelle pagine dell'elenco delle fatture del progetto

Gli utenti del settore pubblico possono aggiungere i valori di **ID concessione** e **Nome concessione** alle pagine elenco **Proposte di fatturazione del progetto** e **Fatture del progetto**. Queste colonne sono abilitate usando la funzionalità **Aggiungi informazioni sulla concessione alle pagine elenco delle fatture del progetto**. Questa funzionalità è disattivata per impostazione predefinita e può essere abilitata in **Aree di lavoro > Gestione funzionalità**. Contatta l'amministratore di sistema per assistenza nell'abilitazione di questa funzionalità.

## <a name="on-account-invoicing"></a>Fatturazione acconti
L'importo immesso per un progetto in una fattura di acconto è basato sulla tempistica, la percentuale di completamento e altre condizioni di fatturazione specificate nel contratto di progetto correlato. L'importo non viene calcolato in base alle ore, agli articoli, alle spese o alle commissioni registrate nel progetto. 

È innanzitutto necessario creare una transazione di acconto per un progetto di tempistica e materiali o un progetto a prezzo fisso prima di poter aggiungere la transazione di acconto in una fattura progetto. Nella transazione di acconto, immettere l'importo da fatturare a un cliente. Per creare una fattura di progetto per l'importo, creare una fattura preliminare (proposta di fatturazione). In una proposta di fatturazione selezionare la transazione di acconto. È possibile esaminare le informazioni di acconto nella proposta di fatturazione prima di creare una fattura progetto. 

### <a name="fixed-price-projects"></a>Progetti a prezzo fisso
Per i progetti a prezzo fisso, le transazioni di acconto si basano su una disposizione di fatturazione a fasi stabilita, per unità di consegna o progressiva specificata in un contratto di progetto. Una riga viene creata per ciascun pagamento che deve essere ricevuto dal cliente del progetto. Non è richiesta alcuna detrazione.

### <a name="time-and-material-projects"></a>Progetti di tempistica e materiali

Per i progetti di tempistica e materiali, è possibile fatturare un cliente o un'altra fonte di finanziamento per un importo di pagamento anticipato utilizzando una proposta di fatturazione di acconto. Immettere le transazioni di acconto come una riga. Facoltativamente, è possibile immettere ulteriori righe come detrazioni per compensare tutti i pagamenti anticipati già effettuati dal cliente. Per creare le righe di detrazione, immettere un segno meno prima dell'importo.

## <a name="invoice-control"></a>Controllo fatture
È possibile utilizzare il controllo fatture per tenere traccia delle transazioni fatturate e non fatturate e per analizzare le transazioni rispetto alle offerte e ottenere una visualizzazione completa dei progetti dalla fase dell'offerta alla conclusione. È possibile visualizzare quali transazioni sono state addebitate a un progetto specifico e quali righe sono state fatturate. È inoltre possibile visualizzare le singole transazioni in modo da poterle rettificare dopo la registrazione.

## <a name="invoicing-fixed-price-projects"></a>Fatturazione di progetti a prezzo fisso
Per fatturare un progetto a prezzo fisso è necessario definire un programma di fatturazione e completare la procedura di fatturazione.

### <a name="billing-schedule"></a>Programma di fatturazione

È possibile fatturare progetti a prezzo fisso in base a un programma di fatturazione. Il programma di fatturazione viene definito come uno o più punti cardine del progetto. Per ogni punto cardine, è possibile definire una data, una valuta di vendita, un prezzo di vendita e un'attività specifici. 

È ad esempio possibile impostare il seguente programma di fatturazione:

-   20% al momento della firma del contratto per il progetto
-   30% alla prima consegna
-   15% alla seconda consegna
-   35% alla consegna finale

### <a name="invoicing-procedure"></a>Procedura di fatturazione

Quando i pagamenti cardine sono pronti per essere fatturati, utilizzare la procedura relativa alla fatturazione degli importi di acconto.

## <a name="vendor-invoicing"></a>Fatturazione fornitore
Quando si ordina un articolo da un fornitore e lo si assegna a un progetto, la proprietà riga che si seleziona per la riga ordine fornitore per l'articolo determina se l'articolo acquistato viene fatturato a un cliente. Se si impostano proprietà riga predefinite, tali proprietà vengono visualizzate per l'articolo nella riga ordine fornitore (**Dettagli riga > Progetto > Proprietà riga**). Sono disponibili due metodi per modificare la proprietà riga:

-   Fatturare al cliente del progetto l'articolo. Per fare ciò, impostare la proprietà riga per l'articolo su un valore addebitabile nell'ordine fornitore e quindi fatturare al cliente mediante il metodo di fatturazione corretto per il progetto.
-   Non fatturare al cliente del progetto l'articolo. Per fare ciò, non selezionare la proprietà della riga **Addebitabile** nella riga ordine fornitore per l'articolo. È quindi possibile fatturare l'ordine fornitore e non saranno necessarie ulteriori operazioni.

> [!NOTE] 
> Le righe della ritenuta rilasciata non sono addebitabili per impostazione predefinita. Non è pertanto possibile creare una proposta di fatturazione per la ritenuta rilasciata.

## <a name="credit-notes"></a>Note di accredito
Quando un importo in una fattura cliente ha un valore negativo, la fattura viene classificata Quando il documento viene stampato presenta il titolo "Nota di accredito". 

Quando si crea una nota di accredito per accreditare un importo precedentemente fatturato, è necessario selezionare prima l'importo fatturato per l'accredito. Successivamente sarà necessario creare una nota di accredito effettuando la stessa procedura utilizzata per creare una fattura cliente ordinaria, Si selezionano le transazioni precedentemente registrate in una fattura cliente, quindi si crea e registra una proposta di nota di accredito. 

Lo stesso documento può includere transazioni selezionate per l'accredito, transazioni di accredito e transazioni che sono state registrate. A seconda che l'importo totale sia positivo o negativo, il documento verrà classificato come fattura o come nota di accredito. 

Per accreditare un importo fatturato, è necessario prima selezionare l'importo fatturato da accreditate, quindi creare una nota di accredito. Una nota di accredito si crea effettuando la stessa procedura utilizzata per generare una fattura cliente. 

È possibile creare una fattura con un importo negativo; in questo caso la fattura viene classificata come nota di accredito. Per creare e stampare una nota di accredito, è necessario selezionare le transazioni precedentemente registrate per una fattura cliente e, successivamente, modificarle. A meno che l'indirizzo della persona giuridica si trovi in Germania, il titolo della fattura è "Fattura correttiva".





[!INCLUDE[footer-include](../../includes/footer-banner.md)]