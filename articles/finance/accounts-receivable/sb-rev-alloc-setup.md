---
title: Imposta allocazione ricavi con più elementi
description: Questo argomento descrive come impostare i parametri per l'allocazione dei ricavi con più elementi nella fatturazione abbonamento.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: e422b16d1c4505b2837bb282918ecada902b806e
ms.sourcegitcommit: 23588e66e25c05e989f3212ac519d7016820430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2022
ms.locfileid: "8566361"
---
# <a name="set-up-multiple-element-revenue-allocation"></a>Imposta allocazione ricavi con più elementi

L'allocazione dei ricavi con più elementi consente di impostare diversi modelli utilizzati per calcolare e allocare i ricavi per più elementi. Questa funzionalità può aiutarti a rispettare Accounting Standards Codification Topic 606 (ASC 606) e/o l'International Financial Reporting Standard 15 (IFRS 15).

## <a name="multiple-element-revenue-allocation-parameters"></a>Parametri di allocazione ricavi con più elementi

Usa la pagina **Parametri di allocazione ricavi con più elementi** per impostare i parametri per l'allocazione dei ricavi con più elementi.

### <a name="standalone-selling-price-origin"></a>Origine prezzo di vendita autonomo

Il campo **Origine prezzo di vendita autonomo** determina da dove viene il prezzo di vendita autonomo. È possibile aggiornare il valore nella pagina **Prezzo di vendita autonomo articolo** e nella transazione. Sono disponibili le seguenti opzioni.

| Opzione | Description |
|--------|-------------|
| Importo | Il prezzo di vendita autonomo è un importo specificato dall'utente maggiore di 0 (zero). L'importo viene convertito tra le valute funzionali e di origine come richiesto. |
| Prezzo di vendita base | Il prezzo di vendita autonomo corrisponde al prezzo di vendita di base dell'articolo. |
| Prezzo fattura | Il prezzo di vendita autonomo corrisponde al prezzo in fattura dell'articolo. |
| Percentuale di articolo | Il prezzo di vendita autonomo è specificato come valore percentuale e viene calcolato in base al prezzo dell'articolo. Se selezioni questa opzione, specifica la percentuale predefinita. |
| Alloca importo residuo | <p>L'origine del prezzo di vendita autonomo è calcolata come *Valore totale contratto dell'articolo padre* – *Prezzo di vendita autonomo totale degli articoli figlio*:</p><ul><li>*Valore totale contratto dell'articolo padre* è l'importo netto o fatturato.</li><li>*Prezzo di vendita autonomo totale degli articoli figlio* è la somma del prezzo di vendita autonomo esteso o di contratto di tutti gli articoli figlio, ad eccezione dell'articolo figlio che utilizza questa origine del prezzo di vendita autonomo.</li></ul><p>Se l'importo calcolato è un valore negativo, l'importo viene impostato su 0 (zero).</p><p>**Nota:** Questa opzione può essere selezionata per un solo articolo figlio nella suddivisione dei ricavi.</p> |
| Nessuna | L'origine del prezzo di vendita autonomo si basa sugli articoli figlio. Questa opzione si applica agli articoli definiti come articoli padre in un modello di suddivisione dei ricavi. Se la casella di controllo **Suddivisione ricavi** è selezionata, questa opzione è selezionata automaticamente e l'impostazione non può essere modificata. |
| Percentuale di prezzo di fattura padre | L'origine del prezzo di vendita autonomo è una percentuale del prezzo in fattura dell'articolo padre. Puoi modificare il valore predefinito. Questa opzione è disponibile solo per articoli figlio in un modello di suddivisione dei ricavi. |
| Percentuale di prezzo standard padre | L'origine del prezzo di vendita autonomo è una percentuale del prezzo standard dell'articolo padre. Puoi modificare il valore predefinito. Questa opzione è disponibile solo per articoli figlio in un modello di suddivisione dei ricavi. È l'opzione predefinita per gli articoli figlio. Quando l'opzione per un articolo figlio viene modificata da **Percentuale del prezzo standard padre** a **Percentuale del prezzo in fattura padre**, o da **Percentuale del prezzo in fattura padre** a **Percentuale del prezzo standard padre**, vengono aggiornati anche i valori calcolati. |

### <a name="account-for-revenue-allocation-rounding-differences"></a>Conto per differenze di arrotondamento allocazione ricavi

