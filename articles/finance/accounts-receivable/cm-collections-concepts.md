---
title: Concetti chiave della gestione delle riscossioni
description: Gli argomenti definiscono i concetti chiave della gestione delle riscossioni.
author: mikefalkner
manager: AnnBe
ms.date: 11/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: eb2ec9969bdec985e1f8c731eade1c1a81a4766c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993016"
---
# <a name="collections-management-key-concepts"></a>Concetti chiave della gestione delle riscossioni

[!include [banner](../includes/banner.md)]

Prima di iniziare a impostare o a utilizzare le riscossioni, è necessario comprendere i concetti seguenti:

- Gli snapshot di aging dei clienti contengono informazioni sui saldi con aging in un momento specifico nel tempo.
- I pool di clienti per riscossioni facilitano l'organizzazione del lavoro.
- Gli agenti di riscossione possono avere pool di clienti propri.
- Le pagine elenco consentono di organizzare casi, attività e clienti di riscossione.
- Tutte le informazioni sulle riscossioni relative a un cliente si trovano in un'unica pagina in cui è possibile intraprendere le azioni necessarie.
- È possibile rinunciare a interessi e commissioni, ripristinarli oppure stornarli in un unico passaggio.
- È possibile creare transazioni di annullamento in un unico passaggio.
- È possibile elaborare pagamenti NSF (Non Sufficient Funds, senza copertura) in un unico passaggio.

Questo argomento descrive ogni concetto.

## <a name="customer-aging-snapshots"></a>Snapshot di aging cliente 

Uno snapshot di aging contiene i saldi con aging calcolati per un cliente in un determinato momento. Queste informazioni vengono visualizzate nella pagina elenco **Saldi con aging** e nella pagina **Riscossioni**. Per visualizzare le informazioni nelle pagine elenco di riscossione, è necessario creare uno snapshot di aging (**Saldi con aging**, **Attività di riscossione** e **Casi di riscossione**).

Per ogni cliente, uno snapshot di aging include l'intestazione dello snapshot e i record di dettaglio corrispondenti a ciascun periodo di aging nella definizione del periodo di aging.

L'intestazione dello snapshot di aging contiene l'importo totale dovuto, il limite di credito, l'importo del documento di trasporto, l'importo dell'ordine cliente, il numero di transazioni controverse e l'importo totale delle transazioni controverse per il conto cliente. Nel calcolo di questi importi sono incluse tutte le transazioni del cliente. L'importo totale dovuto, il limite di credito, l'importo del documento di trasporto e l'importo dell'ordine cliente vengono visualizzati nel riquadro Dettaglio informazioni **Informazioni crediti** della pagina **Riscossioni**.

Per ogni periodo di aging nella definizione del periodo di aging viene creato un record di dettaglio dello snapshot di aging. Ogni record di dettaglio contiene l'ID del periodo di aging e l'importo totale delle transazioni che hanno date comprese nel periodo di aging. Le transazioni vengono assegnate a un periodo di aging, ad esempio 30 giorni oltre la scadenza. La data è relativa alla data in **Aging a partire da** specificata al momento della creazione dello snapshot di aging. Queste informazioni vengono visualizzate nella pagina elenco **Saldi con aging** e nel riquadro Dettaglio informazioni **Saldi con aging** nella pagina **Riscossioni**.

## <a name="collections-customer-pools"></a> Pool di clienti per riscossioni 

I pool di clienti sono query che definiscono un gruppo di record cliente. È possibile utilizzare questi record raggruppati per visualizzare informazioni per i conti cliente inclusi e per gestire i processi di riscossione o di aging per tali account. È possibile utilizzare i pool di clienti per filtrare le informazioni presenti nelle pagine elenco di riscossione. È anche possibile utilizzarli per filtrare i conti cliente inclusi quando vengono creati gli snapshot di aging.

## <a name="collections-agents"></a>Agenti di riscossione

Per impostazione predefinita, gli utenti possono visualizzare tutte le informazioni sui clienti nelle pagine elenco di riscossione. I record agente di riscossione consentono di determinare i pool di clienti utilizzabili per filtrare le informazioni presenti nelle pagine elenco di riscossione e nella pagina **Riscossioni**.

