---
title: Costi il contenuto di potenza di gestione BI
description: "In questo argomento vengono descritte viene incluso nel contenuto di costo di potenza di gestione BI. Descrive come accedere i report di Power BI e fornisce informazioni sul modello dati e sulle entità utilizzati per costruire il contenuto."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations
ms.custom: 270314
ms.assetid: 9680d977-43c8-47a7-966d-2280ba21402a
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: e4de011e6eeac58643b828b65e24b874d981d5e7
ms.lasthandoff: 03/31/2017


---

# <a name="cost-management-power-bi-content"></a>Costi il contenuto di potenza di gestione BI

In questo argomento vengono descritte viene incluso nel contenuto di costo di potenza di gestione BI. Descrive come accedere i report di Power BI e fornisce informazioni sul modello dati e sulle entità utilizzati per costruire il contenuto.

# <a name="overview"></a>Panoramica

** Gestione costi ** il contenuto di potenza di Microsoft BI serve ai contabili o gli utenti di magazzino dell'organizzazione responsabili per il magazzino. ** Gestione costi ** il contenuto di Power BI fornisce alla direttiva in magazzino e nelle scorte di (WIP) del lavoro in corso e come costo si procede attraverso nel tempo per la categoria. Le informazioni possono essere utilizzate come supplemento dettagliato nel rendiconto finanziario.

## <a name="key-measures"></a>Misurazioni chiave

+ Saldo iniziale
+ Saldo finale
+ Modifica netto
+ Variazione netta in %
+ Invecchiare

## <a name="key-performance-indicators"></a>Indicatori di prestazioni chiave
+ Rotazione scorte
+ Precisione inventario

Fonte dei dati principale per CostAggregatedCostStatementEntryEntity è la tabella di CostStatementCache. Questa tabella viene gestita dal framework della cache del set di dati. Per impostazione predefinita, la tabella viene aggiornata ogni 24 ore, ma è possibile attivare gli aggiornamenti manuali nella configurazione della cache di dati. È possibile eseguire un aggiornamento manuale ** gestione dei costi o ** ** analisi dei costi ** nell'area di lavoro. Dopo l'aggiornamento di CostStatementCache viene eseguito, è necessario aggiornare la connessione a OData di potenza BI.com visualizzare i dati aggiornati nel sito. Le misure di scostamento (acquisto, produzione) nel contenuto di Power BI coprono solo gli articoli che vengono valorizzati con il metodo di magazzino in costo standard. Lo scostamento di produzione viene calcolato come la differenza tra i costi attivi e costo realizzato. Lo scostamento di produzione viene calcolato quando l'ordine di produzione con stato Finito di ** **. Per ulteriori informazioni sui tipi di scostamento produzione e come ciascun tipo di calcolo, vedere [su analizzare gli scostamenti per un ordine di produzione completato] (https://technet.microsoft.com/en-us/library/gg242850.aspx).

## <a name="accessing-the-power-bi-content"></a>Accesso al contenuto di Power BI
** Gestione costi ** il contenuto di Power BI è disponibile da PowerBI.com. Per ulteriori informazioni su come caricare e collegare il sistema Microsoft Dynamics 365 per le operazioni dati, vedere [Accesso di contenuto Power BI da PowerBI.com] () power-bi-home-page.md.

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>In inclusa contenuto di Power BI
Il contenuto include un insieme delle pagine del report. Ciascuna pagina è costituita da un insieme criteri di valutazione che viene visualizzata come i grafici, le mattonelle e tabelle. Nella seguente tabella viene fornita una panoramica delle visualizzazioni in ** gestione dei costi ** alimenta BI il contenuto.

