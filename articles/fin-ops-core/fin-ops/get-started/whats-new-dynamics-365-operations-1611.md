---
title: Novità o modifiche introdotte in Dynamics 365 for Operations versione 1611 (novembre 2016)
description: Questo argomento descrive le funzionalità nuove o modificate di Dynamics 365 for Operations versione 1611.
author: sericks007
manager: AnnBe
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ROBOTS: NOINDEX, NOFOLLOW
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.custom: 221294
ms.assetid: 357931ed-f843-4bf5-bc85-0da3de0619ec
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 0b3ede085533fee1bb779ed9da899f509a77fc0c
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/08/2020
ms.locfileid: "4693433"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-operations-version-1611-november-2016"></a>Novità o modifiche introdotte in Dynamics 365 for Operations versione 1611 (novembre 2016)

[!include [banner](../includes/banner.md)]

Questo argomento descrive le funzionalità nuove o modificate di Dynamics 365 for Operations versione 1611.

## <a name="cost-accounting"></a>Contabilità industriale

<table>
<thead>
<tr>
<th>Operazioni che è possibile effettuare</th>
<th>Perché questo è importante</th>
</tr>
</thead>
<tbody>
<tr>
<td>Definire le dimensioni elemento di costo e importare i membri di dimensioni elemento di costo.</td>
<td>Gli elementi di costo vengono utilizzati nella contabilità industriale per classificare i costi e documentare il flusso dei costi. Gli elementi di costo primari sono importati tramite un connettore dati di Microsoft Dynamics 365 for Operations per ottenere i conti principali direttamente da Operations oppure utilizzando un connettore dati generico, dove ottenere i conti principali tramite Microsoft Excel da qualsiasi altro tipo di sistema di origine. Dopo che i conti principali vengono importati nella contabilità industriale, vengono utilizzati come membri di dimensioni elemento di costo. Gli elementi di costo secondari sono definiti dall'utente e vengono utilizzati nelle allocazioni per documentare il flusso dei costi.</td>
</tr>
<tr>
<td>Mappare le dimensioni elemento di costo.</td>
<td>Se i conti principali delle persone giuridiche non possono essere condivisi a causa di requisiti statutari di contabilità, è possibile mapparli dopo che averli importati nella contabilità industriale per ottenere una visualizzazione olistica nell'intera organizzazione.</td>
</tr>
<tr>
<td>Definire le dimensioni oggetto di costo e importare i membri di dimensioni oggetto di costo.</td>
<td>Gli oggetti di costo sono qualsiasi tipo di oggetto a cui i costi vengono allocati. Gli oggetti di costo tipici includono prodotti, progetti, risorse, i reparti, i centri di costo e aree geografiche. È possibile utilizzare un connettore dati di Microsoft Dynamics 365 for Operations per ottenere le dimensioni finanziarie e i valori da Operations o utilizzare un connettore dati generico, in cui è possibile ottenere le dimensioni e i valori tramite Excel da qualsiasi altro tipo di sistema di origine. Ad esempio, se si utilizza la dimensione finanziaria centro di costo come dimensione oggetto, tutti i centri di costo importati sono i membri della dimensione per l'oggetto di costo.</td>
</tr>
<tr>
<td>Definire o importare dimensioni statistiche.</td>
<td>I membri di dimensioni statistiche vengono misurati in unità non monetarie, ad esempio ore-macchina, numero di dipendenti e quadrato. Vengono utilizzate nei rendiconti, o come base per le allocazioni e le distribuzioni.</td>
</tr>
<tr>
<td>Creare modelli provider di misure statistiche.</td>
<td>Un modello provider di misure statistiche viene utilizzato per trasformare i dati di Dynamics 365 for Operations in misure statistiche. Il modello viene poi associato a un membro specifico di dimensione statistica. I modelli sono prefiltrati in modo che mostrino solo le tabelle associate alle dimensioni finanziarie.</td>
</tr>
<tr>
<td>Creare movimenti CoGe di contabilità industriale.</td>
<td>Un conto CoGe di contabilità industriale è un conto CoGe agnostico che utilizza il proprio calendario e valuta. Svolge un ruolo fondamentale nell'elaborazione di tutte le transazioni di costo. Ad esempio, un conto CoGe di contabilità industriale classifica i costi in base ai propri elementi di costo e raggruppa i costi in base alle proprie dimensioni oggetto. È possibile creare il numero di movimenti CoGe di contabilità industriale necessario per eseguire il reporting di gestione da varie prospettive.</td>
</tr>
<tr>
<td>Creare unità di controllo costi.</td>
<td>Le unità di controllo costi rappresentano la struttura dei costi e definiscono il flusso dei costi in un conto CoGe di contabilità industriale. Devono essere associate alle dimensioni oggetto di costo per rappresentare le dimensioni oggetto di costo nella contabilità generale.</td>
</tr>
<tr>
<td>Elaborare voci di contabilità generale.</td>
<td>Per misurare le prestazioni effettive, è necessario disporre di dati. I dati vengono importati utilizzando i connettori definiti per i movimenti CoGe di contabilità industriale. Quando si elaborano le voci di contabilità generale, i dati vengono importati in modo incrementale.</td>
</tr>
<tr>
<td>Elaborare voci di budget.</td>
<td>Per misurare le prestazioni a budget, è necessario disporre di dati. I dati vengono importati utilizzando i connettori definiti per i movimenti CoGe di contabilità industriale. Quando si elaborano le voci di budget, i dati vengono importati in modo incrementale.</td>
</tr>
<tr>
<td>Creare e applicare criteri di comportamento costo.</td>
<td>Utilizzare i criteri di comportamento costo per classificare i costi come fissi, variabili o semi-variabili. I criteri sono basati su regole e date di validità. Per impostazione predefinita, tutti i costi sono contrassegnati come non classificati finché non si applica un criterio di comportamento costo e si calcolano gli effetti della regola. Dopo il calcolo, i costi vengono classificati.</td>
</tr>
<tr>
<td>Tracciare i costi.</td>
<td>Per comprendere meglio l'impatto dei criteri dei costi, la contabilità industriale consente di tracciare i costi ai valori di origine e le regole applicate in cui originano. Questa funzionalità consente la tracciabilità completa su quando i costi sono verificati, il tipo di costi quali regole di comportamento costo sono state applicate.</td>
</tr>
<tr>
<td>Definire gerarchie di dimensioni.</td>
<td>È possibile creare gerarchie di dimensioni per scopi di classificazione o categorizzazione. Ad esempio, è possibile definire una gerarchia di categorizzazione basata su una dimensione elemento di costo e i relativi membri. In alternativa, è possibile definire una gerarchia di classificazione basata su una dimensione oggetto di costo e i relativi membri. Le strutture gerarchiche vengono utilizzate nelle seguenti situazioni:
<ul>
<li>Per definire allocazioni, i tassi di costo e regole di rollup dei costi.</li>
<li>Per visualizzare rendiconti tramite l'area di lavoro.</li>
<li>Per definire l'accesso per visualizzare i dati aggregati.</li>
<li>Per visualizzare dati in Excel.</li>
</ul></td>
</tr>
<tr>
<td>Creare rendiconti che possono essere visualizzati nell'area di lavoro.</td>
<td>Utilizzare l'area di lavoro per una rapida panoramica dei costi effettivi e quelli a budget e le deviazioni. È possibile filtrare dati per periodo o livello di costo. L'area di lavoro è stata progettata per i responsabili del controllo costi. Aderisce alle regole di accesso definite per le gerarchie di dimensioni.</td>
</tr>
<tr>
<td>Creare report utilizzando Excel.
<blockquote>[!NOTE] È necessario eseguire Microsoft Excel 2016.</blockquote>
</td>
<td>È possibile esportare dati di contabilità industriale direttamente in Excel tramite entità di dati e utilizzare una Tabella pivot Microsoft per creare report.</td>
</tr>
</tbody>
</table>

## <a name="expense-management"></a>Gestione spese

| Operazioni che è possibile effettuare | Perché questo è importante |
|-----------------|-----------------------|
| Riassegnare transazioni con carta di credito di dipendenti il cui rapporto di lavoro è concluso. | Talvolta, quando un dipendente ha concluso il rapporto di lavoro, il relativo account di Active Directory Domain Services (AD DS) viene disabilitato durante l'importazione delle transazioni con carta di credito che devono essere calcolate come spesa. In precedenza, non era possibile assegnare un delegato per l'inserimento spese o collegare transazioni con carta di credito a una nota spese. È ora possibile utilizzare la pagina **Transazioni con carta di credito** per riassegnare al dipendente qualsiasi transazione con carta di credito del dipendente associato che ha concluso il rapporto di lavoro. Dopo aver riassegnato la transazione con carta di credito, la transazione può essere selezionata per una nota spese e essere pagata tramite il normale processo di rimborso della nota spese. |
| Modificare le informazioni della carta di credito per le spese di dipendenti in sospeso e passati. | È possibile modificare le informazioni della carta di credito per la gestione spese per i lavoratori in sospeso e i lavoratori passati. In precedenza, era possibile modificare le informazioni relative alla carta di credito per le spese solo se il lavoratore era un dipendente attivo. |
| Copiare una nota spese. | È ora possibile copiare una nota spese esistente quando si crea una nuova spesa nella stessa nota spese. È possibile copiare una nota spese e tutte le spese non con carta di credito associate in una nuova nota spese. È ancora necessario specificare i dettagli richiesti e allegare le ricevute richieste, in base ai criteri  e alle categorie di spesa definiti. È possibile aggiungere transazioni con carta di credito alla nota spese scegliendo di aggiungere le spese non riconciliate. |
| Modificare in blocco spese. | Alcune transazioni con carta di credito potrebbero non essere mappate a una categoria di spesa o essere mappate in modo non corretto quando vengono importate. In questo caso, i dipendenti devono modificare manualmente la categoria di spesa associata. Quando si gestiscono le spese non riconciliate, è possibile modificare in blocco la categoria di spesa per le spese selezionate. Inoltre, quando si gestiscono le spese selezionate per una specifica nota spese, è possibile modificare in blocco le informazioni sul progetto e le informazioni aggiuntive. |
| Modificare il tasso di cambio per le transazioni con carta di credito. | Il tasso di cambio effettivo utilizzato per una transazione con carta di credito può essere diverso da quello impostato nel sistema. In precedenza, i dipendenti non potevano modificare il tasso di cambio per alcuna transazione con carta di credito importata in Gestione spese. È ora possibile impostare la pagina **Parametri di Gestione spese** per consentire di modificare il tasso di cambio per le transazioni con carta di credito. |
| Impostare l'attestazione anticorruzione per le spese. | Alcuni dipendenti per un'organizzazione potrebbero avere rapporti commerciali con funzionari statali e alcune spese che si verificano come parte di tali rapporti potrebbero essere percepite come corruzione. In Gestione spese, è ora possibile impostare un'attestazione anticorruzione visualizzata per categorie di spesa selezionate, ad esempio pasti e regali. I dipendenti devono selezionare se le spese impostate per l'attestazione anticorruzione soddisfano i criteri definiti dai criteri dell'organizzazione. |
| Impedire l'immissione manuale delle spese per categorie specifiche di spesa. | Una categoria di spesa può essere impostata per rappresentare una transazione con carta di credito per cui la categoria non può essere modificata. Un esempio è una commissione per il pagamento ritardato con carta di credito. È ora possibile impostare una categoria di spesa che consente che le spese vengano create solo tramite importazione. Questa funzionalità impedisce ai dipendenti di creare manualmente una spesa per la categoria. Inoltre non consente che la categoria venga modificata per le transazioni importate e che utilizzano la categoria. |
| Allegare una ricevuta a più spese. | Una ricevuta caricata in Gestione spese potrebbe essere relativa a più spese. In precedenza, una ricevuta relativa a più spese doveva essere caricata una volta per ciascuna spesa. È ora possibile allegare a una spesa una ricevuta che è già stata caricata e allegata a un'altra spesa nella stessa nota spese. Inoltre, se si carica una ricevuta nell'intestazione della nota spese, è possibile selezionare una o più righe a cui allegare la ricevuta. |
| Creare spese con data futura. | Quando si copia una nota spese, ad esempio, la data della transazione per la spesa può avere una data futura. Le versioni precedenti non consentono le spese con date future. È ora possibile creare e salvare le spese con una data futura. Tuttavia, non è possibile inviare una spesa con data futura. |
| Configurare le imposte su spese per uno stato/regione o provincia. | In alcuni paesi, le spese sostenute in stati/regioni o province differenti potrebbero essere soggette a diverse aliquote IVA. È ora possibile impostare le configurazioni imposte spese a livello di stato/regione o provincia, non solo a livello di paese. Se si lascia vuoto il campo **Stato/Regione/Provincia** nella pagina **Configurazione fiscale**, la fascia IVA viene applicata a tutti gli stati/regioni/provincie del paese specificato. |
| Impostare tipi di carta di credito per le spese. | In precedenza, non esisteva una pagina in cui creare nuovi tipi di carta di credito, ad esempio Visa, MasterCard o AMEX, utilizzabili con Gestione spese. È ora possibile creare i tipi di carta di credito da utilizzare per Gestione spese. La pagina di trova nell'area **Impostazione**, sezione **Calcoli e codici**. |
| Definire un flusso di lavoro di approvazione multilivello per le note spese. | Un nuovo flusso di lavoro per le note spese supporta un processo di approvazione multilivello. I dipendenti immettono gli approvatori provvisori e gli approvatori finali durante la creazione della nota spese. Il flusso di lavoro indirizza quindi la nota spese agli approvatori provvisori per primi. Dopo che la nota spese è approvata a quel livello, il flusso di lavoro la indirizza agli approvatori finali per l'approvazione finale. |
| Creare e gestire le spese non collegate a una nota spese. | L'utente può ora creare spese e gestirle, (ad esempio allegando o dettagliando  ricevute o assegnando ospiti) senza dover prima creare una nota spese. Una o più spese possono essere selezionate e aggiunte a una nuova nota spese, in modo che possono essere inviate per l'approvazione. Una nuova pagina per la gestione delle spese è disponibile in **Gestione spese** &gt; **Spese personali** &gt; **Spese**. |

