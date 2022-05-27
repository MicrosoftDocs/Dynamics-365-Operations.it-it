---
title: Riscossioni nella contabilità clienti
description: Le informazioni sulla riscossione della contabilità clienti vengono gestite in una visualizzazione centrale utilizzando la pagina Riscossioni di Microsoft Dynamics 365 Finance. I responsabili crediti e riscossioni possono utilizzare tale visualizzazione centrale per gestire le riscossioni. Gli agenti di riscossione possono avviare il processo di riscossione dagli elenchi di clienti generati utilizzando criteri di riscossione predefiniti o nella pagina Clienti.
author: ShivamPandey-msft
ms.date: 10/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustAgingSnapshot, CustBankAccounts, CustCollections, CustCollectionsActivitiesListPage, CustCollectionsAgent, CustCollectionsCaseListPage, CustCollectionsPool, CustCollectionsPoolsListPage, CustTable
audience: Application User
ms.reviewer: kfend
ms.custom: 3061
ms.assetid: fd851520-8d93-434b-845b-be127d6ac3a6
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 03d1304c39628323c6d6e15181263a73ba965930
ms.sourcegitcommit: 04e6c1c9400e1b582180cf3e0e4767434e736c26
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2022
ms.locfileid: "8710359"
---
# <a name="collections-in-accounts-receivable"></a>Riscossioni nella contabilità clienti

[!include [banner](../includes/banner.md)]

Le informazioni sulla riscossione della contabilità clienti vengono gestite in una visualizzazione centrale utilizzando la pagina Riscossioni di Microsoft Dynamics 365 Finance. I responsabili crediti e riscossioni possono utilizzare tale visualizzazione centrale per gestire le riscossioni. Gli agenti di riscossione possono avviare il processo di riscossione dagli elenchi di clienti generati utilizzando criteri di riscossione predefiniti o dalla pagina Clienti.

Prima di iniziare a impostare o a utilizzare le riscossioni, è necessario comprendere i concetti seguenti:
-   Gli snapshot di aging dei clienti contengono informazioni sui saldi con aging in un momento specifico del tempo
-   I pool di clienti per la riscossione facilitano l'organizzazione del lavoro
-   Gli agenti di riscossione possono avere propri pool di clienti
-   Le pagine elenco consentono di organizzare casi, attività e clienti di riscossione
-   Tutte le informazioni sulla riscossione relative a un cliente si trovano in un'unica pagina in cui è possibile intraprendere le azioni necessarie
-   È possibile rinunciare all'addebito di interessi e commissioni, ripristinarli o stornarli in un unico passaggio
-   È possibile creare transazioni di annullamento in un unico passaggio
-   È possibile elaborare pagamenti NSF (Non Sufficient Funds, senza copertura) in un unico passaggio

Nelle sezioni seguenti viene descritto ogni concetto.

## <a name="customer-aging-snapshots"></a>Snapshot di aging cliente 
Uno snapshot di aging contiene i saldi con aging calcolati per un cliente in un determinato momento. Queste informazioni vengono visualizzate nella pagina elenco Saldi con aging e nella pagina Riscossioni. Per visualizzare le informazioni sulle pagine elenco di riscossione, è necessario creare uno snapshot di aging. 

Per ogni cliente, uno snapshot di aging contiene l'intestazione dello snapshot e i record di dettaglio corrispondenti a ciascun periodo di aging nella definizione del periodo di aging. 

L'intestazione dello snapshot di aging contiene l'importo totale dovuto, il limite di credito, l'importo del documento di trasporto, l'importo dell'ordine cliente, il numero di transazioni controverse e l'importo totale delle transazioni controverse per il conto cliente. Nel calcolo di questi importi sono incluse tutte le transazioni del cliente. L'importo totale dovuto, il limite di credito, l'importo del documento di trasporto e l'importo dell'ordine cliente vengono visualizzati nel riquadro Dettaglio informazioni relativo alle informazioni crediti della pagina Riscossioni. 

Per ogni periodo di aging nella definizione del periodo di aging viene creato un record di dettaglio dello snapshot di aging. Ogni record di dettaglio dello snapshot di aging contiene l'ID del periodo di aging e l'importo totale delle transazioni con le date comprese nel periodo di aging. Le transazioni vengono assegnate a un periodo di aging, ad esempio 30 giorni oltre la scadenza. La data è relativa alla data specificata in Aging a partire da al momento della creazione dello snapshot di aging. Queste informazioni vengono visualizzate nella pagina elenco Saldi con aging e nel riquadro Dettaglio informazioni relativo ai saldi con aging nella pagina Riscossioni.

