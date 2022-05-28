---
title: Mantenere la certificazione fornitore
description: In questo argomento vengono descritti i passaggi che i fornitori possono utilizzare per mantenere le proprie certificazioni utilizzando l'area di lavoro Collaborazione fornitore.
author: v-kiarnd
ms.date: 04/27/2021
ms.topic: article
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2021-02-09
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: b1b2cdd4389afd8997b60fe8e7a9b6851cbde199
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2022
ms.locfileid: "8735697"
---
# <a name="maintain-vendor-certification"></a>Mantenere la certificazione fornitore

[!include [banner](../includes/banner.md)]

In questo argomento vengono descritti i passaggi che i fornitori possono utilizzare per mantenere le proprie certificazioni utilizzando l'**area di lavoro Collaborazione fornitore**. Esempi di certificazioni potrebbero includere Woman Business Enterprise (WBE) o LEED (Leadership in Energy and Environment Design). I fornitori dovranno inserire le informazioni sulla certificazione nell'area di lavoro **Informazioni fornitore**. Da lì, i fornitori selezioneranno **Più dettagli** e quindi **Certificazioni**.

## <a name="turn-on-the-vendor-certification-feature"></a>Attivare la funzionalità di certificazione del fornitore

Prima di poter utilizzare questa funzione, è necessario attivarla nel sistema. Gli amministratori possono utilizzare la pagina [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e abilitarla se necessario. Nell'area di lavoro **Gestione funzionalità**, la funzione è elencata nel modo seguente:

- **Modulo** - *Contabilità fornitori*
- **Nome funzionalità** - *Abilita gestione della certificazione per collaborazione con fornitori*

## <a name="add-a-new-certification"></a>Aggiungere una nuova certificazione

Per aggiungere una nuova certificazione, seleziona il pulsante **Aggiungi** che si trova sopra la griglia **Certificazione** nell'area di lavoro **Informazioni fornitore**. Immettere le seguenti informazioni:

- Numero certificazione
- Tipo di certificazione
- Autorità di certificazione
- Data certificazione
- Importo soggettività tributaria, se applicabile
- Data di validità
- Data di scadenza
- Commenti, facoltativi

Se sono presenti documenti relativi alla specifica certificazione, è possibile allegarli selezionando il pulsante **Documento**.

Alle certificazioni immesse dai fornitori in questa pagina verrà assegnata un'origine "Fornitore". Puoi inserire le informazioni sul certificato per conto del tuo fornitore nei conti bancari del fornitore. Le informazioni verranno visualizzate qui e l'origine verrà visualizzata come **Cliente**.

I fornitori possono modificare o eliminare le loro certificazioni secondo necessità.

## <a name="vendor-collaboration-generated-certification-records"></a>Record di certificazioni generate da collaborazione con fornitore

Dopo l'aggiunta delle informazioni sulla certificazione da parte di un fornitore, le informazioni saranno visibili nella pagina **Certificazioni generate da collaborazione con fornitore**. Per aprire la pagina, vai a **Contabilità fornitori > Richieste di informazioni > Report fornitori > Certificazioni generate da collaborazione con fornitore**. Per impostazione predefinita, tutti i record di certificazione nuovi o modificati sono visibili. Un addetto alla contabilità fornitori può visualizzare le modifiche e convalidare le informazioni tramite il processo di conferma per la convalida. Dopo la conferma delle informazioni, il record di certificazione elencato nella pagina può essere selezionato e contrassegnato come esaminato. Quando il record viene contrassegnato come esaminato, viene rimosso dall'elenco predefinito.

Tutte le modifiche alla certificazione sono visibili nella pagina **Certificazioni generate da collaborazione con fornitore**. Se una modifica non viene visualizzata nella pagina, puoi visualizzarla modificando i filtri per il conto fornitore, l'intervallo di date di validità o scegliendo se includere o meno le informazioni per le modifiche alla certificazione che sono state esaminate.