## <a name="financial-management"></a>Gestione finanziaria

<table>
<thead>
<tr>
<th>Operazioni che è possibile effettuare</th>
<th>Perché questo è importante</th>
</tr>
</thead>
<tbody>
<tr>
<td>Tenere traccia delle valutazioni cespiti utilizzando un unico concetto di "libro".</td>
<td>In precedenza, due tipi diversi di valutazione sono stati utilizzati per tenere traccia dei valori di cespiti: modelli di valore e registri beni ammortizzabili. Nella versione corrente, questi due concetti sono stati uniti in un unico concetto di valutazione denominato libri. I libri hanno tutte le funzionalità dei modelli di valore e dei registri beni ammortizzabili. Ad esempio, è possibile disabilitare la registrazione nella contabilità generale. I libri che registrano nella contabilità generale sono in genere utilizzati per i report finanziari aziendali. I libri che non registrano nella contabilità generale possono essere utilizzati per i report fiscali.</td>
</tr>
<tr>
<td>Eseguire la chiusura di fine anno della contabilità generale per più persone giuridiche.</td>
<td>Per accelerare il processo di chiusura di fine anno, è ora possibile eseguire la chiusura di fine anno per più persone giuridiche da una pagina di chiusura di fine anno condivisa. Gruppi di persone giuridiche possono essere definiti, insieme alle impostazioni che devono essere mantenute da un anno all'altro. Altri miglioramenti di usabilità sono inoltre stati apportati al processo di chiusura di fine anno.</td>
</tr>
<tr>
<td>Sfruttare i miglioramenti relativi alla rivalutazione valuta estera della contabilità generale.</td>
<td>I seguenti miglioramenti sono stati apportati al processo di contabilità generale per la rivalutazione valuta estera:
<ul>
<li>Un tipo di tasso di cambio è stato aggiunto al conto principale. Questo tipo di tasso di cambio viene ora utilizzato per determinare il tasso di cambio durante la rivalutazione valuta. Se non si definisce un tipo di tasso di cambio, il processo continua a utilizzare il tipo di tasso di cambio definito nella contabilità generale.</li>
<li>È ora più semplice selezionare un intervallo di conti principali e valute per cui eseguire il processo di rivalutazione.</li>
<li>La rivalutazione può essere eseguita per più persone giuridiche.</li>
<li>Il sistema ora gestisce lo storico di ogni processo di rivalutazione eseguito, così come dei processi di rivalutazione per la contabilità clienti e la contabilità fornitori.</li>
<li>Quando si esegue il processo, è ora possibile visualizzare l'anteprima dei risultati della rivalutazione. L'anteprima mostra i risultati per tutte le persone giuridiche in cui il processo è stata eseguito. È quindi possibile registrare tutte le persone giuridiche, o un sottoinsieme di esse, dall'anteprima. È inoltre possibile esportare i risultati dall'anteprima in Excel.</li>
</ul></td>
</tr>
<tr>
<td>Visualizzare transazioni per livelli di registrazione aggiuntivi.</td>
<td>Nella pagina elenco <strong>Bilancio di verifica</strong> e nel report <strong>Rendiconto dimensioni</strong> è ora possibile selezionare i livelli di registrazione supplementari aggiunti alla contabilità generale. Quando si selezionano i livelli di registrazione aggiuntivi, le rettifiche di tali livelli di registrazione vengono incluse nei saldi nella pagina elenco o nel report.</td>
</tr>
<tr>
<td>Allegare la documentazione di procedura al modello di chiusura del periodo finanziario.</td>
<td>In precedenza, era possibile allegare la documentazione dopo l'esecuzione di un'attività. Ad esempio, era possibile allegare un report generato. È ora possibile anche allegare un documento di procedura al modello. Questo documento di procedura verrà copiato in ogni attività nella programmazione del periodo finanziario, in modo che il proprietario dell'attività può visualizzare le istruzioni su come completare l'attività.</td>
</tr>
<tr>
<td>Definire l'impostazione della contabilità interaziendale da una pagina condivisa.</td>
<td>La <strong>pagina di impostazione della contabilità interaziendale</strong> è ora condivisa, in modo che un'organizzazione possa definire tutte coppie di persone giuridiche che possono eseguire transazioni tra loro. Inoltre, è ora possibile immettere una transazione nella persona giuridica di origine ma non dalla persona giuridica di destinazione. Se una delle due persone giuridiche può avviare una transazione interaziendale, la coppia reciproca deve essere definita. Pertanto, la persona giuridica di destinazione è anche impostata come persona giuridica di origine.</td>
</tr>
<tr>
<td>Inviare documenti di motivazione per i piani di budget.</td>
<td>È possibile creare un modello di motivazione come documentazione aggiuntiva per tutti gli importi di budget richiesti. Gli utenti possono immettere i dettagli del modello e allegare il modello al piano di budget, in modo che può essere utilizzato durante il processo di approvazione.</td>
</tr>
<tr>
<td>Abilitare regole avanzate per le voci del registro di budget.</td>
<td>Se le regole avanzate vengono configurate nella contabilità generale, tali regole possono essere utilizzate per nuove voci e trasferimenti nel registro di budget.</td>
</tr>
<tr>
<td>Sfruttare la migliorata visibilità dell'attività di fatturazione del pagamento anticipato.</td>
<td>Una nuova pagina elenco <strong>Pagamenti anticipati aperti</strong> fornisce uno snapshot dello stato dell'attività di fatturazione del pagamento anticipato. La pagina fornisce al reparto CF informazioni sugli ordini fornitore con valori rimanenti di pagamento anticipato da fatturare, i valori fatturati che devono essere pagati e i valori di fattura pagati da applicare alle fatture standard. Inoltre, i miglioramenti relativi all'applicazione automatica alle fatture standard delle fatture di pagamento anticipato pagate aiutano gli addetti alla fatturazione ad immettere i dati con più efficienza.</td>
</tr>
<tr>
<td>Utilizzare l'area di lavoro <strong>Fatturazione di collaborazione fornitore</strong>.</td>
<td>Una nuova area di lavoro <strong>Fatturazione</strong> nell'area <strong>Collaborazione fornitore</strong> consente ai fornitori esterni di accedere in modo sicuro alle proprie informazioni di fatturazione. Ad esempio, i fornitori possono vedere se una fattura è stata pagata e inviare la propria fattura. Questa modifica promuove una comunicazione più efficiente e più tempestiva con i fornitori esterni. Di conseguenza, gli addetti alla fatturazione subiscono meno interruzioni.</td>
</tr>
<tr>
<td>Passare da una persona giuridica all'altra nell'inserimento fatture.</td>
<td>I miglioramenti consentono agli addetti alla fatturazione che devono inserire fatture per più persone giuridiche di rapidamente cambiare la persona giuridica dalle pagine di fatturazione. Questa funzionalità consente di risparmiare tempo degli addetti alla fatturazione, poiché non devono più disconnettersi dalla persona giuridica corrente e accedere in una persona giuridica diversa. Sia la pagina <strong>Giornale di registrazione fatture globale</strong> che la pagina <strong>Fatture fornitore</strong> consentono agli utenti di modificare la persona giuridica durante l'immissione dei dati.</td>
</tr>
<tr>
<td>Supporto per i file elettronici per il programma di presentazione del modulo 1099 IRS (Internal Revenue Service) federale/statale combinato</td>
<td>Quando la chiave di configurazione <strong>US</strong> è abilitata, il processo di presentazione elettronica 1099 fornisce funzionalità aggiuntive conformi alla normativa IRS per il programma di presentazione federale/statale combinato. L'IRS ha stabilito questo programma in modo che possa essere inoltrare elettronicamente informazioni da restituire agli stati partecipanti.</td>
</tr>
<tr>
<td>Miglioramenti nella liquidazione</td>
<td>I miglioramenti aiutano gli addetti ai pagamenti a liquidare con più efficienza, poiché possono consentire la liquidazione di più pagamenti non registrati a fronte della stessa fattura.</td>
</tr>
<tr>
<td>Visualizzazione interaziendale</td>
<td>Gli addetti ai pagamenti centralizzati possono ora visualizzare le fatture scadute di più società. Le aree di lavoro <strong>Pagamenti fornitore</strong> e <strong>Pagamenti clienti</strong> ora offrono una maggiore visibilità e controllo sulle fatture scadute fornendo un modo per visualizzare e filtrare più società che fanno parte di una gerarchia organizzativa di pagamento centralizzato.</td>
</tr>
<tr>
<td>Utilizzare l'area di lavoro <strong>Gestione banche</strong>.</td>
<td>Una nuova area di lavoro <strong>Gestione banche</strong> aiuta a tenere traccia dei conti bancari e dei saldi delle persone giuridiche. I saldi correnti e in sospeso sono immediatamente disponibili per tutti i conti ed è possibile eseguire il drill-back dai saldi a giustificativi dettagliati delle transazioni. È inoltre possibile visualizzare i dati storici del saldo di ciascun conto bancario, o un riepilogo per tutti i conti bancari della società, in visualizzazioni sia a breve termine che a lungo termine. È possibile ottenere una visione più approfondita della riconciliazione degli estratti conto, poiché la data dell'ultima riconciliazione viene riportata per ciascun conto bancario ed è presente anche un indicatore per le riconciliazioni in corso.</td>
</tr>
<tr>
<td>Importare rendiconti bancari elettronici per tutte le persone giuridiche in un unico passaggio.</td>
<td>È ora possibile importare rendiconti bancari elettronici per tutte le persone giuridiche in un unico passaggio. I file di rendiconto bancario possono contenere i rendiconti da molti conti bancari e persone giuridiche e i file ZIP possono contenere più file di rendiconto bancario. Utilizzando un singolo processo di importazione, è possibile avviare la riconciliazione per tutti i conti bancari dichiarati in tutte le persone giuridiche. Questa funzionalità consente di risparmiare tempo, in quanto non è necessario passare da una società all'altra e più importazioni di rendiconti. È inoltre possibile eseguire automaticamente le regole di abbinamento su tutti i rendiconti importati in ciascuna società.</td>
</tr>
<tr>
<td>Tracciabilità delle valutazioni</td>
<td>Un singolo cespite può avere più valutazioni per diversi standard contabili e può facoltativamente registrare le transazioni associate nella contabilità generale. In precedenza, le valutazioni erano tracciate utilizzando i modelli di valore o i registri beni ammortizzabili. È ora possibile tracciare queste valutazioni, che ora sono note come libri, utilizzando un insieme comune di giornali di registrazione, richieste di informazioni e report. L'esperienza unificata semplifica l'implementazione e riduce il numero delle interfacce che i processi periodici richiedono.</td>
</tr>
<tr>
<td>Sfruttare i miglioramenti alle esecuzioni degli ammortamenti interaziendali.</td>
<td>È ora possibile avviare l'esecuzione dell'ammortamento per i cespiti per tutte le persone giuridiche da una singola pagina. È inoltre possibile registrare automaticamente i giornali di registrazione dopo la creazione. È possibile inviare la creazione e la registrazione dei giornali di registrazione all'elaborazione batch, in modo che l'ammortamento viene eseguito in background. Questi miglioramenti riducono le inefficienze, in quanto non è necessario eseguire separatamente singoli cicli di ammortamento per ogni società. Il miglioramento abilita anche una migliore gestione centralizzata dei cespiti.</td>
</tr>
</tbody>
</table>