## <a name="collections-customer-pools"></a>Pool di clienti per riscossioni
I pool di clienti sono query che definiscono un gruppo di record cliente che possono essere visualizzati e gestiti per i processi di riscossione o di aging. Utilizzare i pool di clienti per filtrare le informazioni presenti nelle pagine elenco Saldi con aging, Attività di riscossione e Casi di riscossione. È inoltre possibile utilizzare i pool di clienti per filtrare i conti cliente inclusi quando vengono creati gli snapshot di aging.

## <a name="collections-agents"></a>Agenti di riscossione
Per impostazione predefinita, gli utenti possono visualizzare tutte le informazioni sui clienti nelle pagine elenco di riscossione. È possibile utilizzare i record agente di riscossione per determinare i pool di clienti disponibili per filtrare le informazioni presenti nelle pagine elenco di riscossione e nella pagina Riscossioni. 

Un agente di riscossione è una persona che lavora con i clienti per accertarsi che i pagamenti vengano riscossi con puntualità. Gli agenti di riscossione sono lavoratori assegnati agli utenti nella pagina di configurazione dell'utente.

## <a name="collections-list-pages"></a> Pagine elenco Riscossioni 
Le pagine elenco seguenti facilitano l'organizzazione delle informazioni sulla riscossione.
-   Saldi con aging: nelle colonne della pagina elenco vengono visualizzati i saldi dei clienti e gli importi con aging in base al periodo di aging. Tali informazioni vengono archiviate in uno snapshot di aging. I periodi di aging vengono determinati dalla definizione del periodo di aging utilizzata. La definizione del periodo di aging viene ricavata dal pool di clienti, se ne è stato specificato uno per la query sul pool. Se il pool di clienti non contiene una definizione del periodo di aging, viene utilizzata la definizione del periodo di aging predefinita specificata nella pagina Parametri contabilità clienti. Se non è stata specificata alcuna definizione del periodo di aging predefinita, viene utilizzata la prima definizione del periodo di aging della pagina Definizioni periodo di aging.
-   Attività di riscossione: nelle colonne della pagina elenco vengono visualizzate le attività identificate come attività di riscossione. Tali attività vengono create mediante la pagina Riscossione. Utilizzare le attività per tenere traccia del lavoro svolto in relazione alle riscossioni.
-   Casi di riscossione: nelle colonne della pagina elenco vengono visualizzate le informazioni relative ai casi che hanno una categoria del caso di tipo Riscossioni.

> [!NOTE]
> Per poter visualizzare le informazioni in queste pagine elenco, è necessario creare uno snapshot di aging. Le informazioni vengono visualizzate solo per i clienti per i quali è stato creato uno snapshot di aging. È possibile filtrare ulteriormente i record presenti nella pagina elenco nel modo seguente:
> <li>Per impostazione predefinita, un utente di Finance and Operations ha accesso a tutti i clienti che dispongono di uno snapshot di aging.</li>
> <li>Se sono presenti pool di clienti, è necessario che un utente sia impostato come agente di riscossione per utilizzare i pool per filtrare le informazioni nelle pagine elenco di riscossione. Le informazioni sono limitate ai clienti inclusi nel pool di clienti selezionato.</li>
> <li>Se un utente viene impostato come agente di riscossione, nella pagina elenco saranno disponibili solo i pool selezionati per tale agente di riscossione. Se il pulsante Consenti ad agente di visualizzare tutti i pool di clienti è selezionato nella pagina Agenti di riscossione per un agente di riscossione specifico, tutti i pool sono disponibili per tale agente.</li>


## <a name="collections-page"></a> Pagina Riscossioni
Utilizzare la pagina Riscossioni per visualizzare, gestire e intraprendere le azioni necessarie sui casi, le attività e le informazioni sulla riscossione per un cliente. 

Nel riquadro superiore vengono visualizzati i casi per il cliente selezionato. Nel riquadro centrale vengono visualizzate le transazioni per il cliente. Nel riquadro inferiore vengono visualizzate le attività per il cliente. È possibile creare casi di riscossione per tenere traccia delle informazioni sulla riscossione per una o più transazioni e attività. Le informazioni presenti nei riquadri superiore e inferiore possono essere filtrate in base al caso. 

