---
title: Personalizzare i titoli dei passi e le istruzioni per l'applicazione mobile Warehouse Management
description: Questo articolo descrive come creare e mostrare istruzioni personalizzate per ogni passo di ogni flusso di attività che hai impostato per l'applicazione mobile Warehouse Management.
author: Mirzaab
ms.date: 08/09/2022
ms.topic: article
ms.search.form: WHSMobileAppFlowStepListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-08-11
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: faa9bfa320823664603153601c56654170e7e23a
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/23/2022
ms.locfileid: "9334478"
---
# <a name="customize-step-titles-and-instructions-for-the-warehouse-management-mobile-app"></a>Personalizzare i titoli dei passi e le istruzioni per l'applicazione mobile Warehouse Management

> [!IMPORTANT]
> Le caratteristiche che sono descritte in questo articolo si applicano solo alla nuova applicazione mobile Warehouse Management. Non riguardano la vecchia app del magazzino, che ora è deprecata.

Questo articolo descrive come creare e mostrare istruzioni personalizzate per ogni passo di ogni flusso di attività che hai impostato per l'applicazione mobile Warehouse Management. Quando i magazzinieri ricevono istruzioni ben scritte, possono iniziare immediatamente a usare i nuovi flussi senza richiedere una formazione precedente. Questa funzione offre i seguenti vantaggi:

- **Aumenta i lavoratori più velocemente facendo loro seguire semplici istruzioni per ogni fase del lavoro.** Ogni passo di un flusso fornisce istruzioni che permettono ai lavoratori di prima linea di capire il compito.
- **Fornite istruzioni che corrispondono ai vostri processi.** Scrivete le vostre istruzioni per adattarle ai vostri processi aziendali e di magazzino. Per esempio, puoi adattare la terminologia al tuo spazio fisico e alle abbreviazioni locali.

## <a name="turn-the-warehouse-app-step-instructions-feature-on-or-off"></a>Attivare o disattivare la funzionalità Istruzioni per i passaggi dell'app di magazzino

Per poter utilizzare la funzionalità, è necessario attivarla per il sistema. A partire dalla versione 10.0.29 di Supply Chain Management, questa funzionalità è obbligatoria e non può essere disattivata. Se si sta eseguendo una versione precedente alla versione 10.0.29, gli amministratori possono attivare o disattivare questa funzionalità cercando la funzionalità *Istruzioni per i passaggi dell'app di magazzino* nell'area di lavoro [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="step-titles-and-step-instructions-in-the-app"></a>Titoli dei passi e istruzioni dei passi nell'app

Ogni passo in un flusso di attività nell'applicazione mobile Warehouse Management è identificato da un ID di passo. Inoltre, ogni passo ha un titolo, un'icona e un'istruzione. (Per maggiori informazioni, vedi [Assegnare icone e titoli dei passi per l'app mobile Warehouse Management](step-icons-titles.md))

### <a name="step-titles"></a>Titoli dei passi

Il *titolo di un passaggio* è una breve descrizione di ciò che un lavoratore dovrebbe fare durante un passaggio. Appare come un testo grande nella parte superiore dello schermo, come mostrato nella seguente illustrazione.