## <a name="human-capital-management"></a>Gestione risorse umane

<table>
<thead>
<tr>
<th>Operazioni che è possibile effettuare</th>
<th>Perché questo è importante</th>
</tr>
</thead>
<tbody>
<tr>
<td>Creare un giornale di registrazione prestazioni.</td>
<td>Prima di completare la revisione, spesso si raccolgono informazioni sulle attività o sugli eventi che hanno contribuito al proprio successo come dipendente durante il periodo di revisione. È possibile aggiungere una voce al giornale di registrazione prestazioni per documentare tali attività ed eventi. È inoltre possibile collegare tali attività e gli eventi a un obiettivo o una revisione delle prestazioni per fornire ulteriori informazioni al revisore.</td>
</tr>
<tr>
<td>Creare obiettivi più dettagliati.</td>
<td>Si dispone di maggiore controllo sul contenuto degli obiettivi impostati. È possibile creare misure per gli obiettivi, collegare inserimenti nel giornale di registrazione prestazioni alle misure e collegare e visualizzare documenti. È possibile archiviare gli obiettivi come modelli e riutilizzarle per un'impostazione rapida.</td>
</tr>
<tr>
<td>Creare revisioni delle prestazioni più dettagliate.</td>
<td>Le revisioni delle prestazioni, definite formalmente come discussioni, sono ora sufficientemente flessibili da supportare sia riscontri continui che revisioni più formali. È possibile estrarre obiettivi attivi e registrare commenti di essi, e aggiungere sezioni per una revisione delle proprie competenze. Sono fornite sezioni aggiuntive in cui è possibile aggiungere o visualizzare misure, gli inserimenti nel giornale di registrazione delle prestazioni, gli allegati e le conferme correlati alla revisione.</td>
</tr>
<tr>
<td>Associare gerarchie di posizione aggiuntive ai flussi di lavoro.</td>
<td>È possibile associare un flusso di lavoro a una gerarchia posizioni. È inoltre possibile modificare i passaggi del flusso di lavoro per ottimizzare il processo di approvazione in modo che soddisfi i requisiti aziendali. Di conseguenza, è possibile definire una struttura di approvazione valida che corrisponda alle diverse relazioni gerarchiche in uso nell'organizzazione.</td>
</tr>
<tr>
<td>Supporto al flusso di lavoro per immettere i numeri di identificazione personale (PIN) in Dipendente self-service.</td>
<td>Le funzionalità di flusso di lavoro per il reparto Risorse umane (HR) è stata espansa e ora include il supporto per i PIN. I dipendenti possono aggiungere e modificare il relativo PIN per migliorare l'efficienza. Tuttavia, i lavoratori HR possono controllare la precisione e la completezza di queste informazioni prima di aggiungerle al record del dipendente.</td>
</tr>
<tr>
<td>Creare modelli di obiettivo e usarli per aggiungere nuovi obiettivi.</td>
<td>È possibile creare modelli di obiettivo per gli obiettivi condivisi da numerosi dipendenti della società. I dipendenti possono aggiungere i propri obiettivi da un modello, i responsabili possono aggiungere obiettivi per il team da un modello e i membri del team HR possono aggiungere obiettivi per i dipendenti in tutta la società.</td>
</tr>
<tr>
<td>Creare gruppi di obiettivi e usarli per aggiungere nuovi obiettivi.</td>
<td>È possibile aggiungere i modelli di obiettivo a un gruppo e utilizzare il gruppo per creare uno o più obiettivi per un dipendente, un team, una posizione, un reparto o la società.</td>
</tr>
<tr>
<td>Disporre di più controllo sul processo di revisione.</td>
<td>È possibile utilizzare un flusso di lavoro per controllare il processo di revisione. È possibile creare modelli di revisione e utilizzarli per creare le revisioni. È inoltre possibile aggiungere valutazioni a una revisione.</td>
</tr>
<tr>
<td>Utilizzare i periodi di revisione per definire l'intervallo temporale per la revisione.</td>
<td>È possibile definire un periodo per una revisione delle prestazioni e le date di inizio e di fine della revisione vengono immesse automaticamente. Tuttavia, è possibile modificare tali date predefinite secondo le esigenze.</td>
</tr>
<tr>
<td>Accesso a cinque nuovi pacchetti di contenuti Power BI per Risorse umane</td>
<td>I nuovi pacchetti di contenuti consentono alle organizzazioni di risorse umane e ai responsabili delle risorse umane di analizzare i seguenti aspetti:
<p>Metriche forza lavoro</p>
<ul>
<li>Analisi dei dati demografici in base a età, sesso e stato civile</li>
<li>Confronto dei tassi di conflitto nell'arco degli anni e analisi di un elenco di motivi che hanno indotto alcuni dipendenti a lasciare l'organizzazione</li>
<li>Visualizzazione di un elenco di posizioni aperte, nonché un confronto tra posizioni aperte e posizioni chiuse</li>
</ul>
<p>Retribuzione e benefit</p>
<ul>
<li>Confronto tra dipendenti stipendiati e dipendenti con paga oraria</li>
<li>Visualizzazione del numero di dipendenti iscritti ai benefit disponibili</li>
<li>Visualizzazione dei dipendenti in base al tipo di impiego</li>
</ul>
<p>Selezione del personale</p>
<ul>
<li>Analisi dei candidati in base al numero di candidati, alla loro provenienza e alle posizioni per le quali si candidano per la formazione nell'organizzazione</li>
</ul>
<p>Formazione organizzativa</p>
<ul>
<li>Registrazione ai corsi in base all'ubicazione</li>
<li>Frequentazione dei corsi in base allo stato</li>
<li>Elenco di dipendenti registrati per i corsi per lo sviluppo e le competenze</li>
</ul>
<p>Competenze e sviluppo del dipendente</p>
<ul>
<li>Elenco di competenze possedute dai dipendenti</li>
<li>Analisi dei tipi di competenze posseduti dai membri di un team</li>
</ul>
</td>
</tr>
</tbody>
</table>

## <a name="localizations"></a>Localizzazioni

