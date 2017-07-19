---
title: Area di lavoro controllo costi
description: "In questo argomento vengono fornite informazioni sull'area di lavoro mobile Controllo costi. Questa area di lavoro rappresenta un punto centrale i cui manager responsabile per un oggetto controllo di costi o dell'insieme di oggetti dei costi in una o più dimensioni possono accedere ai report."
author: YuyuScheller
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMCostControlWorkspaceConfiguration, CAMCostControlWorkspace
audience: Application User
ms.reviewer: yuyus
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: YuyuScheller
ms.search.validFrom: 2016-11-30T00:00:00.000Z
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 63160b9473c7f45b0eb0ca7139f9ed47c8e1446f
ms.openlocfilehash: 5c5f06d1a518963738e446b5032261059d98bf13
ms.contentlocale: it-it
ms.lasthandoff: 06/20/2017

---

# <a name="cost-control-overview"></a>Panoramica sul controllo costi 

[!include[banner](../includes/banner.md)]

L'area di lavoro **Controllo costi** rappresenta un punto centrale in cui i manager responsabili del controllo di un oggetto di costo o di un set di oggetti di costo in una o più dimensioni (ad esempio centri di costo e gruppi di prodotti) possono accedere ai report. I report nell'area di lavoro vengono gestiti dai contabili, in modo che il layout e i dati utilizzati per il reporting possano essere coerenti nell'intera organizzazione.

## <a name="cost-control-workspace-configuration"></a>Configurazione area di lavoro controllo costi

I contabili possono definire un numero illimitato di configurazioni di report secondo le necessità della composizione o del layout dei dati desiderato. La configurazione del report è costituita da sei sezioni e ciascuna contribuisce alla selezione della composizione o del layout dei dati di destinazione.

Per configurare un'area di lavoro di controllo costi, fare clic su **Contabilità industriale** \> **Impostazione** \> **Configurazione area di lavoro controllo costi**.

### <a name="general"></a>Generale

Nella scheda dettaglio **Generale**, è possibile creare un layout di report univoco. Il nome del report sarà un identificatore univoco che l'utente è in grado di riconoscere nell'area di lavoro **Controllo costi**. È inoltre possibile specificare se il report deve essere condiviso o mantenuto per uso interno dei contabili.

| Campo       | descrizione |
|-------------|-------------|
| Nome        | Immettere un nome univoco per il layout. |
| descrizione | Immettere una descrizione dettagliata. |
| Pubblicata   | Se si imposta il campo su **Sì**, un utente assegnato a uno dei seguenti ruoli può visualizzare il report nell'area di lavoro **Controllo costi** :<ul><li>Responsabile contabilità industriale</li><li>Contabile</li><li>Addetto contabilità</li><li>Controller oggetto di costo</li></ul>Se si imposta il campo su **No**, solo gli utenti assegnati a uno dei seguenti ruoli può visualizzare il report nell'area di lavoro **Controllo costi** :<ul><li>Responsabile contabilità industriale</li><li>Contabile</li><li>Addetto contabilità</li></ul> |

### <a name="data-filtering"></a>Filtro dati

Nella scheda dettaglio **Filtro dati**, è necessario definire la struttura dei dati per il report. Gli utenti di questo report vedranno i valori nel report dopo l'elaborazione dei dati di origine.

| Campo                                                             | descrizione |
|-------------------------------------------------------------------|-------------|
| Movimento CoGe di contabilità industriale                                            | Il **Movimento CoGe di contabilità industriale** su cui è basato il report. Il valore deriva dal campo **Unità di controllo costi**. |
| Unità di controllo costi                                                 | Il valore selezionato determina il movimento CoGe di contabilità industriale e gli oggetti di costo su cui sarà basato il report. |
| Gerarchia di dimensione statistica, Gerarchia dimensioni di elemento di costo | Un record di configurazione dell'area di lavoro **Controllo costi** può indicare valori monetari o non monetari, ma non nello stesso layout. Selezionare un valore nel campo **Gerarchia dimensioni di elemento di costo** per indicare valori monetari. Selezionare un valore nel campo **Gerarchia di dimensione statistica** per indicare valori non monetari. Il record di gerarchia di dimensione selezionato determina la struttura del reporting e dei livelli di aggregazione.<blockquote>[!NOTE]<br>Per visualizzare affiancati i valori monetari e non monetari, è possibile esportare i dati in Microsoft Excel per il pacchetto di contenuti di Microsoft Power BI.</blockquote> |
| Gerarchia dimensioni di oggetto di costo                                   | Selezionare la gerarchia di dimensione della dimensione oggetto di coste adeguata allo scopo del reporting da definire. |
| Versione originale budget                                           | Selezionare l'ID della versione budget che funge da budget originale nel contesto del report. |
| Versione rivista budget                                            | Selezionare l'ID della versione budget che funge da budget rivisto nel contesto del report. |

