---
title: Modelli di fasi
description: Questo articolo spiega come impostare la funzionalità di fatturazione a fasi nella fatturazione abbonamento.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: d3c2cf751e4998c73bc3816e5b81e8d5963c8e53
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8856772"
---
# <a name="milestone-billing"></a>Fatturazione a fasi

[!include [banner](../includes/banner.md)]

Questo articolo spiega come definire i modelli per la funzionalità di fatturazione a fasi nella fatturazione abbonamento. Per ciascuna riga nel modello a fasi, è possibile definire la percentuale o l'importo di allocazione. È quindi possibile assegnare il modello a fasi agli elementi del programma di fatturazione che utilizzano la funzionalità di fatturazione a fasi.

## <a name="add-a-template"></a>Aggiungi un modello

Per aggiungere un modello a fasi, effettua le operazioni indicate di seguito.

1. Vai a **Fatturazione abbonamento \> Fatturazione ricorrente di contratti \> Impostazione \> Modelli a fasi**.
2. Selezionare **Nuovo**.
3. Nel campo **Modello a fasi** immetti un identificatore univoco per il nuovo modello.
4. Nel campo **Descrizione** immettere una descrizione.
5. Nel campo **Metodo di allocazione** seleziona un metodo di allocazione.
6. Opzionale: nel campo **Importo totale** specifica l'importo totale per il modello.
7. Seleziona **Aggiungi** per aggiungere una riga. Quindi, nel campo **Numero articolo** seleziona il numero di articolo per la nuova riga.
8. Esegui uno dei passaggi riportati di seguito, in base al valore selezionato nel campo **Metodo di allocazione**:

    - Se hai selezionato **Percentuale** come metodo di assegnazione, nel campo **Percentuale** specifica la percentuale di allocazione per ciascuna riga. Se specifichi le percentuali, la somma delle percentuali mostrata nel campo **Percentuale totale** deve essere uguale a **100**.
    - Se hai selezionato **Importo variabile** come metodo di assegnazione, nel campo **Importo** specifica l'importo per ciascuna riga.
    - Se hai selezionato **Importo uguale** come metodo di allocazione, non è necessario specificare un importo. Ogni riga verrà aggiornata con la percentuale e l'importo corretti, in base al numero di elementi aggiunti al modello.

9. Seleziona **Salva**.

## <a name="delete-a-template"></a>Eliminare un modello

Per eliminare un modello a fasi, effettua le operazioni indicate di seguito.

1. Seleziona una o più righe da eliminare, quindi seleziona **Elimina**.
2. Quando viene richiesto di confermare l'azione, seleziona **Sì**.

## <a name="milestone-template-fields"></a>Campi del modello a fasi

La pagina **Modello a fasi** contiene i seguenti campi.

| Campo | Description |
|-------|-------------| 
| Modello di fasi | Identificatore univoco del modello a fasi. |
| Description | Descrizione del modello a fasi. |
| Metodo di allocazione | <p>Seleziona il metodo di allocazione:</p><ul><li>**Percentuale di completamento** – Viene utilizzato un valore di completamento cumulativo per ciascuna riga.</li><li>**Percentuale** – È possibile specificare un importo percentuale per l'assegnazione. La somma di tutte le percentuali deve essere 100.</li><li>**Importo variabile** – È possibile specificare un importo per l'assegnazione. L'importo dell'allocazione è specificato a livello di transazione.</li><li>**Importo uguale** – Le percentuali di allocazione vengono calcolate automaticamente e suddivise equamente tra le voci nel modello.</li></ul> |
| Importo totale | Specifica l'importo a fasi per il modello. |
| **Righe** | |
| Numero articolo | Seleziona il numero dell'articolo per il modello a fasi. |
| Nome prodotto | Nome dell'articolo. |
| Percentuale | <p>Immetti la percentuale di allocazione per la riga:</p><ul><li>Se il campo **Metodo di allocazione** è impostato su **Percentuale**, specifica la percentuale per la riga.</li><li>Se il campo **Metodo di allocazione** è impostato su **Importo uguale**, la percentuale viene automaticamente divisa in percentuali uguali, in base al numero di elementi nel modello.</li></ul><p>La somma di tutte le percentuali deve essere 100.</p><p>Se un valore **Importo totale** è specificato nell'intestazione e modifichi il valore **Percentuale** per la riga, il valore **Importo** viene aggiornato. Viceversa, se modifichi il valore **Importo**, il valore **Percentuale** viene aggiornato.</p> |
| Importo | <p>L'importo di allocazione per la riga:</p><ul><li>Se il campo **Metodo di allocazione** è impostato su **Importo variabile**, specifica l'importo per la riga.</li><li>Se il campo **Metodo di allocazione** è impostato su **Importo uguale**, l'importo viene automaticamente diviso in importi uguali, in base al numero di elementi nel modello e al valore **Importo totale** specificato nell'intestazione.</li></ul><p>La somma di tutti gli importi deve essere uguale al valore **Importo totale** specificato nell'intestazione.</p><p>Se un valore **Importo totale** è specificato nell'intestazione e modifichi il valore **Importo** per la riga, il valore **Percentuale** viene aggiornato. Viceversa, se modifichi il valore **Percentuale**, il valore **Importo** viene aggiornato.</p> |
| **Totali** | |
| Percentuale totale | La somma delle percentuali. La somma di tutte le percentuali deve essere 100. |
| Importo totale | La somma dei valori **Importo** per tutte le righe. La somma deve essere uguale al valore **Importo totale** specificato nell'intestazione. |
| Importo residuo | Importo rimanente. Il valore è calcolato come il valore **Importo totale** dell'intestazione meno la somma dei valori **Importo** per tutte le righe.|

## <a name="milestone-allocation"></a>Allocazione fasi

