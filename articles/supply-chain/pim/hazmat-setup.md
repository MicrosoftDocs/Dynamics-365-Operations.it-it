---
title: Impostare i materiali pericolosi
description: Questo argomento spiega come impostare i dati necessari per classificare gli articoli come materiali pericolosi. Quando crei un ordine di vendita che include un articolo classificato come materiale pericoloso, il sistema genera la documentazione relativa ai materiali pericolosi per l'ordine di vendita quando viene spedito.
author: dasani-madipalli
manager: tfehr
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: aaf66b98717c72b4260e0a482400bdb29bbd9ecb
ms.sourcegitcommit: c009ec75f53872272f11c92a1ce81a391e3845a2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/18/2020
ms.locfileid: "3699631"
---
# <a name="set-up-hazardous-materials"></a>Impostare i materiali pericolosi

[!include [banner](../includes/banner.md)]

Per utilizzare la funzionalità relativa ai materiali pericolosi, è necessario prima impostare i dati necessari per classificare gli articoli come materiali pericolosi. Pertanto quando crei un ordine di vendita che include un articolo classificato come materiale pericoloso, il sistema genera la documentazione relativa ai materiali pericolosi per l'ordine di vendita quando viene spedito.

## <a name="turn-on-the-hazardous-materials-feature-for-your-system"></a>Attivare la funzione relativa ai materiali pericolosi per il sistema

Prima di poter utilizzare questa funzione, è necessario attivarla nel sistema. Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e abilitarla. Nell'area di lavoro **Gestione funzionalità**, la funzione è elencata nel modo seguente:

- **Modulo:** *Gestione informazioni sul prodotto*
- **Nome funzionalità:** *Informazioni sul prodotto con materiali pericolosi e documentazione di spedizione*

## <a name="hazardous-material-regulations"></a>Normativa sui materiali pericolosi

Per utilizzare i processi relativi ai materiali pericolosi, è necessario prima creare una normativa. Le normative definiscono come viene creato il testo di spedizione stampato per un articolo. Definiscono anche le modalità di consegna associate.

Ecco alcune normative comuni:

- **ADR** - Normative relative al trasporto internazionale di merci pericolose via terra
- **CFR 49** - Normative negli Stati Uniti per il trasporto di merci pericolose
- **IMDG** – Il codice International Marine Dangerous Goods (IMDG)
- **IATA** - Le normative sulle merci pericolose della International Air Transport Association (IATA)

Queste normative aiutano a determinare quali informazioni devono essere mostrate quando si stampa il testo di spedizione per un articolo. È possibile definire tutte le normative a cui è necessario conformarsi.

> [!IMPORTANT]
> La funzionalità per l'impostazione dei codici di informazione relativi a materiali pericolosi non rende la società conforme alle normative. È solo uno strumento che aiuta a costruire processi per la società.

In genere, è disponibile una normativa per una modalità di trasporto specifica, come il trasporto marittimo, via terra o aereo. È quindi possibile associare a ogni normativa una modalità di consegna. La modalità di consegna verrà utilizzata quando vengono stampati documenti specifici in Gestione magazzino. In Gestione magazzino, ogni spedizione è collegata a un vettore di spedizione e a un servizio di trasporto impostati nel modulo **Trasporto**. La modalità di consegna è associata al vettore di spedizione e al servizio di trasporto. Quando si esegue un report, la modalità di consegna viene utilizzata per trovare il testo di stampa della spedizione associato a un articolo rilasciato.

Questi dati di configurazione non sono specifici per ciascuna persona giuridica (società). Pertanto, è possibile disporre di una serie comune di informazioni sui materiali pericolosi condivise tra tutte le persone giuridiche.

Per ogni normativa, è possibile definire un elenco di materiali e utilizzarlo come elenco modello associato agli articoli rilasciati. Per ogni normativa è inoltre possibile definire un'impostazione di stampa. Un'impostazione di stampa consente di definire la modalità di costruzione del testo di spedizione per un articolo. L'impostazione di stampa viene utilizzata per costruire il testo di stampa di spedizione per un articolo rilasciato.

