---
title: Impostazione automatica dei costi
description: In questo argomento viene descritto come impostare le regole relative ai costi per vari livelli di viaggio in entrata. Sulla base di queste regole, il sistema calcola i costi e li aggiunge automaticamente. Pertanto, gli utenti non devono aggiungere manualmente i costi.
author: sherry-zheng
ms.date: 01/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMCostAutoSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-01-21
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: e1db6c1da4ab311cc3e304d4f422004d5b8423d76f24c8bc8e528f742b1f42fa
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6736769"
---
# <a name="auto-costs-setup"></a>Impostazione automatica dei costi

[!include [banner](../../includes/banner.md)]

È possibile utilizzare la pagina **Costi automatici** per impostare le regole relative ai costi per varie aree di costo (come viaggi, contenitori di spedizione, registrazioni, ordini fornitore, articoli o righe di ordine di trasferimento). In base alle regole e ai campi selezionati dagli utenti quando creano record per una delle aree di costo, il sistema calcola i costi e li aggiunge automaticamente. Pertanto, gli utenti non devono aggiungere manualmente i costi.

Per utilizzare i costi automatici, selezionare **Costo sbarcato \> Configurazione dei costi \> Costi automatici**. Quindi impostare le regole dei costi automatici come descritto di seguito.

## <a name="work-with-cost-areas"></a>Utilizzare le aree di costo

I costi automatici funzionano come accordi commerciali o spese varie automatiche. Ogni record di costo automatico appartiene a uno specifico livello di costo. Usare il campo **Area di costo** nel riquadro elenco della pagina **Costi automatici** per selezionare l'area di costo che intendi utilizzare. Il riquadro elenco mostra solo i costi automatici che appartengono all'area di costo attualmente selezionata. Qualsiasi costo automatico che crei apparterrà all'area di costo attualmente selezionata.

Le aree di costo consentono al sistema di ripartire i costi tra le righe di ordine fornitore in un'area di costo. Ad esempio, un costo per un contenitore di spedizione ripartirà il valore tra tutti i prodotti in quel contenitore. Se sono presenti due o più contenitori di spedizione, è possibile specificare lo stesso tipo di costo per ciascun contenitore di spedizione. Pertanto, il tipo di contenitore può essere utilizzato per trovare il costo automatico corretto.

## <a name="buttons-on-the-action-pane"></a>Pulsanti nel riquadro Azioni

Nella seguente tabella sono descritti i pulsanti disponibili nel riquadro Azioni della pagina **Costi automatici**.

| Pulsante | Descrizione |
|---|---|
| Modifica | Modifica un costo automatico esistente. |
| Nuove | Crea un costo automatico. |
| Elimina | Elimina un costo automatico. |
| Copia da | Crea un nuovo record di costo automatico basato su un record esistente. È quindi possibile modificare liberamente il nuovo record. Questo pulsante consente di creare rapidamente nuovi costi automatici. |
| Visualizza dimensioni | Apre una finestra di dialogo in cui è possibile selezionare le dimensioni inventariali disponibili per le transazioni costi visualizzate. Se si deselezionano le caselle di controllo, verranno visualizzate meno dimensioni inventariali per le transazioni costi. Pertanto, verranno mostrati meno dettagli per la transazione. Se una dimensione inventariale viene specificata per un costo automatico, il costo automatico verrà applicato solo quando la dimensione inventariale specificata viene utilizzata per l'articolo in un viaggio. |

## <a name="settings-on-the-header"></a>Impostazioni nell'intestazione

La combinazione delle impostazioni nella sezione dell'intestazione determina quando e come un costo automatico specifico viene aggiunto a un viaggio. Un costo automatico verrà applicato a un viaggio, un contenitore di spedizione o una registrazione solo quando i dettagli del costo automatico corrispondono ai dettagli nell'intestazione di quell'area di costo. La somma di tutti i costi automatici corrispondenti determina il costo sbarcato stimato di un viaggio. Questo costo viene ripartito tra tutti gli articoli nell'imbarcazione o nel viaggio.

Nella seguente tabella vengono descritti tutti i campi disponibili nella sezione dell'intestazione. Tuttavia, i campi specifici disponibili variano a seconda dell'area di costo e delle dimensioni di visualizzazione attualmente selezionate.

