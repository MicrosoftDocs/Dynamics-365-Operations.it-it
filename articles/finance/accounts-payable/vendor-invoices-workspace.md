---
title: Area di lavoro Automazione fattura fornitore
description: Questo argomento spiega come impostare l'area di lavoro correlata alle fatture fornitore e che mostra le informazioni disponibili tramite Microsoft Power BI.
author: abruer
ms.date: 02/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.assetid: ''
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2020-09-21
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: f28cc5f63df2f0d8a4c8cae407f7166aa4fa03db
ms.sourcegitcommit: 6102f70d4595d01b90afe5b23dfd8ec2ea030653
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/16/2022
ms.locfileid: "8182581"
---
# <a name="vendor-invoice-automation-workspace"></a>Area di lavoro Automazione fattura fornitore

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Questo argomento spiega come impostare l'area di lavoro correlata alle fatture fornitore e che mostra le informazioni disponibili tramite Microsoft Power BI. Le informazioni sulla fattura del fornitore in questa area di lavoro vengono filtrate per utenti specifici e visualizzate in un formato grafico.

## <a name="overview"></a>Panoramica

Nell'area di lavoro **Automazione fattura fornitore** vengono visualizzate le informazioni correlate all'elaborazione delle fatture del fornitore. Include una visualizzazione **Lavoro personale** e una pagina **Analisi - Tutte le società**. Nella visualizzazione **Lavoro personale** vengono visualizzati i riquadri di riepilogo, le griglie di transazione fornitore e le informazioni correlate al fornitore. La pagina **Analisi - Tutte le società** utilizza le funzionalità di Microsoft Power BI per visualizzare le rappresentazioni correlate alle fatture fornitore.

## <a name="set-up-the-workspace-to-show-power-bi-content"></a>Impostare l'area di lavoro per visualizzare il contenuto Power BI

È necessario completare questa configurazione prima che i dati possano essere visualizzati nelle visualizzazioni Power BI nell'area di lavoro **Automazione fattura fornitore**.

