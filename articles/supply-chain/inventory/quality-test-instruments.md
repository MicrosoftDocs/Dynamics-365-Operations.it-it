---
title: Strumenti di test di gestione qualità
description: Questo argomento descrive come creare strumenti di test che possano essere utilizzati per i test in ordini di controllo qualità in Microsoft Dynamics 365 Supply Chain Management.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestInstrument
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 39624a9f00829e551fe3790a024155b6104318ef5cc1c582ab263c3868462063
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6774104"
---
# <a name="quality-management-test-instruments"></a>Strumenti di test di gestione qualità

[!include [banner](../includes/banner.md)]

Questo argomento descrive come creare strumenti di test che possano essere utilizzati per i test in ordini di controllo qualità in Microsoft Dynamics 365 Supply Chain Management.

Utilizza la pagina **Strumenti di test** per definire e visualizzare i dettagli sui dispositivi utilizzati per eseguire i test sugli ordini di controllo qualità. Gli strumenti di test sono facoltativi. Tuttavia, possono aiutare gli addetti al controllo qualità a sapere quale dispositivo o strumento dovrebbero utilizzare per eseguire un test specifico.

## <a name="test-instrument-example"></a>Esempio di strumento di test

Stai eseguendo vari test su componenti elettrici. Alcuni test riguardano la tensione di uscita dei componenti, un test è per la loro temperatura e un test è per il loro peso. Per eseguire ogni test vengono utilizzati strumenti, dispositivi o apparecchiature diversi. Ad esempio, un voltmetro viene utilizzato per misurare la tensione, un termometro viene utilizzato per misurare la temperatura e una bilancia viene utilizzata per misurare il peso. È possibile configurare ciascuno di questi dispositivi come uno strumento di test e indicare l'unità di misura in cui devono essere registrati i risultati del test. Ad esempio, i risultati del voltmetro vengono registrati in volt, i risultati del termometro vengono registrati in gradi Fahrenheit o gradi Celsius e i risultati della bilancia vengono registrati in libbre o chilogrammi.

## <a name="create-a-test-instrument"></a>Creare uno strumento di test

1. Andare a **Gestione articoli \> Impostazioni \> Controllo qualità \> Strumenti di test**.
1. Nel riquadro azioni seleziona **Nuova** per aggiungere una riga alla griglia. Quindi imposta i seguenti campi per la nuova riga:

    - **Strumento di test** – Immetti un ID o nome univoco per lo strumento di test.
    - **Descrizione** - Immettere una descrizione dettagliata dello strumento di test.
    - **Unità** - Selezionare l'unità in cui lo strumento misura i risultati. Il campo **Precisione** viene impostato automaticamente, in base all'unità selezionata.

1. Chiudere la pagina.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Test di gestione qualità](quality-tests.md)
- [Gruppi di test di gestione qualità](quality-test-groups.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