### <a name="assign-calculation-records"></a>Assegna record di calcolo

Il calcolo dei costi generali viene eseguito con più operazioni di calcolo sui dati di origine, ad esempio la classificazione comportamento costo, la distribuzione dei costi e l'allocazione dei costi. I calcoli dei costi generali più possono essere eseguiti per lo stesso periodo fiscale, nel caso in cui i dati di origine siano mancanti o le regole devono essere aggiornate. Ciascun calcolo dei costi generali verrà salvato con un ID univoco. Il contabile può selezionare uno specifico ID calcolo dei costi generali. Gli utenti del report, ad esempio i responsabili, verranno visualizzati i risultati del calcolo dei costi generali nell'area di lavoro **Controllo costi**.

| Campo                  | descrizione |
|------------------------|-------------|
| Periodo di calendario fiscale | Selezionare il periodo del calendario fiscale da assegnare a un ID calcolo dei costi generali.<blockquote>[!NOTE]<br>I periodi fiscali elencati nel campo provengono dal calendario fiscale associato alla contabilità industriale.</blockquote> |
| Versione effettiva         | Selezionare l'ID calcolo dei costi generali appropriato. |
| Versione budget         | Selezionare l'ID calcolo dei costi generali appropriato. |
| Versione budget rivista | Selezionare l'ID calcolo dei costi generali appropriato. |

### <a name="fiscal-periods-per-column"></a>Periodi fiscali per colonna

Nella scheda dettaglio **Periodi fiscali per colonna**, il contabile decide il periodo fiscale che deve essere visualizzato nel layout del report.

I valori indicati nelle colonne selezionate verranno moltiplicati per i valori selezionati nella scheda dettaglio **Periodi fiscali per colonna**.

| Campo                | descrizione |
|----------------------|-------------|
| Periodo corrente       | Viene visualizzato il saldo del periodo fiscale corrente.<blockquote>[!NOTE]<br>Per impostazione predefinita, il periodo corrente è determinato dalla data della sessione. Nell'area di lavoro **Controllo costi**, un periodo fiscale specifico può essere selezionato. Il valore selezionato rappresenta quindi il periodo corrente.</blockquote> |
| Periodo precedente      | Viene visualizzato il saldo del periodo fiscale precedente. Viene utilizzata la seguente formula:<br>Periodo fiscale corrente - 1<blockquote>[!NOTE]<br>Per impostazione predefinita, il periodo precedente è derivato dalla data della sessione. Nell'area di lavoro **Controllo costi**, un periodo fiscale specifico può essere selezionato come periodo corrente. Il **Periodo precedente** verrà ricalcolato di conseguenza.</blockquote> |
| Da inizio anno a oggi         | Viene visualizzato il valore calcolato dall'inizio dell'anno a oggi. Viene utilizzata la seguente formula:<br>YearToDate (periodo fiscale corrente)<blockquote>[!NOTE]<br>Per impostazione predefinita, il periodo corrente è determinato dalla data della sessione. Nell'area di lavoro **Controllo costi**, un periodo fiscale specifico può essere selezionato. Il valore selezionato rappresenta quindi il periodo corrente e il valore **Da inizio anno a oggi** verrà aggiornato di conseguenza.</blockquote> |
| Media da inizio anno a oggi | Viene visualizzato il valore medio calcolato dall'inizio dell'anno a oggi. Viene utilizzata la seguente formula:<br>(YearToDate [periodo fiscale corrente]) ÷ (Count [periodo fiscale corrente])<p><strong>Esempio</strong></p><ul><li>**Membro di dimensione statistica:** Dipendenti a tempo pieno</li><li>**Data corrente:** 3-21-2017</li><li>**Periodo:** Periodo fiscale 1, Periodo fiscale 2, Periodo fiscale 3</li><li>**Grandezza:** 10, 10, 12</li></ul>In questo caso, **Media da inizio anno a oggi** = (10 + 10 + 12) ÷ 3 = 10,67<p>Il valore **Media da inizio anno a oggi** può essere calcolato per i membri di dimensione elemento di costo e i membri di dimensione statistica.</p><blockquote>[!NOTE]<br>Per impostazione predefinita, il periodo corrente è determinato dalla data della sessione. Nell'area di lavoro **Controllo costi**, un periodo fiscale specifico può essere selezionato. Il valore selezionato rappresenta quindi il periodo corrente e i valori **Da inizio anno a oggi** e **Media da inizio anno a oggi** verranno aggiornati di conseguenza.</blockquote> |