| Campo | Descrizione |
|---|---|
| **Codice conto** | <p>Selezionare uno dei seguenti valori:</p><ul><li>**Tabella** - La regola dei costi si applica solo a un fornitore specifico.</li><li>**Gruppo** - La regola dei costi si applica solo a un gruppo di fornitori specifico. Il sistema cercherà il [gruppo del tipo di costo fornitore](costing-parameters-setup.md) associato al record fornitore.</li><li>**Tutti** - La regola dei costi viene applicata a tutti i fornitori. |
| **Società di spedizione** | Seleziona il fornitore o il gruppo di fornitori a cui si applica la regola dei costi. Questo campo è disponibile solo se si seleziona *Tabella* o *Gruppo* nel campo **Codice conto**. |
| **Broker doganale** | Seleziona il fornitore o il gruppo di fornitori a cui si applica la regola dei costi. Questo campo è disponibile solo se si seleziona *Tabella* o *Gruppo* nel campo **Codice conto**. |
| **Codice articolo** | <p>Selezionare uno dei seguenti valori:</p><ul><li>**Tabella** - La regola dei costi si applica solo a un articolo specifico.</li><li>**Gruppo** - La regola dei costi si applica solo a un gruppo di articoli specifico. Il sistema cercherà il [gruppo del tipo di costo articolo](costing-parameters-setup.md) associato al record articolo.</li><li>**Tutti** - La regola dei costi viene applicata a tutti gli articoli.|
| **Relazione articolo** | Seleziona l'articolo o il gruppo di articoli a cui si applica la regola dei costi. Questo campo è disponibile solo se si seleziona *Tabella* o *Gruppo* nel campo **Codice articolo**. |
| **Modalità di consegna** | Seleziona la modalità di consegna (ad esempio aerea o marittima) a cui si applica la regola dei costi. |
| **Tipo di contenitore** | Il tipo di contenitore di spedizione in cui verrà spedita la merce. Un costo automatico può essere applicato a un viaggio solo se il tipo di contenitore per l'impostazione dei costi automatici corrisponde al tipo di contenitore del viaggio. |
| **Porto di origine** e **Porto di destinazione** | Il porto di origine ("da") e quello di destinazione ("a") del viaggio. (alcuni contenitori di spedizione potrebbero avere porti di destinazione differenti, poiché il viaggio potrebbe comportare scali in più porti). Un costo automatico può essere applicato a un viaggio solo se i porti di origine e destinazione nell'impostazione dei costi automatici corrispondono ai porti di origine e destinazione del viaggio. |
| **Numero costo automatico** | L'identificatore univoco della regola dei costi automatici. Il valore di questo campo viene generato automaticamente in base alla sequenza numerica impostata nella pagina **Parametri del costo sbarcato**. |
| **Dimensioni inventariali** | Alcune aree di costo consentono di includere una o più dimensioni articolo nell'intestazione (come dimensioni, colore, magazzino e numero di batch). Selezionare **Visualizza dimensioni** nel riquadro Azioni per selezionare le dimensioni da includere. |

## <a name="settings-on-the-lines-fasttab"></a>Impostazioni nella Scheda dettaglio Righe

Nella Scheda dettaglio **Righe**, aggiungere una riga per ciascuna valuta che può essere utilizzata quando un costo viene applicato a una riga di ordine fornitore di un viaggio. 

Per gli articoli e gli ordini fornitore, il sistema abbinerà la valuta di ciascuna riga di ordine fornitore alle valute specificate nella Scheda dettaglio **Righe**. Applicherà solo il valore del costo impostato per la riga o l'elemento corrispondente. Se non è impostata alcuna riga per la valuta della riga o dell'articolo, il costo automatico non verrà applicato a tale riga o articolo.

Per altri tipi di aree di costo, tutte le righe nella Scheda dettaglio **Righe** verranno applicate a ogni riga di viaggio, contenitore di spedizione, registrazione o ordine di trasferimento che corrisponde ai valori stabiliti nell'intestazione.

Nella seguente tabella vengono descritti tutti i campi disponibili in ogni riga. Tuttavia, i campi specifici disponibili variano a seconda dell'area di costo attualmente selezionata.