Il campo **Conto per differenze di arrotondamento allocazione ricavi** specifica il conto utilizzato per registrare eventuali rettifiche di arrotondamento a un importo di ricavi di contratto. È disponibile quando viene utilizzata la fatturazione di contratto ricorrente.

## <a name="item-standalone-selling-price"></a>Prezzo di vendita autonomo articolo

Usa la pagina **Prezzo di vendita autonomo dell'articolo** per specificare l'origine e il prezzo di vendita autonomo di un articolo. I valori specificati in questa pagina vengono utilizzati come valori predefiniti nella pagina **Allocazione ricavi** nell'allocazione dei ricavi con più elementi e nella fatturazione del contratto ricorrente.

### <a name="specify-item-standalone-selling-price"></a>Specificare il prezzo di vendita autonomo dell'articolo

Per specificare il prezzo autonomo per un articolo, attieniti alla seguente procedura.

1. Nella pagina **Prezzo di vendita autonomo dell'articolo** nel campo **Origine del prezzo di vendita autonomo** seleziona l'origine del prezzo di vendita autonomo.
2. Esegui uno dei passaggi riportati di seguito, in base al valore selezionato nel campo **Origine del prezzo di vendita autonomo**:

    * Se hai selezionato **Percentuale dell'articolo**, specifica la percentuale nel campo **Percentuale**.
    * Se hai selezionato **Importo**, specifica l'importo nel campo **Prezzo di vendita autonomo**.

2. Per ogni articolo che vuoi aggiungere all'elenco seleziona **Aggiungi**.
3. Nel campo **Codice articolo** seleziona il codice articolo. Nel campo **Relazione articolo** seleziona la relazione dell'articolo. Per gli articoli in cui la casella di controllo **Suddivisione ricavi** è deselezionata, la combinazione selezionata di codice articolo e relazione articolo deve essere univoca.
4. Modifica il valore predefinito del campo **Origine del prezzo di vendita autonomo**, **Prezzo di vendita autonomo**, o **Percentuale** come richiesto.
5. Per ogni articolo padre che vuoi aggiungere all'elenco seleziona **Aggiungi**.
6. Nel campo **Codice articolo** seleziona il codice articolo. Nel campo **Relazione articolo** seleziona la relazione dell'articolo.
7. Seleziona la casella di controllo **Suddivisione ricavi**.
8. Nel campo **Relazione articolo** seleziona la relazione dell'articolo. L'elenco viene aggiornato con l'articolo padre e tutti gli articoli figlio.
9. Per l'articolo figlio, modifica il valore predefinito del campo **Origine del prezzo di vendita autonomo**, **Percentuale del prezzo standard padre**, **Percentuale del prezzo in fattura padre**, o **Alloca importo residuo** come richiesto.
10. Per aggiungere più articoli contemporaneamente, seleziona **Aggiungi articoli**.
11. Aggiorna la query per selezionare l'intervallo di articoli che desideri aggiungere.
12. Seleziona **OK**, rivedi l'elenco di articoli che hai aggiunto e seleziona **OK**.

### <a name="fields"></a>Campi

La pagina **Prezzo di vendita autonomo dell'articolo** contiene i seguenti campi.