Gli agenti di riscossione lavorano con i clienti per accertarsi che i pagamenti vengano riscossi con puntualità. Sono lavoratori assegnati agli utenti nella pagina **Impostazione utente**.

## <a name="collections-list-pages"></a>Pagine elenco di riscossione

Le pagine elenco seguenti facilitano l'organizzazione delle informazioni sulla riscossione:

- **Saldi con aging:** nelle colonne di questa pagina elenco vengono visualizzati i saldi dei clienti e gli importi con aging in base al periodo di aging. Tali informazioni vengono archiviate in uno snapshot di aging. I periodi di aging vengono determinati dalla definizione del periodo di aging utilizzata. La definizione del periodo di aging viene ricavata dal pool di clienti, se ne è stato specificato uno per la query sul pool. Se il pool di clienti non contiene una definizione del periodo di aging, viene utilizzata la definizione del periodo di aging predefinita specificata nella pagina **Parametri contabilità clienti**. Se non è stata specificata alcuna definizione del periodo di aging predefinita, viene utilizzata la prima definizione del periodo di aging della pagina **Definizioni periodo di aging**.
- **Attività di riscossione:** nelle colonne di questa pagina elenco vengono visualizzate le attività identificate come attività di riscossione. Tali attività vengono create nella pagina **Riscossioni**. Le attività sono utilizzate per tenere traccia del lavoro svolto in relazione alle riscossioni.
- **Casi di riscossione:** nelle colonne di questa pagina elenco vengono visualizzate le informazioni relative ai casi che appartengono a una categoria di casidi tipo **Riscossioni**.

### <a name="aging-snapshots"></a>Snapshot di aging

Per poter visualizzare le informazioni sulle pagine elenco di riscossione, è necessario creare uno snapshot di aging. Le informazioni vengono visualizzate solo per i clienti per i quali è stato creato uno snapshot di aging. È possibile filtrare ulteriormente i record presenti nella pagina elenco nel modo seguente:

- Per impostazione predefinita, gli utenti hanno accesso a tutti i clienti che dispongono di uno snapshot di aging.
- Se sono presenti pool di clienti, è necessario che un utente sia impostato come agente di riscossione per utilizzare i pool per filtrare le informazioni nelle pagine elenco di riscossione. Le informazioni sono limitate ai clienti inclusi nel pool di clienti selezionato.
- Se un utente viene impostato come agente di riscossione, nelle pagine elenco di riscossione saranno disponibili solo i pool selezionati per tale agente di riscossione. Se il pulsante **Consenti ad agente di visualizzare tutti i pool di clienti** è selezionato nella pagina **Agenti di riscossione** per l'agente di riscossione, tutti i pool sono disponibili per tale agente.

## <a name="collections-page"></a> Pagina Riscossioni

È possibile utilizzare la pagina **Riscossioni** per visualizzare, gestire e intraprendere le azioni necessarie sui casi, le attività e le informazioni sulla riscossione per un cliente.

La sezione superiore della pagina mostra i casi per il cliente selezionato, la sezione centrale mostra le transazioni per il cliente e la sezione inferiore mostra le attività per il cliente. È possibile creare casi di riscossione per tenere traccia delle informazioni sulla riscossione per una o più transazioni e attività. Le informazioni presenti nelle sezioni superiore e inferiore possono essere filtrate in base al caso.

Nei riquadri Dettaglio informazioni vengono visualizzati i saldi con aging e le informazioni sul limite di credito per il cliente selezionato. Tali informazioni vengono archiviate nello snapshot di aging. Se necessario, è possibile aggiornare lo snapshot di aging con le informazioni correnti.

Il riquadro azioni contiene i pulsanti che consentono di visualizzare le informazioni correlate per il cliente, il caso, la transazione o l'attività selezionata. È inoltre possibile eseguire azioni comuni quali la modifica dello stato di riscossione di una transazione, l'invio di corrispondenza via posta elettronica tramite l'integrazione con il provider di posta elettronica, il rimborso dei clienti, l'elaborazione di pagamenti senza copertura e l'annullamento di saldi inesigibili.

