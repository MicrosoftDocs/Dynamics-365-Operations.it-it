---
title: Variabili di test di gestione qualità
description: Questo argomento descrive come creare variabili di test che possano essere utilizzati per i test qualitativi in ordini di controllo qualità in Microsoft Dynamics 365 Supply Chain Management.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4495c3d3f8df9f07ec079d8e497a17979abbe3ee
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7575874"
---
# <a name="quality-management-test-variables"></a>Variabili di test di gestione qualità

[!include [banner](../includes/banner.md)]

Questo argomento descrive come creare variabili di test che possano essere utilizzati per i test qualitativi in ordini di controllo qualità in Microsoft Dynamics 365 Supply Chain Management.

È necessario definire una variabile di test e i possibili relativi risultati per ogni test qualitativo definito nella pagina **Test**. (Per i test qualitativi, il campo **Tipo** nella pagina **Test** è impostato su *Opzione*).

Utilizzare la pagina **Variabili di test** per impostare, modificare e visualizzare i possibili risultati di una variabile di test associata a un test qualitativo. Per ogni risultato, si assegna uno stato di risultato tra *Superato* e *Non superato* per indicare se il test è superato o meno quando tale risultato viene selezionato come risultato del test. Utilizzare la pagina **Gruppi di test** per assegnare una variabile di test e il risultato predefinito reletivo a un test qualitativo individuale.

Per ogni variabile di test, ti consigliamo di definire almeno due risultati: uno con stato di risultato *Superato* e uno che ha uno stato di risultato di *Non superato*. Non c'è limite al numero totale di variabili o risultati che possono essere definiti. Inoltre, più test possono utilizzare le stesse variabili di test per registrare i risultati.

## <a name="examples-of-test-variables"></a>Esempi di variabili di test

### <a name="example-1"></a>Esempio 1

Una società di produzione esegue due test sui materiali fabbricati. In un test, il livello di pH è associato a una striscia colorata. I livelli di pH accettabili sono in colori più chiari e i livelli di pH inaccettabili sono in colori più scuri. In un altro test, vengono eseguite più ispezioni visive e gli addetti alla qualità usano il loro giudizio per determinare se l'articolo supera o meno l'ispezione visiva.

### <a name="example-2"></a>Esempio 2

Una società produttrice di biscotti utilizza un test di ispezione per il prodotto finito. Il test di ispezione ha diverse variabili. Una variabile si riferisce al gusto e i possibili risultati per questa variabile sono buono o cattivo. Una seconda variabile riguarda il colore e i risultati possibili troppo scuro, troppo chiaro e corretto.

## <a name="create-a-test-variable"></a>Creare una variabile di test

Per creare una variabile di test, eseguire i passaggi indicati di seguito:

1. Andare a **Gestione articoli \> Impostazioni \> Controllo qualità \> Variabili di test**.
1. Nel riquadro azioni seleziona **Nuova** per aggiungere una riga alla griglia. Quindi imposta i seguenti campi per la nuova riga:

    - **Variabile** – Immetti un ID o nome univoco per la variabile.
    - **Descrizione** - Immettere una descrizione dettagliata della variabile.

1. Mentre la nuova riga è ancora selezionata, seleziona **Risultati** nel riquadro azioni.
1. Nella pagina **Risultati variabile di test**, nel riquadro azioni selezionare **Nuovo** per aggiungere una riga alla griglia. Quindi imposta i seguenti campi per la nuova riga:

    - **Risultato** – Immetti un ID o nome univoco per il risultato.
    - **Descrizione** - Immettere una descrizione dettagliata del risultato.
    - **Stato risultato** – seleziona *Superato* o *Non superato* per indicare se il test è superato o meno quando tale risultato viene selezionato come risultato del test.

1. Ripeti il passaggio precedente per ogni risultato aggiuntivo. Assicurati che almeno un risultato abbia uno stato di risultato di *Superato* e almeno uno ha uno stato di risultato di *Non superato*.
1. Chiudere le pagine.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Strumenti di test di gestione qualità](quality-test-instruments.md)
- [Test di gestione qualità](quality-tests.md)
- [Gruppi di test di gestione qualità](quality-test-groups.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
