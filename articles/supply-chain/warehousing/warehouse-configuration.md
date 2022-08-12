---
title: Panoramica della configurazione del magazzino
description: Questo articolo illustra come configurare un magazzino. Sono riportate le informazioni su come abilitare un layout e i processi di magazzino.
author: perlynne
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventLocation, WHSLocation, WHSLocationBuild, WHSLocationProfile, WHSLocationType, WHSLocDirTable, WHSParameters, WHSWaveTemplateTable, WHSWorkPool, WHSWorkTemplateTable, WHSZone, WHSZoneGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "11554"
- intro-internal
ms.assetid: 262b7b88-2cce-44f7-9a5b-77c12af1be20
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7643a333c269a7e1976563ff0f10b89c1fb91674
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9065189"
---
# <a name="warehouse-configuration-overview"></a>Panoramica della configurazione del magazzino

[!include [banner](../includes/banner.md)]

Questo articolo illustra come configurare un magazzino. Sono riportate le informazioni su come abilitare un layout e i processi di magazzino.

> [!NOTE]
> Questo articolo si applica alle funzionalità nel modulo **Gestione magazzino**. Non viene applicato alle funzionalità di magazzino nel modulo **Gestione inventario**.

## <a name="warehouse-layout"></a>Layout magazzino
I processi di gestione del magazzino (WMS) in Supply Chain Management offre modalità flessibili per definire il layout di magazzino per soddisfare le mutevoli esigenze, in modo da poter raggiungere un efficienza di magazzino ottimale.

-   È possibile impostare aree di immagazzinamento ad alta priorità e a priorità bassa per un posizionamento ottimale delle merci.
-   È possibile suddividere il magazzino in aree per soddisfare varie esigenze di immagazzinamento, ad esempio requisiti della temperatura, o vari tassi di fatturato per gli articoli.
-   È possibile specificare le ubicazioni del magazzino a qualsiasi livello (ad esempio, sito, magazzino, sezione, scaffale, ripiano e posizione collocazione).
-   È possibile raggruppare le ubicazioni utilizzando le impostazioni del vincolo di capacità fisica.
-   È possibile controllare come vengono immagazzinati e prelevati gli articoli, in base a regole definite su query.

Per usare WMS in Supply Chain Management, occorre creare un magazzino e abilitarlo per WMS. Nella pagina **Magazzini** selezionare l'opzione **Usa processi di gestione del magazzino**.

### <a name="zone-groups-zones-location-types-and-locations"></a>Gruppi di zone, zone, tipi di ubicazione e ubicazioni

Durante il processo per abilitare un layout di magazzino, è necessario definire gruppi di zone magazzinaggio e zone, profili ubicazione, tipi di ubicazione e ubicazioni.

-   **Gruppi di zone**: Un raggruppamento logico o fisico di zone all'interno di un magazzino.
-   **Zone**: Un raggruppamento logico o fisico di ubicazioni all'interno di un magazzino.
-   **Profili ubicazione**: Un raggruppamento logico o fisico di ubicazioni con gli stessi criteri per il processo di ubicazione di magazzino (ad esempio, una combinazione di numeri di articolo differenti può essere archiviata in questa opzione e gli stessi vincoli di capacità fisica si applicano).
-   **Tipi di ubicazione**: Un raggruppamento logico o fisico di ubicazioni del magazzino. Ad esempio, è possibile creare un tipo di ubicazione per tutte le ubicazioni di gestione temporanea. Le impostazioni obbligatorie nella pagina **Parametri di gestione magazzino** determinano il processo di definizione dei tipi di ubicazione di gestione temporanea e del tipo di ubicazione di spedizione finale.
-   **Ubicazioni** – Il livello più basso di informazioni sull'ubicazione. Le ubicazioni vengono utilizzate per tenere traccia di dove vengono immagazzinate e prelevate le scorte disponibili in un magazzino.

