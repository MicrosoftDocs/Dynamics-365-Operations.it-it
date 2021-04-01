---
title: Configurare una voce di menu del dispositivo mobile per fornire una panoramica della riga di prelievo
description: Questo argomento spiega come definire quando verrà mostrato un elenco di tutte le righe di lavoro ai lavoratori del magazzino che stanno elaborando il lavoro del magazzino su un dispositivo mobile. Questa funzionalità può essere utile per i magazzinieri che spesso richiedono una panoramica delle righe di prelievo in un ordine di lavoro in modo da poter ottimizzare la sequenza di prelievo.
author: MarkusFogelberg
manager: tfehr
ms.date: 09/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2020-09-03
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 22e724b60ec5cc8bf39a520022f43784d3a328eb
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5232913"
---
# <a name="set-up-a-mobile-device-menu-item-to-provide-a-pick-line-overview"></a>Configurare una voce di menu del dispositivo mobile per fornire una panoramica della riga di prelievo

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

In questo argomento viene illustrato come configurare le opzioni correlate alla panoramica delle righe di prelievo per le voci di menu del dispositivo mobile utilizzate per elaborare il lavoro di prelievo. La panoramica delle righe di prelievo consente ai magazzinieri di visualizzare e selezionare da un elenco di tutte le righe di lavoro correlate all'attività corrente. Questa funzionalità può aiutare i lavoratori a ottimizzare la loro sequenza di prelievo. La funzionalità fornisce opzioni che sostituiscono il pulsante **Ignora** standard che consente ai lavoratori di scorrere le righe una alla volta, in un ordine fisso. (Tuttavia, l'opzione per utilizzare quel pulsante è ancora disponibile).

Gli amministratori possono configurare singolarmente ogni voce di menu per controllare come, quando e dove l'app di magazzino presenta la panoramica della riga di prelievo.

## <a name="turn-on-the-work-pick-line-overview-feature"></a>Attivare la funzionalità Panoramica delle righe di prelievo lavoro

Prima di poter utilizzare questa funzione, è necessario attivarla nel sistema. Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e se necessario abilitarla. Nell'area di lavoro **Gestione funzionalità**, la funzione è elencata nel modo seguente:

- **Modulo:** _Gestione magazzino_
- **Nome funzionalità:** _Panoramica delle righe di prelievo lavoro_

## <a name="configure-menu-items-to-show-a-list-of-all-work-lines"></a>Configurare le voci di menu per mostrare un elenco di tutte le righe di lavoro

Per configurare una voce di menu del dispositivo mobile per fornire una panoramica della riga di prelievo, segue questi passaggi.

1. Passare a **Gestione magazzino \> Impostazione \> Dispositivo mobile \> Voci di menu del dispositivo mobile**.
1. Seleziona o crea una voce di menu correlata al lavoro di prelievo e imposta i seguenti valori:

    - **Modalità:** *Lavoro*
    - **Utilizza lavoro esistente:** *Sì*
    - **Diretto da:** *Diretto dall'utente* o *Diretto dal sistema*

    Per altre informazioni su come creare voci di menu e utilizzare le varie impostazioni disponibili nella pagina **Voci di menu del dispositivo mobile**, vedi [Configurare i dispositivi mobili per il lavoro di magazzino](configure-mobile-devices-warehouse.md).

1. Nella Scheda dettaglio **Generale**, configura la funzionalità impostando il campo **Mostra elenco righe di lavoro** su uno dei seguenti valori:

    - **Mostra solo su richiesta**: i lavoratori possono scegliere di visualizzare l'elenco delle righe di prelievo selezionando il pulsante **Passa a** nell'app di magazzino.
    - **Mostra all'inizio di ogni selezione**: i lavoratori visualizzano l'elenco ogni volta che iniziano o finiscono una riga di prelievo. Possono anche visualizzare nuovamente l'elenco selezionando il pulsante **Passa a** nell'app del magazzino.
    - **Mostra solo all'inizio della prima selezione**: i lavoratori vedono l'elenco ogni volta che iniziano nuovi lavori di selezione, ma non dopo ogni riga. Possono anche visualizzare nuovamente l'elenco selezionando il pulsante **Passa a** nell'app del magazzino.
    - **Non mostrare mai**: il pulsante **Ignora** standard viene visualizzato nell'app di magazzino e la visualizzazione dell'elenco delle righe di lavoro è disattivata. Il pulsante **Ignora** consente ai lavoratori di scorrere le righe una alla volta, in un ordine fisso. Possono anche scorrere l'elenco tutte le volte che lo richiedono, finché tutte le righe non sono state elaborate.

1. Nel riquadro azioni selezionare **Salva**.

    Se imposti il campo **Mostra elenco righe di lavoro** su qualsiasi valore tranne *Non mostrare mai*, il pulsante **Elenco campi** diventa disponibile nel riquadro azioni.

1. Nel riquadro azioni seleziona **Elenco campi**.
1. Nella pagina **Elenco campi**, configura le informazioni che l'app di magazzino mostra per ogni riga nell'elenco.

    - Il campo **Controllo primario** è sempre impostato su *LineNum*. Pertanto, ogni riga nell'elenco inizia con un numero di riga.
    - Utilizza i campi **Campo di visualizzazione** restanti per aggiungere fino a sette campi di visualizzazione aggiuntivi, come richiesto. In ciascun campo **Campo di visualizzazione**, seleziona il nome di un campo della riga di lavoro. Ogni riga mostrerà quindi un valore per quel campo. I valori verranno visualizzati nell'ordine selezionato qui. Puoi lasciare alcuni dei campi **Campo di visualizzazione** vuoti se non si richiedono tutti e sette i valori.

1. Nel riquadro azioni, seleziona **Salva**, quindi chiudi la pagina **Elenco campi**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]