<table>
<thead>
<tr>
<th>Operazioni che è possibile effettuare</th>
<th>Perché questo è importante</th>
</tr>
</thead>
<tbody>
<tr>
<td>Localizzazioni sono disponibili per 18 paesi aggiuntivi:
<ul>
<li>Austria</li>
<li>Belgio</li>
<li>Brasile</li>
<li>Cina</li>
<li>Repubblica Ceca</li>
<li>Estonia</li>
<li>Finlandia</li>
<li>Ungheria</li>
<li>Italia</li>
<li>Lettonia</li>
<li>Lituania</li>
<li>Norvegia</li>
<li>Polonia</li>
<li>Arabia Saudita</li>
<li>Spagna</li>
<li>Svezia</li>
<li>Svizzera</li>
<li>Thailandia</li>
</ul>
<p>I seguenti paesi richiedono inoltre la localizzazione di Retail. La localizzazione di Retail per questi paesi non è stata completata ed è pianificata solo per la prima metà del 2017:</p>
<ul>
<li>Brasile</li>
<li>Repubblica Ceca</li>
<li>Estonia</li>
<li>Ungheria</li>
<li>Lettonia</li>
<li>Lituania</li>
<li>Malaysia</li>
<li>Polonia</li>
<li>Svezia</li>
</ul>
</td>
<td>Dynamics 365 for Operations è disponibile in 18 paesi aggiuntivi. Come parte dell'impegno di Microsoft di rendere la localizzazione più semplice e configurabile, le funzionalità di creazione dei report elettronici in base alle normative sono state convertite in configurazioni di creazione di report elettronici (ER) e alcuni report Microsoft SQL Server Reporting Services (SSRS) regolamentari sono stati convertiti in configurazioni ER che utilizzano modelli di Excel. Queste funzionalità convertite sono specificate più avanti nella tabella.</td>
</tr>
<tr>
<td>Giappone - Raggruppare i cespiti quando si stampa il modulo 26 e le tabelle allegate.</td>
<td>Il modulo 26 deve essere inviato a ogni città in cui opera la società. Per risparmiare risorse quando si stampa il modulo 26, i cespiti possono essere raggruppate e ordinato automaticamente per ubicazione.</td>
</tr>
<tr>
<td>Giappone - Vedere gli importi di ammortamento accelerato e aggiuntivo sul profilo.</td>
<td>Il profilo può fornire una stima accurata degli importi di ammortamento accelerato e aggiuntivo.</td>
</tr>
<tr>
<td>Giappone - Calcolare progressivamente la ritenuta d'acconto.</td>
<td>Il Governo giapponese richiede di calcolare la ritenuta d'acconto progressivamente, in base all'importo del pagamento.</td>
</tr>
<tr>
<td>Giappone - Importare il file dei codici postali per specifici edifici di grandi aziende.</td>
<td>Il file dei codici postali per l'ufficio tributario prevede per specifici edifici di grandi aziende può essere importato nel sistema. L'indirizzo potrà quindi essere derivato dai codici postali.</td>
</tr>
<tr>
<td>Giappone - Configurare un periodo di inattività per i cespiti.</td>
<td>I periodi di inattività consentono all'utente di sospendere l'ammortamento del cespite durante il periodo specificato. Questa funzionalità è richiesta dalla normativa.</td>
</tr>
<tr>
<td>Europa - Configurare un numero di partita IVA per l'indirizzo di una parte utilizzando il framework ID registrazione.</td>
<td>È possibile configurare un numero di partita IVA per l'indirizzo di una parte utilizzando il framework ID registrazione e una nuova categoria di registrazione <strong>ID IVA</strong>.</td>
</tr>
<tr>
<td>Finlandia - Configurare un numero cliente per dogana per l'indirizzo di una parte utilizzando il framework ID registrazione.</td>
<td>È possibile configurare un numero cliente per dogana per l'indirizzo di una parte utilizzando il framework ID registrazione e una nuova categoria di registrazione <strong>ID cliente per dogana</strong>.</td>
</tr>
<tr>
<td>Francia - Stampare le fatture cliente in un layout specifico per la Francia.</td>
<td>La stampa delle fatture cliente viene modificata per soddisfare i requisiti specifici della Francia.</td>
</tr>
<tr>
<td>Francia - applicare la numerazione cronologica dei documenti in base al periodo fiscale.</td>
<td>Per soddisfare i requisiti specifici della Francia per la numerazione delle fatture cliente, è possibile impostare sequenze numeriche per le fatture cliente per periodo fiscale.</td>
</tr>
<tr>
<td>Localizzazione per l'Austria - Configurazioni report elettronici</td>
<td>
<ul>
<li>Formato XML elenco vendite UE per l'Austria</li>
<li>Formato Intrastat per l'Austria</li>
<li>Formato di pagamento bonifico ISO20022 per l'Austria</li>
<li>Formato di pagamento in addebito diretto ISO20022 per l'Austria</li>
<li>Formato EDIFACT-PAYMUL austriaco</li>
<li>Dichiarazione IVA per l'Austria</li>
</ul>
</td>
</tr>
<tr>
<td>Localizzazione per il Belgio - Configurazioni report elettronici</td>
<td>
<ul>
<li>Formato BLWI per il Belgio</li>
<li>Formato XML elenco vendite UE per il Belgio</li>
<li>Report cespiti per il Belgio</li>
<li>Formato Intervat per il Belgio</li>
<li>Formato Intrastat per il Belgio</li>
<li>Report fatturato per il Belgio</li>
<li>Formato di esportazione delle transazioni contabili per il Belgio</li>
<li>Formato di pagamento fornitori SWIFT per il Belgio</li>
<li>Formato di importazione per rendiconto bancario CODA per il Belgio</li>
<li>Formato di pagamento bonifico ISO20022 per il Belgio</li>
<li>Formato di pagamento in addebito diretto ISO20022 per il Belgio</li>
</ul>
</td>
</tr>
<tr>
<td>Localizzazione per il Brasile - Configurazioni report elettronici</td>
<td>
<ul>
<li>GIA SP per il Brasile</li>
<li>GIA-ST per il Brasile</li>
</ul>
</td>
</tr>
<tr>
<td>Localizzazione per la Repubblica Ceca - Configurazioni report elettronici</td>
<td>
<ul>
<li>Formato XML dell'elenco vendite UE per la Repubblica Ceca.</li>
<li>Formato Intrastat per la Repubblica Ceca</li>
<li>Dichiarazione IVA per la Repubblica Ceca</li>
</ul>
</td>
</tr>
<tr>
<td>Localizzazione per la Cina - Configurazioni report elettronici</td>
<td>
<ul>
<li>Formato di report di aging clienti per la Cina</li>
<li>Formato report analisi importo dovuto clienti per la Cina</li>
<li>Formato di report di aging fornitori per la Cina</li>
<li>Formato report analisi importo dovuto fornitori per la Cina</li>
<li>Formato analisi di aging del pagamento di importi a credito per la Cina</li>
<li>Formato report di bilancio clienti per la Cina</li>
<li>Formato report di bilancio contabilità generale per la Cina</li>
<li>Formato di report di bilancio fornitori per la Cina</li>
<li>File GBT per la Cina</li>
<li>Formato del file di esportazione Golden Tax</li>
<li>Formato report scostamento consumo di produzione per la Cina</li>
</ul>
</td>
</tr>
<tr>
<td>Localizzazione per l'Estonia - Configurazioni report elettronici</td>
<td>
<ul>
<li>Formato XML elenco vendite UE per l'Estonia</li>
<li>Formato Intrastat per l'Estonia</li>
<li>Rendiconto riclassificazione inventariale per l'Estonia</li>
<li>Formato di pagamento bonifico ISO20022 per l'Estonia</li>
<li>Report avvisi saldo fornitore cliente per l'Estonia</li>
<li>Dichiarazione IVA per l'Estonia</li>
</ul>
</td>
</tr>
<tr>
<td>Localizzazione per la Finlandia - Configurazioni report elettronici</td>
<td>
<ul>
<li>Formato TXT elenco vendite UE per la Finlandia</li>
<li>Formato Intrastat per la Finlandia</li>
<li>Formato di pagamento bonifico ISO20022 per la Finlandia</li>
</ul>
</td>
</tr>
<tr>
<td>Localizzazione per l'Ungheria - Configurazioni report elettronici</td>
<td>
<ul>
<li>Formato XML elenco vendite UE per l'Ungheria</li>
<li>Formato Intrastat per l'Ungheria</li>
<li>Formato Intrastat semplificato per l'Ungheria</li>
<li>Formato di esportazione per elenco fatture per l'Ungheria</li>
<li>Dichiarazione IVA per l'Ungheria</li>
<li>Dichiarazione IVA dettagliata per l'Ungheria</li>
<li>Rendiconto inventario per l'Ungheria</li>
<li>Formato di pagamento MultiCash per l'Ungheria</li>
</ul>
</td>
</tr>
<tr>
<td>Localizzazione per l'Italia - Configurazioni report elettronici</td>
<td>
<ul>
<li>Formato Intrastat per l'Italia</li>
<li>Formato fattura progetto per l'Italia</li>
<li>Formato fattura vendita per l'Italia</li>
<li>Formato di pagamento bonifico ISO20022 per l'Italia</li>
<li>Formato di pagamento in addebito diretto ISO20022 per l'Italia</li>
<li>Formato di rimessa raccolta RIBA per l'Italia</li>
<li>Report di transazioni di imposta nazionale per l'Italia</li>
<li>Report block list per l'Italia</li>
<li>Report Modello770 per l'Italia</li>
<li>Report di comunicazione annuale imposte per l'Italia</li>
</ul>
</td>
</tr>
<tr>
<td>Localizzazione per la Lettonia - Configurazioni report elettronici</td>
<td>
<ul>
<li>Report su utilizzo ricevute (Lettonia)</li>
<li>Formato XML elenco vendite UE per la Lettonia</li>
<li>Formato XML correzioni elenco vendite UE per la Lettonia</li>
<li>Formato Intrastat (A) per la Lettonia</li>
<li>Formato Intrastat (B) per la Lettonia</li>
<li>Elenco di conteggio scorte per la Lettonia</li>
<li>Rendiconto di conteggio scorte per la Lettonia</li>
<li>Movimenti scorte per la Lettonia</li>
<li>Bolla di consegna trasferimento interno per la Lettonia</li>
<li>Documento riclassificazione inventario per la Lettonia</li>
<li>Formato di pagamento bonifico ISO20022 per la Lettonia</li>
<li>Dichiarazione IVA per la Lettonia</li>
</ul>
</td>
</tr>
<tr>
<td>Localizzazione per la Lituania - Configurazioni report elettronici</td>
<td>
<ul>
<li>Formato XML elenco vendite UE per la Lituania</li>
<li>Formato Intrastat per la Lituania</li>
<li>Rendiconto inventario per la Lituania</li>
<li>Formato di pagamento bonifico ISO20022 per la Lituania</li>
<li>Report di intra-riconciliazione fornitore cliente per la Lituania</li>
<li>Dichiarazione IVA per la Lituania</li>
</ul>
</td>
</tr>
<tr>
<td>Localizzazione per la Norvegia - Configurazioni report elettronici</td>
<td>
<ul>
<li>Formato lettera di sollecito per la Norvegia</li>
<li>Formato di pagamento AutoGiro per la Norvegia</li>
<li>Formato di pagamento cliente AvtaleGiro per la Norvegia</li>
<li>Formato di pagamento cliente eFaktura per la Norvegia</li>
<li>Formato di pagamento bonifico ISO20022 per la Norvegia</li>
<li>Formato di pagamento NETS per la Norvegia</li>
</ul>
</td>
</tr>
<tr>
<td>Localizzazione per la Polonia - Configurazioni report elettronici</td>
<td>
<ul>
<li>Formato Intrastat per la Polonia</li>
<li>Documenti di magazzino per la Polonia</li>
<li>Documento riclassificazione inventario per la Polonia</li>
<li>Formato di pagamento MultiCash per la Polonia</li>
<li>Formato di pagamento estero MultiCash per la Polonia</li>
<li>Report conferma saldi fornitori clienti per la Polonia</li>
</ul>
</td>
</tr>
<tr>
<td>Localizzazione per l'Arabia Saudita - Configurazioni report elettronici</td>
<td>Formato di allocazione spese varie LC banca per l'Arabia Saudita</td>
</tr>
<tr>
<td>Localizzazione per la Spagna - Configurazioni report elettronici</td>
<td>
<ul>
<li>Formato TXT elenco vendite UE per la Spagna</li>
<li>Formato Intrastat per la Spagna</li>
<li>Formato fattura progetto per la Spagna</li>
<li>Formato fattura vendita per la Spagna</li>
<li>Formato di pagamento bonifico ISO20022 per la Spagna</li>
<li>Formato di pagamento in addebito diretto ISO20022 per la Spagna</li>
<li>Formato libro IVA spagnolo</li>
<li>Formato riepilogo libro IVA spagnolo</li>
<li>Esportazione dichiarazione 347 in ASCII per la Spagna</li>
<li>Report dichiarazione 347 per la Spagna</li>
</ul>
</td>
</tr>
<tr>
<td>Localizzazione per la Svezia - Configurazioni report elettronici</td>
<td>
<ul>
<li>Formato Intrastat per la Svezia</li>
<li>Formato di pagamento dei clienti Bankgirot Autogiro per la Svezia</li>
<li>Formato di pagamenti fornitore Bankgirot per la Svezia</li>
<li>Formato di pagamento fornitori SWIFT per la Svezia</li>
<li>Formato esportazione SIE per la Svezia</li>
<li>Formato di pagamento bonifico ISO20022 per la Svezia</li>
</ul>
</td>
</tr>
<tr>
<td>Localizzazione per la Svizzera - Configurazioni report elettronici</td>
<td>
<ul>
<li>Formato di pagamento DebitDirect per la Svizzera</li>
<li>Formato di pagamento di addebito diretto LSV per la Svizzera</li>
<li>Formato di pagamento bonifico ISO20022 per la Svizzera</li>
<li>Formato di pagamento di addebito diretto ISO20022 per la Svizzera</li>
<li>Formato di importazione per rendiconto bancario ESR per la Svizzera</li>
</ul>
</td>
</tr>
<tr>
<td>Germania - Esporta pagamenti fornitore in formato DTAZV</td>
<td>In Germania è obbligatorio utilizzare il formato DTAZV con specifica di formato estero, che rappresenta un messaggio di bonifico (pagamento fornitore) in base alle specifiche per i pagamenti transfrontalieri dalla Germania a un conto di una banca estera o di una banca locale con valuta estera.</td>
</tr>
</tbody>
</table>

### <a name="electronic-reporting"></a>Creazione di report elettronici