Le entità create per definire il layout di magazzino vengono utilizzate nelle query impostate nei modelli di lavoro per determinare gli ordini di lavoro nel magazzino. Di conseguenza, quando si definiscono le zone, i tipi di ubicazione e così via, considerare come vengono utilizzate le diverse zone nel magazzino per i diversi processi. Inoltre, considerare fattori quali le caratteristiche fisiche di un'area specifica. Vi possono ad esempio essere aree in cui è possibile utilizzare solo un determinato tipo di carrello elevatore. Se invece l'azienda esegue la produzione nella stessa struttura in cui conserva i prodotti finiti, è possibile che si desideri creare un unico magazzino in Supply Chain Management, per poi separare le due funzioni creando due gruppi di area. Assegnare alle entità nomi descrittivi, in modo che sia facile identificarle quando le si utilizza nelle query del modello.

### <a name="location-stocking-limits-location-profiles-and-fixed-picking-locations"></a>Limiti stoccaggio ubicazione, profili dell'ubicazione e ubicazione di prelievo fisse

È necessario considerare il layout fisico del magazzino, sia per determinare le capacità di stoccaggio (limiti stoccaggio ubicazione e profili ubicazioni) sia come parte dei tentativi di ottenere processi ottimali di magazzino. 

I limiti di stoccaggio dell'ubicazione aiutano a garantire che non venga creato lavoro per richiedere che l'inventario sia inserito in un'ubicazione che non ha la capacità fisica di contenerlo. Se ad esempio alcune posizioni all'interno di un magazzino possono contenere solo un pallet, è possibile abilitare i limiti di stoccaggio ubicazione. Il valore **Quantità** può essere impostato su **1** e il valore **Unità** può essere impostato su **Profitti e perdite** in un raggruppamento specifico di profili ubicazione. 

Se calcoli più avanzati sono necessari per controllare i vincoli di capacità dell'ubicazione, le impostazioni del profilo dell'ubicazione possono essere utilizzate. In questo caso, peso e volume vengono considerati quando vengono effettuati i calcoli di capacità. 

Per ottenere processi in uscita ottimali, è necessario valutare se utilizzare le ubicazioni di prelievo fisse e/o le ubicazioni di imballaggio. Spesso, il rifornimento minimo/massimo viene utilizzato per i processi di rifornimento da un'area di stoccaggio alle ubicazioni di prelievo fisse e più ubicazioni di prelievo fisse possono essere abilitate nello stesso magazzino e per le varianti prodotto. Considerare la flessibilità che può essere raggiunta abilitando ubicazioni di overflow di rifornimento della domanda dedicate utilizzate solo per l'elaborazione di rifornimento carico/ondata.

### <a name="location-setup-wizard"></a>Impostazione guidata ubicazione

Per creare rapidamente le ubicazioni all'interno di un magazzino, è possibile utilizzare l'**Impostazione guidata ubicazione**. Come parte del processo, è possibile gestire facilmente il formato dei nomi di ubicazione.

## <a name="warehouse-processes"></a>Processi di magazzino
Come parte della configurazione del magazzino, è importante abilitare i processi di magazzino in base ai requisiti aziendali. I componenti più importanti che è necessario configurare sono i modelli di ondata, i modelli di lavoro, i pool di lavoro e le direttive ubicazione.

### <a name="wave-templates"></a>Modelli ondata

I modelli di ondata consentono di abilitare il processo "Rilascia in magazzino". Non appena le righe ordine vengono rilasciate (direttamente dai documenti di origine, tramite i processi batch o tramite i carichi già creati), la funzionalità del modello di ondata viene utilizzata. 

È possibile creare i tre tipi di modelli di ondata: 
-   **Spedizione**
-   **Ordine di produzione**
-   **Kanban** 

