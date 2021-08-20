---
title: Tenere traccia dei viaggi in entrata e dei percorsi dei contenitori di spedizione
description: In questo argomento viene descritto come è possibile utilizzare la pagina Tracciabilità in entrata per tenere traccia dell'avanzamento dei viaggi e dei percorsi dei contenitori di spedizione.
author: sherry-zheng
ms.date: 01/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMContainerActivityTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 86e73ddc8b259299abe73ad3e393cfdf3dd68824421f216a68308ddcac735828
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6779256"
---
# <a name="track-inbound-voyages-and-shipping-container-journeys"></a>Tenere traccia dei viaggi in entrata e dei percorsi dei contenitori di spedizione

[!include [banner](../../includes/banner.md)]

La pagina **Tracciabilità in entrata** consente di tenere traccia dell'avanzamento dei viaggi e dei percorsi dei contenitori di spedizione. Ogni viaggio e percorso è suddiviso per *attività*, ognuna dei quali ha una propria riga nella pagina. È possibile utilizzare la pagina per visualizzare e immettere date stimate e date effettive per attività.

In genere, a seconda della configurazione nel [Centro di controllo tracciabilità](delivery-information-setup.md#tracking-control-center), queste attività mostrano automaticamente la data di sbarco stimata alla destinazione finale. Inoltre, a seconda dell'configurazione, la data finale di solito aggiorna la data di consegna o la data confermata nelle righe dell'ordine fornitore. Per le righe dell'ordine fornitore, è possibile impostare il sistema affinché aggiorni la data di entrata.

Per aprire la pagina **Tracciabilità in entrata**, selezionare **Costo sbarcato \> Tracciabilità \> Tracciabilità in entrata**.

## <a name="filter-the-activities-list"></a>Filtrare l'elenco delle attività

È possibile usare i campi **Viaggio** e **Contenitore di spedizione** nella parte superiore della pagina **Tracciabilità in entrata** per filtrare la pagina in modo che mostri solo le attività associate al viaggio e/o al contenitore di spedizione selezionato.

## <a name="update-tracking-information"></a>Aggiornare le informazioni di tracciabilità

Per aggiornare la programmazione di un viaggio o di un percorso, immettere la data di inizio della prima attività. La data di fine stimata dell'ultima attività viene quindi aggiornata. La configurazione di ogni scalo e modello di percorso nel [Centro di controllo tracciabilità](delivery-information-setup.md#tracking-control-center) determina i lead time stimati. Le date di fine stimate utilizzano il lead time della data di inizio dell'attività. Quindi, quando viene registrata la data di fine effettiva, la data di inizio dell'attività successiva viene aggiornata alla stessa data della data di fine effettiva dell'attività precedente. Il lead time effettivo viene aggiornato per scopi di confronto e analisi. È possibile immettere note aggiuntive nel campo **Nota**.

L'ordine delle attività nella griglia è determinato dall'ordine degli scali nel modello di viaggio pertinente. Se l'ordine degli scali nel percorso associato cambia, cambia anche il controllo della tracciabilità.

È possibile aggiornare le date per tutti i contenitori selezionando **Aggiorna data di inizio** o **Aggiorna data di fine effettiva** nel riquadro Azioni. In alternativa, è possibile inserire le date per contenitore nella spedizione. Questo approccio consente una maggiore flessibilità poiché i contenitori possono essere suddivisi in un ambiente con più percorsi.

## <a name="buttons-on-the-action-pane"></a>Pulsanti nel riquadro Azioni

È possibile utilizzare i pulsanti nel riquadro Azioni della pagina **Tracciabilità in entrata** per i viaggi e i percorsi in entrata. Nella seguente tabella vengono descritti i pulsanti disponibili.

| Pulsante | Descrizione |
|---|---|
| Modifica | Consente di modificare un viaggio o un percorso. |
| Nuove | Consente di creare un nuovo viaggio o percorso. |
| Elimina | Elimina un viaggio o un percorso selezionato. |
| Aggiorna data di inizio | Aggiorna la data di inizio di un'attività per tutti i contenitori in un viaggio. Quando la data di inizio di una specifica attività o di uno scalo di un viaggio viene aggiornata, le successive date di inizio stimate vengono aggiornate in base al lead time specificato. |
| Aggiorna data di fine effettiva | Aggiorna la data di fine di un'attività per tutti i contenitori in un viaggio. Quando la data di fine di una specifica attività viene aggiornata, le successive attività vengono aggiornate in base al lead time specificato. |
| Aggiungi attività | Consente di aggiungere manualmente un'attività a un viaggio. Ad esempio, si potrebbe aggiungere un'attività di fumigazione. L'aggiunta potrebbe causare la modifica della data di consegna confermata delle merci nell'imbarcazione o nel viaggio. Quando un'attività viene aggiunta al percorso, i giorni stimati non vengono immessi fino a quando non viene aggiornata la data di inizio di uno scalo del viaggio. |

## <a name="information-and-settings-on-the-overview-tab"></a>Informazioni e impostazioni nella scheda Panoramica

La scheda **Panoramica** mostra un elenco di tutte le attività che appartengono al viaggio e/o al contenitore di spedizione selezionato nella parte superiore della pagina. Nella seguente tabella vengono descritti i campi disponibili per ogni attività.

| Campo | Descrizione |
|---|---|
| Scalo | L'ID scalo dell'attività, come definito dal modello di percorso. |
| Modalità di consegna | Il metodo di consegna previsto per l'attività. |
| Attività | Questo campo in genere identifica il processo o l'operazione associato all'attività. Esempi tipici includono *Navigazione* e *Sdoganamento*. |
| Descrizione | Una descrizione dettagliata dell'attività. |
| Data di inizio | Questo campo mostra inizialmente la data di inizio stimata dell'attività. Tuttavia, dopo aver immesso la data di fine effettiva dell'attività precedente, viene visualizzata la data di inizio effettiva. Questo campo è utilizzato per determinare la data di fine stimata, in base al lead time. |
| Data di fine stimata | Il valore di questo campo viene calcolato in base alla data di inizio e al lead time. Di solito il valore non viene modificato direttamente. |
| Data di fine effettiva | Un utente deve aggiornare questo campo il prima possibile dopo l'esecuzione dell'attività. Il lead time effettivo viene quindi aggiornato. |
| Giorni stimati | Il periodo di tempo previsto (in giorni) necessario per completare l'attività. |
| Giorni effettivi | Il periodo di tempo effettivo (in giorni) necessario per completare l'attività. |
| Nota | Usare questo campo per aggiungere note e dettagli vari sull'attività. |

## <a name="information-and-settings-on-the-general-tab"></a>Informazioni e impostazioni nella scheda Generale

La scheda **Generale** mostra informazioni sullo scalo selezionato nella scheda **Panoramica**. Sebbene ripeta alcune delle informazioni che appaiono nella scheda **Panoramica**, include anche informazioni aggiuntive sullo scalo selezionato.