1. Nell'area di lavoro **Gestione delle funzionalità**, filtrare l'elenco per trovare la funzionalità **Automazione fatture fornitore**.
3. Selezionare **Abilita ora**.
4. Per garantire che le fatture possano essere elaborate dall'inizio alla fine senza richiedere un intervento manuale, impostare un flusso di lavoro di fatturazione fornitore. Per configurare un flusso di lavoro, vai a **Contabilità fornitori \> Imposta \> Flussi di lavoro contabilità fornitori**.
5. Andare a **Contabilità fornitori \> Imposta \> Parametri contabilità fornitori** e selezionare la scheda **Automazione fatture fornitore**. Per ulteriori informazioni, vedere [Opzioni di configurazione per l'automazione delle fatture fornitore](vnd-invoice-set-up-options.md).
6. Impostare l'opzione **Invia automaticamente fatture importate a flusso di lavoro** su **Sì**.
7. Se le entrate prodotti devono essere abbinate automaticamente, impostare l'opzione **Abbina automaticamente entrate prodotti a righe di fattura** su **Sì**.
8. Rivedere le restanti impostazioni facoltative e configurarle in base ai requisiti dell'organizzazione.
9. Andare a **Amministrazione sistema \> Imposta \> Parametri di sistema** e impostare i campi **Valuta di sistema** e **Tasso di cambio del sistema**.
10. Andare a **Contabilità generale \> Imposta \> Contabilità generale** e impostare i campi **Valuta di contabilizzazione** e **Tipo di tasso di cambio**.
11. Andare a **Contabilità generale \> Valute \> Tassi di cambio valuta** e immettere i tassi di cambio tra la valuta della transazione e la valuta contabile e tra la valuta contabile e la valuta del sistema.
12. Andare ad **Amministrazione di sistema \> Imposta \> Store di entità** e cercare **Misura di automazione fatture fornitore**. Selezionare **Aggiorna**.

Per visualizzare le informazioni visualizzate nell'area di lavoro, è necessario disporre del ruolo di sicurezza Responsabile contabilità fornitori o Addetto contabilità fornitori.

## <a name="my-work-view"></a>Visualizzazione Lavoro personale

### <a name="company-selection"></a>Selezione società

Quando la funzionalità **Automazione fattura fornitore** è attivata, il campo **Società** viene visualizzato nella parte superiore dell'area di lavoro. La selezione del campo **Società** influisce su tutte le informazioni visualizzate nell'area di lavoro. Per impostazione predefinita, la vista mostra le informazioni per l'azienda a cui è stato effettuato l'accesso. Selezionando una società diversa nel campo **Società** è possibile visualizzare le informazioni per quella società nell'area di lavoro. È quindi possibile selezionare un riquadro nell'area di lavoro per andare alla pagina correlata nella società selezionata.

### <a name="summary-tiles"></a>Sezioni Riepilogo

I riquadri nella sezione **Riepilogo fatture in sospeso** della visualizzazione **Lavoro personale** forniscono una panoramica dello stato delle fatture del fornitore. È possibile visualizzare i giornali di registrazione non ancora registrati e le fatture in sospeso. Inoltre, ci sono i quattro riquadri associati alla funzione di automazione delle fatture fornitore:

- **Abbinamento ricezione manuale necessario**
- **Convalida abbinamento non riuscita**
- **Fatture non inviate al flusso di lavoro**
- **Fatture non importate**

(Questi quattro riquadri richiedono che la funzione di automazione della fattura fornitore sia attivata in **Gestione funzionalità**.)

Per utilizzare il riquadro **Recupera fatture fornitore** la funzione deve essere attivata in **Parametri contabilità fornitori**. Andare a **Contabilità fornitori \> Parametri contabilità fornitori** e quindi nella scheda **Fattura** impostare l'opzione **Consenti recupero fattura fornitore** su **Sì**.

Quando la funzione è attiva, verranno raggruppati anche tre riquadri nell'area di lavoro in una sezione chiamata **Giornali di registrazione**. I riquadri sono intitolati **Giornali di registrazione**, **Giornali di registrazione - Assegnati all'utente corrente** e **Pool di fatture**. 

Le informazioni nella sezione **Riepilogo fatture in sospeso** è per la società impostata come società predefinita per l'accesso.

### <a name="creating-new-records"></a>Creazione di nuovi record

Per creare un nuovo record di fattura, selezionare **Nuovo**, quindi selezionare uno dei seguenti tipi di record nell'elenco:

- Fattura fornitore
- Giornale di registrazione fatture
- Giornale di registrazione fatture globale
- Registro fatture
- Approvazione fattura

Si noti che il record che si crea si basa sul filtro della società e non sulla società a cui è stato effettuato l'accesso. Ad esempio, è stato effettuato l'accesso alla società **UMSF** ma il filtro della società è impostato su **GBSI**. In questo caso, quando si seleziona **Nuovo** e quindi un tipo di record nell'elenco, il record viene creato nella società GBSI.

### <a name="documents-not-invoiced-grids"></a>Griglie dei documenti non fatturati

La sezione **Documenti non fatturati** contiene griglie che mostrano i documenti in attesa di fatture fornitore.

La griglia **Ordini di acquisto aperti** mostra tutti gli ordini di acquisto non ancora completamente fatturati. È possibile usare il pulsante **Fattura ora** per creare una fattura fornitore per un ordine di acquisto. È possibile usare il pulsante **Fattura pagamento anticipato ora** per creare una fattura di pagamento anticipato per un ordine di acquisto.

La griglia **Entrate prodotti** mostra tutte le transazioni di entrata di acquisto non ancora completamente fatturate. È possibile usare il pulsante **Fattura ora** per creare una fattura fornitore per un ordine di acquisto.

La griglia **Fatture fornitore in sospeso** mostra tutte le fatture fornitore che non sono state inviate al sistema del flusso di lavoro. È possibile usare il campo **Ricerca** e/o il filtro della società per cercare una specifica fattura fornitore. È possibile usare il pulsante **Modifica** per modificare una transazione che appare nella griglia.

Nella griglia **Trova ordine di acquisto** è possibile usare il campo **Ricerca** per cercare un ordine di acquisto specifico.

### <a name="related-information"></a>Informazioni correlate

È possibile visualizzare le informazioni sulle fatture registrate utilizzando i collegamenti sul lato destro dell'area di lavoro. Questi collegamenti includono **Fatture fornitore aperte**, **Giornale di registrazione fatture** e **Cronologia fatture e dettagli corrispondenti**. Nella sezione **Fornitori** è possibile accedere a un elenco filtrato che mostra tutti i fornitori in attesa oppure utilizzare il collegamento **Tutti i fornitori**. I collegamenti **Tutti gli ordini di acquisto** e **Pagamenti anticipati aperti** sono anche disponibili.

### <a name="analytics--all-companies-page"></a>Pagina Analisi - Tutte le società

Quando l'opzione **Invia automaticamente fatture importate al flusso di lavoro** è impostata su **Sì** nella pagina **Parametri contabilità fornitori** è possibile visualizzare l'analisi dell'automazione. La pagina **Analisi - Tutte le società** fornisce metriche importanti, come le fatture del fornitore che sono in approvazione da parte del responsabile approvazione e dalla società. Questa pagina contiene cinque pagine di report. In una pagina viene fornita una panoramica e nelle altre pagine vengono fornite informazioni dettagliate sulle metriche di automazione della contabilità fornitori.

Nella seguente tabella vengono illustrate le visualizzazioni disponibili in ciascuna pagina del report.

| Pagina di report                    | Visualizzazioni |
|--------------------------------|----------------|
| Panoramica delle fatture fornitore        | <ul><li>Fatture fornitore in sospeso nell'automazione nella valuta di sistema</li><li>Fatture che non sono state importate</li><li>Fatture nel flusso di lavoro</li><li>Le fatture touchless durano 30 giorni</li><li>Le fatture completamente automatizzate durano 30 giorni</li><li>Saldo delle fatture aperte nella valuta di sistema</li><li>Motivi di errori, ultimi 30 giorni</li><li>Percentuale di fatture registrate che sono state elaborate automaticamente</li><li>Giorni per elaborare una fattura</ul></li> |
| Stato automazione              | <ul><li>Le fatture touchless durano 30 giorni</li><li>Le fatture touchless durano 30 giorni per società</li><li>Le fatture touchless durano 30 giorni per gruppo di fornitori</li><li>Percentuale di fatture registrate che sono state elaborate automaticamente</li><li>Giorni per elaborare una fattura</li></ul> |
| Fatture che non sono state importate | <ul><li>Fatture che non sono state importate</li><li>Fatture che non sono state importate per società</li></ul> |
| Motivi dell'automazione non riuscita | <ul><li>Fatture non riuscite</li><li>Fatture non riuscite per società</li><li>Fatture non riuscite per gruppo di fornitori</li></ul> |
| Stato flusso di lavoro                | <ul><li>Fatture nel flusso di lavoro</li><li>Istanze del flusso di lavoro di fatture fornitori</li><li>Assegnazione per responsabile approvazione</li><li>Flusso di lavoro fattura fornitore per società</li><li>Giorni impiegati in media nel flusso di lavoro per approvatore</li></ul> |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
