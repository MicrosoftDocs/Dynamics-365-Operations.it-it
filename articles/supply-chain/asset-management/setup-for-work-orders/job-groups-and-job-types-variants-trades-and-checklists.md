---
title: Categorie di tipi di processo di manutenzione e tipi di processo di manutenzione, varianti di tipi di processo di manutenzione, settori di processo di manutenzione ed elenchi di controllo di manutenzione
description: In questo argomento vengono descritti categorie di tipi di processo di manutenzione e tipi di processo di manutenzione, varianti di tipi di processo di manutenzione, settori di processo di manutenzione ed elenchi di controllo di manutenzione
author: johanhoffmann
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetJobTypeDefaultForecast, EntAssetJobTrade, EntAssetJobTypeDefaultCopy, EntAssetChecklistVariableValueLookup, EntAssetChecklistTemplateCreate, EntAssetJobVariant, EntAssetJobTypeDefaultReference, EntAssetJobTypeDefaultChecklist, EntAssetJobTypeDefault, EntAssetJobType, EntAssetJobTypeDefaultChecklistCopy, EntAssetChecklistTemplate, EntAssetJobTypeDefaultDescription, EntAssetJobTypeLookup, EntAssetJobTypeDefaultToolCopy, EntAssetJobTypePreviewPart, EntAssetJobTypeDefaultTool, EntAssetJobTypeDefaultForecastCopy, EntAssetChecklistTemplateLookup, EntAssetJobGroup, EntAssetChecklistVariable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: eb73fb36ee31d93b2121437d57d959ba6c01a337
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5842275"
---
# <a name="maintenance-job-type-categories-and-maintenance-job-types-maintenance-job-type-variants-maintenance-job-trades-and-maintenance-checklists"></a>Categorie di tipi di processo di manutenzione e tipi di processo di manutenzione, varianti di tipi di processo di manutenzione, settori di processo di manutenzione ed elenchi di controllo di manutenzione

[!include [banner](../../includes/banner.md)]

 

Un tipo cespite è associato a ogni cespite. I tipi di cespite definiscono i tipi di processo di manutenzione (e di conseguenza i processi di manutenzione) che possono essere eseguiti nei cespiti. Quando si crea un ordine di lavoro, è necessario selezionare un tipo di processo di manutenzione. È possibile selezionare solo i tipi di processo di manutenzione correlati all'impostazione del tipo di cespite utilizzato per il cespite.

Per una panoramica grafica dei cespiti e dei tipi di processo di manutenzione e la connessione degli stessi agli ordini di lavoro, vedere [Unità funzionali e cespiti](../overview/functional-locations-and-objects.md).

Le varianti di tipi di processo di manutenzione possono essere impostate in un tipo di processo di manutenzione. Le varianti di tipi di processo di manutenzione definiscono le variazioni di un tipo di processo, ad esempio dimensioni (piccole, medie o grandi), periodi (settimanale, bisettimanale, un mese o tre mesi) e configurazioni (prestazioni ridotte, standard, flessibili o alte).

I settori di processo di manutenzione forniscono informazioni sui settori professionali, ad esempio i settori meccanico, elettrico e idraulico. I requisiti delle competenze possono essere impostati in un settore di processo di manutenzione. Tutti i settori di processo di manutenzione possono essere utilizzati in relazione a tutti i tipi di processo di manutenzione. La selezione di una variante di tipi di processo di manutenzione e/o di un settore di processo di manutenzione in un ordine di lavoro è facoltativa.

Per ogni tipo di processo di manutenzione, è possibile creare variazioni dell'impostazione del tipo di processo di manutenzione. Ad esempio, se si ha un tipo di processo di manutenzione denominato **Tagliando**, è possibile creare le seguenti variazioni per quel tipo: **Camion 30.000 km**, **Automobili 30.000 km** e **Furgoni 30.000 km**.

Le categorie di tipi di processo di manutenzione sono utilizzate per raccogliere un gruppo di tipi di processo di manutenzione per scopi di panoramica. Esempi di categorie di tipi di processo di manutenzione possono includere **Calibratura**, **Ispezione**, **Revisione** e **Strumentazione**.

