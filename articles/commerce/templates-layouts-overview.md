---
title: Panoramica modelli e layout
description: In questo argomento vengono descritti i modelli e i layout in Microsoft Dynamics 365 Commerce.
author: phinneyridge
ms.date: 12/12/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 888f5295dce601d4ce5d823f14169bbcdfe48d6b
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2022
ms.locfileid: "7986096"
---
# <a name="templates-and-layouts-overview"></a>Panoramica modelli e layout


[!include [banner](includes/banner.md)]

I modelli sono un elemento chiave del modello di pagina di Microsoft Dynamics 365 Commerce. Se lo scopo è di ottimizzare l'efficienza e la coerenza dei flussi di lavoro di creazione di siti, è importante apprendere a utilizzare al meglio i modelli per il proprio sito Web. Le decisioni iniziali sulla struttura dei modelli sono importanti e possono influenzare significativamente i costi e l'agilità degli aggiornamenti giornalieri, stagionali e a livello di sito del marchio. I modelli ben strutturati presentano anche altri vantaggi. Ad esempio, consentono di migliorare i punteggi di ottimizzazione del motore di ricerca a livello di sito e riducono al minimo il numero di bug.

Un ottimo modo di iniziare a utilizzare i modelli è comprendere i vantaggi funzionali di modelli e layout, le differenze tra gli stessi e la gerarchia.

Nella figura seguente è illustrata la gerarchia dei modelli di pagina dietro una pagina Web di cui è stato eseguito il rendering.

![Diagramma del modello di pagina.](../commerce/media/page-model-diagram.png)

| Entità        | Funzione di base |
|---------------|----------------|
| Modello      | I modelli definiscono le opzioni per i moduli e lo scaffolding di base per un set di layout e istanze di pagina. |
| Layout        | I layout definiscono la selezione e la disposizione finale dei moduli per una pagina o un set di pagine. |
| Istanza di pagina | Le istanze di pagina definiscono i dati e il contenuto di specifiche pagine. |

## <a name="templates"></a>Modelli

I modelli si trovano nella parte superiore della gerarchia dei modelli di pagina di Dynamics 365 Commerce e rappresentano un passaggio iniziale importante per la configurazione del sito. Concettualmente, i modelli consentono di controllare la coerenza in una famiglia di pagine e layout figlio definendo la struttura di base e le opzioni di creazione per i flussi di lavoro di creazione di layout e pagine downstream. I modelli possono contribuire a semplificare il processo di creazione di contenuti tramite elementi predefiniti gestiti centralmente (ad esempio intestazioni e piè di pagina) e flussi di creazione guidati che garantiscono scelte di configurazione di moduli conformi al marchio.

### <a name="controlling-consistency"></a>Controllare la coerenza

Quando si progetta un modello, la decisione aziendale più importante da prendere è il tipo di controllo che il modello deve avere sul processo di creazione di pagine. Un modello che lascia qualsiasi soluzione a un autore downstream è il tipo più semplice di modello da creare, ma potrebbe avere conseguenze a lungo termine per la gestione delle pagine create con lo stesso. Un modello ben scritto fornisce istruzioni e un'esperienza di creazione semplificata, ma offre agli autori anche una flessibilità sufficiente per completare la propria attività. Tutti questi aspetti dipendono dal livello di controllo applicato dal modello.

I modelli possono consentire agli autori di contenuti di essere più produttivi e di rimanere conformi al marchio nei seguenti modi:

- Limitano i moduli che possono essere utilizzati in una pagina.
- Suggeriscono il modulo predefinito e le scelte di configurazione.
- Eseguono esplicitamente alcune scelte relative a moduli e configurazioni che sono controllate a livello di modello. Questo processo è anche noto come *blocco* di un'impostazione.

Nell'esempio seguente viene illustrato il modo in cui un modello di base (modello X) può essere configurato:

- Tutti i layout figlio del modello X devono avere un contenitore intestazione, un contenitore corpo e un contenitore piè di pagina.
- Nel modello X, la configurazione del contenitore intestazione è bloccata e può essere modificata solo nel modello X stesso. Tutti i layout e le pagine figlio hanno sempre questa intestazione.
- Il contenitore corpo necessita almeno un modulo e fino a un massimo di dieci moduli. Questi moduli sono definiti da layout e pagine downstream.
- Per il contenitore corpo, sono disponibili i moduli Hero, Funzionalità, Sequenza e Banner.
- Un contenitore piè di pagina è configurato nel modello X, ma può essere sostituito da layout e pagine downstream.