| Campo | Description |
|-------|-------------|
| Origine prezzo di vendita autonomo | <p>Seleziona l'origine del prezzo di vendita autonomo:</p><ul><li>**Importo** – Il prezzo di vendita autonomo è un importo specificato dall'utente maggiore di 0 (zero). L'importo viene convertito tra le valute funzionali e di origine come richiesto.</li><li>**Prezzo di vendita di base** – Il prezzo di vendita autonomo corrisponde al prezzo di vendita di base dell'articolo.</li><li>**Prezzo in fattura** – Il prezzo di vendita autonomo corrisponde al prezzo in fattura dell'articolo.</li><li>**Percentuale dell'articolo** – Il prezzo di vendita autonomo è specificato come valore percentuale e viene calcolato in base al prezzo dell'articolo. Se selezioni questa opzione, specifica la percentuale predefinita.</li></ul>**Alloca importo residuo** – L'origine del prezzo di vendita autonomo è calcolata come *Valore totale contratto dell'articolo padre* – *Prezzo di vendita autonomo totale degli articoli figlio*:</p><ul><li>*Valore totale contratto dell'articolo padre* è l'importo netto o fatturato.</li><li>*Prezzo di vendita autonomo totale degli articoli figlio* è la somma del prezzo di vendita autonomo esteso o di contratto di tutti gli articoli figlio, ad eccezione dell'articolo figlio che utilizza questa origine del prezzo di vendita autonomo.</li></ul><p>Se l'importo calcolato è un valore negativo, l'importo viene impostato su 0 (zero).</p><p>**Nota:** Questa opzione può essere selezionata per un solo articolo figlio nella suddivisione dei ricavi.</p></li><li>**Nessuno** – L'origine del prezzo di vendita autonomo si basa sugli articoli figlio. Questa opzione si applica agli articoli definiti come articoli padre in un modello di suddivisione dei ricavi. Se la casella di controllo **Suddivisione ricavi** è selezionata, questa opzione è selezionata automaticamente e l'impostazione non può essere modificata.</li><li>**Percentuale del prezzo in fattura padre** – L'origine del prezzo di vendita autonomo è una percentuale del prezzo in fattura dell'articolo padre. Puoi modificare il valore predefinito. Questa opzione è disponibile solo per articoli figlio in un modello di suddivisione dei ricavi.</li><li>**Percentuale del prezzo standard padre** – L'origine del prezzo di vendita autonomo è una percentuale del prezzo standard dell'articolo padre. Puoi modificare il valore predefinito. Questa opzione è disponibile solo per articoli figlio in un modello di suddivisione dei ricavi. È l'opzione predefinita per gli articoli figlio. Quando l'opzione per un articolo figlio viene modificata da **Percentuale del prezzo standard padre** a **Percentuale del prezzo in fattura padre**, o da **Percentuale del prezzo in fattura padre** a **Percentuale del prezzo standard padre**, vengono aggiornati anche i valori calcolati.</li></ul> |
| Prezzo di vendita autonomo | Specifica il prezzo di vendita autonomo dell'articolo. Questo campo è disponibile quando il campo **Origine del prezzo di vendita autonomo** è impostato su **Importo**. |
| Percentuale | Specifica la percentuale del prezzo di vendita autonomo. Questo campo è disponibile quando il campo **Origine del prezzo di vendita autonomo** è impostato su **Percentuale dell'articolo**, **Percentuale del prezzo in fattura padre**, o **Percentuale del prezzo standard padre**. |
| Suddivisione ricavi | <p>Specifica se una riga utilizza la suddivisione dei ricavi:</p><ul><li>**Selezionato** – Solo gli articoli per i quali è impostato un modello di suddivisione dei ricavi possono essere selezionati nel campo **Relazione articolo**. Puoi selezionare questa casella di controllo solo per gli articoli padre di un modello di suddivisione dei ricavi.</li><li>**Deselezionato** – L'articolo è un articolo standard che non utilizza la suddivisione dei ricavi.</li></ul> |
| Relazione | Un simbolo indica se l'articolo è un articolo apdre o figlio in una suddivisione dei ricavi. |
| Codice articolo | <p>Seleziona il codice articolo: **Tabella** o **Gruppo**.</p><p>Se la casella di controllo **Suddivisione ricavi** è selezionata, questo campo è impostato su **Tabella** e il valore non può essere modificato.</p> |
| Relazione articolo | <p>Seleziona il numero articolo.</p><p>Se la casella di controllo **Suddivisione ricavi** è selezionata, sono disponibili per la selezione solo gli articoli padre per i quali è impostato un modello di suddivisione dei ricavi. Quando l'articolo padre è selezionato, l'elenco viene aggiornato automaticamente con gli articoli figlio di quell'articolo padre.</p> |
| Articolo padre | Per l'articolo padre, questo campo mostra il numero dell'articolo. Per gli articoli figlio in una suddivisione dei ricavi, mostra il numero dell'articolo padre. |

## <a name="mea-templates"></a>Modelli MEA

Usa la pagina **Modelli MEA** per creare e modificare gli ID modello MEA (Multiple Element Arrangement). Questi ID vengono utilizzati nella pagina **Allocazione ricavi** per raggruppare gli articoli.

### <a name="create-a-template"></a>Crea un modello

Per impostare un modello MEA, effettua le operazioni seguenti.

1. Nella pagina **Modelli MEA**, seleziona **Nuovo**.
1. Nel campo **ID modello MEA** immetti un ID univoco.
1. Nel campo **Descrizione** immettere una descrizione.
1. Nel campo **Conto ricavi contratto differiti** seleziona il conto che vuoi utilizzare per le scritture contabili quando viene creata una fattura contratto MEA. Questo campo è disponibile quando la fatturazione del contratto ricorrente è abilitata e utilizzata.
1. Seleziona **Salva**.
