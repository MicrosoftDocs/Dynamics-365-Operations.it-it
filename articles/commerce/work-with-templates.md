---
title: Utilizzare i modelli
description: In questo argomento viene descritto come utilizzare i modelli in Microsoft Dynamics 365 Commerce.
author: phinneyridge
ms.date: 04/14/2020
ms.topic: article
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
ms.openlocfilehash: 96a8cbfd208095833514f374c060bb2d43781913
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5793851"
---
# <a name="work-with-templates"></a>Utilizzare i modelli

[!include [banner](includes/banner.md)]

In questo argomento viene descritto come utilizzare i modelli in Microsoft Dynamics 365 Commerce.

Come discusso in [Panoramica modelli e layout](templates-layouts-overview.md), i modelli definiscono l'insieme di opzioni disponibile per gli autori downstream. I modelli sono utili per un team di creazione di siti Web di un'azienda per diversi motivi e i modelli ben strutturati possono rivelarsi utili per i seguenti scopi:

- Semplificare l'esperienza di creazione per ruoli di editor di contenuti quotidiani.

    - Filtrare le opzioni dei moduli di modo che solo i moduli pertinenti siano visualizzati per una sezione di pagina specifica (ad esempio, una sezione di marketing di un modello può essere configurata per filtrare i moduli inutili che non devono mai essere utilizzati in quel contesto e che non farebbero che complicare le attività di creazione di contenuti se visualizzati).
    - Configurare l'impostazione di modulo predefinita per migliorare l'efficacia della creazione.
    - Definire frammenti pagina predefiniti per migliorare l'efficacia della creazione (ad esempio, i frammenti intestazione e piè di pagina in un modello saranno automaticamente visualizzati in ogni pagina downstream).

- Mantenere i siti aziendali conformi al marchio definendo un insieme approvato di opzioni di disposizione e configurazione di moduli.

    > [!TIP] 
    > I siti di e-Commerce di successo forniscono ai clienti modelli di concezione di esperienze utente (UX) noti, riutilizzabili e conformi al marchio. Utilizzando i modelli, si agevola il controllo della coerenza nel sito.

- Migliorare i punteggi di ottimizzazione del motore di ricerca assicurando metadati e definizioni di pagina ripetibili e definiti a livello di codice.

> [!NOTE]
> Sebbene i modelli siano progettati per controllare la coerenza in un sito, in teoria possono essere configurati di modo non applichino alcuna coerenza. Gli amministratori di marchi e siti possono definire qualsiasi livello di variabilità per le pagine del loro sito. Ad esempio, un modello può essere lasciato completamente aperto, di modo che gli autori di contenuti possano creare una progettazione di pagina qualsiasi. In tal caso, nessuno dei vantaggi elencati sopra è applicabile.

## <a name="modify-a-template"></a>Modificare un modello

I modelli vengono modificati utilizzando l'editor di modelli.

Per aprire l'editor di modelli, eseguire uno dei seguenti passaggi:

- Nel pannello di navigazione del sito selezionare **Modelli**, quindi selezionare il modello da modificare.
- Nell'editor di pagine di una pagina esistente, selezionare il nodo principale nell'albero a sinistra. Quindi, nel riquadro delle proprietà a destra, selezionare **Modifica modello**.

La visualizzazione ad albero a sinistra mostra le opzioni e le strutture di modulo disponibili per pagine e layout figlio. Quando si seleziona un modulo nell'albero, è possibile visualizzare le proprietà del modello per il modulo selezionato nel riquadro delle proprietà a destra. Alcune di queste proprietà sono specifiche alla modifica del modello. Queste proprietà sono descritte nella tabella seguente.

