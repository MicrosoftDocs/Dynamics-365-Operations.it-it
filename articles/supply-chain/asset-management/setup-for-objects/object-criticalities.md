---
title: Tipi di criticità dei cespiti
description: L'argomento descrive i tipi di criticità dei cespiti in Gestione cespiti.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetCriticality, EntAssetObjectCriticality
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4b7d6e3dea1b3c1ef47490df678f639c036cdd5c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431058"
---
# <a name="asset-criticality-types"></a>Tipi di criticità dei cespiti

[!include [banner](../../includes/banner.md)]

 

L'argomento descrive i tipi di criticità dei cespiti in Gestione cespiti. La criticità dei cespiti è correlata ai cespiti e viene trasferita agli ordini di lavoro. Non può essere modificata in un ordine di lavoro. La criticità dei cespiti viene utilizzata per calcolare la criticità dell'ordine di lavoro durante la programmazione dell'ordine di lavoro. Ovvero, è utilizzata per calcolare la misura in cui un processo di manutenzione di un cespite influisce sulla programmazione di produzione e la produttività della società. Per ulteriori informazioni sull'impostazione relativa al calcolo dei punteggi di valutazione per la programmazione degli ordini di lavoro, vedere [Parametri di Gestione cespiti](../setup-for-objects/enterprise-asset-management-parameters.md).

Per impostare la criticità, è necessario innanzitutto creare i tipi di criticità che devono essere utilizzati nell'impostazione del cespite. Si imposteranno quindi le criticità dei cespiti.

## <a name="set-up-criticality-types"></a>Impostare i tipi di criticità

1. Selezionare **Gestione cespiti** \> **Impostazione** \> **Cespiti** \> **Tipi di criticità**.
2. Selezionare **Nuovo** per creare un record.
3. Nel campo **Criticità**, immettere un numero che indica la criticità.
4. Nel campo **Nome** immettere un nome per il tipo di criticità.
5. Nel campo **Fattore** immettere un fattore. Il fattore viene utilizzato durante il calcolo della programmazione dell'ordine di lavoro per determinare il record di criticità da utilizzare. Il record con il più alto fattore viene utilizzato sempre. Questa impostazione è rilevante se, come illustrato nella figura seguente, righe di criticità vengono create con lo stesso valore di criticità.

    ![Pagina Tipi di criticità](media/23-setup-for-objects.png)

## <a name="set-up-asset-criticalities"></a>Impostare la criticità cespiti

1. Selezionare **Gestione cespiti** \> **Impostazione** \> **Criticità cespiti**.
2. Selezionare **Nuovo** per creare un record.
3. A seconda del livello di dettaglio necessario per la criticità cespiti, selezionare opzioni appropriate nei campi **Unità funzionale**, **Tipo di cespite**, **Produttore**, **Modello**, **Cespite**, **Categoria tipo di processo**, **Tipo di processo**, **Variante tipo di processo** e **Fabbisogno processo**.

    > [!NOTE]
    > Quando una criticità cespiti è selezionata, Gestione cespiti analizza tutti i record di criticità cespiti per verificare la presenza di una corrispondenza possibile. Controlla sempre la combinazione più specifica per prima. In altre parole, Gestione cespiti controlla prima **Fabbisogno processo**. Se non trova corrispondenza, controlla **Variante tipo di processo**. Se non trova corrispondenza, controlla **Tipo di processo** e così via. Come si vede nel layout della pagina, questo comportamento significa che, per individuare la combinazione più specifica, Gestione cespiti controlla ogni record da destra a-sinistra per una corrispondenza. Se non viene trovata alcuna corrispondenza, il record "predefinito" senza selezioni viene utilizzato.

4. Nel campo  **Criticità**, selezionare uno dei valori di criticità creati nella procedura precedente.

### <a name="notes-about-criticality-setup"></a>Note sull'impostazione di criticità

- Se si modifica una criticità cespiti in questa impostazione dopo che è stata già utilizzata in un ordine di lavoro, la criticità nell'ordine di lavoro non viene aggiornata di conseguenza.
- La criticità in un ordine di lavoro viene ricalcolata ogni volta in cui una riga di ordine di lavoro viene aggiunta o eliminatq dall'ordine di lavoro.
- Se un ordine di lavoro contiene più processi dell'ordine di lavoro, la più alta criticità, a seconda del campo **Fattore** della pagina **Tipi di criticità**, è sempre utilizzata nell'ordine di lavoro.
- In genere, la criticità cespiti può cambiare in un periodo. La criticità può essere influenzata dall'acquisto di nuova apparecchiatura, rinnovamenti, e così via. Si consiglia di rivalutare le criticità dei cespiti a intervalli regolari, (ad esempio una volta l'anno o ogni due anni) per assicurarsi che le definizioni di criticità corrispondano alla impostazione di produzione corrente.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]