Vengono utilizzati dei parametri per definire quanto il sistema dovrebbe addentrarsi automaticamente nell'elaborazione del lavoro in uscita. Un modello di ondata è selezionato in base alla sequenza modello ondata e ai criteri specificati nel modello. Se un modello è elencato nella parte superiore della sequenza, i criteri in tale modello vengono verificati per primi. Se i criteri possono essere soddisfatti, il modello di ondata viene elaborato. In caso contrario, vengono controllati i criteri nel modello successivo e così via. Di conseguenza, è buona idea inserire il modello con i criteri più specifici nella parte superiore dell'elenco della sequenza del modello di ondata, in modo che venga elaborato per primo. Ad esempio, si desidera elaborare tutto il lavoro per un vettore specifico e ritardare temporaneamente l'elaborazione del lavoro di altri vettori. In questo caso, il modello di ondata che seleziona il lavoro di questo vettore deve essere elencato più in alto nella sequenza rispetto agli altri modelli. In caso contrario, il lavoro per gli altri vettori potrebbe essere elaborato prima che venga completato il lavoro di questo vettore. 

È necessario specificare i metodi di elaborazione ondata in ogni modello di ondata. I metodi disponibili variano in base al tipo di modello di ondata.

### <a name="work-templates"></a>Modelli di lavoro

Le definizioni di modello di lavoro svolgono un ruolo importante nella definizione dei processi di lavoro di gestione magazzino. Consentono di definire il lavoro eseguito e il modo in cui viene eseguito. I modelli possono inoltre contenere un codice di direttiva collegato a una direttiva di ubicazione per determinare dove viene eseguito il lavoro. I modelli di lavoro includono una query che specifica i criteri per il lavoro. Ogni modello deve includere almeno un'operazione di prelievo e un'operazione di inserimento per gestire le operazioni di lavori di base per il trasferimento delle scorte disponibili da un'ubicazione a un'altra. 

Se più lavoratori devono poter elaborare il lavoro per alcune delle operazioni di magazzino, è possibile utilizzare per il concetto *gestione temporanea* per l'inventario e separare l'esecuzione del lavoro in classi diverse di lavoro.

### <a name="work-pools"></a>Pool lavoro

I pool di lavoro vengono utilizzati per organizzare il lavoro in gruppi. Ad esempio, è possibile creare un pool di lavoro per classificare il lavoro che si verifica in un'ubicazione specifica del magazzino. Per tutti i tipi di lavoro eccetto il conteggio, è possibile assegnare un pool di lavoro a un modello di lavoro. Per il conteggio ciclo, è possibile assegnare un pool di lavoro nelle seguenti pagine:

-   Piani di conteggio ciclo
-   Soglie conteggio ciclo
-   Lavoro conteggio ciclo per ubicazione
-   Lavoro conteggio ciclo per articolo

Quando si utilizzano i modelli di lavoro per creare il lavoro, il pool di lavoro viene assegnato automaticamente al lavoro. 

ID pool lavoro possono anche essere utilizzati per limitare il tipo di lavoro che è diretto a un addetto magazzino specifico, purché questa funzionalità sia configurata nella voce di menu del dispositivo mobile.

### <a name="location-directives"></a>Direttive ubicazione

Come suggerisce il nome, le direttive ubicazione vengono utilizzate per indirizzare le transazioni di lavoro alle ubicazioni appropriate nel magazzino. In altre parole, definiscono dove effettuare il prelievo e l'inserimento. 

Per rendere più semplice e più rapido definire le azioni associate a ogni riga di direttive di ubicazione, utilizzare una delle strategie predefinite. Ad esempio, è possibile utilizzare la strategia **Ubicazione vuota senza alcun lavoro in entrata** per individuare le ubicazioni libere in un magazzino oppure la strategia **Prenotazione batch FEFO** per il prelievo vendite in uscita.

## <a name="additional-resources"></a>Risorse aggiuntive

[Configurare le ubicazioni in un magazzino abilitato WMS](tasks/configure-locations-wms-enabled-warehouse.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]