Per impostare le normative sui materiali pericolosi, andare a **Gestione informazioni sul prodotto \> Impostazione \> Documentazione per la spedizione di materiali pericolosi \> Normativa sui materiali pericolosi**. Nella pagina **Normativa sui materiali pericolosi** è possibile creare un numero qualsiasi di normative e configurarle utilizzando i campi descritti nelle sottosezioni seguenti.

### <a name="hazardous-material-regulation-header"></a>Intestazione normativa sui materiali pericolosi

Ogni normativa ha un codice e una descrizione. Nella seguente tabella vengono illustrati i campi disponibili nell'intestazione.

| Campo | descrizione |
|---|---|
| Codice normativa | Immettere un codice per identificare il record di normativa sui materiali pericolosi. |
| descrizione | Immettere una descrizione della normativa sui materiali pericolosi. |

### <a name="print-setup-fasttab"></a>Scheda dettaglio Impostazioni di stampa

Ogni normativa può avere un numero qualsiasi di impostazioni di stampa. Le impostazioni di stampa vengono definite nella scheda dettaglio **Impostazioni di stampa**. Nella seguente tabella vengono illustrati i campi disponibili per ogni impostazione di stampa.

| Campo | descrizione |
|---|---|
| Sequenza | Definire l'ordine in cui si fa riferimento ai campi nel testo di spedizione. |
| Stampa campo | Selezionare il campo da includere nel testo di spedizione. Non tutti i campi per il materiale pericoloso saranno disponibili per la stampa. Saranno disponibili solo i campi comuni che vengono utilizzati per definire il testo di spedizione nelle varie normative. È necessario definire il primo campo di stampa come un separatore di campo con il valore *0* (zero) per **Sequenza**, in modo che possa essere utilizzato come separatore per altri campi. È richiesto un solo riferimento al separatore di campo.<p>Sono disponibili i valori seguenti:</p><ul></li><li>**Separatore di campo** - Questo campo di stampa viene utilizzato come separatore di campo per il testo. È richiesto un solo separatore di campo nella sequenza. Di solito il valore **Sequenza** per questo campo di stampa viene impostato su *0* (zero). Il sistema cercherà un separatore di campo e utilizzerà il primo che trova nell'elenco. Il valore di testo utilizzato nella stringa proviene dal campo **Stampa dopo**.</li><li>**Identificazione** - Questo campo di stampa inserisce il [codice identificativo e/o la descrizione](#identification) nel testo stampato.</li><li>**Classe** - Questo campo di stampa inserisce il [codice classe e/o la descrizione](#classes) nel testo stampato.</li><li>**Divisione** - Questo campo di stampa inserisce il [codice divisione e/o la descrizione](#divisions) nel testo stampato.</li><li>**Gruppo di imballaggio** - Questo campo di stampa inserisce il [codice gruppo di imballaggio e/o la descrizione](#packing-group) nel testo stampato.</li><li>**Codice tunnel e/o descrizione** - Questo campo di stampa inserisce il [codice tunnel e/o la descrizione](#tunnel) nel testo stampato.</li><li>**Nome spedizione corretto** - Questo campo di stampa inserisce il [nome spedizione corretto](hazmat-items.md#hazmat-description) nel testo stampato.</li><li>**Nome tecnico** - Questo campo di stampa inserisce il [nome tecnico e/o la descrizione](#technical-name) nel testo stampato.</li><li>**Categoria trasporto** - Questo campo di stampa inserisce il [codice categoria trasporto e/o la descrizione](#transport-category) nel testo stampato.</li><li>**Stivaggio** - Questo campo di stampa inserisce il [codice stivaggio e/o la descrizione](#stowage) nel testo stampato.</li><li>**Testo fisso** - Questo campo di stampa inserisce il testo definito nel campo **Testo fisso** per questa riga.</li><li>**Codice etichetta e/o descrizione** - Questo campo di stampa inserisce il [codice etichetta e/o la descrizione](#label) nel testo stampato.</li><li>**Imballaggio aereo** - Questo campo di stampa inserisce il [codice istruzioni di imballaggio aereo e/o la descrizione](#packing-instruction) nel testo stampato.</li><li>**Quantità limitata** - Questo campo di stampa controlla se l'articolo è contrassegnato come [articolo in quantità limitata](hazmat-items.md#material-management) e, se lo è, inserisce il testo definito nel campo **Testo fisso** per questa riga.</li><li>**Descrizione imballaggio** - Questo campo di stampa inserisce la [descrizione imballaggio](#packing-description) nel testo stampato.</li></ul> |
| Stampa prima | Immettere il testo che deve essere stampato prima del contenuto definito dall'impostazione **Stampa campo**. |
| Stampa dopo | Immettere il testo che deve essere stampato dopo il contenuto definito dall'impostazione **Stampa campo**. |
| Stampa con precedente | Selezionare questa casella di controllo per impedire che il separatore di campo venga stampato tra il campo precedente e questo campo. Utilizzare questa casella di controllo per i campi di stampa che sono opzionali o inclusi con un altro campo di stampa. |
| Testo fisso | Se si imposta il campo **Stampa campo** su **Testo fisso** o **Quantità limitata**, inserire il testo da stampare. |
| Includi in stampa | Selezionare quale valore o valori dal campo di stampa selezionato devono essere stampati per questa riga. È possibile stampare il codice, la descrizione o sia il codice che la descrizione. |

### <a name="mode-of-delivery-fasttab"></a>Scheda dettaglio Modalità di consegna

La normativa è una tabella condivisa e non è specifica per ciascuna persona giuridica. Tuttavia, le modalità di consegna dipendono dalla persona giuridica. Pertanto, quando si imposta una modalità di consegna, è necessario selezionare la relazione tra la normativa, la persona giuridica e la modalità di consegna.

Nella seguente tabella vengono illustrati i campi disponibili nella Scheda dettaglio **Modalità di consegna**.

| Campo | descrizione |
|---|---|
| Società | Selezionare una persona giuridica da associare a questa normativa. |
| Modalità di consegna | In base alla persona giuridica selezionata, selezionare la modalità di consegna da associare alla normativa. |

### <a name="country-fasttab"></a>Scheda dettaglio Paese

A scopo di riferimento, è possibile elencare i paesi o le aree geografiche per i quali la normativa è rilevante. Tuttavia, quando vengono eseguiti i report di spedizione, viene utilizzata solo la modalità di consegna per determinare la normativa. Quando si esamina una spedizione magazzino, non c'è un collegamento diretto alla modalità di consegna. La consegna può essere associata a un vettore di spedizione e a un servizio di trasporto. Quando si definisce un servizio di trasporto, è necessario associarlo a una modalità di consegna. Questa relazione verrà utilizzata nei report di spedizione come la polizza di carico per trovare il testo di stampa della spedizione per un articolo.

Nella seguente tabella viene illustrato il campo disponibile nella Scheda dettaglio **Paese**.

| Campo | descrizione |
|---|---|
| Paese | Selezionare un paese/area geografica da associare alla normativa. |

## <a name="material-codes"></a><a name="hazmat-codes"></a>Codici materiale

I codici materiale stabiliscono le impostazioni relative a uno specifico componente pericoloso che potrebbe essere incluso in un prodotto rilasciato. Ogni codice materiale appartiene a una specifica normativa sui materiali pericolosi e la sua definizione deve essere conforme a tale normativa. Quando si applica un codice materiale a un prodotto rilasciato utilizzando il campo **Codice materiale**, tutte le impostazioni relative ai materiali pericolosi del codice materiale vengono applicate automaticamente a quel prodotto. Pertanto, il processo di impostazione dei prodotti rilasciati è più veloce e meno soggetto a errori.

Per gestire le definizioni dei materiali pericolosi, seguire questi passaggi.

1. Andare a **Gestione informazioni sul prodotto \> Impostazione \> Documentazione per la spedizione di materiali pericolosi \> Normativa sui materiali pericolosi**.
2. Selezionare la normativa per cui impostare una definizione di materiale pericoloso.
3. Nel riquadro azioni, nella scheda **Imposta**, selezionare **Materiali pericolosi**.
4. Nel campo **Codice materiale** immettere un codice materiale per la definizione di materiale pericoloso. Si seleziona questo valore quando si applica il codice materiale a un prodotto rilasciato.

    Il campo **Codice normativa** è di sola lettura e mostra la normativa selezionata al passaggio 2.

5. Utilizzare i campi rimanenti in questa pagina per creare e impostare ogni materiale pericoloso che si applica alla normativa selezionata. I campi disponibili sono un sottoinsieme dei campi dei materiali pericolosi disponibili per i singoli prodotti rilasciati. Per ulteriori informazioni, vedere [Materiali pericolosi in prodotti, ordini, spedizioni e carichi](hazmat-items.md).

## <a name="hazardous-material-classification-groups"></a><a name="classification-groups"></a>Gruppi di classificazione dei materiali pericolosi

Ciascun gruppo di classificazione dei materiali pericolosi definisce un gruppo di valori di campo che stabiliscono un modello. È possibile utilizzare questo modello in un secondo momento, quando si impostano le informazioni sui materiali pericolosi per un articolo rilasciato.

Quando si assegna il codice per un gruppo di classificazione dei materiali pericolosi a un articolo rilasciato, le informazioni associate a tale gruppo di classificazione verranno copiate nei campi appropriati dell'articolo. Pertanto, è possibile semplificare i processi di impostazione stabilendo una serie di valori di campo correlati che si utilizzano spesso insieme.

Questi dati di configurazione non sono specifici per ciascuna persona giuridica. Pertanto, è possibile disporre di una serie comune di informazioni sui materiali pericolosi condivise tra tutte le persone giuridiche.

Per impostare le normative sui gruppi di classificazione dei materiali pericolosi, andare a **Gestione informazioni sul prodotto \> Impostazione \> Documentazione per la spedizione di materiali pericolosi \> Gruppo di classificazione dei materiali pericolosi**. Nella pagina **Gruppo di classificazione dei materiali pericolosi** è possibile creare un numero qualsiasi di gruppi e configurarli utilizzando i campi descritti nella tabella seguente.

| Campo | descrizione |
|---|---|
| Codice gruppo | Immettere un codice per identificare il gruppo. |
| descrizione | Immettere una descrizione del gruppo. |
| Codice classe | Associare un [codice classe](#classes) di materiale pericoloso al gruppo. |
| Codice divisione | Associare un [codice divisione](#divisions) di materiale pericoloso al gruppo. |
| Codice gruppo di imballaggio | Associare un [codice gruppo di imballaggio](#packing-group) al gruppo. |
| Codice categoria trasporto | Associare un [codice categoria trasporto](#transport-category) al gruppo. |
| Moltiplicatore | Immettere il moltiplicatore di materiali pericolosi che si applica alla classe e alla divisione selezionate dei materiali pericolosi, in base alla normativa applicabile. Questo moltiplicatore viene utilizzato come parte della formula che calcola il totale dei *punti materiale pericoloso* inclusi in un carico o in una spedizione. Per ulteriori informazioni sui punti materiale pericoloso e sul moltiplicatore, vedere [Scheda dettaglio Gestione materiali](hazmat-items.md#material-management). |

## <a name="hazardous-material-classes"></a><a name="classes"></a>Classi di materiale pericoloso

Una classe di materiale pericoloso viene in genere associata all'elenco di classi fornito nella normativa a cui ci si conforma. Ad esempio, la normativa statunitense CFR 49 elenca la "classe 3" come liquidi infiammabili e combustibili. È possibile impostare le classi rilevanti per i materiali che è necessario classificare.

Ogni classe verrà assegnata a una configurazione materiale nell'elenco dei materiali correlato al regolamento. Si assegna una classe a ciascun articolo rilasciato come necessario, per descrivere la natura pericolosa di un prodotto.

Questi dati di configurazione non sono specifici per ciascuna persona giuridica. Pertanto, è possibile disporre di una serie comune di informazioni sui materiali pericolosi condivise tra tutte le persone giuridiche.

Le classi di materiale pericoloso vengono utilizzate insieme a divisioni, gruppi e gruppi di compatibilità nel modo seguente:

- Quando si assegna una classe di materiale pericoloso a un articolo rilasciato, è necessario assegnare anche una [divisione di materiale pericoloso](#divisions).
- È possibile utilizzare le classi di materiale pericoloso insieme ai [gruppi di classificazione dei materiali pericolosi](#classification-groups) per stabilire un modello di codici per l'impostazione degli articoli.
- È possibile usare i [gruppi di compatibilità di materiali pericolosi](#compatibility-groups) per stabilire quali classi e divisioni di materiale pericoloso possono essere spedite insieme.

Per impostare le classi di materiale pericoloso, andare a **Gestione informazioni sul prodotto \> Impostazione \> Documentazione per la spedizione di materiali pericolosi \> Classe di materiale pericoloso**. Nella pagina **Classe di materiale pericoloso** è possibile creare un numero qualsiasi di classi e configurarle utilizzando i campi descritti nella tabella seguente.

| Campo | descrizione |
|---|---|
| Codice classe | Immettere un codice per identificare la classe. Si definisce questo codice per l'articolo. Verrà quindi utilizzato negli elenchi di ricerca quando si assegna una classe di materiale pericoloso a un articolo rilasciato. |
| descrizione | Immettere una descrizione della classe. |

## <a name="hazardous-material-divisions"></a><a name="divisions"></a>Divisioni di materiale pericoloso

Una divisione di materiale pericoloso è un sottoinsieme di una classe di materiale pericoloso. È necessario assegnare sia una divisione che una classe a ogni prodotto che include materiali pericolosi.

Per le classi che non hanno divisioni, creare una divisione con il codice *0*. Ad esempio, nella normativa IATA, i materiali radioattivi di classe 7 non hanno suddivisioni. In questo caso, si crea una divisione *0* da associare a un prodotto rilasciato quando si assegna la classe.

Questi dati di configurazione non sono specifici per ciascuna persona giuridica. Pertanto, è possibile disporre di una serie comune di informazioni sui materiali pericolosi condivise tra tutte le persone giuridiche.

Le divisioni di materiale pericoloso vengono utilizzate insieme a classi, gruppi e gruppi di compatibilità nei modi seguenti:

- Quando si assegna una divisione di materiale pericoloso a un articolo rilasciato, è necessario assegnare anche una [classe di materiale pericoloso](#classes).
- È possibile utilizzare le divisioni di materiale pericoloso insieme ai [gruppi di classificazione dei materiali pericolosi](#classification-groups) per stabilire un modello di codici per l'impostazione degli articoli.
- È possibile usare i [gruppi di compatibilità di materiali pericolosi](#compatibility-groups) per stabilire quali classi e divisioni di materiale pericoloso possono essere spedite insieme.

Per impostare le divisioni di materiale pericoloso, andare a **Gestione informazioni sul prodotto \> Impostazione \> Documentazione per la spedizione di materiali pericolosi \> Divisione di materiale pericoloso**. Nella pagina **Divisione di materiale pericoloso** è possibile creare un numero qualsiasi di divisioni e configurarle utilizzando i campi descritti nella tabella seguente.

| Campo | descrizione |
|---|---|
| Divisione | Immettere un codice da utilizzare come numero di riferimento per la divisione. |
| descrizione | Immettere una descrizione della divisione. |
| Classe | Cercare e assegnare la classe a cui appartiene la divisione. |

## <a name="hazardous-material-compatibility-groups"></a><a name="compatibility-groups"></a>Gruppi di compatibilità di materiali pericolosi

I gruppi di compatibilità di materiali pericolosi stabiliscono quali classi e divisioni di materiale pericoloso possono essere spedite insieme. Quando gli operatori creano carichi o spedizioni di magazzino, possono eseguire un controllo di compatibilità che emette un avviso se il carico o la spedizione include articoli che non appartengono tutti allo stesso gruppo di compatibilità.

Questi dati di configurazione non sono specifici per ciascuna persona giuridica. Pertanto, è possibile disporre di una serie comune di informazioni sui materiali pericolosi condivise tra tutte le persone giuridiche.

Per impostare le normative sui gruppi di compatibilità di materiali pericolosi, andare a **Gestione informazioni sul prodotto \> Impostazione \> Documentazione per la spedizione di materiali pericolosi \> Gruppo di compatibilità di materiali pericolosi**. Nella pagina **Gruppo di compatibilità di materiali pericolosi** è possibile creare un numero qualsiasi di gruppi di compatibilità e configurarli utilizzando i campi descritti nelle sottosezioni seguenti.

### <a name="hazardous-material-compatibility-group-header"></a>Intestazione gruppo di compatibilità di materiali pericolosi

Ogni gruppo di compatibilità ha un codice e una descrizione. Nella seguente tabella vengono illustrati i campi disponibili nell'intestazione.

| Campo | descrizione |
|---|---|
| Gruppo di compatibilità | Immettere un codice per identificare il gruppo di compatibilità |
| descrizione | Immettere una descrizione del gruppo di compatibilità. |

### <a name="compatibility-group-details"></a>Dettagli gruppo di compatibilità

Ogni gruppo di compatibilità stabilisce un elenco di classi e divisioni di materiali pericolosi che possono essere spedite insieme.

| Campo | descrizione |
|---|---|
| Classe | Selezionare una classe di materiale pericoloso compatibile con tutte le altre classi del gruppo. |
| Divisione | Selezionare una divisione di materiale pericoloso che appartiene alla classe selezionata. |

## <a name="hazardous-material-specification-values"></a>Valori delle specifiche di materiale pericoloso

Microsoft Dynamics 365 Supply Chain Management fornisce diversi tipi di specifiche di materiale pericoloso. Per ogni tipo, è necessario stabilire un set centralizzato di valori per ogni campo rilevante. Gli utenti possono quindi selezionare tra questi valori quando configurano le definizioni di materiale pericoloso o i prodotti rilasciati. Supply Chain Management fornisce una raccolta di pagine in cui è possibile stabilire i valori. Ogni pagina è dedicata a un tipo di specifica. Per la descrizione di ogni specifica disponibile e per le informazioni su come stabilirne i valori, vedere le sottosezioni seguenti.

Un esempio di specifica di materiale pericoloso è il _codice di stivaggio_, che specifica come un determinato materiale può essere immagazzinato durante il trasporto. Utilizzando le informazioni in questa sezione, si stabilisce una raccolta centrale di codici di stivaggio. Questa raccolta viene quindi presentata agli utenti in un elenco a discesa quando impostano il codice di stivaggio per un prodotto rilasciato.

Questi valori delle specifiche di materiale pericoloso non sono specifici della persona giuridica, pertanto è possibile avere una serie di valori comuni condivisi tra tutte le persone giuridiche.

I [codici materiale](#hazmat-codes) vengono utilizzati per stabilire raccolte comuni di impostazioni per ciascuna specifica in conformità a una determinata normativa. È quindi possibile applicare il codice appropriato a ciascun prodotto rilasciato come necessario. Per informazioni su come applicare un codice di materiale pericoloso a uno specifico prodotto rilasciato e su come configurare le singole impostazioni di quel prodotto per qualsiasi specifica qui descritta, vedere [Materiali pericolosi in prodotti, ordini, spedizioni e carichi](hazmat-items.md).

### <a name="hazardous-material-emergency-response"></a>Risposta di emergenza materiale pericoloso

La specifica *Risposta di emergenza materiale pericoloso* indica cosa fare in caso di problemi durante il trasporto di un prodotto che contiene un determinato materiale pericoloso.

Per impostare i valori per la specifica, andare a **Gestione informazioni sul prodotto \> Impostazione \> Documentazione per la spedizione di materiali pericolosi \> Risposta di emergenza materiale pericoloso**. Nella pagina **Risposta di emergenza materiale pericoloso** è possibile creare un numero qualsiasi di valori e configurarli con un codice di classificazione e una breve descrizione.

### <a name="hazardous-material-identification"></a><a name="identification"></a>Identificazione materiale pericoloso

La specifica *Identificazione materiale pericoloso* identifica la classe o la natura di un materiale pericoloso. Il valore in genere è un codice che si basa su uno standard delle Nazioni Unite (ONU). Ogni classe è identificata da un codice e una descrizione e può impostare limiti sui metodi di trasporto. Ad esempio, per identificare un articolo o un materiale infiammabile, creare una classe di materiale pericoloso che utilizza il codice *FL* e la descrizione *Infiammabile*. Si specifica inoltre che la classe non deve essere trasportata in aereo.

Per impostare i valori per la specifica, andare a **Gestione informazioni sul prodotto \> Impostazione \> Documentazione per la spedizione di materiali pericolosi \> Identificazione materiale pericoloso**. Nella pagina **Identificazione materiale pericoloso** è possibile creare un numero qualsiasi di valori e configurarli utilizzando i campi descritti nella tabella seguente.

| Campo | descrizione |
|---|---|
| Identificazione | Immettere un codice da utilizzare come numero di riferimento che identifica questa classe di materiale pericoloso. |
| descrizione | Immettere una descrizione per questa classe. |
| Limita dal trasporto aereo | Selezionare questa casella di controllo per indicare che questa classe di materiale pericoloso non deve essere trasportata per via aerea. |
| Limita dal trasporto marittimo | Selezionare questa casella di controllo per indicare che questa classe di materiale pericoloso non deve essere trasportata via mare. |

### <a name="hazardous-material-label"></a><a name="label"></a>Etichetta materiale pericoloso

La specifica *Etichetta materiale pericoloso* identifica l'etichetta delle merci pericolose che deve essere applicata ai prodotti rilasciati pertinenti. Le etichette stesse descrivono come il prodotto deve essere maneggiato. Ad esempio, supponiamo il caso di un prodotto che contiene un gas velenoso. In questo caso, si imposta un codice di etichetta che rappresenta l'etichetta del gas velenoso. Il processo aziendale deve essere creato in modo che questo valore venga cercato quando si spediscono i prodotti.

Per impostare i valori per la specifica, andare a **Gestione informazioni sul prodotto \> Impostazione \> Documentazione per la spedizione di materiali pericolosi \> Etichetta materiale pericoloso**. Nella pagina **Etichetta materiale pericoloso** è possibile creare un numero qualsiasi di etichette e configurarli con un codice di identificazione e una breve descrizione.

### <a name="hazardous-material-packing-descriptions"></a><a name="packing-description"></a>Descrizioni imballaggio materiale pericoloso

La specifica *Descrizioni imballaggio materiale pericoloso* indica come un articolo pericoloso deve essere imballato. Ad esempio, potrebbe dover essere imballato in un tipo specifico di fusto di acciaio o in un altro tipo di imballaggio speciale.

Per impostare i valori per la specifica, andare a **Gestione informazioni sul prodotto \> Impostazione \> Documentazione per la spedizione di materiali pericolosi \> Descrizioni imballaggio materiale pericoloso**. Nella pagina **Descrizioni imballaggio materiale pericoloso** è possibile creare un numero qualsiasi di descrizioni imballaggio e configurarle con un codice di identificazione e una breve descrizione.

### <a name="hazardous-material-packing-group"></a><a name="packing-group"></a>Gruppo di imballaggio materiali pericolosi

La specifica *Gruppo di imballaggio materiali pericolosi* identifica il gruppo di imballaggio per un articolo pericoloso. Il gruppo di imballaggio consente di definire un codice e una descrizione per indicare come devono essere imballati gli articoli con materiale pericoloso durante il trasporto o la spedizione. Il gruppo di imballaggio viene assegnato all'articolo tramite la pagina **Materiali pericolosi articolo**.

Per impostare i valori per la specifica, andare a **Gestione informazioni sul prodotto \> Impostazione \> Documentazione per la spedizione di materiali pericolosi \> Gruppo di imballaggio materiali pericolosi**. Nella pagina **Gruppo di imballaggio materiali pericolosi** è possibile creare un numero qualsiasi di gruppi di imballaggio e configurarli con un codice di identificazione e una breve descrizione.

### <a name="hazardous-material-packing-instruction"></a><a name="packing-instruction"></a>Istruzione di imballaggio materiale pericoloso

La specifica *Istruzione di imballaggio materiale pericoloso* identifica le istruzioni di imballaggio che devono essere seguite quando un determinato articolo pericoloso viene preparato per il trasporto aereo.

Per impostare i valori per la specifica, andare a **Gestione informazioni sul prodotto \> Impostazione \> Documentazione per la spedizione di materiali pericolosi \> Istruzione di imballaggio materiale pericoloso**. Nella pagina **Istruzione di imballaggio materiale pericoloso** è possibile creare un numero qualsiasi di identificatori di istruzione di imballaggio e configurarli con un codice di identificazione e una breve descrizione.

### <a name="hazardous-material-stowage"></a><a name="stowage"></a>Stivaggio materiali pericolosi

La specifica *Stivaggio materiali pericolosi* indica come un prodotto deve essere stivato su una nave quando viene trasportato via mare.

Per impostare i valori per la specifica, andare a **Gestione informazioni sul prodotto \> Impostazione \> Documentazione per la spedizione di materiali pericolosi \> Stivaggio materiali pericolosi**. Nella pagina **Stivaggio materiali pericolosi** è possibile creare un numero qualsiasi di identificatori di stivaggio e configurarli con un codice di identificazione e una breve descrizione.

### <a name="hazardous-material-transport-category"></a><a name="transport-category"></a>Categoria trasporto materiali pericolosi

La specifica *Categoria trasporto materiali pericolosi* viene generalmente utilizzata per raggruppare prodotti pericolosi simili nei report. Ad esempio, le categorie di trasporto vengono utilizzate nel report **Riepilogo spedizione** che è possibile stampare dal record di spedizione magazzino.

Per impostare i valori per la specifica, andare a **Gestione informazioni sul prodotto \> Impostazione \> Documentazione per la spedizione di materiali pericolosi \> Categoria trasporto materiali pericolosi**. Nella pagina **Categoria trasporto materiali pericolosi** è possibile creare un numero qualsiasi di categorie di trasporto e configurarle con un nome visualizzato e una breve descrizione.

### <a name="hazardous-material-technical-name"></a><a name="technical-name"></a>Nome tecnico materiale pericoloso

La specifica *Nome tecnico materiale pericoloso* può essere utilizzata per fornire un nome interno o comunemente usato nella società che descrive ogni materiale.

Per impostare i valori per la specifica, andare a **Gestione informazioni sul prodotto \> Impostazione \> Documentazione per la spedizione di materiali pericolosi \> Nome tecnico materiale pericoloso**. Nella pagina **Nome tecnico materiale pericoloso** è possibile creare un numero qualsiasi di nomi tecnici e configurarli con un nome visualizzato e una breve descrizione.

### <a name="hazardous-material-tunnel"></a><a name="tunnel"></a>Tunnel materiali pericolosi

La specifica *Tunnel materiali pericolosi* limita i tipi di tunnel attraverso i quali un materiale pericoloso può essere trasportato identificando i tipi di tunnel che devono essere utilizzati. Le categorie di tunnel sono stabilite dalle normative applicabili per il trasporto di materiali pericolosi. Questa specifica di solito si applica solo al trasporto su strada.

Per impostare i valori per la specifica, andare a **Gestione informazioni sul prodotto \> Impostazione \> Documentazione per la spedizione di materiali pericolosi \> Tunnel materiali pericolosi**. Nella pagina **Tunnel materiali pericolosi** è possibile creare un numero qualsiasi di identificatori di tunnel e configurarli con un codice di identificazione e una breve descrizione.