| Operazioni che è possibile effettuare | Perché questo è importante |
|-----------------|-----------------------|
| Configurare i report ER per inserire i dati, in vari formati, dall'archivio di gestione documenti nei messaggi elettronici generati. | I report ER possono inserire i dati generati nei messaggi elettronici dall'archivio di gestione documenti. Di conseguenza, gli allegati di un documento aziendale possono essere aggiunti ai messaggi elettronici generati per il documento, in conformità ai requisiti legali. Attualmente, gli allegati possono essere aggiunti nel formato MIME a un messaggio XML generato. In alternativa, gli allegati possono essere aggiunti in formato Base64 a un messaggio binario che viene generato. |
| Configurare i report ER per generare i documenti elettronici in Excel, in Microsoft Word, o in formato PDF. | Una configurazione consente ai report ER di generare i documenti elettronici in tre diversi formati: Foglio di lavoro OpenXML (Excel), Word e formato XFDF (XML Forms Data Format) (PDF). Gli utenti possono selezionare un formato aggiungendo un modello di formato a una report ER come documento di Excel, Word o PDF. |
| Configurare i report di ER per inserire i dati nelle intestazioni e nei piè di pagina di documenti elettronici generati nel formato del foglio di lavoro OpenXML e per controllare interruzioni di pagina. | I report di ER possono immettere i dati aziendali nelle intestazioni e nei piè di pagina e anche determinare dove inserire interruzioni di pagina. Di conseguenza, i report possono supportare le sezioni inferiori e superiori statiche delle pagine di documenti elettronici generati. Possono inoltre supportare la paginazione specifica dei documenti, in modo che sono conformi ai requisiti legali. |
| Configurare la destinazione dei report ER in modo da inviare l'output come messaggi di posta elettronica e in modo da poter utilizzare dati aziendali e la logica ER (espressioni) per specificare, in fase di esecuzione, l'indirizzo di posta elettronica da utilizzare. | In precedenza, alla configurazione di una destinazione ER, l'indirizzo di posta elettronica del destinatario dell'output poteva essere definito in fase di progettazione. È ora possibile configurare un'espressione nel formato ER. Questa espressione può quindi essere selezionata in una destinazione come origine dell'indirizzo di posta elettronica per ogni configurazione di formato e ciascun componente di output (cartella o file) separatamente. Pertanto, quando un report ER è in esecuzione, ogni file generato può essere inviato per posta elettronica a un destinatario diverso e l'indirizzo di posta elettronica può essere definito in base alla logica ER e ai dati aziendali. |
| Configurare la destinazione dei report ER in modo da inviare l'output nella cartella di Microsoft SharePoint come un nuovo file denominato o nuova versione del file esistente e in modo da poter utilizzare i dati aziendali nel framework di Power BI Microsoft come un set di dati o report. | Quando si configurano i report ER, è ora possibile preparare facilmente (senza codifica) i dati aziendali necessari da poter utilizzare nel framework di Power BI. Quando si eseguono i report ER, è possibile fornire al framework di Power BI i dati aziendali e/o i report di Excel appropriati che sono già disponibili. Se si programma l'esecuzione del report in modalità ricorrente, è possibile stabilire il push programmato dei dati aziendali da Dynamics 365 for Operations a Power BI per supportare la programmazione dell'aggiornamento dei report basati su Power BI. |
| Configurare i report ER per utilizzare la parte del documento elettronico che è già stata generata come origine dati per generare il resto del documento. | È possibile configurare i report ER che creano l'output in formato testo per eseguire il conteggio delle righe documento. Queste informazioni possono quindi essere utilizzate in altre parti del documento per creare righe che includono i dettagli di riepilogo. Le informazioni di riepilogo (totali e numeri) possono essere calcolate e stampate nei documenti elettronici generati, senza richiedere trasformazioni aggiuntive dei dati. Di conseguenza, questa funzionalità migliora le prestazioni di esecuzione dei report e aiuta a semplificare la gestione futura del formato di ER configurato. |
| Configurare i report ER per specificare l'estensione del file per i documenti elettronici generati in formato testo. | È possibile configurare i report ER per creare l'output in formato testo, in modo che può essere salvato come file con una estensione specifica. Oltre all'estensione predefinita .txt, è possibile configurare estensioni quali .csv e .prn, in conformità alla specifica di formato. |
| Creare nuovi report ER basati su una versione specifica di un modello ER. | In precedenza, quando si creava un nuovo formato ER, solo la più recente versione del modello ER selezionato poteva essere utilizzata come percorso di origine dati di formato. È ora possibile selezionare qualsiasi versione disponibile del modello ER selezionato. Questa funzionalità consente di gestire i report ER per l'anno corrente e progettare una nuova versione del modello ER per l'anno successivo in parallelo. |
| Cercare le origini dati e i formati/modelli in base al testo o elemento selezionato con un clic. Risolvere proattivamente i conflitti di riassegnazione e risolvere i conflitti tra configurazioni. Configurare i report ER per creare più messaggi di convalida per gli errori che vengono rilevati fino all'interruzione dell'esecuzione del report. | Alcuni miglioramenti nell'esperienza utente nel framework ER aiutano gli utenti a utilizzare ER in modo più efficiente e semplice. |
| Mostrare l'area di lavoro **ER** nei report di Power BI. | Gli utenti possono configurare la pagina dell'**area di lavoro ER** in modo da includere le nuove voci di menu e i riquadri animati che eseguono i report basati su Power BI. |

## <a name="payroll"></a>Retribuzioni

<table>
<thead>
<tr>
<th>Operazioni che è possibile effettuare</th>
<th>Perché questo è importante</th>
</tr>
</thead>
<tbody>
<tr>
<td>Configurare i record di pagamenti ed elaborare le retribuzioni utilizzando la funzionalità che equivale a quella del modulo <strong>Retribuzioni</strong> in Microsoft Dynamics AX 2012 R3.</td>
<td>È ora possibile configurare ed elaborare le retribuzioni negli Stati Uniti utilizzando un set di funzionalità che equivale al set di funzionalità in AX 2012 R3.
<ul>
<li>È possibile configurare i cicli e periodi retributivi, cicli di lavoro e periodi di lavoro, codici di reddito e gruppi di codici di reddito, programmazioni, i tipi di congedo e i piani di accumulo benefit.</li>
<li>È inoltre possibile impostare le detrazioni obbligatorie per benefit e imposte e registrare le informazioni sulla retribuzione per le posizioni e i lavoratori per scopi di analisi e di report.</li>
<li>È inoltre possibile impostare e gestire le detrazioni per i pignoramenti e i gettiti di imposta e per tutte le commissioni amministrative correlate.</li>
</ul>
</td>
</tr>
<tr>
<td>Monitorare ed elaborare il processo dei periodi retributivi utilizzando la nuova area di lavoro <strong>Gestione retribuzioni </strong>.</td>
<td>È ora possibile monotorare facilmente l'elaborazione delle retribuzioni. A colpo d'occhio, gli amministratori delle retribuzioni possono visualizzare buste paga e rendiconti di pagamento che richiedono attenzione, in modo che il ciclo di pagamenti sia completo e accurato. L'area di lavoro <strong>Gestione retribuzioni </strong> consente agli utenti di monitorare ed eseguire i processi end-to-end da una singola area di lavoro.</td>
</tr>
<tr>
<td>Generare file di pagamenti sicuri per assegni retribuzioni.</td>
<td>È presente una nuova estensione alla funzionalità di pagamenti sicuri di Gestione cassa e banche per i pagamenti delle retribuzioni. Voci di menu separate sono state aggiunte nel processo di base per abilitare la configurazione isolata specifica della retribuzione. La funzionalità è identica alla funzionalità di pagamenti sicuri di base rilasciata in Microsoft Dynamics AX versione applicazione 7.0.1 (maggio 2016). Grazie all'estensione, i dati relativi alle retribuzioni sono completamente isolati dal resto delle transazioni di pagamenti sicuri. Questo isolamento assicura che solo gli utenti delle retribuzioni possono accedere e visualizzare i dati correlati alle retribuzioni.</td>
</tr>
<tr>
<td>Importare le righe rendiconto redditi da un'origine esterna utilizzando la nuova entità di dati Riga busta paga.</td>
<td>Una nuova entità di dati importante abilita l'integrazione con sistemi esterni di calcolo dei redditi e di tempo. L'entità di dati importa le righe busta paga ed esegue tutta la stessa logica predefinita che l'utente ha immesso direttamente nella busta paga. Dopo l'importazione, le righe vengono associate automaticamente al documento busta paga appropriato. Se un documento busta paga appropriato non è disponibile, un documento viene creato automaticamente.</td>
</tr>
</tbody>
</table>

## <a name="planning-and-scheduling"></a>Pianificazione e programmazione

| Operazioni che è possibile effettuare | Perché questo è importante |
|-----------------|-----------------------|
| Impostare le impostazioni di ordine predefinite per le vendite e gli acquisti, in base a qualsiasi dimensione prodotto attiva nella rappresentazione generale prodotto. Di conseguenza, è possibile definire le impostazioni di ordine predefinite per l'unità di stockkeeping (SKU) o una unità SKU parziale. | È possibile specificare impostazioni di ordine predefinite applicabili a una dimensione prodotto o a una combinazione di dimensioni prodotto.<p>**Esempio**</p><p>Vendete un prodotto denominato Polo T-shirt. Questo prodotto è disponibile in due colori: Verde e blu. È inoltre disponibile in due taglie: Small e Medium. Il colore e la taglia sono dimensioni prodotto attive per Polo T-shirt. È possibile bloccare gli acquisti di tutte le Polo T-shirt di colore verde, indipendentemente dalla taglia.</p> |

## <a name="product-master-data"></a>Dati di rappresentazione generale prodotto

<table>
<thead>
<tr>
<th>Operazioni che è possibile effettuare</th>
<th>Perché questo è importante</th>
</tr>
</thead>
<tbody>
<tr>
<td>Impostare tutte le impostazioni di ordine predefinite e le impostazioni di ordine specifiche del sito contemporaneamente, da un'unica pagina.</td>
<td>Questa funzionalità offre una panoramica più dettagliata delle impostazioni articolo.</td>
</tr>
<tr>
<td>Creare una nomenclatura per i numeri di variante prodotto.</td>
<td>È possibile includere elementi come dimensioni prodotto, attributi e caratteri nei numeri di variante prodotto. Quando si crea un ordine cliente o un ordine fornitore, è possibile trovare rapidamente la variante prodotto specifica.</td>
</tr>
<tr>
<td>Cercare prodotti e varianti prodotto in scenari di vendite e acquisti.</td>
<td>Quando si crea una riga vendita o una riga acquisto, è possibile eseguire la ricerca di prodotti utilizzando le dimensioni prodotto e tutti i numeri prodotto ad eccezione dei numeri GTIN (Global Trade Identification Number) e dei codici a barre. La ricerca è una ricerca full-text che sostituisce la ricerca "inizia con" utilizzata nell'elenco di ricerca di vendite e acquisto. Questa funzionalità consente di individuare i gruppi di prodotti con le proprietà simili o un unico prodotto con caratteristiche univoche. Per abilitare questa funzionalità, selezionare il parametro <strong>Abilita ricerca prodotto</strong> nella pagina <strong>Parametri ricerca</strong>.</td>
</tr>
<tr>
<td>Specificare direttamente la variante prodotto durante la creazione di una transazione di vendita o acquisto. In alternativa, è possibile selezionare in un elenco di combinazioni valide di dimensioni.</td>
<td>Questa funzionalità è un miglioramento di produttività.
<p><strong>Esempio</strong></p>
<p>Vendete un prodotto denominato Polo T-shirt. Questo prodotto è disponibile in due colori: Verde e blu. È inoltre disponibile in due taglie: Small e Medium. Il colore e la taglia sono dimensioni prodotto attive per Polo T-shirt. Quando si immette una riga di vendita per Polo T-shirt di colore Verde e taglia Small, non è necessario immettere i dati nei campi <strong>Numero articolo</strong>, <strong>Colore</strong> e <strong>Dimensione</strong>. È possibile creare la riga seguendo uno di questi passaggi:</p>
<ul>
<li>Nel campo <strong>Numero articolo</strong>, immettere il numero di varianti prodotto, il valore di un colore o la taglia. Nella ricerca, trovare la variante specifica che si desidera vendere e creare la riga di vendita.</li>
<li>Nel campo <strong>Numero articolo</strong> immettere il numero articolo. Passare a qualsiasi campo di dimensione prodotto. Nella ricerca <strong>Dimensione prodotto</strong>, vedrete tutte le combinazioni di dimensioni rilasciate applicabili a Polo T-shirt. In un solo passaggio, è possibile selezionare la variante prodotto che si desidera vendere.</li>
</ul>
</td>
</tr>
<tr>
<td>Specificare se i numeri prodotto appaiono nelle pagine transazionali.</td>
<td>Le pagine transazionali, ad esempio ordini cliente e fornitore, vengono visualizzate solo  nei campi <strong>Numero articolo</strong> e <strong>Nome prodotto</strong>. Per visualizzare il campo <strong>Numero prodotto</strong>, selezionare il parametro <strong>Mostra numeri di prodotto nei moduli</strong> in <strong>Parametri di gestione informazioni sul prodotto</strong>.</td>
</tr>
</tbody>
</table>

## <a name="project-management-and-accounting"></a>Gestione progetti e contabilità