### <a name="columns-to-display-for-costs"></a>Colonne da visualizzare per costi

Nella scheda dettaglio **Colonne da visualizzare per costi**, il contabile decide le colonne da includere nel report. Sono disponibili tre categorie: Costo fisso, Costo variabile e Costo non classificato.

| Campo                 | descrizione |
|-----------------------|-------------|
| Costo fisso            | Questo tipo di colonna mostra il costo fisso, in base all'ID calcolo dei costi generali selezionato.<blockquote>[!NOTE]<br>Questo tipo di colonna mostra un saldo solo quando un ID calcolo dei costi generali è selezionato per il periodo fiscale.</blockquote> |
| Costo variabile         | Questo tipo di colonna mostra il costo variabile, in base all'ID calcolo dei costi generali selezionato.<blockquote>[!NOTE]<br>Questo tipo di colonna mostra un saldo solo quando un ID calcolo dei costi generali è selezionato per il periodo fiscale.</blockquote> |
| Costo fisso + variabile | Questo tipo di colonna mostra il costo fisso e il costo variabile, in base all'ID calcolo dei costi generali selezionato.<blockquote>[!NOTE]<br>Questo tipo di colonna mostra un saldo solo quando un ID calcolo dei costi generali è selezionato per il periodo fiscale.</blockquote> |
| Costo totale            | Questo tipo di colonna mostra il costo totale (costo non classificato, costo fisso e costo variabile).<blockquote>[!NOTE]<br>Questo tipo di colonna mostra sempre il saldo.</blockquote> |
| Costo non classificato     | Questo tipo di colonna mostra il costo non classificato.<blockquote>[!NOTE]<br>Questa colonna può essere utilizzata per verificare se i costi vengono classificati correttamente dal calcolo dei costi generali o se le regole di comportamento costo devono essere modificate.</blockquote> |

### <a name="columns-to-display-for-budgeted-costs"></a>Colonne da visualizzare per costi a budget

Nella scheda dettaglio **Colonne da visualizzare per costi a budget**, il contabile decide le colonne da includere per le versioni di budget selezionate. È possibile effettuare singole selezioni per il budget originale e il budget rivisto.

> [!NOTE]
> Poiché i seguenti campi si comportano ugualmente per il budget originale e il budget rivisto, verranno spiegati insieme.

| Campo                     | descrizione |
|---------------------------|-------------|
| Budget                    | I saldi budget verranno visualizzati per le colonne selezionate.<blockquote>[!NOTE]<br>I saldi si basano sulle versioni di budget selezionate nella scheda dettaglio **Filtro dati**.</blockquote> |
| Scostamento budget           | Calcolare e visualizzare la differenza tra i valori effettivi e quelli a budget. Viene utilizzata la seguente formula:<br>Saldo budget - Saldo effettivo |
| Scostamento budget in %      | Calcolare e visualizzare la differenza in percentuale tra i valori effettivi e quelli a budget. Viene utilizzata la seguente formula:<br>(Saldo budget - Saldo effettivo) ÷ Saldo budget |
| Soglia periodo scostamento | Impostare una soglia per lo scostamento dell'importo monetario per il periodo corrente. Se la soglia viene superata, la riga verrà evidenziata in rosso nell'area di lavoro **Controllo costi**.<blockquote>[!NOTE]<br>Questo campo è valido solo per gli elementi di costo che rappresentano le spese.</blockquote> |
| Soglia anno scostamento   | Impostare una soglia per lo scostamento dell'importo monetario per l'anno. Se la soglia viene superata, la riga verrà evidenziata in rosso nell'area di lavoro **Controllo costi**. |
| Soglia scostamento %      | Impostare una soglia per lo scostamento in percentuale. Se la soglia viene superata, la riga verrà evidenziata in rosso nell'area di lavoro **Controllo costi**.<blockquote>[!NOTE]<br>La stessa soglia in percentuale si applica al periodo e all'anno correnti.</blockquote> |

