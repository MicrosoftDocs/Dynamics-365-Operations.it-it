---
title: Allocazione ricavi
description: Questo argomento spiega come usare l'allocazione ricavi nella fatturazione abbonamento.
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
ms.openlocfilehash: 09d3e9295f1fb753156aa603b00372316173721e
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2022
ms.locfileid: "8695248"
---
# <a name="revenue-allocation"></a>Allocazione ricavi

Questo argomento spiega come impostare i parametri di allocazione ricavi per un programma di fatturazione. Puoi impostare o modificare l'allocazione ricavi quando crei il programma di fatturazione. Quando apri la pagina **Allocazione ricavi** per un programma di fatturazione attivo o terminato, i campi sono di sola lettura.

## <a name="specify-the-revenue-allocation-for-a-billing-schedule"></a>Specificare l'allocazione ricavi per un programma di fatturazione

Per specificare l'allocazione ricavi per un programma di fatturazione, segui questi passaggi.

1. Nella pagina elenco **Tutti i programmi di fatturazione o Programmi di fatturazione attivi** seleziona un programma di fatturazione o una riga di programma di fatturazione.
2. Sulla scheda **Allocazione ricavi** nella parte superiore della pagina, seleziona **Allocazione ricavi**.
3. Nel campo **Tipo di organizzazione con più elementi**, seleziona il tipo di organizzazione con più elementi (MEA).
4. Nel campo **Numero di organizzazione con più elementi**, specifica il numero MEA. Poi, nel campo **Conto ricavi di contratto differiti**, specifica il conto ricavi del contratto differiti.

    Se imposti il campo **Tipo di organizzazione con più elementi** su **Singolo**, gli stessi valori **Numero di organizzazione con più elementi** e **Conto ricavi di contratto differiti** si applicano a ciascuna riga. Se imposti il campo **Tipo di organizzazione con più elementi** su **Multiplo**, puoi specificare diversi valori di **Numero di organizzazione con più elementi** e **Conto ricavi di contratto differiti** per ciascuna riga.
    
    Un numero MEA può essere assegnato solo a due o più articoli. Una singola riga non può avere il proprio numero MEA.

5. Seleziona **Salva**.

### <a name="fields"></a>Campi

La pagina **Organizzazione con più elementi** contiene i seguenti campi.