I modelli e le variabili di elenchi di controllo di manutenzione vengono utilizzati per impostare gli elenchi di controllo di manutenzione. Gli elenchi di controllo di manutenzione sono impostati nei tipi di processo di manutenzione e utilizzati negli ordini di lavoro.

Innanzi tutto, si impostano le categorie e le varianti di tipi di processo di manutenzione e i settori di processo di manutenzione. Quindi si creano i tipi di processo di manutenzione. Infine, nella pagina **Valori predefiniti tipo di processo di manutenzione**, si creano tutte le variazioni dei tipi di processo di manutenzione necessarie per l'attrezzatura. In quella pagina, è anche possibile impostare previsioni, elenchi di controllo di manutenzione e strumenti per una combinazione di tipi di processo di manutenzione.

> [!NOTE]
> Un tipo di processo di manutenzione può essere associato a una sola categoria di tipi di processo di manutenzione.

## <a name="create-a-maintenance-job-type-category"></a>Creare una categoria di tipi di processo di manutenzione

1. Selezionare **Gestione cespiti** \> **Impostazione** \> **Processi** \> **Categorie tipi di processo di manutenzione**.
2. Selezionare **Nuovo**.
3. Nel campo **Categoria tipi di processo di manutenzione**, immettere un ID per la categoria di tipi di processo di manutenzione.
4. Nel campo **Nome** immettere un nome.

    Dopo aver associato categorie dei tipi di processo di manutenzione a tipi di processo di manutenzione, nel campo **Tipi di processo** viene visualizzato il numero di tipi di processo di manutenzione associati a questa categoria di tipi di processo di manutenzione.

![Pagina Categorie di tipi di processi di manutenzione](media/01-setup-for-work-orders.png)

## <a name="create-a-maintenance-job-type-variant"></a>Creare una variante di tipi di processo di manutenzione

1. Selezionare **Gestione cespiti** \> **Impostazione** \> **Processi** \> **Varianti tipi di processo di manutenzione**.
2. Selezionare **Nuovo**.
3. Nel campo **Variante tipi di processo di manutenzione**, immettere un ID per la variante di tipi di processo di manutenzione.
4. Nel campo **Descrizione** immettere una descrizione.
5. Nella Scheda dettaglio **Tipi di processo di manutenzione**, selezionare **Aggiungi** per aggiungere un tipo di processo di manutenzione.
6. Selezionare il tipo di processo di manutenzione nel campo **Tipo di processo di manutenzione**.
7. Ripetere i passaggi da 5 a 6 per aggiungere altri tipi di processo di manutenzione alla variante di tipi di processo di manutenzione.

    Nella Scheda dettaglio **Dettagli**, il campo **Tipi di processo** visualizza il numero di tipi di processo di manutenzione aggiunti a questa variante.

![Pagina Varianti di tipo di processo di manutenzione](media/02-setup-for-work-orders.png)

## <a name="create-a-maintenance-job-trade"></a>Creare un settore di processo di manutenzione

1. Selezionare **Gestione cespiti** \> **Impostazione** \> **Processi** \> **Settore processo di manutenzione**.
2. Selezionare **Nuovo**.
3. Nel campo **Settore**, immettere un ID per il settore di processo di manutenzione.
4. Nel campo **Descrizione** immettere una descrizione.
5. Nella Scheda dettaglio **Competenze**, selezionare **Aggiungi** per aggiungere una nuova competenza che deve essere associata al settore di processo di manutenzione.
6. Nel campo **Competenza** selezionare la competenza.
7. Nel campo **Livello** selezionare la competenza.
8. Ripetere i passaggi da 5 a 7 per aggiungere ulteriori competenze al settore di processo di manutenzione.

    Nella Scheda dettaglio **Dettagli**, il campo **Competenze** visualizza il numero di competenze aggiunte a questo settore.

9. Nella Scheda dettaglio **Certificati**, selezionare **Aggiungi** per aggiungere un certificato al settore di processo di manutenzione.
10. Nel campo **Tipo di certificato** selezionare il certificato.
11. Ripetere i passaggi da 9 a 10 per aggiungere ulteriori certificati al settore di processo di manutenzione.

    Nella Scheda dettaglio **Dettagli**, il campo **Certificati** visualizza il numero di certificati aggiunti a questo settore.

![Pagina Settore processo di manutenzione](media/03-setup-for-work-orders.png)