## <a name="cost-control-workspace"></a>Area di lavoro controllo costi

L'area di lavoro **Controllo costi** è stata progettata come report Web. Di conseguenza, a tutti i responsabili di un oggetto di costo può essere concesso l'accesso come descritto in [Definire i diritti di accesso per i controller oggetto di costo](access-rights-cost-object-controller.md).

L'elenco dei report disponibili per gli utenti, ad esempio i responsabili, è controllato dall'impostazione dell'opzione **Pubblicato** nella pagina **Configurazioni area di lavoro controllo costi**.

![Report che gli utenti possono visualizzare nell'area di lavoro Controllo costi](./media/report-cost-control.png)

Un responsabile può selezionare il periodo del calendario fiscale da visualizzare. La data della sessione viene utilizzata per determinare il periodo corrente predefinito.

I valori nel periodo del calendario fiscale sono determinati dal nome del report e dal calendario fiscale selezionato per la contabilità industriale associata al nome del report nella pagina **Configurazioni area di lavoro controllo costi**.

Nella gerarchia dimensioni di oggetto di costo, gli utenti possono selezionare il livello di aggregazione secondo cui i saldi devono essere visualizzati. Abilitando la sicurezza a livello di accesso, si controllano le autorizzazioni, in modo che gli utenti possono selezionare solo i livelli della gerarchia per cui dispongono del diritto di accesso. Di conseguenza, possono vedere solo i saldi aggregati per cui è stato loro concesso l'accesso.

### <a name="add-or-remove-columns"></a>Aggiungi o rimuovi colonne

Gli utenti possono personalizzare le colonne di un report in base alle esigenze.

### <a name="view-details"></a>Visualizza dettagli

Gli utenti possono analizzare a fondo i dettagli relativi ai saldi visualizzati nell'area di lavoro. Se gli utenti selezionano un nodo gerarchia dimensioni elemento di costo e fanno clic su **Visualizza dettagli**, viene visualizzata la finestra di dialogo **Dettagli elemento di costo** con le informazioni dettagliate per il nodo.

Una griglia mostra ciascun elemento di costo associato al nodo gerarchia dimensioni elemento di costo e i relativi valori. Le colonne visualizzate nella griglia corrispondono alle impostazioni dell'area di lavoro.

Due grafici mostrano un riepilogo dei valori effettivi rispetto al budget e lo scostamento budget per periodo.

![I grafici che mostrano un riepilogo dei valori effettivi rispetto al budget e lo scostamento budget per periodo](./media/cost-element-details-operations.png)

Gli utenti possono fare clic su **Voci di costo** per eseguire il drill-down dei dettagli della voce in base alle esigenze.

![Voci di costo](./media/cost-entries.png)

Ad esempio, il noleggio è una spesa che viene distribuita ai centri di costo. Un utente che desidera conoscere il costo del noleggio incluso nel proprio centro di costo può eseguire il drill-down per vedere come è stato calcolato il noleggio.

Se gli utenti fanno clic su **Base di allocazione** nella pagina **Voci di costo**, viene visualizzata una finestra di dialogo. Gli utenti possono quindi assegnare la base di allocazione alla regola e visualizzare le misurazioni statistiche corrispondenti registrate per il periodo.

Nel seguente esempio, la base di allocazione è di tipo **Base di allocazione formula** e la formula viene visualizzata. I fattori che definiscono la formula sono elencati. Inoltre, una griglia visualizza il calcolo effettuato per oggetto di costo.

![Calcoli per oggetto di costo](./media/cost-entries-allocation-base.png)

Vedere anche 

[Definire i diritti di accesso per i controller oggetto di costo](access-rights-cost-object-controller.md)