| Nome proprietà | Descrizione |
|---|---|
| Numero minimo ricorrenze | Questa proprietà definisce il numero minimo di occorrenze per il modulo selezionato. Ad esempio, se il valore è **1**, il modulo è necessario per autori downstream, mentre se è **0** (zero), il modulo è facoltativo. |
| Numero massimo ricorrenze | Questa proprietà definisce il numero massimo di occorrenze per il modulo selezionato. Ad esempio, se il valore è **1**, il modulo può essere aggiunto una sola volta. |
| Numero minimo di moduli (contenitori) | Per i moduli che contengono altri moduli (ovvero i *moduli contenitore*), questa proprietà definisce il numero minimo di moduli totali che devono essere aggiunti come figlio. Ad esempio, per un modulo Sequenza, il valore può essere impostato su un numero maggiore di 1. |
| Numero massimo di moduli (contenitori) | Per i moduli contenitore, questa proprietà definisce il numero massimo di moduli totali che devono essere aggiunti come figlio. Ad esempio, per un modulo Sequenza, il valore può essere impostato su un numero minore di 10. |
| Bloccato | Un controllo booleano **Bloccato** è visualizzato accanto a tutte le proprietà del modulo principale. Consente all'autore del modello di bloccare un'impostazione di modulo nel modello. Un'impostazione di modulo bloccata non può essere sostituita da pagine o layout figlio. Diventa un valore di proprietà modificabile centralmente per tutti i layout e le pagine che utilizzano il modello. |

## <a name="create-a-new-template"></a>Crea un nuovo modello

Per creare un nuovo modello, completare i passaggi seguenti.

1. Nel pannello di navigazione del sito selezionare **Modelli** per aprire la visualizzazione controllo modelli.
1. Selezionare **Nuovo modello**.
1. Nella finestra di dialogo per la creazione di modelli, immettere un nome e una descrizione per il modello. I valori immessi saranno visibili agli autori quando questi creano nuove pagine. Di conseguenza, immettere metadati che saranno utili agli autori di pagine. Ad esempio, immettere **Utilizzare questo modello per creare pagine di marketing generali** come descrizione. Questi metadati possono essere modificati in un secondo momento.
1. Selezionare **OK** per creare il nuovo modello e aprire l'editor di modelli. L'editor di modelli mostra un albero a sinistra e un riquadro della proprietà a destra.
1. Nell'albero, espandere i nodi e selezionare lo slot **Intestazione HTML**.
1. Se non vi sono ancora moduli in questo slot, selezionare il pulsante con i puntini di sospensione (**...**) e quindi selezionare **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo** selezionare **Riepilogo pagina predefinita** e quindi selezionare **OK**.
1. Nell'albero, selezionare il nuovo modulo, quindi nel riquadro delle proprietà, immettere tutte le impostazioni predefinite che devono essere configurate automaticamente per tutte le pagine figlio del modello. Se non si desidera alcuna impostazione predefinita, lasciare i campi vuoti.
1. Nell'albero, selezionare lo slot **Corpo**, selezionare il pulsante con i puntini di sospensione e quindi **Aggiungi modulo**.
1. Selezionare un modulo contenitore pagina (potrebbe esserci una sola opzione), quindi selezionare **OK**.

Sotto il nuovo modulo contenitore pagina, viene visualizzato un nuovo set di slot (**Intestazione**, **Principale** e così via). Qui è possibile aggiungere e configurare le opzioni di modulo che saranno disponibili per gli autori quando creano pagine a partire da questo modello. Per impostazione predefinita, se non si aggiungono moduli a uno slot, tutti i tipi di modulo disponibili sono supportati per quello slot.

Il modello è ora tecnicamente valido e può essere salvato, archiviato e utilizzato per creare nuove pagine. Tuttavia, le tre sezioni seguenti descrivono alcune altre impostazioni predefinite che l'utente potrebbe voler configurare per prime.

## <a name="add-a-header-and-a-footer"></a>Aggiungere un'intestazione e un piè di pagina

Se il sito ha già un frammento intestazione, seguire questi passaggi per aggiungere un'intestazione e un piè di pagina a un modello.

1. Nell'albero, espandere lo slot **Corpo** e il relativo modulo pagina figlio.
1. Selezionare lo slot **Intestazione**.
1. Selezionare il pulsante con i puntini di sospensione per lo slot **Intestazione** e quindi selezionare **Aggiungi frammento**.
1. Cercare e selezionare il frammento intestazione del sito e quindi selezionare **OK**.