| Pagina del report | Grafici | Titoli |
|---|---|---|
|Magazzino predefinito (complessivo per periodo corrente) |Precisione |Misurazioni di magazzino:<br>Saldo finale di magazzino<br>Modifica di rete di magazzino<br>Modifica % netto di magazzino<br>|
| |Rotazione scorte | |
| |Saldo finale base al gruppo di risorse | |
| |Modifica netto in base al livello 2 di livello 1 dei nomi di categoria e nome della categoria| |
| |Acquisti gli scostamenti livello 3 da nome della categoria e il gruppo di risorse | |
|Registrare i costi degli articoli standard per il periodo corrente) |Saldo finale base al nome e il gruppo di risorse del sito | |
| |Giro di magazzino dal nome e il gruppo di risorse del sito | |
| |Saldo finale base alla città e dal gruppo di risorse | |
|Magazzino dal gruppo di risorse (standard per il periodo corrente) |Misurazioni di magazzino | |
| |Accuratezza inventariali in base all'importo dal gruppo di risorse | |
| |Giro inventariali in base all'importo dal gruppo di risorse | |
|Scorte (YOY dei costi standard e quello precedente) |Misurazioni di magazzino | |
| |Scorte KPI:<br>Rotazione scorte<br>Precisione inventario | |
| |Saldo finale dell'anno e dal gruppo di risorse | |
| |Acquisti gli scostamenti livello 3 da nome della categoria e di anno | |
|Le di aging (standard per anno corrente) |Le di aging dal trimestre e dal gruppo di risorse | |
| |Le di aging in base al nome del sito e il trimestre | |
|WIP (complessivo standard per il periodo corrente) |Modifica della rete WIP dal livello 2 di livello 1 dei nomi di categoria e nome della categoria |Misurazioni Semilavorati WIP:<br>Saldo finale WIP<br>Modifica della rete WIP<br>Modifica % di rete WIP<br> |
| |Gli scostamenti produzione per gruppo di risorse e la categoria nominano il livello 3 | |
| |Modifica della rete WIP dal gruppo di risorse | |
|WIP in base al sito (standard per il periodo corrente) |Misurazioni Semilavorati WIP | |
| |La modifica netto WIP dal nome del sito e la categoria nominano il livello 2 | |
| |Gli scostamenti produzione per il nome e la categoria del sito nominano il livello 3 | |

## <a name="understanding-the-data-model-and-entities"></a>Informazioni su modelli ed entità di dati
Dynamics 365 per le operazioni che i dati utilizzati per popolare le pagine del report in ** gestione dei costi ** alimentano BI il contenuto. Questi dati sono rappresentate come misure aggregate che sono con stato Approntato nella memoria di entità, ovvero un database di Microsoft SQL che viene ricerca per l'analisi dei dati. Per ulteriori informazioni, vedere [panoramica dei gruppi Administrators e Power Users di integrazione BI al punto vendita] dell'entità (power-bi-integration-entity-store.md). Le seguenti misure aggregate chiave vengono utilizzate come base del contenuto.

| Entità            | Misura aggregata chiave | Origine dati per Dynamics 365 per le operazioni | Campo             | descrizione                       |
|-------------------|---------------------------|---------------------------------------------|-------------------|-----------------------------------|
| Voci di rendiconto | Modifica netto                | CostAggregatedCostStatementEntryEntity      | somma (importo di\[\])   | Importo nella valuta di contabilizzazione |
| Voci di rendiconto | Quantità del fabbisogno netto       | CostAggregatedCostStatementEntryEntity      | somma (quantità\]\[) |                                   |

Nella tabella seguente vengono illustrate le misurazioni aggregate chiave vengono utilizzate per creare diverse misure calcolate nel set di dati del contenuto.

