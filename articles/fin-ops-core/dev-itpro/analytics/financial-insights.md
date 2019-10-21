---
title: Informazioni finanziarie dettagliate
description: Informazioni finanziarie dettagliate utilizza Microsoft Power BI per combinare dati di indicatori di prestazione chiave (KPI) finanziari, grafici, e rendiconti finanziari.
author: kweekley
manager: AnnBe
ms.date: 05/22/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 106233
ms.assetid: 517e6a88-e7a1-4398-9971-b22fa83306ba
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 596a067611ac4477f4469dbbc370c971e0f7a35d
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2181774"
---
# <a name="financial-insights"></a>Informazioni finanziarie dettagliate

[!include [banner](../includes/banner.md)]

**Informazioni finanziarie dettagliate** utilizza Microsoft Power BI per combinare dati di indicatori di prestazione chiave (KPI) finanziari, grafici, e rendiconti finanziari. Power BI è incluso nell'applicazione. **Informazioni finanziarie dettagliate** è incentrato sulla creazione di report analitici. Le persone di un'organizzazione possono visualizzare, ricercare, analizzare ed eseguire azioni. 

**Informazioni finanziarie dettagliate** combina i dati di contabilità generale e di giornali di registrazione secondari per fornire un quadro più completo sull'integrità finanziaria dell'organizzazione.

> [!NOTE]
> In questo documento viene utilizzata la seguente terminologia di Power BI:
> 
> - **Report** - Un singolo file .pbix in cui vengono salvati tutti gli oggetti visivi di tutte le schede.
> - **Pagina** - Una scheda in un singolo file .pbix. Ogni pagina può contenere uno o più oggetti visivi.
> - **Oggetto visivo** - Una singola origine dati, ad esempio scheda, KPI, diagramma, grafico, matrice o rendiconto finanziario. Una pagina con un rendiconto finanziario come oggetto visivo non può contenere altri oggetti visivi, a causa della dimensione dei dati inclusi.

Attualmente, l'area di lavoro **Informazioni finanziarie dettagliate** viene utilizzata per visualizzare dati relativi alla persona giuridica attiva o a tutte le persone giuridiche. Nelle versioni future, l'area di lavoro verrà trasformata in un punto in cui sarà possibile utilizzare Power BI per modificare e creare oggetti visivi.

L'area lavoro **Panoramica responsabile finanziario** mostra gli stessi oggetti visivi di **Informazioni finanziarie dettagliate**, ma con lo scopo principale di visualizzare e filtrare dati nei report esistenti. Nelle versioni future, sarà possibile aggiungere nuovi oggetti visivi all'area di lavoro **Informazioni finanziarie dettagliate**. I nuovi oggetti visivi possono anche essere disponibili in aree di lavoro focalizzate su altri ruoli, come project manager o responsabili di contabilità fornitori. L'area di lavoro **Panoramica responsabile finanziario** continuerà a mostrare i dati per tutte le persone giuridiche, indipendentemente dalle persone giuridiche a cui il ruolo ha accesso.

## <a name="dynamics-365-finance-setup"></a>Impostazione di Dynamics 365 Finance
**Contabilità generale**

Il tipo di conto principale e le categorie di conto principale vengono utilizzati per compilare i conti principali predefiniti appropriati nel rendiconto finanziario dello **Stato patrimoniale** e nei vari rendiconti finanziari del **Conto economico** in **Informazioni finanziarie dettagliate**.

Nella pagina **Conti principali** è necessario definire il conto principale in modo da assegnare uno dei seguenti tipi:

- Ricavi
- Expense
- Cespiti
- Passività
- Capitale netto

Non assegnare ai conti principali nessun altro tipo di conto principale, ad esempio **Stato patrimoniale** o **Profitti e perdite**. La creazione di report non può determinare il tipo di account principale quando vengono assegnati altri tipi di conti principali, perché non sono abbastanza granulari. Per mostrare le passività e i ricavi come importi positivi nei report finanziari, deve essere determinato il tipo di conto principale.