Tutte le pagine che utilizzano il modello ora erediteranno automaticamente questo frammento intestazione.

Se il sito non ha ancora un frammento intestazione, vedere [Creare un frammento](work-with-fragments.md#create-a-fragment) per informazioni su come crearlo, quindi completare la procedura precedente.

## <a name="change-the-template-theme"></a>Cambiare il tema di un modello

Per impostare il tema predefinito per tutte le pagine che utilizzano un modello, effettuare le seguenti operazioni.

1. Nell'albero a sinistra espandere, lo slot **Corpo**.
1. Nello slot **Corpo**, selezionare il modulo contenitore pagina (ad esempio **Pagina predefinita**).
1. Nel riquadro delle proprietà a destra, nel campo **Tema**, selezionare un tema.

Per impostazione predefinita, tutte le nuove pagine ora utilizzeranno il tema selezionato. Per impedire alle pagine di sostituire questa impostazione a livello di pagina o layout, impostare il controllo booleano **Bloccato** su **True**.

## <a name="add-a-script-to-a-template"></a>Aggiungere uno script a un modello

È possibile aggiungere elementi **&lt;script&gt;** HTML che contengono JavaScript al modello. In questo modo, è possibile fornire comportamenti di script predefiniti alle sezioni intestazione HTML, inizio corpo e fine corpo delle pagine.

Per aggiungere uno script a un modello, effettuare le operazioni seguenti.

1. Nell'albero a sinistra, selezionare lo slot in cui si desidera aggiungere l'elemento **&lt;script&gt;** (ad esempio, intestazione HTML, inizio corpo o fine corpo).
1. Selezionare il pulsante con i puntini di sospensione per lo slot, quindi selezionare **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo**, selezionare un modulo Script (ad esempio **Script esterno** o **Script inline**).
1. Nel riquadro delle proprietà a destra, nel controllo delle proprietà di script appropriato (ad esempio **Script inline** o **Tag script**), immettere lo script.
1. Nel riquadro delle proprietà, immettere qualsiasi altra impostazione facoltativa che si desidera configurare.

> [!TIP]
> Se si desidera riutilizzare un qualsiasi modulo Script per altri modelli, è possibile convertirli in frammenti. In questo modo, si rende il processo di creazione più efficiente e si centralizza quello di aggiornamento. Per informazioni su come convertire un modulo Script in un frammento, vedere [Salvare una configurazione di modulo esistente come frammento](work-with-fragments.md#save-an-existing-module-configuration-as-a-fragment).

## <a name="save-check-in-preview-and-publish-a-template"></a>Salva, archiviare, visualizzare in anteprima e pubblicare un modello

Per salvare e archiviare un modello, effettuare le operazioni indicate di seguito.

1. Selezionare **Salva** nella parte superiore dell'editor di modelli. Le modifiche salvate non influiscono sulle pagine downstream fino a che non vengono archiviate.
1. Selezionare **Fine modifica**. Le modifiche sono ora individuabili per i flussi di lavoro downstream.

Per visualizzare un'anteprima delle modifiche, aprire una pagina esistente che utilizza il modello o creare una nuova pagina a partire dal modello.

Dopo avere visualizzato un'anteprima delle modifiche al modello, eseguire una di queste operazioni per pubblicare il modello sul sito live:

* Andare a **Modelli**, selezionare il modello e quindi **Pubblica**.
* Selezionare il nome del layout per aprire l'editor del layout, quindi selezionare **Pubblica**.
* Pubblicare una pagina che fa riferimento al modello non pubblicato. Il modello viene pubblicato automaticamente.

> [!WARNING]
> Quando un modello, o qualsiasi altro elemento del sistema di gestione dei contenuti, viene pubblicato, è individuabile su Internet. Non pubblicare documenti o asset fino a che non si è pronti a renderli pubblici. Le versioni dei documenti che sono state salvate e archiviate, ma non pubblicate, risultano individuabili solo per gli utenti di sistema autenticati.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica modelli e layout](templates-layouts-overview.md)

[Utilizzare i layout preimpostati](work-with-layouts.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