| Operazioni che è possibile effettuare | Perché questo è importante |
|-----------------|-----------------------|
| Utilizzare la selezione recente quando si registrano le proposte di fatturazione in un batch. | I contabili di progetto possono impostare un processo batch per selezionare automaticamente le proposte di fatturazione da registrare, se le proposte soddisfano i criteri specificati nel processo batch. Questa funzionalità consente di migliorare l'automazione della registrazione fatture, poiché il processo batch può essere eseguito in modo continuativo e selezionare automaticamente le proposte per la registrazione. |
| Creare l'analisi nel desktop di Power BI. | Il contenuto di business intelligence (BI) dei dati correlati al progetto e alle risorse può essere creato facilmente sul desktop di Power BI. |
| Utilizzare i pagamenti anticipati dell'ordine fornitore e includerli correttamente nel processo di stima del progetto. | Per gli ordini fornitore del progetto, i pagamenti anticipati devono essere elaborati prima che un pagamento può essere rilasciato ai fornitori. Queste fatture di pagamento anticipato ora sono visualizzate nel processo di stima/riconoscimento dei progetti di tipo **Prezzo fisso**. |
| Accedere e gestire le stime dei ricavi e di costi e le richieste articolo, direttamente da un'attività di struttura di suddivisione del lavoro (WBS). | È possibile gestire le stime dei costi, stime dei ricavi e delle richieste articolo per un'attività WBS specifica nella finestra di dialogo relativa ai dettagli per l'attività in questione nella visualizzazione di pianificazione WBS. |
| Selezionare una fonte di finanziamento sui giornali di registrazione commissioni. | Se il contratto per un progetto contiene più fonti di finanziamento, è possibile selezionare una fonte di finanziamento specifica quando le commissioni vengono registrate. Se non si seleziona una fonte di finanziamento specifica, le regole di finanziamento specificate nel contratto vengono utilizzate per assegnare la commissione. |
| Aprire i rendiconti di progetto in Excel. | Nuove entità di dati per gli aggiornamenti contabili e gli aggiornamenti budget consentono di aprire i dati dei rendiconti di progetto in Excel e creare l'analisi dei dati utilizzando le funzionalità di Excel. |
| Utilizzare solo una chiave di configurazione per abilitare la funzionalità per Gestione progetti e contabilità. | Le chiavi di configurazione correlate al progetto sono state sostituite da una unica chiave di configurazione progetto che abilita la funzionalità Gestione progetti e contabilità. |

## <a name="retail-and-commerce"></a>Vendita al dettaglio e commercio

### <a name="advanced-warehouse-management-in-a-retail-store"></a>Gestione magazzino avanzata in un punto vendita al dettaglio

I rivenditori possono utilizzare la soluzione avanzata di gestione magazzino nei propri punti vendita e fare gli aggiornamenti necessari alle funzionalità POS correnti per supportarla. I processi della soluzione portatile devono funzionare in un punto come in qualsiasi altro magazzino. Tutti i processi Retail Store Inventory e i processi POS che creano o aggiornano le operazioni di magazzino vengono aggiornati in modo che utilizzino i requisiti specifici dei magazzini abilitati per la gestione.

| Operazioni che è possibile effettuare | Perché questo è importante |
|-----------------|-----------------------|
| Utilizzare il POS per cercare le scorte disponibili nei punti vendita abilitati per la gestione magazzino. | Durante la ricerca delle scorte, il processo deve funzionare come in precedenza. La ricerca deve visualizzare le quantità disponibili a livello di magazzino e non deve considerare e dimensioni Ubicazione, Stato inventario o Targa. |
| Utilizzare il POS per elaborare un'entrata prodotti per un ordine di trasferimento in un punto vendita abilitato per la gestione magazzino. | È possibile ricevere ordini di trasferimento nel POS per un punto vendita e articoli abilitati per la gestione magazzino. L'utente deve poter selezionare le ubicazioni in cui ricevere in e deve poter immettere gli ID targa per popolare automaticamente le righe di ricevimento. |
| Utilizzare il POS per elaborare un'entrata prodotti per un ordine fornitore in un punto vendita abilitato per la gestione magazzino. | È possibile ricevere ordini fornitore nel POS per un punto vendita e articoli abilitati per la gestione magazzino. L'utente deve poter selezionare le ubicazioni in cui ricevere in e deve poter immettere gli ID targa per popolare automaticamente le righe di ricevimento. |
| Utilizzare il POS per elaborare una spedizione di prodotti da un punto vendita abilitato per la gestione magazzino. | È possibile registrare trasferimenti dal POS per un punto vendita e articoli abilitati per la gestione magazzino. L'utente deve poter selezionare le ubicazioni di origine della spedizione, lo stato dell'inventario deve essere generato automaticamente e le targhe devono essere ignorate. |

### <a name="enable-seamless-omni-channel-commerce"></a>Abilitare il commercio integrato su più canali

Il commercio integrato su più canali si riferisce alla gestione e l'elaborazione degli ordini in negozi fisici, punti vendita online, servizio clienti e commercio mobile. Per questa versione, gli investimenti seguenti sono stati effettuati in quest'area:

- Miglioramenti alla pubblicazione per i punti vendita di e-commerce
- Una nuova app per dispositivi mobili destinata ai consumatori che consente di individuare i prodotti, gestire l'account e acquistare online

| Operazioni che è possibile effettuare | Perché questo è importante |
|-----------------|-----------------------|
| Consumatore: La versione corrente dell'app per consumatori include le seguenti funzionalità: ricerca di prodotti, esplorazione delle categorie, aggiunta al carrello e check out come guest. I rivenditori possono anche applicare il proprio marchio all'app e quindi pacchettizzarla per i punti vendita app iOS e Android. | I rivenditori possono creare facilmente un'app destinata ai consumatori che consente di sfogliare, cercare prodotti e spedire prodotti come guest dai propri dispositivi mobili. |
| Elenchi di preferenze di clienti per punti vendita online c-commerce | I fornitori di software indipendenti (ISV) possono utilizzare il controllo degli elenchi di preferenze per consentire agli utenti di creare e gestire più elenchi nel proprio punto vendita online e visualizzare/utilizzare tali elenchi nel POS. |
| Creazione asincrona di clienti tramite punti vendita online e-commerce | Gli ISV ora possono creare account cliente anche quando Commerce Data Exchange: Real-time Service non è disponibile. |
| Pubblicare prodotti di canale dal server Retail a punti vendita di terzi. | Il server Retail ora supporta l'autenticazione da servizio a servizio. Gli ISV possono usufruire della pubblicazione dei prodotti di canale dal server Retail ai punti vendita di terzi. |

### <a name="extensibility"></a>Estendibilità

- I progetti runtime di Commerce sono ora separati da Retail SDK.
- Distribuzione e assistenza più semplici mediante i pacchetti di componenti Microsoft e pacchetti ISV per stazioni POS, server Retail, database, pagamento e hardware.

| Operazioni che è possibile effettuare | Perché questo è importante |
|-----------------|-----------------------|
| CRT/Retail Server: I rivenditori o ISV possono estendere CRT tramite hook di estensione. Le modifiche di codice inline non verranno più supportate. | Per abilitare l'integrazione continua e la distribuzione continua, le modifiche di codice inline devono essere completamente evitate. Inoltre, per supportare la facile adozione di hotfix senza alcuna unione e distribuzione di codice per i componenti CRT. |

### <a name="personalized-product-recommendations"></a>Suggerimenti sul prodotto personalizzati

| Operazioni che è possibile effettuare | Perché questo è importante |
|-----------------|-----------------------|
| Consente di visualizzare i suggerimenti personali del prodotto in più touchpoint sul POS (POS) per determinare a cosa potrebbe essere interessato un cliente in base allo storico acquisti, gli articoli nell'elenco delle preferenze e gli articoli che altri clienti hanno acquistato online e nei negozi | Per i rivenditori con cataloghi di grandi dimensioni, i suggerimenti personali aiutano il cliente a individuare i prodotti e consentono alle filiali di gestire i clienti in modo intelligente. Mostrando i prodotti in base agli interessi e alle abitudini di acquisto di un cliente, i suggerimenti sul prodotto possono aiutare i rivenditori nell'upselling e possono aumentare la fidelizzazione dei clienti. In Retail i suggerimenti sul prodotto sono generati da servizi cognitivi e da Microsoft Azure Machine Learning. |

### <a name="pos-task-recorder"></a>Registrazione attività POS

| Operazioni che è possibile effettuare | Perché questo è importante |
|-----------------|-----------------------|
| I rivenditori possono utilizzare la funzione Registrazione attività POS per produrre il materiale di formazione, diagrammi BPM (Modellatore di processi aziendali) e generare il contenuto della Guida per migliorare la produttività e l'analisi e la progettazione delle applicazioni. | Per abilitare l'integrazione continua e la distribuzione continua, le modifiche inline devono essere completamente evitate. Inoltre, per supportare la facile adozione di hotfix senza alcuna unione e distribuzione di codice per i componenti CRT. |
| Guida in tempo reale in POS. | Il cassiere o un responsabile può ottenere Guida in tempo reale dal POS sul processo aziendale senza cambiare contesto. |

### <a name="store-system-providing-a-seamless-on-premises-store-experience"></a>Sistema punto vendita: Fornitura di un'esperienza integrata di punto vendita locale

Sistema punto vendita è una scelta di distribuzione per i rivenditori che favorisce la gestione di una serie di operazioni del punto vendita, che sia un punto vendita locale, il cloud pubblico Microsoft, o il cloud privato del cliente. In questa versione, l'ambito è solo interno al punto vendita. Per supportare meglio gli ambienti con connettività di rete lenta e inaffidabile, dobbiamo fornire un'opzione per i rivenditori per distribuire il database di canale e il server Retail nel punto vendita. Possono quindi continuare l'esecuzione dei principali scenari dell'attività anche quando non è presenta la connettività con la sede centrale. In base a diversi punti dati, incluse discussioni del team di progettazione, risultati dei sondaggi dei clienti e l'analisi della concorrenza, abbiamo identificato il seguente ambito della soluzione come il più adeguato per i clienti Microsoft destinatari:

- Un pacchetto self-service è disponibile per il sistema punto vendita.
- L'impostazione predefinita è una distribuzione unica ma la distribuzione personalizzata è consentita.
- Abilitare semplice distribuzione/self-service.
- Il server Retail e il database del punto vendita sono nel punto vendita, insieme al servizio Async Client.
- Il server Retail nel punto vendita comunica direttamente con il server oggetti applicativi (AOS) nella sede centrale per il sistema punto vendita.
- Supportare scenari tra terminale dove non è presente connettività con la sede centrale.
- Retail Modern POS e POS cloud comunicano sempre con il server Retail nel punto vendita.
- Supportare Retail Modern POS e POS cloud dove non c'è connettività con la sede centrale.
- Supportare un database offline specifico per Retail Modern POS (isolato in ciascuna istanza di Retail Modern POS) in cui non c'è la connettività con la sede centrale.
- L'autenticazione è da servizio a servizio solo per il sistema punto vendita.
- Le chiamate Real-time Service non sono supportate se non è presente alcuna connettività a Internet.
- La connettività di database diretta di Retail Modern POS al database di canale non è supportata.
- Abilitare telemetria/monitoraggio.

| Operazioni che è possibile effettuare | Perché questo è importante |
|-----------------|-----------------------|
| Un rivenditore scarica il programma di installazione self-service del sistema punto vendita dalla pagina del database di canale nella sede centrale di Dynamics AX e scarica il file di configurazione. | Il rivenditore può semplicemente scaricare il pacchetto self-service. |
| Un rivenditore installa il sistema punto vendita tramite il programma di installazione self-service. | Il rivenditore può installare il sistema punto vendita tramite il pacchetto self-service. |
| Il responsabile IT configura il sistema punto vendita in Dynamics 365 for Operations (database di canale, profilo del canale, punto vendita e pacchetto distribuibile). | Il responsabile IT può configurare in modo semplice ed efficiente il sistema punto vendita. |
| Un rivenditore utilizza Retail Modern POS nel punto vendita locale e può effettuare operazioni in tempo reale, ad esempio emettere gift card, quando è presente la connettività. | Il rivenditore può eseguire le azioni in tempo reale dal sistema punto vendita in caso di connettività. |
| Un rivenditore può sincronizzare i dati dal sistema punto vendita locale alla sede centrale ogni volta che c'è la connettività. | Il rivenditore può eseguire la sincronizzazione verso e dal sistema punto vendita in caso di connettività. |
| Un rivenditore può avere comunicazione protetta tra il sistema punto vendita locale e la sede centrale. | Il rivenditore può comunicare dal sistema punto vendita in modo sicuro in caso di connettività. |
| Il responsabile IT e Microsoft Operations possono monitorare e creare report sul sistema punto vendita locale (diagnostica e segnalazione di modifiche). | Il responsabile IT e Microsoft Operations possono monitorare il sistema punto vendita in modo sicuro e risolvere i problemi con efficienza. |