Nei riquadri Dettaglio informazioni vengono visualizzati i saldi con aging e le informazioni sul limite di credito per il cliente selezionato. Tali informazioni vengono archiviate nello snapshot di aging. Se necessario, è possibile aggiornare lo snapshot di aging con le informazioni correnti. 

Il riquadro azioni contiene i pulsanti che consentono di visualizzare le informazioni correlate per il cliente, il caso, la transazione o l'attività selezionata. È inoltre possibile eseguire azioni comuni quali la modifica dello stato di riscossione di una transazione, l'invio di corrispondenza via posta elettronica tramite l'integrazione con il provider di posta elettronica, il rimborso dei clienti, l'elaborazione di pagamenti senza copertura e l'annullamento di saldi inesigibili.

## <a name="waive-reinstate-or-reverse-interest-and-fees"></a> Rinunciare all'addebito di interessi o commissioni, ripristinarli o stornarli 
È possibile rinunciare all'addebito di note d'interesse complete o di commissioni e interessi sulle transazioni che fanno parte di una nota d'interesse, stornarle o ripristinarle. È possibile effettuare tali operazioni dalla scheda Raccogli nel riquadro azioni della pagina elenco Tutti i clienti facendo clic su Nota d'interesse, Interessi transazione o Commissioni. 

Tali rettifiche hanno effetto solo sulle note d'interesse e sugli interessi e le commissioni in esse inclusi. Utilizzare i passaggi descritti nella sezione "Creare transazioni di annullamento in un unico passaggio" per annullare tutte le spese dovute da un cliente.

Per ulteriori informazioni, vedere [Creare un codice interessi con un intervallo](tasks/create-interest-code-range.md) e [Elaborare interessi](tasks/process-interest.md). 

## <a name="create-writeoff-transactions"></a>Creare transazioni di annullamento
È possibile annullare crediti inesigibili facendo clic su Annulla nel modulo Riscossioni e nelle pagine elenco Saldi con aging, Clienti e Fatture cliente aperte. 

Quando si annullano alcune transazioni per un cliente, tutte le transazioni del cliente vengono contrassegnate automaticamente per la liquidazione. L'importo annullato dipende dall'importo netto delle transazioni contrassegnate. La transazione di annullamento viene creata in un giornale di registrazione generale e può contenere fino a tre tipi di righe di giornale di registrazione.

-   Il primo tipo di riga di giornale contiene la voce di annullamento del cliente. Se le transazioni contrassegnate contengono più combinazioni di codice valuta, dimensione e profilo di registrazione, viene creata una riga di giornale separata per ciascuna combinazione.
-   Il secondo tipo di riga di giornale contiene la voce di annullamento di contabilità generale. Se le transazioni contrassegnate contengono più combinazioni di codice valuta, dimensione e profilo di registrazione, viene creata una riga di giornale separata per ciascuna combinazione.
-   Il terzo tipo di riga di giornale contiene le informazioni sull'annullamento della contabilità generale per l'IVA. Questa riga del giornale di registrazione viene creata solo se nella pagina di parametri di contabilità clienti è selezionato il pulsante IVA separata. Se le transazioni contrassegnate contengono più combinazioni di conto IVA a debito, dimensione e codice IVA, viene creata una riga di giornale separata per ciascuna combinazione.

La transazione di annullamento viene creata nella valuta della transazione.

Per ulteriori informazioni, vedere [Creare un giornale di registrazione annullamento per un cliente](tasks/create-write-off-journal-customer.md).

## <a name="process-not-sufficient-funds-nsf-payments"></a>Elaborare un pagamento NSF (Non Sufficient Funds, senza copertura)  

È possibile elaborare pagamenti NSF facendo clic su Pagamento NSF nella pagina Riscossioni. Quando si fa clic su questo pulsante, il pagamento viene annullato. Se al cliente viene applicata una commissione NSF, viene creata una transazione di spese in un giornale di registrazione pagamenti. L'importo della commissione si basa sulle impostazioni delle spese automatiche. Le spese automatiche che si applicano ai pagamenti NSF vengono specificate in base al gruppo di spese varie selezionato nella pagina Conti bancari per il conto bancario interessato.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