## <a name="waiving-reinstating-or-reversing-interest-and-fees"></a>Rinunciare all'addebito di interessi o commissioni, ripristinarli o stornarli

È possibile rinunciare all'addebito di note d'interesse complete o di commissioni e interessi sulle transazioni che fanno parte di una nota d'interesse, stornarle o ripristinarle. Nella scheda **Raccogli** nel riquadro azioni della pagina elenco **Tutti i clienti** selezionare **Nota d'interesse**, **Interessi transazione** o **Commissioni**.

Tali rettifiche hanno effetto solo sulle note d'interesse e sugli interessi e le commissioni in esse inclusi. Per informazioni su come annullare tutte le spese dovute da un cliente, consultare la sezione [Creare transazioni di annullamento](#creating-write-off-transactions) di questo argomento.

Per ulteriori informazioni, vedere Creare un codice interessi con un intervallo e Elaborare interessi.

## <a name="creating-write-off-transactions"></a>Creare transazioni di annullamento

È possibile annullare crediti inesigibili selezionando **Annulla** nella pagina **Riscossioni** e nelle pagine elenco di riscossione.

Quando si annullano le transazioni per un cliente, tutte le transazioni di quel cliente vengono contrassegnate automaticamente per la liquidazione. L'importo annullato dipende dall'importo netto delle transazioni contrassegnate. La transazione di annullamento viene creata in un giornale di registrazione generale e può contenere fino a tre tipi di righe di giornale di registrazione:

- Il primo tipo di riga di giornale contiene la voce di annullamento del cliente. Se le transazioni contrassegnate contengono più combinazioni di codici valuta, dimensioni e profili di registrazione, viene creata una riga di giornale separata per ciascuna combinazione.
- Il secondo tipo di riga di giornale contiene la voce di annullamento di contabilità generale. Se le transazioni contrassegnate contengono più combinazioni di codici valuta, dimensioni e profili di registrazione, viene creata una riga di giornale separata per ciascuna combinazione.
- Il terzo tipo di riga di giornale contiene le informazioni sull'annullamento della contabilità generale per l'IVA. Questa riga del giornale di registrazione viene creata solo se nella pagina **Parametri contabilità clienti** è selezionata l'opzione **IVA separata**. Se le transazioni contrassegnate contengono più combinazioni di conti IVA a debito, dimensioni e codici IVA, viene creata una riga di giornale separata per ciascuna combinazione. La transazione di annullamento viene creata nella valuta della transazione. Per ulteriori informazioni, vedere Creare un giornale di registrazione annullamento per un cliente.

## <a name="process-nsf-payments"></a>Elaborare pagamenti NSF

È possibile elaborare pagamenti NSF (Non Sufficient Funds, senza copertura) selezionando **Pagamento NSF** nella pagina **Riscossioni**. Quando si seleziona questo pulsante, il pagamento viene annullato. Se al cliente viene applicata una commissione NSF, viene creata una transazione di spese in un giornale di registrazione pagamenti. L'importo della commissione si basa sulle impostazioni delle spese automatiche. Le spese automatiche che si applicano ai pagamenti NSF vengono specificate in base al gruppo di spese varie selezionato nella pagina **Conti bancari** per il conto bancario interessato.

## <a name="additional-resources"></a>Risorse aggiuntive

[Impostazione dei parametri di gestione dei crediti cliente](./cm-credit-mgmt-setup.md)

[Informazioni sull'impostazione della gestione dei crediti cliente](./cm-setup-information.md)

[Aggiungere informazioni sulla gestione dei crediti per un cliente](./cm-add-credit-mgmt-information-customer.md)

[Gruppi di crediti cliente](./cm-customer-credit-groups.md)

[Correzioni dei limiti di credito dei clienti](./cm-credit-limit-adjustments.md)

[Sospensioni credito per ordini cliente](./cm-sales-order-credit-holds.md)

[Attività periodiche di gestione dei crediti cliente](./cm-periodic-tasks.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]