| Campo | Description |
|---|---| 
| Tipo di organizzazione con più elementi | <p>Seleziona il tipo MEA per la transazione:</p><ul><li>**Multiplo** – Le voci della transazione fanno parte della MEA o esistono più organizzazioni.</li><li>**Nessuno** – La transazione è una transazione standard che non prevede l'allocazione ricavi.</li><li>**Singolo** – Tutti gli articoli della transazione fanno parte di una unica MEA.</li></ul> |
| Numero di organizzazione con più elementi | <p>Numero MEA per la riga. Questo campo è disponibile solo quando il campo **Tipo di organizzazione con più elementi** è impostato su **Multiplo**.</p><p>Se questo campo è vuoto e si assegna un numero MEA, i campi **Origine prezzo di vendita autonomo** e **Prezzo di vendita autonomo** vengono aggiornati automaticamente in base ai valori della pagina **Prezzo di vendita autonomo articolo**. Sono disponibili solo i numeri MEA assegnati ad altre righe dell'ordine cliente.</p> |
| Conto ricavi di contratto differiti | Specifica il conto da utilizzare per le scritture contabili quando viene creata una fattura di contratto MEA. Questo campo è disponibile solo quando si usa la fatturazione del contratto ricorrente. |
| **Righe** | |
| Numero variante | Numero della variante dell'ordine cliente. |
| Numero articolo | Numero dell'articolo dell'ordine cliente. |
| Frequenza di fatturazione | La frequenza per l'allocazione ricavi: **Giornaliera**, **Mensile**, **Trimestrale**, **Semestrale**, o **Annuale**. |
| Quantity | Il valore proviene dall'ordine cliente. |
| Valore di contratto | Valore del contratto. |
| Numero di organizzazione con più elementi | <p>Numero MEA per la riga. Questo campo è disponibile solo quando il campo **Tipo di organizzazione con più elementi** è impostato su **Multiplo**.</p><p>Se questo campo è vuoto e si assegna un numero MEA, i campi **Origine prezzo di vendita autonomo** e **Prezzo di vendita autonomo** vengono aggiornati automaticamente in base ai valori della pagina **Prezzo di vendita autonomo articolo**. Sono disponibili solo i numeri MEA assegnati ad altre righe dell'ordine cliente. Se questi valori non sono impostati per l'articolo, i valori della pagina **Parametri di allocazione ricavi con più elementi** vengono utilizzati.</p> | 
| Origine prezzo di vendita autonomo | <p>L'origine del prezzo di vendita autonomo:</p><ul><li>**Importo** – Il prezzo di vendita autonomo è un importo specificato dall'utente maggiore di 0 (zero). L'importo viene convertito tra le valute funzionali e di origine come richiesto.</li><li>**Prezzo di vendita di base** – Il prezzo di vendita autonomo corrisponde al prezzo di vendita di base dell'articolo.</li><li>**Prezzo in fattura** – Il prezzo di vendita autonomo corrisponde al prezzo in fattura dell'articolo.</li><li>**Percentuale dell'articolo** – Il prezzo di vendita autonomo è specificato come valore percentuale e viene calcolato in base al prezzo dell'articolo. Se selezioni questa opzione, specifica la percentuale predefinita.</li><li>**Alloca importo residuo** – L'origine del prezzo di vendita autonomo è calcolata come *Valore totale contratto dell'articolo padre* – *Prezzo di vendita autonomo totale degli articoli figlio*:</p><ul><li>*Valore totale contratto dell'articolo padre* è l'importo netto o fatturato.</li><li>*Prezzo di vendita autonomo totale degli articoli figlio* è la somma del prezzo di vendita autonomo esteso o di contratto di tutti gli articoli figlio, ad eccezione dell'articolo figlio che utilizza questa origine del prezzo di vendita autonomo.</li></ul><p>Se l'importo calcolato è un valore negativo, l'importo viene impostato su 0 (zero).</p><p>**Nota:** Questa opzione può essere selezionata per un solo articolo figlio nella suddivisione dei ricavi.</p></li><li>**Nessuno** – L'origine del prezzo di vendita autonomo si basa sugli articoli figlio. Questa opzione si applica agli articoli definiti come articoli padre in un modello di suddivisione dei ricavi. Se la casella di controllo **Suddivisione ricavi** è selezionata, questa opzione è selezionata automaticamente e l'impostazione non può essere modificata.</li><li>**Percentuale del prezzo in fattura padre** – L'origine del prezzo di vendita autonomo è una percentuale del prezzo in fattura dell'articolo padre. Questa opzione è disponibile solo per articoli figlio in un modello di suddivisione dei ricavi.</li><li>**Percentuale del prezzo standard padre** – L'origine del prezzo di vendita autonomo è una percentuale del prezzo standard dell'articolo padre. Questa opzione è disponibile solo per articoli figlio in un modello di suddivisione dei ricavi. Quando l'opzione per un articolo figlio viene modificata da **Percentuale del prezzo standard padre** a **Percentuale del prezzo in fattura padre**, o da **Percentuale del prezzo in fattura padre** a **Percentuale del prezzo standard padre**, vengono aggiornati anche i valori calcolati.</li></ul> |
| Prezzo di vendita autonomo | <p>Il prezzo di vendita autonomo per la riga, nella valuta della transazione.</p><p>Il valore nel campo **Importo** viene inserito o calcolato.</p> |
| Prezzo di vendita autonomo di contratto | Prezzo di vendita autonomo di contratto. |
| Ricavi di contratto rimanenti | Importo dei ricavi residui per il contratto. Questo importo è la somma di tutte le righe per le quali non sono state ancora create fatture. |
| Totale ricavi di contratto | Importo ricavi contratto totali per la riga. Questo importo è la somma di tutte le righe indipendentemente dal fatto che siano state create fatture. |
| Conto ricavi di contratto differiti | <p>Specifica il conto da utilizzare per le scritture contabili quando viene creata una fattura di contratto MEA.</p><p>Questo campo è disponibile solo quando si usa la fatturazione del contratto ricorrente.</p> |
| Errore | Eventuali errori che si sono verificati per l'allocazione ricavi. |

## <a name="use-revenue-allocation-on-a-sales-order"></a>Usare l'allocazione ricavi in un ordine cliente

Per utilizzare la funzionalità di allocazione ricavi su un ordine cliente, attieniti alla seguente procedura.

1. Nella pagina **Tutti gli ordini cliente**, crea un ordine cliente che ha articoli.
2. Sulla scheda **Fattura** sotto **Allocazione ricavi**, seleziona **Allocazione ricavi**.
3. Nel campo **Tipo di organizzazione con più elementi**, seleziona il tipo MEA.
4. Nel campo **Numero di organizzazione con più elementi**, specifica il numero MEA.
5. Se il campo **Tipo di organizzazione con più elementi** è impostato su **Multiplo**, seleziona le righe desiderate, quindi seleziona **Applica a selezionati**.
6. Seleziona **Salva**.

Se usi i differimenti di spese e ricavi, la pianificazione di differimento viene creata automaticamente. Puoi esaminarla nella pagina **Tutti i programmi di differimento**.
