---
title: Test di gestione qualità
description: Questo argomento descrive come creare test che possano essere utilizzati per gli ordini di controllo qualità in Microsoft Dynamics 365 Supply Chain Management.
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
ms.openlocfilehash: c10b67f86fc29b5e8c08081a9b789d4f42c24cf4
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7573851"
---
# <a name="quality-management-tests"></a>Test di gestione qualità

[!include [banner](../includes/banner.md)]

Questo argomento descrive come creare test che possano essere utilizzati per gli ordini di controllo qualità in Microsoft Dynamics 365 Supply Chain Management.

Utilizzare la pagina **Test** per definire e visualizzare i singoli test che determinano se i prodotti sono conformi alle specifiche di qualità. È possibile assegnare uno o più test singoli a un gruppo di test. In questo caso, è inoltre necessario specificare le informazioni specifiche del test, ad esempio i valori di misura accettabili. I valori di misurazione vengono utilizzati per i test quantitativi. Per i test qualitativi, vengono utilizzate le variabili di test.

- Per test quantitativi, il campo **Tipo** è impostato su *Frazione* o *Intero*. È anche specificata un'unità di misura. Le specifiche di qualità e i risultati del test vengono espressi sotto forma di numeri.
- Per i test qualitativi, il campo **Tipo** è impostato su *Opzione*. I test qualitativi richiedono informazioni aggiuntive sulla variabile di test misurata e sulle relative opzioni enumerate. Le specifiche di qualità e i risultati del test vengono espressi in base a un esito.

È possibile assegnare facoltativamente uno strumento di test a un test. Tuttavia, gli strumenti di test non sono obbligatori per creare e utilizzare i test con gli ordini di controllo qualità. Per ulteriori informazioni, vedere [Strumenti di test di gestione qualità](quality-test-instruments.md).

È anche possibile specificare facoltativamente un'unità per un test, per indicare l'unità di misura in cui vengono registrati i risultati del test. Ad esempio, un test per la temperatura potrebbe includere un'unità di gradi Fahrenheit o gradi Celsius.

## <a name="example-of-a-test"></a>Esempio di un test

Una società di produzione esegue due test sul materiale acquistato, ovvero un test quantitativo sulla qualità del materiale e un test qualitativo sul danno all'imballaggio. La società specifica informazioni aggiuntive sul test qualitativo per definire la variabile di test (ad esempio, per l'imballaggio danneggiato), e i relativi risultati. La società utilizza la pagina **Gruppi di test** per assegnare i due test a un gruppo di test e per specificare le informazioni specifiche del test. Il gruppo di test viene assegnato a un ordine di controllo qualità, in modo che la società possa creare un report per i risultati dei due test.

## <a name="create-a-test"></a>Creare un test

Per creare un test, effettuare le seguenti operazioni.

1. Andare a **Gestione articoli \> Impostazioni \> Controllo qualità \> Test**.
1. Nel riquadro azioni seleziona **Nuova** per aggiungere una riga alla griglia. Quindi imposta i seguenti campi per la nuova riga:

    - **Test** – Immetti un ID o nome univoco per il test.
    - **Descrizione** - Immettere una descrizione dettagliata del test.
    - **Tipo** - Seleziona il tipo di risultati che il test produce. Per i test quantitativi, selezionare *Frazione* o *Intero*. Per i test qualitativi, selezionare *Opzione*.
    - **Strumento di test** - Selezionare uno [strumento di test](quality-test-instruments.md) da utilizzare per il test.
    - **Unità** - Se hai selezionato *Frazione* o *Intero* nel campo **Tipo** (ovvero, se il test è un test quantitativo), selezionare l'unità di misura in cui devono essere registrati i risultati del test.

1. Chiudere la pagina.

> [!NOTE]
> Dopo aver salvato un test, non è più possibile modificare il campo **Tipo** nella griglia. Se è necessario modificare il tipo di risultati del test che verranno registrati per un test, selezionare **Cambia tipo di test qualità** nel riquadro azioni. Nella finestra di dialogo **Cambia tipo di test qualità**, impostare il campo **Nuovo tipo** sul tipo desiderato, quindi selezionare **OK** per chiudere la finestra di dialogo.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Strumenti di test di gestione qualità](quality-test-instruments.md)
- [Gruppi di test di gestione qualità](quality-test-groups.md)
- [Variabili di test di gestione qualità](quality-test-variables.md)
- [Associazioni di controllo qualità](quality-associations.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