## <a name="create-a-maintenance-checklist-variable"></a>Creare una variabile di elenco di controllo di manutenzione

Quando si creano righe di elenco di controllo di manutenzione nel valore predefinito di tipo di processo di manutenzione, è necessario selezionare un tipo di elenco di controllo di manutenzione. **Variabile** è un tipo di elenco di controllo di manutenzione. Viene utilizzato per definire un possibile risultato in un intervallo in una riga di elenco di controllo di manutenzione associata a una riga di ordine di lavoro. Una variabile consente di creare un set di risultati predefiniti senza dover eseguire una misura esatta.

**Esempio 1:** è possibile misurare il livello dell'olio definendo tre valori: **Livello troppo alto**, **Livello troppo basso** e **Livello corretto**. Per ogni valore, è necessario definire se il risultato è **Superato**, **Errore** o **Nessuno**.

**Esempio 2:** si esegue un'ispezione visiva di un'attrezzatura per stabilirne l'usura.

1. Selezionare **Gestione cespiti** \> **Impostazione** \> **Elenchi di controllo di manutenzione** \> **Variabile elenco di controllo di manutenzione**.
2. Selezionare **Nuovo**.
3. Nel campo **Variabile**, immettere un ID per la variabile di elenco di controllo di manutenzione.
4. Nel campo **Nome** immettere un nome.
5. Nella Scheda dettaglio **Generale**, selezionare **Aggiungi** per aggiungere una riga per una variabile.

    Un numero di riga sequenziale viene immesso automaticamente nel campo **Numero riga**. Dopo aver aggiunto tutte le righe, è possibile modificare i numeri di riga come necessario. Quando si seleziona la riga e si preme il tasto **Freccia Giù**, il numero successivo nella sequenza viene automaticamente immesso nella riga successiva.

6. Nel campo **Valore** immettere una descrizione del valore.
7. Nel campo **Risultato**, selezionare un risultato per la riga.

![Pagina Variabili elenco di controllo di manutenzione](media/04-setup-for-work-orders.png)

## <a name="create-a-maintenance-checklist-template"></a>Creare un modello di elenco di controllo di manutenzione

I modelli di elenco di controllo di manutenzione possono essere utilizzati come set comune di attività che un lavoratore deve eseguire per completare correttamente un ordine di lavoro. Ai modelli si fa riferimento dalle righe di elenco di controllo di manutenzione nel valore predefinito di tipo di processo di manutenzione. Ai modelli è possibile fare riferimento in molteplici righe predefinite di tipo di processo di manutenzione. Di conseguenza, è possibile riutilizzare facilmente un set di attività comuni di elenco di controllo di manutenzione. Esempi di modelli di elenchi di controllo di manutenzione includono istruzioni di sicurezza generali e un elenco di elementi e condizioni che devono essere verificati in una specifica pompa o in modelli simili di un nastro trasportatore.

1. Selezionare **Gestione cespiti** \> **Impostazione** \> **Elenchi di controllo di manutenzione** \> **Modelli elenco di controllo di manutenzione**.
2. Selezionare **Nuovo**.

    Un ID di modello viene automaticamente immesso nel campo **Modello elenco di controllo di manutenzione**.

3. Nel campo **Nome** immettere un nome per il modello di elenco di controllo di manutenzione.
4. Nella Scheda dettaglio **Righe elenco di controllo di manutenzione**, selezionare **Aggiungi** per aggiungere una riga di modello.

    Un numero di riga sequenziale viene immesso automaticamente nel campo **Numero riga**. Dopo aver aggiunto tutte le righe, è possibile modificare i numeri di riga come necessario. Quando si seleziona la riga e si preme il tasto **Freccia Giù**, il numero successivo nella sequenza viene automaticamente immesso nella riga successiva.