### <a name="universal-windows-platform-app-for-retail-modern-pos"></a>App della piattaforma UWP (Universal Windows Platform) per Retail Modern POS

Attualmente, Retail Modern POS è disponibile solo come applicazione di Windows 8.1 per computer desktop e tablet e come POS cloud per browser di desktop o tablet. In questa versione, Retail Moderns POS viene convertito in app della piattaforma UWP (Universal Windows Platform). In questo modo sarà possibile eseguire Retail Modern POS su qualsiasi dispositivo Windows 10 (desktop, tablet o telefono) e alternare le visualizzazioni per i dispositivi abilitati per Continuum.

| Operazioni che è possibile effettuare | Perché questo è importante |
|-----------------|-----------------------|
| Abilitare importanti funzionalità POS per dispositivi a piccolo fattore di forma. | La funzionalità di Retail POS è disponibile per i telefoni e altri dispositivi a piccolo fattore di forma che eseguono Windows 10. |

## <a name="supply-chain-management"></a>Gestione della supply chain

### <a name="consignment-inventory"></a>Inventario spedizione

| Operazioni che è possibile effettuare | Perché questo è importante |
|-----------------|-----------------------|
| Come fornitore, è possibile immagazzinare le materie prime nel magazzino del cliente. Come cliente, è possibile posticipare l'acquisto effettivo finché le materie prime non sono richieste per la produzione. | Mantenere un inventario delle materie prime può implicare costi elevati. Utilizzando l'inventario spedizione, un fornitore può immagazzinare le materie prime nel magazzino del cliente. Il cliente può quindi posticipare l'acquisto effettivo finché le materie prime non sono richieste per la produzione. Le materie prime vengono ordinate e ricevute tramite un ordine di rifornimento spedizione. L'ordine di rifornimento registra le transazioni fisiche ma non influisce sulla contabilità generale. Per distinguere tra gli articoli di magazzino di proprietà del cliente e gli articoli di magazzino di proprietà del fornitore, è possibile utilizzare la dimensione inventariale Proprietario. Il trasferimento di proprietà dell'inventario viene gestito da un processo di giornale di registrazione che gestisce il passaggio di proprietà per le materie prime dell'inventario di proprietà del fornitore all'inventario di proprietà del cliente. Questo processo attiva la creazione di un ordine fornitore e di un'entrata prodotti.<blockquote>[!NOTE] Questa funzionalità è limitata alla spedizione in entrata delle materie prime per la produzione. Non è integrata con la gestione magazzino e la gestione trasporto.</blockquote> |
| Come fornitore, ottenere le informazioni sull'importo di inventario spedito trasferito al cliente. | Per fatturare a un cliente, il fornitore richiede informazioni sulle materie prime acquistate dall'inventario spedizione e la data di acquisto. Il fornitore può inoltre monitorare le scorte disponibili presso il sito di un cliente utilizzando l'interfaccia di collaborazione fornitore. |
| Spostare l'inventario di proprietà del fornitore utilizzando un giornale di registrazione trasferimenti. | Per tenere traccia dell'ubicazione fisica dell'inventario di proprietà del fornitore, è necessario poter registrare l'ubicazione nel sistema. Tramite l'utilizzo di un giornale di registrazione trasferimenti, è possibile registrare lo spostamento fisico delle scorte, ad esempio movimenti da un'ubicazione in un magazzino in un'altra ubicazione nel magazzino. |
| Rettificare l'inventario di proprietà del fornitore utilizzando un giornale di registrazione di conteggio. | È importante mantenere le scorte disponibili nel sistema sincronizzate con l'inventario fisico effettivo. L'inventario di proprietà del fornitore può essere rettificato in entrata e in uscita tramite processi di conteggio quali la correzione della quantità e processi di giornale di registrazione di conteggio. |
| Scoprire ulteriori informazioni sul supporto di spedizione in Dynamics 365 for Operations | Per ulteriori informazioni sul supporto per i processi di spedizione, vedere [Spedizione](../../../supply-chain/inventory/consignment.md), [Impostazione della spedizione](../../../supply-chain/inventory/set-up-consignment.md), [Creare un ordine di rifornimento spedizione (guida attività)](../../../supply-chain/inventory/tasks/create-consignment-replenishment-order.md) e [Modificare la proprietà dell'inventario di spedizione in base alla domanda di produzione (guida attività)](../../../supply-chain/inventory/tasks/change-ownership-consignment.md). |

### <a name="vendor-collaboration-previously-known-as-the-vendor-portal"></a>Collaborazione fornitore (in precedenza noto anche come Portale fornitori)

| Operazioni che è possibile effettuare | Perché questo è importante |
|-----------------|-----------------------|
| Abilitare i fornitori a rispondere a ogni riga di ordine fornitore e suggerire modifiche. | In alcuni casi, i fornitori desiderano accettare alcune righe dell'ordine ma rifiutarne altre. I fornitori possono ora gestire singole righe di ordine fornitore. Ogni riga può essere rifiutata, accettata, oppure accettata con modifiche. Ad esempio, i fornitori potranno modificare la data di consegna, dividere la consegna e la quantità, o suggerire un articolo alternativo. |
| Abilitare i fornitori a gestire le informazioni di contatto. | I fornitori possono gestire le informazioni di contatto per la propria società. Tali informazioni includono i nomi, indirizzi di posta elettronica e numeri di telefono. L'accesso alla funzionalità viene assegnato tramite un ruolo di sicurezza dedicato. |
| Condividere documenti correlati agli ordini fornitore con i fornitori. | Quando è necessario condividere un documento con un fornitore, ad esempio un documento sui fabbisogni, risulta utile collegare il documento nell'ordine fornitore pertinente. Il fornitore può quindi condividere le note e gli allegati con il cliente collegando il documento alla relativa risposta all'ordine fornitore. Gestione documenti è il framework di supporto sottostante e solo note e allegati e che vengono classificati come "esterni" possono essere condivisi con i fornitori. |
| Eseguire il provisioning di nuovi utenti fornitore. | Se i fornitori utilizzano l'interfaccia di collaborazione fornitore, hanno un modo integrato per richiedere i nuovi account utente quando nuovi contatti richiedono l'accesso alla collaborazione fornitore. I professionisti dell'approvvigionamento possono inviare una richiesta per un account utente per un contatto presso l'organizzazione del fornitore. Anche un contatto del fornitore che è già un utente di collaborazione fornitore potrà inviare questo tipo di richiesta. Questa richiesta crea infine un nuovo utente in Dynamics 365 for Operations con ruoli di sicurezza specifici per il fornitore. Facilita inoltre una richiesta nel portale B2B di Microsoft Azure per il provisioning all'utente di un nuovo account utente Azure Active Directory (Azure AD). I fornitori possono inoltre richiedere che specifici account utente fornitore siano disattivati, o che i ruoli di sicurezza vengano modificati. |
| Scoprire ulteriori informazioni sulla collaborazione fornitore in Dynamics 365 for Operations. | Per ulteriori informazioni sulla collaborazione fornitore, vedere [Collaborazione fornitore con i fornitori esterni](../../../supply-chain/procurement/vendor-collaboration-work-external-vendors.md), [Collaborazione fornitore con i clienti](../../../supply-chain/procurement/vendor-collaboration-work-customers-dynamics-365-operations.md), [Gestire utenti di collaborazione fornitore](../../../supply-chain/procurement/manage-vendor-collaboration-users.md), [Impostare e gestire la collaborazione fornitore](../../../supply-chain/procurement/set-up-maintain-vendor-collaboration.md) e [Area di lavoro fatturazione di collaborazione fornitore](../../../finance/accounts-payable/vendor-portal-invoicing-workspace.md). |

### <a name="intercompany-order-processing"></a>Elaborazione di ordini interaziendali

<table>
<thead>
<tr>
<th>Operazioni che è possibile effettuare</th>
<th>Perché questo è importante</th>
</tr>
</thead>
<tbody>
<tr>
<td>Definire, direttamente nelle righe di ordine cliente, l'origine della domanda e come deve essere approvvigionata.
<p><strong>Esempio</strong></p>
<p>Creare una riga ordine cliente e specificare la consegna diretta come tipo di consegna. Il fornitore principale viene aggiunto alla riga di ordine cliente come punto di approvvigionamento.</p>
</td>
<td>Il flusso per la ricezione degli ordini è stato migliorato in modo significativo. È ora possibile definire, direttamente nelle righe di ordine cliente, l'origine della domanda e come deve essere approvvigionata. Più non è necessario attendere fino ad avere aggiunto tutte le righe all'ordine cliente. Nuove opzioni sulle righe ordine cliente consentono di specificare il tipo di consegna quando si specifica un fornitore. Quando si associa un fornitore con le righe ordine cliente, catene di ordini vengono create per la consegna dal fornitore.
<ul>
<li>Il fornitore può essere un fornitore interaziendale che usa un ordine fornitore e un ordine cliente interni oppure un fornitore esterno che utilizza un ordine fornitore esterno.</li>
<li>Il tipo di consegna può essere <strong>Consegna diretta</strong> o <strong>Scorte</strong>. Il tipo di consegna <strong>Scorte</strong> indica che il fornitore deve fornire al magazzino locale prima di spedire al cliente.</li>
</ul>
</td>
</tr>
<tr>
<td>Creare una promessa di ordine direttamente dalle righe di ordine cliente.
<p><strong>Esempio</strong></p>
<p>Creare una riga ordine cliente approvvigionata da un fornitore interaziendale. Lasciare la riga. Le date di consegna vengono calcolate in base alla disponibilità nella società di approvvigionamento.</p>
</td>
<td>Quando si creano righe ordine cliente che utilizzano le nuove informazioni di approvvigionamento, le date di consegna vengono calcolate in base al controllo <strong>Data di consegna</strong>. Ad esempio, se un fornitore interaziendale è selezionato, la disponibilità della società di approvvigionamento viene calcolata. In questo modo, le catene di ordini vengono create automaticamente insieme alle righe ordine cliente. Questa funzionalità assicura che le date di consegna diventino visibili nella società di approvvigionamento, in modo che i profili available-to-promise (ATP) possano gestire le richieste anticipate direttamente man mano che gli ordini cliente vengono creati.</td>
</tr>
<tr>
<td>Verificare la disponibilità di prodotto in tutte le ubicazioni di approvvigionamento e selezionare la migliore opzione di approvvigionamento.</td>
<td>La pagina <strong>Alternative di consegna</strong> è stata riprogettata e ora vengono fornite informazioni preziose su tutti i fornitori interni ed esterni approvati. Tali informazioni includono le opzioni di approvvigionamento per l'approvvigionamento dal fornitore. Quando si seleziona una modalità di consegna, il sistema calcolerà le date di consegna supportate. È possibile selezionare semplicemente la migliore opzione per il cliente e applicare questa opzione a ciascuna riga di ordine cliente.</td>
</tr>
</tbody>
</table>

### <a name="warehouse-enhancements-for-high-volume-distribution-centers"></a>Miglioramenti di magazzino per i centri di distribuzione con volumi elevati

| Operazioni che è possibile effettuare | Perché questo è importante |
|-----------------|-----------------------|
| Creare lavoro dopo che le merci sono state imballate a una stazione d'imballaggio. | Questa funzionalità è utile se esistono processi aggiuntivi dopo operazioni manuali di imballaggio (ad esempio, pallettizzazione, controllo qualità, consolidamento delle spedizioni, o modifiche alle banchine di carico). Il nuovo tipo di lavoro **Prelievo contenitore imballato** consente di modellare queste attività utilizzando le righe separate di lavoro. È ora possibile modellare le stazioni d'imballaggio per generare il lavoro dopo l'imballaggio. Questo lavoro può essere utilizzato per organizzare i movimenti delle scorte imballate. |
| Raggruppare contenitori alla stazione di imballaggio. | Questa funzionalità consente ai più colli di essere raggruppati in un contenitore o targa alla stazione d'imballaggio. Ad esempio, un operatore di e-commere/all'ingrosso può raggruppare 100 pacchi imballati singolarmente in un unico contenitore (ad esempio un pallet o una gabbia). Il contenitore può quindi essere spostato, approntato o caricato tramite una singola istruzione di lavoro che un lavoratore genera tramite la scansione di un singolo codice a barre (targa) per il contenitore raggruppato. Questa funzionalità riduce al minimo le transazioni di lavoro per spostare molti più piccoli contenitori imballati. Per altre informazioni, vedere [Creare una voce di menu del dispositivo mobile per il consolidamento delle targhe (Guida attività)](../../../supply-chain/warehousing/tasks/create-mobile-device-license-plate-consolidation.md). |
| Creare criteri di rilascio per i contenitori imballati. | Lavoro che viene attivato dal rilascio dei contenitori può essere creato automaticamente o manualmente. Quando è automatico, il lavoro viene generato alla chiusura del contenitore utilizzando la direttiva ubicazione e il framework del modello di lavoro. Se il rilascio è manuale, l'imballatore può decidere se il lavoro dovrà essere generato per un singolo contenitore o per un gruppo di contenitori. Questa funzionalità consente di ridurre il rischio che contenitori chiusi verranno prelevati e spostati prima che siano pronti per essere spostati dalla stazione d'imballaggio. Consente anche il rilascio raggruppato non guidato dal sistema. |
| Riallocazione del prelievo breve | Il supporto è stato aggiunto per i processi di prelievo breve, per aiutare un associato che non può prelevare le merci e vuole evadere l'ordine quando l'articolo richiesto è disponibile in un'altra ubicazione. È possibile utilizzare un processo di riallocazione automatica, in cui vengono utilizzate le stesse direttive ubicazione per recuperare le merci se sono disponibili in un'altra ubicazione. In alternativa, quando viene usata la riallocazione manuale, il dispositivo mobile mostra un elenco di ubicazioni con la quantità disponibile. L'addetto al magazzino può quindi selezionare da quale ubicazione utilizzare le scorte. Questi due metodi possono essere impostati singolarmente o combinati come singolo comando nel menu dell'addetto al magazzino. Quando si usa la riallocazione manuale, l'addetto al magazzino può selezionare la quantità dell'articolo per prelievo breve da diverse ubicazioni. Per ulteriori informazioni, vedere [Impostare la riallocazione articolo per prelievo breve (guida attività)](../../../supply-chain/warehousing/tasks/set-up-short-picking-item-reallocation.md). |
| Spostare scorte a cui è associato lavoro. | È ora possibile spostare scorte a cui è associato lavoro. Questa funzionalità può risultare utile se, ad esempio, un lavoratore desidera liberare un certo spazio banchina di entrata e spostare i pallet registrati in attesa di essere stoccati in un'altra ubicazione in entrata. La banchina viene liberata e può ricevere un carico aggiuntiva di merci e le scorte spostate vengono aggiornate con le nuove informazioni di stoccaggio. Questa funzionalità è utilizzabile anche per liberare spazio alle ubicazioni di prelievo spostando le scorte con lavoro associato e creando lo spazio per il rifornimento. È inoltre possibile utilizzarla per spostare i carichi da una ubicazione di gestione temporanea all'altra senza perdere il lavoro di carico generato. In questo modo, la funzionalità può ottimizzare il tempo necessario a caricare i camion quando arrivano. È possibile spostare le scorte prenotate per ordini cliente, uscite di ordini di trasferimento, entrate di ordini di trasferimento e gli ordini fornitore. Lo spostamento verrà impedito se comporterà la divisione di righe. Ad esempio, se si dispone di una riga di lavoro per 100 pezzi di un articolo, non è possibile spostare solo 30 pezzi di tale articolo in un'altra ubicazione. |
| Unire targhe a cui è associato lavoro. | È possibile unire targhe a cui è associato lavoro in uscita. Ad esempio, quando un prelievo è stato suddiviso in diverse parti di lavoro, può essere utile consentire l'unione delle targhe dopo la consegna all'ubicazione di gestione temporanea. Le targhe possono essere consolidate solo se sono nello stessa ubicazione, sono membri dello stesso carico e con le stesse informazioni di spedizione. |
| Bloccare lavoro di prelievo associato al rifornimento a livello di riga. | È ora possibile bloccare il lavoro a livello di riga anziché a livello di intestazione, in modo che i lavoratori possono evadere le righe di prelievo non bloccate dal rifornimento della domanda. Di conseguenza, un venditore all'ingrosso con ordini cliente grandi o un rivenditore al dettaglio con ordini cliente o ordini di trasferimento rifornimento grandi può consentire di iniziare il lavoro di prelievo su tutte le righe non soggette al lavoro di rifornimento. Il lavoro di prelievo e di rifornimento può quindi essere completato in parallelo. Questa funzionalità può essere configurata in modo da poter selezionare bloccare a livello di intestazione o a livello di riga. È anche possibile utilizzare entrambi i metodi e creare un modello di lavoro per ogni metodo. La configurazione intestazione/riga viene impostata sui modelli di lavoro, ma è possibile modificarla direttamente nel lavoro generato. |
| Annullare lavoro utilizzando il dispositivo mobile. | È ora possibile annullare il lavoro utilizzando il dispositivo mobile, con o senza rifornimento della domanda. In precedenza, era necessario utilizzare il rich client. Per abilitare questa funzionalità, creare una voce di menu del dispositivo mobile in cui impostare la modalità su **Indiretto** e il codice attività su **Annulla lavoro**. |

### <a name="warehouse-operation-enhancements"></a>Miglioramenti alle operazioni di magazzino

| Operazioni che è possibile effettuare | Perché questo è importante |
|-----------------|-----------------------|
| Modellare diversi tipi di contenitore. | È possibile utilizzare diversi tipi di contenitore nel magazzino per ottimizzare l'immagazzinamento e per altri motivi. La nuova entità Tipo di contenitore presenta le caratteristiche fisiche dei tipi di contenitore. È ora possibile associare le targhe a un tipo specifico di contenitore e utilizzare i limiti di stoccaggio di ubicazione. Ad esempio, è possibile utilizzare questa funzionalità per controllare il numero di pallet (o altri tipi di contenitore) consentiti in una determinata ubicazione. I tipi di contenitore anche sono stati aggiunti a gruppi di sequenze unità per aggiungere tipi di contenitore predefiniti per il processo di ricevimento. I tipi di contenitore possono essere utilizzati insieme alle direttive ubicazione in entrata e in uscita. Possono inoltre essere utilizzati nella visualizzazione delle scorte disponibili per determinare quanti tipi di contenitore sono attualmente disponibili in magazzino. Per ulteriori informazioni, vedere il post di blog [Utilizzo di targhe associato a un tipo di contenitore per guidare i processi di gestione magazzino](https://blogs.msdn.microsoft.com/dynamicsaxscm/2016/06/20/use-of-license-plates-associated-with-a-container-type-to-drive-warehouse-management-processes/). Sebbene questo post di blog descriva un aggiornamento a Microsoft Dynamics AX 2012, lo stesso supporto è stato ora aggiunto a Dynamics 365 for Operations. |
| Stornare le spedizioni. | In un magazzino, è necessario poter gestire le modifiche dell'ultimo minuto. Ad esempio, alcune merci potrebbero essere danneggiate, in modo che non sia possibile spedirle. In alternativa, un cliente può effettuare una richiesta tardiva di annullamento o modifica di un ordine. Dynamics 365 for Operations ora consente di stornare una spedizione. Di conseguenza, è possibile annullare un documento di trasporto in modo che sia possibile aggiornarlo successivamente con le quantità corrette. Analogamente, sul flusso di entrata, è possibile annullare le entrate prodotti in modo da poter creare una versione aggiornata. |
| Utilizzare i pallet con articoli combinati. | È ora possibile ricevere e registrare un pallet "combinato". Un pallet combinato consiste di articoli diversi che sono assemblati in un unico pallet per uno o più ordini fornitore o righe. Tutte le registrazioni possono essere riepilogate in una sola targa di destinazione. Questo processo è abilitato tramite il dispositivo mobile del magazzino. Ad esempio, quando il pallet degli articoli combinati arriva presso il magazzino, l'addetto ricevente identifica gli articoli e le quantità sul pallet prima che il pallet verrà spostato nelle ubicazioni di stoccaggio dedicate. Le ubicazioni di stoccaggio vengono identificate da modelli di lavoro e direttive ubicazione. Se le ubicazioni di stoccaggio sono distribuite su diversi articoli con ubicazioni fisse, questa funzionalità crea il numero di righe di lavoro di stoccaggio corrispondente al numero di articoli differenti sul pallet combinato. Questa funzionalità rende la registrazione e lo stoccaggio dei pallet di articoli combinati ricevuti più rapidi e più flessibili. Per ulteriori informazioni, vedere il post di blog [Ricevere e registrare un pallet con le righe del documento di origine miste utilizzando una targa](https://blogs.msdn.microsoft.com/dynamicsaxscm/2016/05/13/receive-and-register-a-pallet-with-mixed-source-document-lines-using-1-license-plate-purchase-order-matching/) e le informazioni sul supporto di pallet combinati nell'[annuncio del recente aggiornamento cumulativo Microsoft](https://blogs.msdn.microsoft.com/dynamicsaxscm/2016/06/30/whats-new-in-cu11-for-wms-and-tms/). Sebbene questo post di blog descriva un aggiornamento a AX 2012, lo stesso supporto è stato ora aggiunto a Dynamics 365 for Operations. |

### <a name="minor-feature-enhancements-in-supply-chain-management"></a>Miglioramenti a funzionalità secondarie nella gestione della supply chain

<table>
<thead>
<tr>
<th>Operazioni che è possibile effettuare</th>
<th>Perché questo è importante</th>
</tr>
</thead>
<tbody>
<tr>
<td>Utilizzare nuove entità di dati per importare ed esportare i dati.</td>
<td>È possibile importare ed esportare i dati utilizzando queste entità di dati:
<ul>
<li>Fattura di trasporto</li>
<li>Aggrega scorte in base allo stato inventario e magazzino</li>
<li>Spese inventario</li>
<li>Offerta</li>
</ul>
</td>
</tr>
<tr>
<td>Utilizzare il controllo Gantt migliorato per sviluppare scenari di programmazione interattivi.</td>
<td>Il controllo Gantt migliorato consente di sviluppare nuovi scenari di programmazione interattivi e offrire API avanzate che possono essere utilizzate per personalizzare l'aspetto delle attività. Di seguito sono riportate alcune delle nuove API:
<ul>
<li>Trascinamento verticale di attività</li>
<li>Aggiungere/rimuovere attività</li>
<li>Anteprima periodi prenotati nella barra di riepilogo</li>
<li>Modificare il colore e lo stile dei bordi attività</li>
<li>Modificare il colore, lo stile e lo sfondo del testo nella griglia</li>
</ul>
</td>
</tr>
<tr>
<td>Migliore gestione della pianificazione di materiali e risorse.</td>
<td>Alcuni miglioramenti sono stati effettuati alla pianificazione di materiali e risorse:
<ul>
<li>Il margine di uscita viene ora gestito quando un articolo è disponibile.</li>
<li>Sovrascrivere la data di consegna quando si stabilizzano gli ordini pianificati.</li>
<li>Dare la priorità all'evasione degli ordini sulle scorte di sicurezza.</li>
<li>Impedire la programmazione di ordini pianificati nel passato.</li>
</ul>
</td>
</tr>
<tr>
<td>Segnalare il consumo effettivo per la produzione e visualizzare lo stato dell'inventario.</td>
<td>È possibile visualizzare il consumo effettivo per la produzione. Inoltre, una nuova casella di controllo <strong>Visualizza stato inventario</strong> aggiunta a <strong>Spostamento</strong> nella voce di menu <strong>Creazione lavoro</strong> consente di visualizzare lo stato dell'inventario.</td>
</tr>
<tr>
<td>Calcolare il peso volumetrico, se le tariffe per il vettore di spedizione sono in base a peso volumetrico.</td>
<td>Un nuovo motore tariffe TMS basato sul peso volumetrico è stato aggiunto, in modo da poter calcolare il peso volumetrico.</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a>Risorse aggiuntive

[Novità o modifiche nella Finance and Operations home page](whats-new-changed.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]