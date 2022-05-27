---
title: Supporto e rinnovi
description: Questo argomento spiega come impostare e utilizzare il processo di supporto e rinnovo per gli ordini cliente per creare un programma di fatturazione per gli articoli di rinnovo.
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
ms.openlocfilehash: 7de74f2b12e8e7201663ba78d936131b301b1ff9
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2022
ms.locfileid: "8685772"
---
# <a name="support-and-renewals"></a>Supporto e rinnovi 

Questo argomento spiega come immettere articoli di supporto o articoli di rinnovo negli ordini cliente. Questi articoli vengono utilizzati per calcolare l'importo dell'addebito per il contratto di supporto originale e/o l'importo del rinnovo utilizzato quando viene creato un programma di fatturazione nella fatturazione abbonamento. Ad esempio, la tua azienda vende un server a un cliente e tu offri un abbonamento per il backup dei dati per il primo anno e la possibilità di rinnovare tale abbonamento ogni anno. L'*articolo di supporto* è l'abbonamento per il primo anno, e l'*articolo di rinnovo* è il rinnovo per ogni anno successivo.

Puoi inserire le informazioni per il contratto di supporto, il contratto di rinnovo o entrambi. Quando immetti le informazioni sul contratto di supporto, solo l'articolo di supporto viene aggiunto all'ordine cliente. Quando immetti le informazioni sul contratto di rinnovo, l'articolo di rinnovo viene utilizzato per creare un programma di fatturazione.

## <a name="support-and-renewal-setup"></a>Configurazione di supporto e rinnovo

Nella pagina **Livelli di supporto e rinnovo** puoi impostare diversi livelli di supporto per gli articoli di supporto e rinnovo. Il supporto o il rinnovo può essere una percentuale dell'importo dell'articolo originale oppure può essere un importo standard.

È possibile selezionare i livelli di supporto predefiniti nella pagina **Parametri di fatturazione ricorrente di contratti**.

Ad esempio, un'azienda potrebbe offrire i seguenti livelli di supporto e rinnovo.

| Livello di supporto | Percentuale supporto | Percentuale di rinnovo |
|---|---|---|
| Illimitata | 40% | 30% |
| Oro | 25% | 18% |
| Argento | 20% | 14% |
| Bronzo | 15% | 10% |

Per creare un livello di supporto o rinnovo, segui questi passaggi.

1. Nella pagina **Livelli di supporto e rinnovo** seleziona **Nuovo**.
2. Nel campo **Livello di supporto** immetti un nome univoco.
3. Nel campo **Descrizione** immettere una descrizione.
4. Nel campo **Metodo di calcolo del supporto** seleziona il metodo di calcolo del supporto. Se selezioni **Percentuale**, inserisci una percentuale di supporto nel campo **Percentuale di supporto**.
5. Nel campo **Metodo di calcolo del rinnovo** seleziona il metodo di calcolo del rinnovo. Se selezioni **Percentuale**, inserisci una percentuale di rinnovo nel campo **Percentuale di rinnovo**.
6. Seleziona **Salva**.

### <a name="fields"></a>Campi

La pagina **Livelli di supporto e rinnovo** contiene i seguenti campi.

| Campo | Description |
|---|---|
| Livello di supporto | Un identificatore univoco per il livello di supporto o di rinnovo (ad esempio, **Oro** o **Argento**). |
| Description | Una descrizione del livello di supporto o rinnovo. |
| Metodo di calcolo supporto | Seleziona il metodo di calcolo del supporto per il livello: **Percentuale** o **Importo standard**. |
| Percentuale supporto | Se hai selezionato **Percentuale** come metodo di calcolo del supporto, specifica la percentuale utilizzata per calcolare il prezzo dell'articolo di supporto. Se hai selezionato **Importo standard** come metodo di calcolo, l'importo viene specificato al momento della creazione della transazione. |
| Metodo di calcolo rinnovo | Seleziona il metodo di calcolo del rinnovo per il livello: **Percentuale** o **Importo standard**. |
| Percentuale di rinnovo | Se hai selezionato **Percentuale** come metodo di calcolo del rinnovo, specifica la percentuale utilizzata per calcolare il prezzo dell'articolo di rinnovo. Se hai selezionato **Importo standard** come metodo di calcolo, l'importo viene specificato al momento della creazione della transazione. |

## <a name="support-and-renewal-process"></a>Elaborazione supporto e rinnovo

La funzionalità di supporto e rinnovo può applicare diversi livelli di supporto agli articoli e aggiornare le informazioni sul rinnovo nella fatturazione abbonamento.

Per poter utilizzare la funzionalità di supporto e rinnovo, è necessario completare le seguenti attività.

1. Nella pagina **Livelli di supporto e rinnovo** crea almeno un livello di supporto o rinnovo.
2. Nella pagina **Configurazione articolo** associa un articolo agli articoli di supporto e rinnovo. Questa attività è necessaria solo se vuoi impostare i valori predefiniti per gli articoli di supporto e/o rinnovo.
3. Nella pagina **Parametri di fatturazione ricorrente di contratti**, specifica il supporto predefinito e le impostazioni di rinnovo per i nuovi programmi di fatturazione.

Per applicare livelli di supporto diversi agli articoli e aggiornare le informazioni sul rinnovo, attieniti alla seguente procedura.