| Campo | Descrizione |
|---|---|
| **Valuta** | Selezionare la valuta a cui si applica la riga. Questa valuta è correlata all'ordine fornitore. Quando il sistema cerca di trovare i costi automatici da applicare a un viaggio e alle relative righe di viaggio, selezionerà la riga che ha la stessa valuta dell'ordine fornitore. Questo campo è disponibile solo quando il campo **Area di costo** è impostato su *Ordine fornitore* o *Articolo*. |
| **Codice tipo di costo** | Il tipo di costo. |
| **Metodo di ripartizione** | <p>Il metodo utilizzato per distribuire i costi alle righe. Di seguito vengono illustrate le opzioni disponibili.</p><ul><li><p>**Percentuale** - Il valore del campo **Valore di costo** è una percentuale che si applica al valore totale delle merci.</p><p>Ad esempio, se il campo **Valore di costo** è impostato su *10* e il valore totale delle merci è $800, il valore del costo è $80 (= $800 × 10 percento).</p></li><li>**Quantità** - Il costo verrà ripartito in base alla quantità delle merci.</li><li>**Importo** - Il costo verrà ripartito in base al valore delle merci.</li><li>**Volume** - Il costo verrà ripartito in base al volume delle merci. Il volume è specificato nel record generale dell'articolo.</li><li>**Peso** - Il costo verrà ripartito in base al peso delle merci. Il peso è specificato nel record generale dell'articolo.</li><li>**Volumetrico** - Il costo verrà ripartito in base alla misura volumetrica della merce.</li><li><p>**Misura** - Questa opzione consente di specificare una misura nel modulo **Costo sbarcato**. È spesso utilizzata dalle organizzazioni che non conoscono il volume o il peso individuale delle merci, ma che richiedono una ripartizione più accurata rispetto a quella mediante le opzioni **Importo** e **Quantità**. Lo spedizioniere o l'agente fornirà all'organizzazione il peso o la misura cubica, a livello di articolo o di ordine fornitore.</p><p>Ad esempio, il trasporto marittimo è pari a $900. L'articolo A ha un peso di 800 chilogrammi (kg) e un volume di 2 metri cubi (m³). L'articolo B ha un peso di 100 kg e un volume di 1 m³. Di seguito sono riportati i risultati della ripartizione in base al peso:</p><ul><li>Articolo A = $800</li><li>Articolo B = $100</li></ul><p>Di seguito sono riportati i risultati della ripartizione in base al volume:</p><ul><li>Articolo A = $600</li><li>Articolo B = $300</li></ul><p>**Nota:** quando il campo **Metodo di ripartizione** è impostato su *Misura*, il sistema utilizza le misure immesse sia per l'area di costo (il contenitore di spedizione) che per le righe. Queste misure non devono necessariamente sommarsi al totale previsto. Tuttavia, se ne si richiede l'aggiunta al totale previsto, è possibile eseguire un controllo utilizzando le statistiche per esaminare la misura totale. L'impostazione del prompt di misura e l'aggiornamento automatico della misura a livello di spedizione o contenitore vengono impostati nell'intestazione del viaggio.</p></li></ul> |
| **Data iniziale** | Specificare l'inizio dell'intervallo di date per la determinazione dei costi, se esiste un intervallo di date. Questa è la prima data in cui verrà applicato il costo automatico. |
| **Data finale** | Specificare la fine dell'intervallo di date per la determinazione dei costi, se esiste un intervallo di date. Questa è l'ultima data in cui verrà applicato il costo automatico. |
| **Categoria** | <p>Selezionare il metodo che deve essere utilizzato per calcolare il costo. Di seguito vengono illustrate le opzioni disponibili.</p><ul><li>**Fisso** - Il costo verrà ripartito in base al metodo di ripartizione.</li><li>**Pezzi** - Il costo verrà allocato per pezzo. Pertanto, il metodo di ripartizione non verrà utilizzato.</li><li>**Percentuale** - Verrà aggiunta una percentuale del valore delle merci. Pertanto, il metodo di ripartizione non verrà utilizzato.</li><li>**Aliquota** - Selezionare questa opzione se sono presenti scomposizioni in base alla quantità. Il campo **Metodo di ripartizione** per la riga deve essere impostato su *Misura*.</li><ul> |
| **Suddiviso per quantità** | <p>Selezionare questa casella di controllo per rendere disponibile il pulsante **Suddivisioni per quantità** nella Scheda dettaglio **Righe**. Le suddivisioni per quantità consentono di suddividere il costo e di variare i diversi costi, a seconda della quantità nella riga di ordine fornitore del viaggio. Questa funzionalità viene spesso utilizzata quando la modalità di consegna è per via aerea. Il campo **Categoria** per la riga deve essere impostato su *Aliquota*.</p><p>La quantità è relativa all'opzione selezionata nel campo **Metodo di ripartizione**. Il valore del costo sarà fino alla quantità immessa nel campo **Valore di costo**.<p>Ad esempio, quantità di 45-100 kg producono una spesa di $6,00 per misura (come kg/m³). Quantità superiori a 100 kg generano una spesa di $5,50 per misura (come kg/m³).</p> |
| **Valore di costo** | Immettere il valore del costo. |
| **Codice valuta costi** | Selezionare la valuta del costo. |
| **Fascia IVA articoli** | Selezionare il codice imposta per il costo. |
| **Costo minimo** | <p>Questo campo si applica solo se la casella di controllo **Suddiviso per quantità** è selezionata. Se la misura non raggiunge questo valore, viene selezionato il valore minimo, indipendentemente dai costi specificati nella pagina **Suddivisioni per quantità**.<p>Ad esempio, quantità di 0-45 kg generano una spesa di $6 per misura (come kg/m³). Quantità di 46-100 kg generano una spesa di $5,50 per misura (come kg/m³). Se vengono spediti 2 kg, la suddivisione per quantità creerà un valore del costo di $12. Tuttavia, se il campo **Costo minimo** è impostato su *$100*, il costo finale sarà $100.</p> |
| **Aggregazione** | Selezionare questa casella di controllo per consentire agli utenti di spostare questo costo dal livello di contenitore di spedizione al livello di viaggio. In questo caso, i costi possono essere calcolati automaticamente a livello di contenitore di spedizione. Tuttavia, possono anche essere combinati e ripartiti tra tutti gli articoli in tutti i contenitori di un viaggio, anziché tra tutti gli articoli nei singoli contenitori di spedizione. |
| **Tipo di costo collegato** | <p>Collegare la riga corrente a un'altra riga nello stesso record di costo automatico specificando il valore **Codice tipo di costo** della riga alla quale collegarsi. Questa funzionalità è disponibile solo quando il campo **Categoria** per la riga corrente è impostato su *Percentuale*. Quando la riga corrente è collegata a un'altra riga, il costo della riga corrente sarà basato sul costo dell'altra riga.</p><p>Ad esempio, il trasporto è $1.000 e si desidera che il supplemento carburante corrisponda al 10% delle spese di trasporto. In questo caso, la riga deve avere il valore **Categoria** impostato su *Percentuale*, il valore **Valore di costo** impostato su *10%* e il valore **Tipo di costo collegato** impostato su *Spese di trasporto*.</p> |
| **Rettifica valore** e **Importo rettifica** | <p>Utilizzare questi campi per rettificare il valore e l'importo di vari valori percentuali. Questi sono disponibili solo quando il campo **Area di costo** è impostato su *Articolo*.</p><p>È possibile impostare costi differenti per diversi componenti di un articolo. Un componente di un articolo potrebbe avere una percentuale di costo diversa rispetto agli altri componenti di quell'articolo. Questo approccio è talvolta richiesto per valutare una parte specifica della merce con aliquote diverse.</p><p>Ad esempio, il dazio di un orologio è calcolato con due aliquote: un componente dell'orologio ha un'aliquota del 10% e un secondo componente ha un'aliquota del 2%. In questo caso, il costo verrà suddiviso tra i due componenti.</p><p>Il costo viene calcolato per l'articolo, ma il valore del costo viene rettificato dal valore dei componenti che hanno una categoria di costo differente. Il costo dei componenti rimanenti può quindi essere calcolato utilizzando l'importo rettificato con il calcolo precedente.</p><p>Ad esempio, il componente A dell'orologio ha un costo di $9,50 e un dazio del 10 percento e il componente B ha un costo di $0,50 e un dazio del 2 percento. Di conseguenza, il costo totale è $10,00. La prima voce è per la riga del 10 percento. Utilizza i valori seguenti:</p><ul><li>**Categoria:** *Percentuale*</li><li>**Valore di costo:** *10*</li><li>**Rettifica valore:** *Rettifica entro*</li><li>**Valore rettificato:** *-0,50*</li></ul><p>Questa configurazione specifica che il costo dell'articolo ($10) deve essere ridotto di $0,50 (il prezzo del componente B) prima che venga calcolato un dazio del 10%. Pertanto, il 10 percento verrà applicato a $9,50.</p><p>La seconda voce è per la riga del 2 percento (lo $0,50 di cui è stata modificata la voce precedente). Utilizza i valori seguenti:</p><ul><li>**Categoria:** *Percentuale*</li><li>**Valore di costo:** *2*</li><li>**Rettifica valore:** *Usa*</li><li>**Rettifica:** *0,50*</li></ul><p>Questa configurazione calcola il dazio rimanente pagabile per il componente B.</p> |