Il modello in questo esempio definisce una struttura semplice e un insieme di opzioni per gli autori di contenuti downstream. Da notare che alcune parti di una pagina (in questo caso l'intestazione) sono definite e bloccate completamente nel modello e non possono essere modificate da autori downstream. Altre parti (in questo caso il corpo) possono essere definite da autori downstream in base a specifiche istruzioni (in questo caso, un numero minimo e un numero massimo di moduli di tipi specifici). E altre parti (in questo caso, il piè di pagina) sono definite nel modello ma possono essere sostituite dagli autori downstream.

Un passaggio iniziale importante per amministratori di siti e marchi consiste nel trovare il giusto equilibrio tra vincolo e flessibilità degli autori di pagine e layout figlio. Quando i modelli sono utilizzati, questo equilibrio è totalmente configurabile. Determina se gli elementi della pagina vengono aggiornati centralmente (bloccati nel modello) o lasciati in singoli livelli figlio che sono più in basso nella gerarchia delle pagine.

Per iniziare a utilizzare i modelli, vedere [Utilizzare i modelli](work-with-templates.md).

## <a name="layouts"></a>Layout

I layout sono il livello successivo nella gerarchia dei modelli di pagina, sotto i modelli. Mentre un modello definisce tutti i moduli consentiti per una pagina, un layout è una selezione e una disposizione esplicita dei moduli. Le pagine sono il livello successivo nella gerarchia dei modelli di pagina, sotto i layout. Definiscono il contenuto localizzato per i moduli selezionati nel layout.

L'esempio seguente utilizza l'esempio di modello nella sezione precedente e illustra come configurare un layout di base:

- Per il modello padre del layout, il contenitore corpo deve avere tra uno e dieci moduli. Questi moduli possono essere solo moduli Hero, Funzionalità, Sequenza e Banner. Di conseguenza, il layout può definire la seguente selezione e disposizione dei moduli:

    - Il primo modulo nel contenitore corpo è un modulo Banner ed è seguito da un modulo Hero e due moduli Funzionalità.
    - Il primo modulo Funzionalità è allineato a sinistra e il secondo è allineato a destra.

- Anche se un piè di pagina predefinito viene ereditato dal modello padre, l'autore del modello ha lasciato il piè di pagina sbloccato. Di conseguenza, il layout può sostituirlo definendo un frammento piè di pagina differente.

Il layout in questo esempio definisce la disposizione finale dei moduli per le pagine figlio. Analogamente a un modello, un layout può definire proprietà di modulo bloccate o predefinite che verranno sempre ereditate dalle pagine figlio (ad esempio l'allineamento dei moduli Funzionalità). Il contenuto o i dati effettivi di ogni modulo nel layout vengono quindi definiti più in basso nella gerarchia, in ogni istanza di pagina figlio. Una distinzione importante è che i layout, a differenza delle relative pagine figlio, non contengono direttamente contenuto localizzabile. La funzione principale del layout è definire la disposizione finale e la configurazione predefinita dei moduli per le relative pagine figlio.

Questa gerarchia è efficace per due motivi. In primo luogo, i layout che condividono lo stesso modello padre vengono considerati come compatibili per gli scenari che comportano il cambiamento di layout. Di conseguenza, il layout di qualsiasi pagina può essere modificato in un altro layout della stessa gerarchia di modelli senza richiedere una nuova creazione del contenuto a livello di pagina. È possibile utilizzare questa funzionalità per eseguire aggiornamenti di progettazione stagionali, sperimentare o effettuare una riprogettazione permanente del sito. In secondo luogo, i layout offrono un altro modo di modificare centralmente elementi condivisi per un gruppo di pagine senza richiedere aggiornamenti di singole pagine. Ad esempio, se una categoria di prodotti ha 1.000 pagine che condividono lo stesso layout, i moduli possono essere riordinati nel layout e tale modifica verrà immediatamente riflessa in tutte le 1,000 pagine figlio.

La comprensione di questa gerarchia consente di fornire una struttura di sito agile ed efficiente che permette di ridurre i costi, è scalabile e genera migliori risultati con l'evoluzione del sito nel tempo.

### <a name="preset-and-custom-layouts"></a>Layout preimpostati e personalizzati

I layout nel sito possono essere *preimpostati* o *personalizzati*:

- I **layout preimpostati** consentono un flusso di lavoro di creazione di pagine in cui tutti i moduli sono già selezionati e disposti ed è richiesta solo l'immissione di dati. Questo approccio consente di risparmiare tempo quando si devono creare molte pagine che hanno gli stessi requisiti di layout. I layout preimpostati hanno una relazione uno-a-molti con le relative pagine figlio. Di conseguenza, un singolo layout preimpostato può essere utilizzato per controllare centralmente la disposizione dei moduli per centinaia o migliaia di pagine figlio.
- I **layout personalizzati** sono essenzialmente layout monouso incorporati in una pagina. Non sono esposti come opzione quando vengono create altre nuove pagine o in scenari che comportano il cambiamento di layout. Il vantaggio di tale approccio è che un autore può sperimentare creando una pagina che utilizza un layout personalizzato. Quindi, se l'autore desidera riutilizzare il layout per altre pagine, può essere convertito facilmente in un layout preimpostato. Il nuovo layout preimpostato viene quindi esposto come opzione in flussi di lavoro di creazione di pagine e in scenari che comportano il cambiamento di layout per le pagine nella stessa gerarchia di modelli. Viceversa, i layout preimpostati possono essere ramificati in layout personalizzati. In questo modo, un autore può separare una pagina dal layout preimpostato e creare un nuovo layout personalizzato monouso (questo nuovo layout personalizzato è ancora soggetto ai vincoli nel modello padre).

Il layout preimpostato e i layout personalizzati vengono modificati in diverse parti del set di strumenti di creazione. Poiché i layout personalizzati non hanno dipendenze da altre pagine, vengono modificati direttamente nell'editor di pagine. In questo caso, l'esistenza di un layout è perlopiù visibile all'utente ed è esposta solo nelle proprietà a livello di pagina e attraverso le azioni per le opzioni di layout. Tuttavia, poiché le modifiche ai layout preimpostati possono alterare molte pagine figlio, queste devono essere modificate nell'editor di layout, dove le azioni di pubblicazione prendono in conto tutto l'impatto downstream sulle pagine figlio.

Le seguenti illustrazioni visualizzano scenari per layout preimpostati e personalizzati.

![Scenari con layout preimpostati e personalizzati.](../commerce/media/template-figure1.png)

Per iniziare a utilizzare layout preimpostati, vedere [Utilizzare layout preimpostati](work-with-layouts.md).

## <a name="additional-resources"></a>Risorse aggiuntive

[Utilizzare i modelli](work-with-templates.md)

[Utilizzare i layout preimpostati](work-with-layouts.md)

[Utilizzare i gruppi di pubblicazione](publish-groups.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]