Prima di iniziare a utilizzare la funzionalità a fasi, è necessario completare queste attività.

1. Aggiungi uno o più modelli a fasi.
2. Creare un gruppo di programmi di fatturazione. Specifica **A fasi** come tipo di elemento e seleziona un modello.
3. Nella pagina **Impostazioni articolo** (**Fatturazione abbonamento \> Fatturazione ricorrente di contratti \> Impostazione \> Articoli**), seleziona una relazione articolo e un modello a fasi per l'impostazione dell'articolo.

Dopo aver creato i modelli a fasi, i gruppi di programmi di fatturazione e gli articoli, puoi creare un programma di fatturazione che utilizzi la funzionalità a fasi.

Per impostare un programma di fatturazione che utilizza le fasi, attieniti alla seguente procedura.

1. Dall'elenco **Tutti i programmi di fatturazione o Programmi di fatturazione attivi** della pagina **Programmi di fatturazione** seleziona **Nuovo**.
2. Nella pagina **Tutti i programmi di fatturazione** crea un nuovo programma di fatturazione e specifica un conto cliente e una data di inizio.
3. Nella sezione **Righe programma di fatturazione**, seleziona **Aggiungi riga**. Quindi aggiungi un numero di articolo e imposta il campo **Tipo di articolo** su **A fasi**.

    Se per l'articolo viene impostato un modello a fasi predefinito, gli eventi a fasi vengono aggiunti automaticamente alle righe programma di fatturazione. Le date di fine sono vuote per le righe a fasi.

    Se per l'articolo non è impostato alcun modello a fasi, seleziona **Allocazione a fasi**. Poi, nella pagina **Allocazione a fasi** seleziona un modello a fasi e apporta gli aggiornamenti richiesti. Quindi seleziona **Chiudi** per tornare al programma di fatturazione e completare la creazione del programma di fatturazione.

4. Per creare fatture per il programma di fatturazione, è necessario aggiornare la data di fine per ogni evento a fasi. Per un singolo programma di fatturazione, è possibile aggiornare la data di fine dell'evento a fasi nelle righe del programma di fatturazione. Per aggiornare più programmi di fatturazione, seleziona **Aggiorna processo data di completamento**.
5. Dopo aver aggiornato la data di fine, è possibile creare la fattura. Per un unico programma di fatturazione, seleziona **Genera fattura** nella pagina **Tutti i programmi di fatturazione**. Per creare fatture per più programmi di fatturazione, seleziona **Genera fattura** o **Genera elaborazione batch fattura** sotto **Attività periodiche**.

## <a name="edit-milestone-allocation-on-a-billing-schedule-line"></a>Modificare l'allocazione a fasi per una riga programma di fatturazione

Per modificare l'allocazione a fasi per una riga programma di fatturazione, segui questi passaggi.

1. Nella pagina **Programmi di fatturazione** > **Tutti i programmi di fatturazione o Programmi di fatturazione attivi**, nel campo **Numero di programma**, seleziona il numero del programma di fatturazione.
2. Nella sezione **Righe programma di fatturazione** immetti un articolo, specifica **A fasi** come tipo e seleziona **Allocazione a fasi**.
3. Nel campo **Modello a fasi**, seleziona un modello a fasi.
4. Seleziona **Elabora**. Le righe del modello a fasi vengono aggiunte automaticamente alle righe del programma di fatturazione.

## <a name="milestone-allocation-fields"></a>Campo di allocazione a fasi

La pagina **Allocazione a fasi** contiene i seguenti campi.

| Campo | Description |
|-------|-------------|
| Articolo padre | Il numero di articolo dell'articolo padre. |
| Prezzo esteso | <p>Il prezzo esteso dell'articolo. Il valore corrisponde al valore **Importo netto** della riga del programma di fatturazione.</p></p>Per un articolo padre a fasi, il valore predefinito è il valore **Importo totale** specificato per il modello a fasi. Se l'importo totale è 0 (zero), il valore predefinito è il valore **Importo netto** della riga del programma di fatturazione.</p> |
| Modello di fasi | ID modello a fasi della voce. |
| Descrizione modello | Descrizione del modello a fasi. |
| Metodo di allocazione | Il metodo di allocazione utilizzato per il modello a fasi. |
| **Righe** | I valori predefiniti per tutte le righe si basano sul modello a fasi selezionato. Se necessario, puoi modificarli. |
| Numero articolo | Il numero dell'articolo per il modello di allocazione a fasi. |
| Nome prodotto | Il nome del prodotto. |
| Percentuale | <p>La percentuale di allocazione per la riga. La somma di tutte le percentuali deve essere 100.</p><p>Se modifichi il valore **Percentuale** per la riga, il valore **Importo netto** viene aggiornato. Viceversa, se modifichi il valore **Importo netto**, il valore **Percentuale** viene aggiornato.</p> |
| Importo netto | <p>L'importo di allocazione per la riga. La somma degli importi netti per tutte le righe deve essere uguale al valore **Prezzo esteso** specificato nell'intestazione.</p><p>Se modifichi il valore **Importo netto** per la riga, il valore **Percentuale** viene aggiornato. Viceversa, se modifichi il valore **Percentuale**, il valore **Importo netto** viene aggiornato.</p> |
| **Totali** | |
| Percentuale totale | La somma dei valori **Percentuale** per tutte le righe. Questa somma deve essere uguale a 100. |
| Importo totale | La somma dei valori **Importo netto** per tutte le righe. La somma deve essere uguale al valore **Prezzo esteso** specificato nell'intestazione. |
| Importo residuo | Importo rimanente. Il valore è calcolato come il valore **Prezzo esteso** dell'intestazione meno la somma dei valori **Importo netto** per tutte le righe. L'importo finale deve essere pari a 0 (zero). |