5. Nel campo **Tipo** selezionare un tipo per la riga di elenco di controllo di manutenzione. Per ogni tipo di elenco di controllo di manutenzione, i campi associati sono visualizzati nella Scheda dettaglio **Dettagli riga**. Sono disponibili i valori seguenti:

    - **Testo** - La riga presenta del testo che descrive cosa fare. Utilizzare questo tipo di elenco di controllo di manutenzione se un lavoratore deve verificare o ispezionare qualcosa ma senza aspettarsi uno specifico risultato (misurabile). Dopo la selezione di questo tipo, immettere un nome o un'intestazione nel campo **Nome**. Nel campo **Istruzioni**, immettere una descrizione di cosa fare. Se il passaggio è obbligatorio per l'elenco di controllo di manutenzione, impostare l'opzione **Obbligatorio** su **Sì**.
    - **Intestazione** - La riga viene utilizzata come intestazione per raggruppare le righe di elenco di controllo di manutenzione visualizzate sotto l'intestazione. Questo tipo è utile se sono presenti varie righe di elenco di controllo di manutenzione che possono essere suddivise in specifiche aree. Le intestazioni forniscono una panoramica del lavoratore che completerà un elenco di controllo di manutenzione con molte righe di elenco di controllo di manutenzione. Dopo aver selezionato questo tipo, immettere un nome descrittivo nel campo **Nome**.
    - **Modello** - La riga viene utilizzata per creare un riferimento a un modello esistente. Dopo aver selezionato questo tipo, immettere un nome per il modello nel campo **Nome**. Nel campo **Modello** selezionare il modello.
    - **Variabile** - La riga viene utilizzata per definire un possibile risultato in un intervallo. Per informazioni su come impostare variabili di elenco di controllo di manutenzione, vedere la sezione [Creare una variabile di elenco di controllo di manutenzione](#create-a-maintenance-checklist-variable). Dopo aver selezionato questo tipo, immettere un nome descrittivo per la variabile nel campo **Nome**. Selezionare la variabile nel campo **Variabile**. Nel campo **Istruzioni**, immettere una descrizione di cosa fare. Se il passaggio è obbligatorio per l'elenco di controllo di manutenzione, impostare l'opzione **Obbligatorio** su **Sì**.
    - **Misura** - La riga viene utilizzata per registrare una specifica misura. È possibile impostare la misura che deve essere associata a un contatore predefinito. Dopo aver selezionato questo tipo, immettere un nome per il modello nel campo **Nome**. Se questo passaggio è obbligatorio per l'elenco di controllo di manutenzione, impostare l'opzione **Obbligatorio** su **Sì**. Se si desidera utilizzare la riga di misura come registrazione contatore, selezionare il contatore nel campo **Contatore**. Il campo **Unità** associato viene quindi aggiornato automaticamente. Se è stato selezionato un contatore, selezionare il metodo di aggiornamento nel campo **Valore**. Nei campi **Valore minimo** e **Valore massimo**, immettere l'intervallo di valori consentito. Nel campo **Istruzioni**, immettere una descrizione di cosa fare.

        > [!NOTE]
        > Qualsiasi riga di tipo **Misura** che non ha un contatore impostato viene gestita come registrazione di misura indipendente per la quale non esiste un follow-up automatico in Gestione cespiti. Analogamente, se il tipo di contatore selezionato non è presente nel cespite associato all'ordine di lavoro, l'attività dell'elenco di controllo di manutenzione viene gestita come misura indipendente. Il valore del contatore può essere modificato più volte. Non viene registrato fino a che lo [stato del ciclo di vita di ordine di lavoro](work-order-lifecycle-states.md) non è uno stato in cui l'opzione **Elabora elenco di controllo di manutenzione** è impostata su **Sì**.

    Nella Scheda dettaglio **Dettagli**, il campo **Verifiche** mostra il numero totale di righe di elenco di controllo nel modello. Questo numero include le righe nidificate in qualsiasi modello esistente a cui si fa riferimento nel modello.

![Pagina Modelli elenco di controllo di manutenzione](media/05-setup-for-work-orders.png)

## <a name="create-a-maintenance-job-type"></a>Creare un tipo di processo di manutenzione

1. Selezionare **Gestione cespiti** \> **Impostazione** \> **Processi** \> **Tipi di processo di manutenzione**.
2. Selezionare **Nuovo**.
3. Nel campo **Tipo di processo di manutenzione**, immettere un ID per il tipo di processo di manutenzione.
4. Nel campo **Nome** immettere un nome.

    Nella Scheda dettaglio **Dettagli** è visualizzata una panoramica del numero di competenze, certificati, processi successivi, tipi di cespite e varianti di tipi di processo di manutenzione che sono stati creati in questo tipo di processo di manutenzione. Nel campo **Righe impostate** viene visualizzato il numero di righe predefinite di tipo di processo di manutenzione impostate in questo tipo di processo di manutenzione. Il campo **Cespiti** mostra il numero di cespiti attivi che utilizzano correntemente questo tipo di processo di manutenzione.

5. Nella Scheda dettaglio **Generale** nel campo **Categoria tipi di processo di manutenzione** selezionare una categoria di tipi di processo di manutenzione.
6. Impostare l'opzione **Attività tempi di fermo per manutenzione** su **Sì** se il tipo di processo di manutenzione richiede un'interruzione dell'attrezzatura prima che il processo possa essere eseguito.
7. Nella Scheda dettaglio **Descrizione**, immettere una descrizione del tipo di processo di manutenzione.
8. Nella Scheda dettaglio campo **Varianti tipi di processo di manutenzione**, è possibile aggiungere varianti al tipo di processo di manutenzione.
9. Nelle schede dettaglio **Competenze richieste** e **Certificati richiesti**, è possibile aggiungere competenze e requisiti di certificati al tipo di processo di manutenzione.
10. Se uno specifico tipo di processo di manutenzione deve essere eseguito successivamente, aggiungerlo alla Scheda dettaglio **Processi successivi**. È anche possibile impostare una variante di tipi di processo di manutenzione e un settore associati al tipo di processo di manutenzione. Se il processo successivo deve iniziare uno specifico numero di giorni prima o dopo l'inizio del processo che utilizza questo tipo di processo di manutenzione, immettere il numero di giorni nel campo **Ritardo in giorni**. I numeri positivi rappresentano i giorni dopo l'avvio del processo associato e quelli negativi rappresentano i giorni prima dell'inizio previsto del processo correlato. Ad esempio, se si immette **5**, il processo successivo inizierà cinque giorni dopo l'avvio del processo associato al tipo di processo di manutenzione. Se si immette **-3**, il processo successivo inizierà tre giorni prima l'avvio previsto del processo associato al tipo di processo di manutenzione.

    > [!NOTE]
    > Se si aggiunge più di una riga di tipo di processo di manutenzione, la sequenza delle righe indica l'ordine di esecuzione delle stesse. La sequenza inizia nella parte superiore dell'elenco.

11. Nella Scheda dettaglio **Tipi di cespite**, è possibile aggiungere tipi di cespite al tipo di processo di manutenzione.

![Pagina Tipi di processo di manutenzione](media/06-setup-for-work-orders.png)

## <a name="create-maintenance-job-type-default-lines-and-related-forecasts-maintenance-checklists-tools-description-and-attachments"></a>Creare righe predefinite di tipo di processo di manutenzione e le relative previsioni, elenchi di controllo di manutenzione, strumenti, Descrizione e allegati

1. Selezionare **Gestione cespiti** \> **Impostazione** \> **Processi** \> **Valori predefiniti tipo di processo di manutenzione**.

    oppure

    Selezionare **Gestione cespiti** \> **Impostazione** \> **Processi** \> **Tipi di processo di manutenzione**, selezionare un tipo di processo di manutenzione e quindi selezionare **Valori predefiniti tipo di processo di manutenzione**.

2. Selezionare **Nuovo**.
3. Nei campi **Unità funzionale**, **Tipo di cespite**, **Produttore**, **Modello** e **Cespite**, selezionare i valori appropriati, a seconda della specificità del valore predefinito di tipo di processo di manutenzione.
4. Nel campo **Tipo di processo di manutenzione**, selezionare un tipo di processo di manutenzione se non è stato selezionato automaticamente.
5. Nei campi **Variante tipi di processo di manutenzione** e **Settore** selezionare una variante e un settore di tipo di processo di manutenzione come necessario.
6. Selezionare **Previsione**.
7. Nella pagina **Previsione predefinita tipo di processo di manutenzione**, è possibile eseguire previsioni per ore, articoli e spese. Nelle schede pertinenti selezionare **Aggiungi** ed effettuare selezioni per creare le previsioni necessarie per il tipo di processo di manutenzione.
8. Nella scheda **Previsione articolo**, è possibile selezionare dimensioni inventariali che devono essere visualizzate nella riga articolo. Selezionare **Inventario** \> **Dimensioni**, selezionare le dimensioni da visualizzare, impostare l'opzione **Salva impostazione** su **Sì**, quindi selezionare **OK**.
9. Nella scheda **Previsione articolo**, selezionare **Utilizzo dell'articolo** per visualizzare una panoramica sull'utilizzo dell'articolo nella riga selezionata in Gestione cespiti in relazione a cespiti, valore predefinito di tipo di processo di manutenzione, pezzi di ricambio e ordini di lavoro. 

    La Scheda dettaglio **Totali previsione di manutenzione** visualizza una panoramica dei totali di previsione. Questa panoramica include il numero totale di ore e righe di previsione create.

    > [!NOTE]
    > Per copiare l'impostazione della previsione da un altro tipo di processo di manutenzione, selezionare **Copia previsione**, quindi selezionare il tipo di processo di manutenzione da cui copiare l'impostazione.

11. Selezionare **Salva** per salvare le modifiche.
12. Chiudere la pagina **Previsione predefinita tipo di processo di manutenzione** per tornare alla pagina **Valori predefiniti tipo di processo di manutenzione**.
13. Selezionare **Elenco di controllo di manutenzione**.
14. Nella pagina **Elenco di controllo dei valori predefiniti tipo di processo di manutenzione**, è possibile aggiungere righe di elenco di controllo di manutenzione al valore predefinito di tipo di processo di manutenzione selezionato. Nella Scheda dettaglio **Righe elenco di controllo di manutenzione**, selezionare **Nuovo** per aggiungere una riga di elenco di controllo di manutenzione.

    I numeri di riga sono automaticamente immessi nel campo **Numero riga** per indicare la sequenza delle righe di elenco di controllo di manutenzione. È possibile modificare i numeri di riga come necessario. Dopo aver creato la prima riga di elenco di controllo di manutenzione, selezionare la riga e premere il tasto **Freccia giù** per aggiungere una riga sotto tale riga. In alternativa, è possibile selezionare una riga di elenco di controllo di manutenzione e quindi **Nuovo**. In questo caso, una nuova riga viene aggiunta sopra la riga di elenco di controllo di manutenzione.

15. Nel campo **Tipo**, selezionare il tipo di riga e quindi aggiungere informazioni relative al tipo di elenco di controllo di manutenzione. Per una descrizione dei tipi disponibili e dei campi correlati, vedere la sezione [Creare un modello di elenco di controllo di manutenzione](#create-a-maintenance-checklist-template).

    > [!NOTE]
    > Per copiare l'impostazione dell'elenco di controllo di manutenzione da un altro tipo di processo di manutenzione, selezionare **Copia elenco di controllo di manutenzione**, quindi selezionare il tipo di processo di manutenzione da cui copiare l'impostazione.
    >
    > È possibile creare facilmente un modello da un elenco di controllo di manutenzione esistente. È quindi possibile riutilizzare il modello in molteplici elenchi di controllo di manutenzione. Il nuovo modello sarà una copia esatta dell'elenco di controllo di manutenzione attivo. Selezionare **Crea modello** e quindi immettere un nome per il modello. Per sostituire l'elenco di controllo di manutenzione esistente con una singola riga che fa riferimento al nuovo modello, impostare l'opzione **Sostituisci** su **Sì**. È possibile visualizzare il contenuto del modello nella pagina dei dettagli **Modelli elenco di controllo di manutenzione**.

16. Selezionare **Salva** per salvare le modifiche.
17. Ritornare alla pagina **Valori predefiniti tipo di processo di manutenzione**.
18. Selezionare **Strumenti**.
19. Nella pagina **Strumenti predefiniti tipo di processo di manutenzione**, è possibile aggiungere gli strumenti (risorse) che devono essere utilizzati per il tipo di processo di manutenzione. Selezionare **Nuovo** e quindi lo strumento nel campo **Risorsa**.

    > [!NOTE]
    > Per copiare l'impostazione dello strumento da un altro tipo di processo di manutenzione, selezionare **Copia strumenti**, quindi selezionare il tipo di processo di manutenzione da cui copiare l'impostazione.

20. Selezionare **Salva** per salvare le modifiche.
21. Ritornare alla pagina **Valori predefiniti tipo di processo di manutenzione**.
22. Selezionare **Descrizione lavoro**.
23. Nella pagina **Descrizione lavoro** selezionare **Modifica**, quindi aggiungere una descrizione relativa al valore predefinito di tipo di processo di manutenzione, come necessario.
24. Selezionare **Salva** per salvare la descrizione.

    Se si aggiunge una descrizione del lavoro, sovrascrive quella eventualmente impostata per il tipo di processo di manutenzione nella pagina **Tipi di processo di manutenzione**. Se non si aggiunge una descrizione del lavoro in questo campo, viene utilizzata una qualsiasi descrizione impostata per il tipo di processo di manutenzione. Le descrizioni vengono trasferite automaticamente agli ordini di lavoro che utilizzano il tipo di processo di manutenzione o il valore predefinito di tipo di processo di manutenzione predefinito.

25. Ritornare alla pagina **Valori predefiniti tipo di processo di manutenzione**.
26. Per impostare gli allegati in una riga predefinita di tipo di processo di manutenzione selezionata, selezionare **Allega documenti**. Gli allegati impostati in una riga predefinita di tipo di processo di manutenzione sono automaticamente inclusi nelle righe di ordine di lavoro che utilizzano quella riga.
27. Selezionare **Nuova** e quindi selezionare un tipo di documento.
28. Caricare il documento o il file.
29. Impostare i campi nella pagina **Allegati**. L'impostazione degli allegati utilizza la funzionalità di impostazione di documenti standard.
30. Selezionare **Salva** per salvare l'allegato.

    > [!NOTE]
    > Gli allegati in una riga predefinita di tipo di processo di manutenzione vengono stampati insieme a un report di ordine di lavoro solo se i tipi di documento degli allegati vengono selezionati nella scheda **Tipi di documento** della pagina **Parametri di gestione cespiti** (**Gestione cespiti** \> **Impostazione** \> **Parametri di gestione cespiti**). Esempi di allegati includono linee guida che descrivono come completare uno specifico processo o elenco di controllo di manutenzione predefinito (se non si utilizza la funzionalità dell'elenco di controllo di manutenzione per le righe predefinite di tipo di processo di manutenzione).

    Nella pagina **Valori predefiniti tipo di processo di manutenzione**, ogni riga mostra il numero di ore previste e il numero di righe create per articoli, spese, elenchi di controllo di manutenzione e strumenti. Il campo **Cespiti** mostra il numero di cespiti attivi relativi alla riga predefinita di tipo di processo di manutenzione.

31. Per copiare un valore predefinito di tipo di processo di manutenzione in un altro valore predefinito di tipo di processo di manutenzione, selezionare la riga predefinita di tipo di processo di manutenzione in cui copiare un'altra impostazione, selezionare **Copia impostazione**, quindi selezionare il valore predefinito di tipo di processo di manutenzione da copiare.
32. Per visualizzare un elenco dei cespiti, i piani di manutenzione o i cicli di manutenzione che utilizzano correntemente una riga predefinita di tipo di processo di manutenzione, selezionare la riga e quindi selezionare **Utilizzato da**.

![Pagina Valori predefiniti per il tipo di processo di manutenzione](media/07-setup-for-work-orders.png)

Quando il sistema seleziona il valore predefinito di tipo di processo di manutenzione disponibile che deve essere utilizzato in una riga di ordine di lavoro, la selezione è basata sul cespite e sull'impostazione del tipo di cespite associata. Gestione cespiti verifica i record predefiniti di tipo di processo di manutenzione relativi al tipo di processo di manutenzione associato al tipo di cespite per rilevare una possibile corrispondenza. Controlla sempre la combinazione più specifica per prima. In altre parole, per individuare la combinazione più specifica, Gestione cespiti verifica dapprima una possibile corrispondenza con il campo **Settore**. Se non trova corrispondenza, controlla **Variante tipo di processo di manutenzione**. Se non viene trovata alcuna corrispondenza, cerca una corrispondenza con il campo **Tipo di processo di manutenzione** e così via (**Settore** quindi **Variante tipi di processo di manutenzione**, **Tipo di processo di manutenzione**, **Cespite**, **Modello**, **Produttore** e **Tipo di cespite**). Se non viene trovata alcuna corrispondenza, viene utilizzato il record predefinito dove solo il tipo di processo di manutenzione è selezionato.

Un ID di attività di progetto viene automaticamente associato a ogni riga predefinita di tipo di processo di manutenzione creata. L'attività di progetto viene creata nel progetto di previsione selezionato nel campo **Progetto previsione di manutenzione** nella scheda **Cespiti** della pagina **Parametri di gestione cespiti**. Lo scopo dell'attività di progetto è di gestire le previsioni per ore, articoli e spese associate agli ordini di lavoro. Le previsioni di tipo di processo di manutenzione vengono trasferite automaticamente alla riga dell'ordine di lavoro e vengono copiate dal progetto di previsione nel progetto di ordine di lavoro creato per la riga di ordine di lavoro. Lo scopo dell'attività di progetto è di gestire le previsioni associate agli ordini di lavoro.

È possibile impostare un processo batch per aggiornare riferimenti predefiniti di tipo di processo di manutenzione a intervalli regolari, oppure è possibile eseguire manualmente il processo. Per creare un processo batch o eseguire un aggiornamento manuale, selezionare **Gestione cespiti** \> **Periodico** \> **Manutenzione preventiva** \> **Aggiorna riferimenti predefiniti tipo di processo di manutenzione**.

## <a name="overview-of-maintenance-job-types-that-are-related-to-assets"></a>Panoramica dei tipi di processo di manutenzione associati a cespiti

Dopo avere creato le combinazioni predefinite di tipo di processo di manutenzione necessarie, è possibile utilizzare la pagina **Tutti i cespiti** per ottenere una panoramica del valore predefinito di tipo di processo di manutenzione corrente associato a uno specifico cespite. La panoramica mostra tutte le combinazioni predefinite di tipo di processo di manutenzione utilizzabili nel tipo di cespite selezionato per il cespite. Queste combinazioni includono combinazioni con variazioni di varianti di tipi di processo di manutenzione e settori di processo di manutenzione.

1. Selezionare **Gestione cespiti** \> **Comune** \> **Cespiti** \> **Tutti i cespiti** o **Cespiti attivi**.
2. Nell'elenco, selezionare il cespite per visualizzare una panoramica delle combinazioni dei tipi di processo di manutenzione.
3. Nella scheda **Generale** del riquadro azioni, nel gruppo **Informazioni correlate**, selezionare **Tipi di processo di manutenzione**.

    Il riquadro sinistro della pagina **Tipi di processo di manutenzione cespite** visualizza un elenco di tutte le combinazioni dei tipi di processo di manutenzione associate al cespite selezionato.

4. Selezionare una combinazione di tipi di processo di manutenzione per visualizzare l'impostazione correlata per previsioni, strumenti ed elenchi di controllo di manutenzione. La sezione **Dettagli** nella Scheda dettaglio **Valori predefiniti tipo di processo di manutenzione** visualizza il numero di elenchi di controllo di manutenzione, ore previste, articoli correlati e così via, associati alla combinazione di tipi di processo di manutenzione selezionata.
5. Per visualizzare i dettagli per il tipo di processo di manutenzione selezionato, selezionare **Tipi di processo di manutenzione**.

![Pagina Tipi di processo di manutenzione cespite](media/08-setup-for-work-orders.png)

## <a name="automatic-update-of-maintenance-job-type-forecasts"></a>Aggiornamento automatico delle previsioni di tipo di processo di manutenzione

In Gestione cespiti, è possibile aggiornare automaticamente qualsiasi modifica alle previsioni di tipo di processo di manutenzione per costi orari, costi degli articoli e spese, che sono state aggiornati in altri moduli. In questo modo, si garantisce l'utilizzo dei prezzi di costo più recenti nelle previsioni del tipo di processo di manutenzione.

1. Selezionare **Gestione cespiti** \> **Periodico** \> **Previsione** \> **Aggiorna previsione tipo di processo di manutenzione**.
2. Nella finestra di dialogo **Aggiorna previsione tipo di processo di manutenzione**, nella Scheda dettaglio **Record da includere**, è possibile aggiungere selezioni per determinati tipi di processo di manutenzione come necessario. Selezionare **Filtro** e quindi **Seleziona** per effettuare le selezioni.
3. Nella Scheda dettaglio **Esecuzione in background**, è possibile impostare l'aggiornamento automatico come processo batch, come necessario.
4. Selezionare **OK** per avviare l'aggiornamento delle previsioni.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]