1. Nella pagina **Tutti gli ordini cliente**, crea un ordine cliente.
2. Nella Scheda dettaglio **Righe ordine cliente**, aggiungi un articolo.
3. Nella scheda **Fattura** seleziona **Supporto e rinnovo \> Aggiungi supporto e rinnovo**.
4. Nella pagina **Processo di supporto e rinnovo** la sezione dell'intestazione viene aggiornata con le impostazioni della pagina **Parametri di fatturazione ricorrente di contratti**. Questi valori si applicano a tutti gli articoli di supporto e rinnovo. Ad esempio, se la frequenza di fatturazione è impostata su **Annuale**, tutte le righe di vendita create con un articolo di rinnovo hanno una frequenza annuale. Per associare l'ordine cliente a un programma di fatturazione esistente, seleziona un valore nel campo **Numero programma di fatturazione**.
5. Per modificare la data di inizio del supporto o del rinnovo, imposta l'opzione **Sostituisci la data di inizio** su **sì**.
6. Per aggiungere o modificare l'articolo di supporto, seleziona la casella di controllo **Supporto**, quindi immetti un articolo di supporto nel campo **Articolo di supporto**. L'articolo viene aggiunto all'ordine cliente.
7. Per aggiungere o modificare l'articolo di rinnovo, seleziona la casella di controllo **Rinnovo**, quindi immetti un articolo di rinnovo nel campo **Articolo di rinnovo**. Quando l'ordine cliente viene fatturato, verrà creato un programma di fatturazione che include l'articolo.
8. Seleziona **OK**.
9. Sulla scheda **Genera**, seleziona **Fattura**. Quando l'ordine cliente viene registrato, viene creato il programma di fatturazione. Nei dettagli del messaggio viene visualizzata una notifica che include le informazioni sul programma di fatturazione.
10. Nella pagina elenco **Tutti i programmi di fatturazione o Programmi di fatturazione attivi**, seleziona il numero del programma di fatturazione per rivedere i dettagli del programma di fatturazione nella pagina **Programmi di fatturazione**.
11. Nella Scheda dettaglio **Righe programma di fatturazione**, seleziona **Supporto e rinnovo** per rivedere i dettagli delle righe che sono state create.

> [!NOTE]
> Se è necessario modificare la data di inizio del rinnovo per una riga programma di fatturazione, è possibile modificare il valore **Data d'inizio** per la riga nella pagina **Programmi di fatturazione**. Quando apri la pagina **Visualizza dettagli di fatturazione** per la riga, il campo **Data di inizio fatturazione** viene aggiornato con la nuova data. Il valore **Data di fine fatturazione** viene ricalcolato in base alla frequenza di fatturazione. La data di inizio del rinnovo può essere aggiornata solo se la prima fattura per il programma di fatturazione del rinnovo non è stata creata e registrata. Dopo aver creato e registrato la prima fattura, la data di inizio non può essere modificata.

Il processo di supporto e rinnovo è disponibile solo per l'ordine cliente. Quando aggiungi gli articoli di supporto e rinnovo a un ordine cliente, puoi creare un nuovo programma di fatturazione o aggiungere l'articolo di rinnovo a un programma di fatturazione esistente.

## <a name="support-and-renewal-audit"></a>Controllo supporto e rinnovo

Nella pagina **Controllo supporto e rinnovo** puoi rivedere i dettagli delle righe programma di fatturazione create dall'articolo di rinnovo in un ordine cliente. Questa opzione è disponibile quando l'articolo del programma di fatturazione è un articolo di rinnovo.

Per modificare le informazioni di supporto e rinnovo per una riga programma di fatturazione, attieniti alla seguente procedura.

1. Nella pagina **Tutti i programmi di fatturazione**, seleziona il numero del programma di fatturazione.
2. Nella sezione **Righe programma di fatturazione**, seleziona una riga, quindi seleziona **Supporto e rinnovo**.
3. Esamina tutte le informazioni per l'articolo di supporto o rinnovo.
4. Apporta le modifiche richieste al livello di supporto, alla percentuale o all'importo di rinnovo, quindi inserisci un valore nel campo **Motivo della modifica**.
5. Seleziona **Elabora**.

### <a name="fields"></a>Campi

La pagina **Controllo supporto e rinnovo** contiene i seguenti campi.

| Campo | Description |
|-------|-------------|
| Numero articolo | Il numero di articolo della riga di programma di fatturazione. |
| Nome prodotto | Il nome del prodotto. |
| Livello piano di supporto | Visualizza o modifica il livello di supporto per l'articolo di rinnovo. |
| Percentuale di rinnovo | Immetti la percentuale di rinnovo utilizzata quando viene calcolato il prezzo unitario per un articolo di rinnovo in un programma di fatturazione. |
| Importo rinnovo | Immetti l'importo di rinnovo utilizzato quando viene calcolato il prezzo unitario per un articolo di rinnovo in un programma di fatturazione. |
| Motivo della modifica | Inserisci il motivo della modifica delle informazioni sul supporto e sul rinnovo. Devi inserire un motivo quando modifichi il valore **Percentuale di rinnovo**, **Importo di rinnovo**, o **Livello del piano di supporto**. |
| Articolo di vendita originale | Il numero dell'articolo di vendita originale dall'ordine cliente. |
| Importo netto originale | L'importo netto originale per l'articolo. |
| Livello supporto originale | Il livello di supporto originale per l'articolo. |
| Percentuale di rinnovo originale | La percentuale di rinnovo originale per l'articolo. |
| Importo rinnovo originale | L'importo di rinnovo originale per l'articolo. |
| **Griglia** | |
| Livello supporto originale | Il livello di supporto precedente. |
| Percentuale di rinnovo originale | La percentuale di rinnovo precedente. |
| Importo rinnovo originale | L'importo di rinnovo precedente. |
| Autore modifica | Nome dell'utente che ha effettuato la modifica. |
| Data e ora modifica | La data in cui è stata apportata la modifica. |
| Motivo | Motivo della modifica. |