Per apparire nei rendiconti finanziari e per essere inclusi in altri oggetti visivi, come i KPI, ciascun conto principale deve essere assegnato a una categoria di conto principale. Le categorie di conti principali sono state migliorare per includere un ordine di visualizzazione. L'ordine di visualizzazione viene utilizzato nei rendiconti finanziari specificatamente in **Informazioni finanziarie dettagliate**. Dopo aver modificato o aggiunto una nuova categoria di conti principali, è possibile modificare il valore dell'**Ordine di visualizzazione** per definire l'ordine in cui le categorie del conto principale devono essere visualizzate in un rendiconto finanziario. Se è necessario modificare l'ordine di visualizzazione per molte categorie di conti principali, è possibile utilizzare la funzionalità Apri in Excel per modificare rapidamente e pubblicare nuovamente le modifiche nell'applicazione.

## <a name="entity-store"></a>Archivio entità
I dati per **Informazioni finanziarie dettagliate** vengono estratti dall'archivio entità (**Amministrazione sistema** \> **Impostazioni** \> **Archivio entità**). Se si apre l'area di lavoro **Panoramica responsabile finanziario** o **Informazioni finanziarie dettagliate** e viene visualizzato il seguente messaggio di avviso negli oggetti visivi, è necessario aggiornare le entità.

![Avviso](./media/Cantdisplay.png)

Per visualizzare i dati delle aree di lavoro **Informazioni finanziarie dettagliate** e **Panoramica responsabile finanziario**, è necessario aggiornare le seguenti entità:

- Versione 2 di Dati transazione dei reporting finanziari (**Nota:** è una nuova funzionalità della versione 10.0.1 e sostituisce l'entità precedente).
- Dati transazione dei report finanziari
- CustCollectionsBIMeasurements
- LedgerCovLiquidityMeasurement
- Cubo Acquisti
- Cubo Vendite

Nella versione precedente, le entità di VendPaymentBIMeasure e LedgerActivityMeasure venivano utilizzate per i dati nell'area di lavoro **Panoramica responsabile finanziario**. Tuttavia, non sono più utilizzate nella versione esistente.

È possibile definire un batch ricorrente per aggiornare regolarmente i dati nelle entità. Poiché ogni entità viene completamente ricostruita durante un aggiornamento, selezionare attentamente l'ora e la frequenza degli aggiornamenti delle entità. L'entità primaria utilizzata per i rendiconti finanziari è l'entità FinancialReportingTransactionData. Di conseguenza, è possibile scegliere di aggiornare più di frequente questa entità.

## <a name="security"></a>Sicurezza
Attualmente, i dati sui report Power BI incorporati non possono essere limitati alle persone giuridiche a cui l'utente ha accesso. Pertanto, i report di Power BI incorporati sono controllati attraverso i diritti dell'impostazione di sicurezza. I diritti definiti consentono l'accesso ai dati per tutte le persone giuridiche o solo per la società attiva. Nella seguente tabella vengono illustrati i diritti esistenti e ruoli a cui sono assegnati. I diritti possono essere rimossi o assegnati ai ruoli diversi, in base ai requisiti dell'organizzazione.

| Imposta                                    | Ruoli | Descrizione |
|-----------------------------------------|-------|------------|
| Visualizza area di lavoro Panoramica responsabile finanziario             | Responsabile finanziario | Questi diritti consentono di accedere all'area di lavoro Panoramica responsabile finanziario. Per impostazione predefinita, la società attiva viene utilizzata come filtro. Tuttavia, è possibile aggiungere tutte le persone giuridiche, indipendentemente dal fatto che l'utente abbia accesso ad altre persone giuridiche. |
| Visualizza informazioni finanziarie dettagliate della società attuale | <ul><li>Contabile</li><li>Direttore amministrativo</li><li>Supervisore contabile</li><li>Revisore</li><li>Responsabile budget</li><li>Amministratore delegato</li><li>Responsabile finanziario</li><li>Supervisore finanziario</li></ul> | Questi diritti consentono di accedere a Informazioni finanziarie dettagliate. Per impostazione predefinita, la società attiva viene utilizzata come filtro. Non è possibile aggiungere altre persone giuridiche. |
| Visualizza informazioni finanziarie dettagliate della società   | In Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition 7.3, questi diritti non sono assegnati a un ruolo. Nella versione successiva, questi diritti verranno assegnati al ruolo Responsabile finanziario. | Questi diritti consentono di accedere alla voce di menu per l'area di lavoro Panoramica responsabile finanziario. Per impostazione predefinita, la società attiva viene utilizzata come filtro. Tuttavia, è possibile aggiungere tutte le persone giuridiche, indipendentemente dal fatto che l'utente abbia accesso ad altre persone giuridiche. |


## <a name="financial-reporting-vs-finanical-insights"></a>Confronto tra Creazione di report finanziari e Informazioni finanziarie dettagliate
Sebbene **Informazioni finanziarie dettagliate** contenga rendiconti finanziari, non sostituisce la creazione di report finanziari nell'applicazione. I rendiconti finanziari predefiniti di **Informazioni finanziarie dettagliate** sono di portata limitata e non includono tutti i tipi di rendiconti finanziari. Il reporting finanziario è ancora lo strumento principale per progettare, creare e generare rendiconti finanziari statutari di legge.

La seguente tabella di confronto aiuterà a differenziare le due opzioni:


|                                                          | Creazione di report finanziari                                               | Informazioni finanziarie dettagliate |
|----------------------------------------------------------|-------------------------------------------------------------------|--------------------|
| **Modifica report predefiniti**                                 | Sì                                                               | No |
| **Creazione nuovi report**                                   | Sì                                                               | No |
| **Stampa report**                                        | Sì                                                               | No |
| **Esporta in Excel**                                      | Sì                                                               | Esportazione limitata di dati non elaborati in Excel, non in un report formattato |
| **Supporto creazione di report con gerarchia/gerarchia organizzativa**   | Sì                                                               | No |
| **Report i dati del giornale d registrazione secondario**                             | Sì limitato solo al fornitore, cliente                              | Sì fornitore, cliente, gruppi di clienti/fornitori, indirizzi clienti/fornitori, e così via. |
| **Valuta di dichiarazione**                                   | Sì valuta di contabilizzazione e convertire in valuta di dichiarazione       | No solo valuta di contabilizzazione |
| **Sicurezza**                                             | Sì conforme alla sicurezza dell'albero gerarchico di creazione report di Finance | Report con visualizzazione limitata per tutte le società (indipendentemente dalla sicurezza di Finance and Operations) o solo per la società attiva |
| **Supporto di diversi piani dei conti e anni fiscali** | Sì                                                               | No |
| **Report di dati esterni**                              | No                                                                | No |
| **Supporto di consolidamenti**                               | Sì                                                               | Limitato Può creare report per più società ma utilizzare solo la valuta di contabilizzazione |

Oltre all'interfaccia utente dell'area di lavoro originale **Panoramica responsabile finanziario**, sono ora disponibili nuovi KPI, grafici e rendiconti finanziari. Sono disponibili i seguenti rendiconti finanziari:

- Bilancio di verifica
- Stato patrimoniale
- Conto economico per area
- Conto economico - Confronto effettivo/budget
- Conto economico con scostamenti
- Conto economico tendenza 12 mesi - Predefinito
- Tendenza spese triennale
- Spese per fornitore
- Vendite per cliente

## <a name="edit-visuals"></a>Modifica degli oggetti visivi
Nella versione iniziale di **Informazioni finanziarie dettagliate** nessuno degli oggetti visivi può essere modificato. Nelle versioni future, gli utenti che dispongono della autorizzazioni di sicurezza appropriate saranno in grado di creare nuovi oggetti visivi, copiare oggetti esistenti e modificare oggetti visivi. Sebbene i file con estensione pbix che contengono i report siano disponibili come risorse, non è consigliabile modificare i report predefiniti. Verranno apportate ulteriori modifiche al modello dati, ai report predefiniti e all'oggetto visivo del rendiconto finanziario personalizzato che vengono utilizzati per creare i rendiconti finanziari. Pertanto, per sfruttare le nuove funzionalità e le modifiche al modello di dati della prossima versione, sarà necessario ripristinare tutte le modifiche apportate ai report predefiniti tramite Microsoft Power BI Desktop.

## <a name="filtering"></a>Filtri
Gli utenti possono filtrare il report utilizzando il riquadro **Filtro** a sinistra. Questo riquadro è lo stesso riquadro disponibile in Power BI Desktop. Esistono vari livelli di filtro, alcuni dei quali potrebbero non essere disponibili, a seconda di cosa si è selezionato in una pagina (scheda) o se si utilizzano le funzionalità drill-through:

- **Filtri a livello di report**: questi filtri vengono applicati a tutti gli oggetti visivi su tutte le pagine (schede).
- **Filtri a livello di pagina**: questi filtri vengono applicati a tutti gli oggetti visivi della scheda attiva. Questi filtri vengono applicati sopra i filtri a livello di report.
- **Filtri a livello di oggetto visivo** : questi filtri vengono applicati solo all'oggetto visivo selezionato. Questi filtri vengono applicati sopra i filtri a livello di pagina.
- **Filtro drill-through**: questo filtro applica il filtro a partire da un oggetto visivo "sorgente" che viene applicato all'oggetto visivo corrente quando si passa dall'oggetto visivo di origine a quello corrente.

![Filtro](./media/filter.png)

Per rimuovere un valore specifico di filtro, selezionare il simbolo della gomma accanto ad esso. Non rimuovere un filtro selezionando la X. Se si seleziona la X, il campo su cui stai filtrando viene rimosso come opzione di filtro. Se si deseleziona accidentalmente un campo dal filtro, chiudere l'area di lavoro e quindi riaprila. Le impostazioni di filtro predefinite verranno applicate nuovamente.

Per impostazione predefinita, quando si aprono per le aree di lavoro, la persona giuridica attiva viene utilizzata come filtro a livello di report. A seconda della protezione, gli utenti possono aggiungere altre persone giuridiche o modificare la persona giuridica predefinita selezionata nel filtro.

Il filtro **Calendario fiscale** è necessario in modo che venga utilizzato il calendario corretto per la visualizzazione. Per impostazione predefinita, il filtro a livello di report è impostato sul calendario fiscale della persona giuridica attiva. Se si modifica il filtro in un calendario fiscale con una data di inizio o di fine diversa, i saldi iniziali non verranno inclusi. Di conseguenza, i rendiconti finanziari dello **Stato patrimoniale** non mostreranno i saldi corretti. Se si seleziona un calendario fiscale aggiuntivo nel filtro, si otterrà un ulteriore set di colonne. Ciascuna serie aggiuntiva di colonne mostra gli importi per un diverso calendario fiscale.

È inoltre necessario il filtro **Livello di registrazione**. Per impostazione predefinita, il filtro è impostato su Corrente. È possibile selezionare ulteriori livelli di registrazione nel filtro per mostrare gli importi aggregati.

I filtri sono inoltre disponibili per i campi **Anno fiscale** e **Data**. In genere, questi filtri vengono applicati a livello di pagina. Per impostazione predefinita, il filtro **Data** utilizza una data relazionale che è possibile modificare. È inoltre possibile rimuovere il filtro data relazionale e utilizzare il filtro **Anno fiscale** in alternativa.

## <a name="currency"></a>Valuta

Tutti gli oggetti visivi che riportano sui dati di contabilità generale mostrano gli importi nella valuta di contabilizzazione. Pertanto, quando si filtra per persona giuridica, è necessario fare attenzione a includere solo le persone giuridiche che hanno la stessa valuta di contabilizzazione. In caso contrario, verranno aggregati dati in valute diverse.

Tutti gli oggetti visivi che forniscono un report dei dati relativi ai giornali di registrazione secondari, come **Previsione di cassa** e **Primi 10** , mostrano gli importi nella valuta del sistema. La valuta di sistema e il tipo di tasso di cambio del sistema vengono definiti nella pagina **Parametri di sistema**.

L'oggetto visivo **Saldo per conto bancario** utilizza gli importi nella valuta dei conti bancari.

## <a name="dimensions"></a>Dimensioni

I rendiconti finanziari predefiniti non includono alcuna dimensione finanziaria ma sono focalizzati solo sul conto principale. Il supporto per le dimensioni finanziarie sarà disponibile nelle versioni future, quando i report saranno modificabili. Le organizzazioni saranno quindi in grado di filtrare i valori delle dimensioni finanziarie.

Alcuni rendiconti finanziari contengono dimensioni basate su transazioni del giornale di registrazione secondario. L'obiettivo dei nuovi rendiconti finanziari è di consentire il filtro su dimensioni che non sono impostate come dimensioni finanziarie. Ad esempio, il report predefinito Spese per fornitore consente di espandersi oltre il conto principale, in modo da poter visualizzare i saldi suddivisi per fornitore. Il fornitore non è impostato come dimensione finanziaria. Invece, il sistema torna alla transazione della registrazione secondaria di origine per trovare il fornitore.

Le seguenti dimensioni vengono utilizzate nei report predefiniti. Nessuna di queste dimensioni è una dimensione finanziaria.

- Fornitore
- Gruppo di fornitori
- Cliente
- Gruppo di clienti
- Paese
- Stato/regione o provincia
- Città

> [!IMPORTANT] 
> Se si riepilogano le transazioni per più fornitori o clienti in un singolo giustificativo utilizzando giornali di registrazione finanziari, i dati saranno errati. La creazione di report non è in grado di determinare quale fornitore o cliente è collegato a un conto CoGe specifico in una scrittura contabile, poiché tali informazioni non sono gestite in nessun punto. Pertanto, non si consiglia di inserire più fornitori, clienti, cespiti o progetti in un unico giustificativo.

## <a name="drill-on-data"></a>Drill dei dati

Tramite Power BI sono disponibili diversi livelli di drill. Ogni livello ha un nome diverso e diverse funzionalità. È anche possibile eseguire il drill di righe e colonne. Questa sezione illustra le varie opzioni utilizzando come esempio il rendiconto finanziario del **Bilancio di verifica** e mostrando come eseguire il drill delle righe. La stessa funzionalità è disponibile per le colonne. È necessario modificare solo il valore **Drill**.

Nell'illustrazione seguente, il rendiconto del **Bilancio di verifica** viene compresso al livello più alto della gerarchia di righe, il tipo di conto principale.

![Bilancio di verifica](./media/trial-balance.png)

Per visualizzare il livello successivo della gerarchia, le categorie principali del conto, è possibile impostare il campo **Drill** su **Righe** e quindi fare clic sul pulsante **Espandi** il terzo pulsante dopo il campo Drill. Tutte le categorie del conto principale vengono espanse. Attualmente, Power BI non consente di espandere solo una riga o una colonna, ma visualizza anche tutte le altre righe o colonne.

![Bilancio di verifica](./media/trial-balance2.png)

Per espandere il conto principale per tutte le righe, è possibile utilizzare di nuovo il pulsante **Espandi**. Tuttavia, per eseguire il drill-down sui conti principali per una sola riga, selezionare innanzitutto il pulsante **Drill-down** (la singola freccia rivolta verso il basso sul lato destro della finestra), quindi selezionare la riga per cui eseguire il drill-down. L'illustrazione seguente mostra il risultato quando viene selezionata la riga **Vendite** dopo aver selezionato il pulsante **Drill-down**.

![Bilancio di verifica](./media/trial-balance3.png)

Dopo aver eseguito il drill-down su una singola riga, sono necessari più clic per tornare al bilancio di verifica completo. Il pulsante **Drill-up** (il primo pulsante dopo il campo **Drill**) esegue il drill-up solo nel contesto della categoria **Vendite**, come mostrato nella seguente illustrazione.

![Bilancio di verifica](./media/trial-balance4.png)

È possibile continuare a utilizzare il pulsante **Drill-up** per tornare al più alto livello di riepilogo per le righe.

Power BI dispone anche di un pulsante che consente di passare al livello successivo nella gerarchia (il secondo pulsante dopo il campo **Drill**). L'effetto di questo pulsante differisce dall'effetto del pulsante **Espandi** (il terzo pulsante dopo il campo **Drill**), che viene utilizzato per espandere la gerarchia. Quando si espande la gerarchia, la gerarchia viene mantenuta nel report. Ad esempio, come mostrato in precedenza, se si espande il tipo di conto principale, nel report viene comunque visualizzato il tipo di account principale. Tuttavia, quando si passa al livello successivo nella gerarchia, il report non mostra più il padre nella gerarchia, come mostrato nella figura seguente.

![Bilancio di verifica](./media/trial-balance5.png)

Per visualizzare i dettagli della transazione alla base dei saldi riepilogati, è possibile selezionare alcuni importi per eseguire il drill-back in Financial and Operations.

Il drill-back dei rendiconti finanziari porta a Esplora origine contabilità, non alle transazioni giustificativo. Esplora origine contabilità non mostra solo le voci contabili nella contabilità generale. Vengono visualizzati invece i dettagli della transazione del giornale di registrazione secondario. Pertanto, si ottengono molti più dettagli sulla transazione di origine che possono essere utilizzati per l'analisi. Ad esempio, è possibile vedere chi era il fornitore o il cliente, ciò che il cliente ha acquistato o il fornitore venduto e anche quale progetto era nella transazione.

I seguenti filtri dei rendiconti finanziari vengono inviati a Esplora origine contabilità, in modo che Esplora origine contabilità mostri le transazioni che vengono aggregate:

Campi obbligatori per il filtro:

- Persona giuridica
- Calendario fiscale
- Anno
- ID conto principale

Campi facoltativi per il filtro:

- Trimestre
- Mese
- Periodo

Se non si espande una riga a sufficienza, il drill-down non funziona. Ad esempio, se si espande solo fino alla categoria di conti principali, non sarà possibile eseguire il drill-down nel saldo Esplora origine contabilità, in quanto il conto principale è un campo obbligatorio per applicare filtri in Esplora origine contabilità.

Se si espande troppo verso il basso una riga, i filtri aggiuntivi nei rendiconti finanziari non verranno inviati a Esplora origine contabilità. Di conseguenza, potrebbe venire visualizzata una differenza nelle cifre. Ad esempio, se si espande verso il basso fino al paese o area nelle righe del conto economico per rendiconto finanziario dell'area, il paese o l'area non verrà inclusa come filtro in Esplora origine contabilità.

> [!NOTE]
> È possibile eseguire un'analisi più approfondita delle righe o colonne del rendiconto finanziario rispetto a quelle attualmente supportate dal filtro di Esplora origine contabilità. Pertanto, in alcune situazioni, la somma delle transazioni dettagliate in Esplora origine contabilità non corrisponderà al saldo su cui si sta eseguendo il drill-back. Questa funzionalità continuerà ad essere migliorata in futuro.

## <a name="hierarchies"></a>Gerarchie

I rendiconti finanziari predefiniti utilizzano due gerarchie per il drill e l'espansione nei dati. Una gerarchia è relativa alle righe e l'altra è alle colonne. Entrambe le gerarchie sono predefinite nella progettazione del rendiconto finanziario. Per la maggior parte dei rendiconti finanziari, la gerarchia di riga è **Tipo di conto principale** \> **Categorie di conti principali** \> **Conto principale**. Tuttavia, alcuni report hanno campi aggiuntivi, come paese e regione. I nodi supplementari della gerarchia sono basati sui dati relativi ai giornali di registrazione secondari per ciascuna transazione.

Per le colonne, la gerarchia è focalizzata sulle persone giuridiche e sui periodi fiscali. Per la maggior parte dei rendiconti finanziari, la gerarchia di colonna è **Persona giuridica** \> **Calendario fiscale** \> **Anno fiscale** \> **Trimestre** \> **Periodo**.

Attualmente, i rendiconti finanziari non supportano le gerarchie organizzative, che consentono l'aggregazione dei dati.

## <a name="data-limitations"></a>Limitazioni dei dati
Agli oggetti visivi del rendiconto finanziario viene applicato un limite relativo al numero di righe che può essere visualizzato. Attualmente, il limite è impostato su 30.000. Se si supera questo limite, all'oggetto visivo sarà associato un simbolo di avviso per informare di questa situazione..

![Limitazioni dei dati](./media/data-limit.png)

Se viene superato il valore massimo, i totali visualizzati nel rendiconto finanziario non saranno corretti, poiché non tutte le righe sono state caricate nell'elemento visivo.

### <a name="empty-rows"></a>Righe vuote
Power BI non fornisce un'opzione per nascondere e mostrare righe vuote. Se una riga non include dei dati, la riga non apparirà nell'oggetto visivo.


## <a name="additional-resources-for-power-bi"></a>Risorse aggiuntive per Power BI

Le informazioni contenute nelle seguenti risorse non sono necessarie per abilitare i report incorporati per la **Panoramica responsabile finanziario** o l'area di lavoro **Informazioni finanziarie dettagliate** in un ambiente di produzione. Al contrario, sono utili per le caselle di sviluppo e se si desidera incorporare i propri report di Power BI.

- <https://blogs.msdn.microsoft.com/dynamicsaxbi/2017/07/29/accessing-analytical-workspaces-on-1box-environment/>

- <https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/add-analytics-tab-workspaces>