| Unità di misura                                 | Funzionamento di misura viene calcolata                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Saldo iniziale                       | \]modifica\]-\[del saldo finale\[                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Quantità del saldo iniziale              | \]quantità della modifica netto\]-\[della quantità del saldo finale\[                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Saldo finale                          | CALCOLI (importo SUM (\]), FILTRO (ALLEXCEPT ("calendari fiscali ", "calendars'entity_PLACEHOLDER [\ fiscale LedgerRecId\], "ID\],\]"nome del entities'entity_PLACEHOLDER [\, che in\]di Ledgers'entity_PLACEHOLDER [\ ",\]descrizione di Ledgers'entity_PLACEHOLDER [\ ",\]nome\[ entities'entity_PLACEHOLDER [\ \ di Ledgers'entity_PLACEHOLDER [), la data di\] = &lt;max ("data del conto\]calendars'entity_PLACEHOLDER [\ \ di calendars'entity_PLACEHOLDER [)( report)                                                                                                                                                                                           |
| Quantità del saldo finale                 | CALCOLI (SUM quantità (\]), FILTRO (ALLEXCEPT ("calendari fiscali ", "calendars'entity_PLACEHOLDER [\ fiscale LedgerRecId\], "ID\],\]"nome del entities'entity_PLACEHOLDER [\, che in\]di Ledgers'entity_PLACEHOLDER [\ ",\]descrizione di Ledgers'entity_PLACEHOLDER [\ ",\]nome\[ entities'entity_PLACEHOLDER [\ \ di Ledgers'entity_PLACEHOLDER [), la data di\] = &lt;max ("data del conto\]calendars'entity_PLACEHOLDER [\ \ di calendars'entity_PLACEHOLDER [)( report)                                                                                                                                                                                         |
| Le il saldo iniziale             | CALCOLI (saldo di apertura\[\],\[a\] tipo di rendiconto di entries'entity_PLACEHOLDER [\ di rendiconto = "magazzino")                                                                                                                                                                                                                                                                                                                                                                                      |
| Saldo finale di magazzino                | CALCOLI (saldo finale\],\[a\] tipo di rendiconto di entries'entity_PLACEHOLDER [\ di rendiconto = "magazzino")                                                                                                                                                                                                                                                                                                                                                                                         |
| Modifica di rete di magazzino                    | CALCOLI\](modifica\[,\] al tipo di rendiconto di entries'entity_PLACEHOLDER [\ di rendiconto = "magazzino")                                                                                                                                                                                                                                                                                                                                                                                             |
| Quantità della modifica netto di magazzino           | CALCOLI (quantità\]della modifica netto\[,\] al tipo di rendiconto di entries'entity_PLACEHOLDER [\ di rendiconto = "magazzino")                                                                                                                                                                                                                                                                                                                                                                                    |
| Modifica % netto di magazzino                  | IF (saldo finale\] dell'inventario\[= 0, 0,\]saldo finale dell'inventario\] / \[della modifica netto dell'inventario \[)                                                                                                                                                                                                                                                                                                                                                                           |
| Giro inventariali in base all'importo                | In alternativa (se il saldo (medio\] dell'&lt;inventario\[= 0, \[' inventario \[ha venduto o consumato le uscite\]&gt;= 0), 0, ABS (le scorte\[ha venduto o consumato le uscite\])/Collettivo magazzino medio\]\[)                                                                                                                                                                                                                                                                                                  |
| Saldo di magazzino medio               | (2)/\]saldi iniziali dell'inventario\] + \[del saldo finale dell'inventario\[                                                                                                                                                                                                                                                                                                                                                                                                       |
| Problemi vendute o consumate di magazzino       | scorte\[ha venduto\] + \[\]di costo consumato scorte materiali                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Costo consumato scorte materiali        | CALCOLI\](modifica netto dell'inventario\[, al nome della categoria di entries'entity_PLACEHOLDER [\ di rendiconto 2 - Livello\_\] = "ConsumedMaterialsCost")                                                                                                                                                                                                                                                                                                                                                            |
| Scorte venduto                          | CALCOLI\](modifica netto dell'inventario\[, al nome della categoria di entries'entity_PLACEHOLDER [\ di rendiconto 2 - Livello\_\] = "Venduto")                                                                                                                                                                                                                                                                                                                                                                             |
| Accuratezza inventariali in base all'importo            | IF (saldo finale\] dell'&lt;inventario\[= 0, IF (OR (Importo conteggiato\[' inventario\[\]&lt;&gt; 0, saldo finale\] 0 dell'&lt; inventario \[), 0, 1), max (0, (saldo finale\] consente ABS (Importo conteggiato il magazzino\[\[\])/saldo finale\]\[' inventario\[)                                                                                                                                                                                                                              |
| Importo conteggiato magazzino                | CALCOLI\](modifica netto dell'inventario\[, al nome della categoria di entries'entity_PLACEHOLDER [\ di rendiconto 3 - Livello\_\] = "particolare")                                                                                                                                                                                                                                                                                                                                                                         |
| Aging delle scorte                         | (se ISBLANK (massimo ('data del conto\]calendars'entity_PLACEHOLDER [\), vuota), max (0, MIN (quantità di aging\] entrate dell'inventario\[, quantità di aging in futuro\] entrate del saldo finale dell'inventario \[delle quantità in magazzino di aging\] - \[)( report) costo unitario di avg dell'inventario \* \[\]                                                                                                                                                                                                                                |
| Quantità di aging entrate di magazzino       | IF (il minDate\] = \[\[minDateAllSelected\], CALCOLA (quantità\]della modifica netto dell'inventario\[,\] "quantità 0, &gt; FILTRO (ALLEXCEPT ("calendari fiscali ", "calendars'entity_PLACEHOLDER [\ fiscale LedgerRecId\], "ID\],\]"nome del entities'entity_PLACEHOLDER [\, che in\]di Ledgers'entity_PLACEHOLDER [\ ",\]descrizione di Ledgers'entity_PLACEHOLDER [\ ",\]nome del entries'entity_PLACEHOLDER [\ di rendiconto di entities'entity_PLACEHOLDER [\ \ di Ledgers'entity_PLACEHOLDER [), la data di\] = &lt;max ('data del conto\]calendars'entity_PLACEHOLDER [\ \ di calendars'entity_PLACEHOLDER [)( report), CALCOLI (quantità\]della modifica netto dell'inventario\[, a\] 0 quantità di entries'entity_PLACEHOLDER &gt; [\ di rendiconto) |
| Quantità di aging del saldo finale di magazzino | \] la quantità del saldo finale dell'inventario\[+ (quantità CALCOLA\], FILTRO (ALLEXCEPT ("calendari fiscali ", "calendars'entity_PLACEHOLDER [\ fiscale LedgerRecId\], "ID\],\]"nome del entities'entity_PLACEHOLDER [\, che in\]di Ledgers'entity_PLACEHOLDER [\ ",\]descrizione di Ledgers'entity_PLACEHOLDER [\ ",\]nome della modifica netto dell'inventario\[di entities'entity_PLACEHOLDER [\ \ di Ledgers'entity_PLACEHOLDER [), la data del conto\] calendars'entity_PLACEHOLDER &gt; [\ massimo ("data del conto\]calendars'entity_PLACEHOLDER [\)( report)                                                                                                                                 |
| Entrate di aging delle scorte in futuro  | CALCOLI\](modifica netto dell'inventario\[, "rendiconti\] 0, &gt; FILTRO (ALLEXCEPT ("calendari fiscali ", "calendars'entity_PLACEHOLDER [\ fiscale LedgerRecId\], "ID\],\]"nome del entities'entity_PLACEHOLDER [\, che in\]di Ledgers'entity_PLACEHOLDER [\ ",\]descrizione di Ledgers'entity_PLACEHOLDER [\ ",\]nome del entries'entity_PLACEHOLDER [\ importo del entities'entity_PLACEHOLDER [\ \ di Ledgers'entity_PLACEHOLDER [), la data di\] max &gt; ('data del conto\]calendars'entity_PLACEHOLDER [\ \ di calendars'entity_PLACEHOLDER [)( report)                                                                                                                                             |
| Costo unitario di avg di magazzino                 | CALCOLI (quantità, ALLEXCEPT\]("calendari fiscali ", "calendars'entity_PLACEHOLDER [\ fiscale LedgerRecId\], "ID\],\]"nome del entities'entity_PLACEHOLDER [\, che in\]di Ledgers'entity_PLACEHOLDER [\ ",\]descrizione di Ledgers'entity_PLACEHOLDER [\ ",\]nome del saldo finale dell'inventario\] / \[del saldo finale dell'inventario\[di entities'entity_PLACEHOLDER [\ \ di Ledgers'entity_PLACEHOLDER [)                                                                                                                                                                                                                 |
| Acquisti gli scostamenti                      | CALCOLI (SUM (importo\[\]), "nome della categoria di entries'entity_PLACEHOLDER [\ di rendiconto 2 - Livello\_\] = "ottenuto ", "\] tipo di rendiconto di entries'entity_PLACEHOLDER [\ di rendiconto = "e")                                                                                                                                                                                                                                                                                                                              |
| Saldo iniziale WIP                   | CALCOLI (saldo di apertura\[\],\[a\] tipo di rendiconto di entries'entity_PLACEHOLDER [\ di rendiconto WIP = "")                                                                                                                                                                                                                                                                                                                                                                                            |
| Saldo finale WIP                      | CALCOLI (saldo finale\],\[a\] tipo di rendiconto di entries'entity_PLACEHOLDER [\ di rendiconto WIP = "")                                                                                                                                                                                                                                                                                                                                                                                               |
| Modifica della rete WIP                          | CALCOLI\](modifica\[,\] al tipo di rendiconto di entries'entity_PLACEHOLDER [\ di rendiconto WIP = "")                                                                                                                                                                                                                                                                                                                                                                                                   |
| Modifica % di rete WIP                        | IF (saldo finale\]\[WIP = 0, 0, saldo finale\]\] / \[WIP della modifica netto \[WIP)                                                                                                                                                                                                                                                                                                                                                                                             |
| Scostamenti di produzione                    | CALCOLI (SUM (importo\[\]), "nome della categoria di entries'entity_PLACEHOLDER [\ di rendiconto 2 - Livello\_\] = "ManufacturedCost ", "\] tipo di rendiconto di entries'entity_PLACEHOLDER [\ di rendiconto = "e")                                                                                                                                                                                                                                                                                                                      |
| Nome della categoria di livello 1                 | aggiuntivi (nome della categoria\[1 - Livello\_\], "Nessuno ", "Nessuno ", "NetSourcing ", "netto approvvigionamento ", "NetUsage ", "utilizzare netto ", "NetConversionCost ", "costo di conversione netto ", "NetCostOfGoodsManufactured ", "costo netto delle merci prodotti ", "BeginningBalance ", "saldo iniziale")                                                                                                                                                                                                         |
| Nome della categoria di livello 2                 | aggiuntivi (nome della categoria\[consente il livello 2\_\], "Nessuno ", "Nessuno ", "ottenuto ", "ottenuto ", "e ", "e ", "in ", "in ", "Venduto ", "Venduto ", "ConsumedMaterialsCost ", "costo consumato materiale ", "ConsumedManufacturingCost ", "costo di produzione consumato ", "ConsumedOutsourcingCost ", "costo consumato di delocalizzazione ", "ConsumedIndirectCost ", "costi indiretti consumati ", "ManufacturedCost", "prodotto il costo ", "gli scostamenti ", "gli scostamenti")                            |
| Nome della categoria di livello 3                 | aggiuntivi (nome della categoria\[3 - Livello\_\], prezzo "Nessuno ", "Nessuno ", "di conteggio ", "Nessuno", "ProductionPriceVariance ", "di produzione", "dimensione di QuantityVariance", "," quantità pari a SubstitutionVariance ", "sostitutivo", "ScrapVariance ", "scarti", "LotSizeVariance ", "di lotto"," modifica ", "RoundingVariance di RevaluationVariance ", "di rivalutazione", "PurchasePriceVariance ", "prezzi di acquisto", "CostChangeVariance ", "di costi, "l'arrotondamento scostamento")                                                   |

Nelle dimensioni chiave vengono utilizzate come filtri per affettare le misurazioni aggregate per ottenere una maggiore granularità e immettere le comprensioni analitiche più contrassegnate.

| Entità           | Esempi di attributi                       |
|------------------|----------------------------------------------|
| Entità         | ID, nome                                     |
| Calendari fiscali | Calendario, mese, trimestre, periodo, anno       |
| Obiettivi KPI        | Destinazione di precisione di magazzino, obiettivo di compensazione di magazzino |
| Contabilità generali          | Valuta, nome, la descrizione                  |
| Siti            | ID, nome, città, paese                      |

## <a name="additional-resources"></a>Risorse aggiuntive
Di seguito sono riportati alcuni collegamenti utili correlati alle entità e alla creazione di contenuto per Power BI:

-   [Entità di dati](..\data-entities\data-entities.md)
-   [Creazione di pacchetti di contenuti per l'organizzazione](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modellazione di dati tramite Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Aggiunta di riquadri Power BI ad aree di lavoro](configure-power-bi-integration.md)