![Esempio di titolo di un passo nell'applicazione mobile Warehouse Management](media/wma-step-title.png "Esempio di titolo di un passo nell'applicazione mobile Warehouse Management")

> [!TIP]
> A causa delle grandi dimensioni del testo, si dovrebbe cercare di mantenere i titoli dei passi il più breve possibile. Altrimenti, il testo potrebbe essere tagliato. Tuttavia, per i titoli lunghi, i lavoratori possono ancora tenere premuto il titolo per aprire una finestra di dialogo che mostra il testo completo.

### <a name="step-instructions"></a>Istruzioni passaggio

Un' *istruzione di passo* è una descrizione più lunga che fornisce maggiori informazioni su ciò che un lavoratore dovrebbe fare durante un passo. Appare in una finestra di dialogo pop-up, come mostrato nella seguente illustrazione.

![Esempio di un'istruzione di passo nell'applicazione mobile Warehouse Management](media/wma-step-instructions.png "Esempio di un'istruzione di passo nell'applicazione mobile Warehouse Management")

L'istruzione del passo viene mostrata automaticamente quando un passo viene aperto. I lavoratori possono respingerla toccando un punto qualsiasi al di fuori della finestra di dialogo a comparsa. Inoltre, la finestra di dialogo include una casella di controllo **Non visualizzare più** che i lavoratori possono selezionare per evitare che l'istruzione appaia la prossima volta che eseguono lo stesso compito.

## <a name="load-the-default-setup"></a>Caricare l'impostazione predefinita

Quando attivi per la prima volta la funzionalità *Istruzioni per i passaggi dell'app di magazzino*, il tuo sistema non conterrà alcun titolo o istruzione a passi personalizzabile. Pertanto, la prima cosa che dovreste fare è caricare il setup di default. L'impostazione predefinita fornisce testi per tutti gli ID dei passi disponibili in ogni lingua supportata. Per caricare l'impostazione predefinita, seguite questi passi.

1. Vai alla **gestione del magazzino \> Impostazione \> Dispositivo mobile \> Passi per il dispositivo mobile**.
1. Nel riquadro azioni, selezionare **Crea impostazione predefinita**. La pagina viene riempita con i passi standard.

## <a name="customize-step-titles-and-instructions"></a>Personalizza i titoli dei passi e le istruzioni

Per personalizzare il titolo e/o le istruzioni di un passo in un numero qualsiasi di lingue, segui questi passi.

1. Vai alla **gestione del magazzino \> Impostazione \> Dispositivo mobile \> Passi per il dispositivo mobile**.

    La pagina dei **passi del dispositivo mobile** elenca tutti i passi disponibili per il tuo sistema. Ogni ID di passo può essere condiviso tra un numero qualsiasi di voci di menu del dispositivo mobile. Se un ID passo è condiviso tra più voci di menu, lo stesso titolo e la stessa istruzione sono mostrati per tutte queste voci di menu. Tuttavia, è possibile creare degli override per personalizzare il titolo e le istruzioni per voci di menu specifiche. (Per maggiori informazioni, vedere la prossima sezione)

    La griglia include le colonne seguenti:

    - **Nome della voce di menu** - Le righe in cui questa colonna è vuota usano il titolo predefinito del passo e le istruzioni che si applicano a tutte le voci di menu del dispositivo mobile per le quali non è stato definito alcun override. Le righe in cui questa colonna è impostata sul nome di una voce di menu hanno delle sovrapposizioni che si applicano solo alla voce di menu specificata.
    - **ID** del passo - L'ID unico del passo.
    - **Titolo per l'input** - Il titolo che viene mostrato quando l'app richiede nuove informazioni. In genere, i campi della pagina sono vuoti (cioè, non hanno valori preimpostati).
    - **Titolo per la conferma** - Il titolo che viene mostrato quando l'applicazione richiede la conferma di un valore che è già memorizzato nel sistema. In genere, i campi della pagina hanno valori preimpostati.

1. Trova la combinazione di valori **ID passo** e **Nome voce di menu** che vuoi modificare e seleziona il valore nella colonna **ID passo** . La pagina che si apre elenca tutte le traduzioni disponibili per il titolo e l'istruzione del passo selezionato.
1. Segui uno di questi passi per personalizzare il testo per qualsiasi lingua. Entrambe le opzioni permettono di modificare i testi per le lingue esistenti. Tuttavia, solo la prima opzione permette di aggiungere testi per nuove lingue, mentre solo la seconda opzione permette di visualizzare e modificare i testi per tutte le sovrapposizioni esistenti specifiche del menu della lingua selezionata.

    - Sulla barra degli strumenti, seleziona **Aggiungi** per aprire una finestra di dialogo dove puoi aggiungere o modificare i testi per qualsiasi lingua supportata. Imposta il campo **Lingua di riferimento** sulla lingua per la quale vuoi visualizzare i valori. I valori sono mostrati nella colonna di sinistra. Imposta il campo **Lingua delle traduzioni** sulla lingua che vuoi aggiungere o personalizzare. Nella colonna di destra, modifica i valori dei campi **Titolo per l'inserimento**, **Istruzioni per l'inserimento**, **Titolo per la conferma** e **Istruzioni per la conferma** come desideri. Selezionare **OK**.
    - Nella griglia, trova e seleziona la riga dove il campo **Lingua** è impostato sulla lingua che vuoi modificare. Sulla barra degli strumenti, selezionare **View &lt;language&gt; translations di questo passo** per aprire una finestra di dialogo dove è possibile modificare i testi per tutte le sovrapposizioni disponibili per la lingua selezionata. La finestra di dialogo include una griglia che ha righe sia per i testi standard (dove il campo **Nome della voce di menu** è vuoto) che per ogni testo di sostituzione disponibile (dove il campo **Nome della voce di menu** è impostato sul nome della voce di menu a cui si applica la sostituzione). Modifica i valori dei campi **Titolo per input**, **Istruzione per input**, **Titolo per conferma** e **Istruzione per conferma** come desideri. Selezionare **OK**.

1. Continuate a lavorare finché non avrete definito ogni titolo e istruzione richiesti per ogni lingua richiesta.

## <a name="add-menu-specific-overrides"></a>Aggiungere override specifici per i menu

Come è stato menzionato nella sezione precedente, è possibile creare un numero qualsiasi di sovrascritte specifiche del menu per ogni ID di passo. Potresti usare questa capacità per modificare e cambiare l'istruzione in modo che si adatti meglio al tuo processo aziendale locale per una specifica voce di menu. Per esempio, per il prelievo delle vendite, se la vostra azienda di solito fornisce ID di lavoro ai lavoratori su un documento stampato, potete fornire un suggerimento che i lavoratori dovrebbero iniziare con la scansione di un ID di lavoro.

Ogni override si applica a una specifica voce di menu del dispositivo mobile e può contenere qualsiasi numero di traduzioni. Se non esiste alcuna sostituzione per una voce di menu, la voce di menu usa i testi standard. Se non è definita alcuna traduzione di sostituzione per una lingua, vengono utilizzati i testi standard, anche per le voci di menu in cui è definita una sostituzione per altre lingue.

Per creare e configurare un override, seguite questi passi.

1. Vai alla **gestione del magazzino \> Impostazione \> Dispositivo mobile \> Passi per il dispositivo mobile**.
1. Nella griglia, trovare e selezionare la riga per cui creare un override.
1. Nel riquadro delle azioni, seleziona **Aggiungi configurazione del passo**.
1. Nella finestra di dialogo a discesa della **configurazione del passo aggiuntivo** , impostare il campo **Voce di menu** sul nome della voce di menu del dispositivo mobile a cui si applica l'override. Selezionare **OK**.
1. La pagina che appare mostra tutti i testi che sono disponibili per il nuovo override. Inizialmente, viene creata una sola lingua. Tutte le altre lingue continueranno a usare i testi standard, a meno che tu non aggiunga queste lingue qui. Modifica i testi e aggiungi nuove lingue secondo le tue esigenze, come descritto nella sezione precedente.
