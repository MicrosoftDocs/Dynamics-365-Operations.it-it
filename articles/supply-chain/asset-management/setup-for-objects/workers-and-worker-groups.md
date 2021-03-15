---
title: Addetti alla manutenzione e gruppi di lavoratori
description: In questo argomento vengono illustrati gli addetti alla manutenzione e i gruppi di lavoratori in Gestione cespiti.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetWorkerGroupCopyFromResourceGroup, EntAssetWorkerGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b81de02f144712786704a46d2096dfb510d5ce68
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2021
ms.locfileid: "5017394"
---
# <a name="maintenance-workers-and-worker-groups"></a>Addetti alla manutenzione e gruppi di lavoratori

[!include [banner](../../includes/banner.md)]

 

In questo argomento vengono illustrati gli addetti alla manutenzione e i gruppi di lavoratori in Gestione cespiti. In Gestione cespiti è possibile collegare gli addetti alla manutenzione alle unità funzionali. Per ulteriori informazioni sulle unità funzionali, vedere [Creare unità funzionali](../functional-locations/create-functional-locations.md). Questa funzionalità può risultare utile se, ad esempio, si programma un processo di manutenzione per una macchina situata nell'unità funzionale 01 e si desidera assegnare addetti alla manutenzione della stessa ubicazione per eseguire il processo.

È inoltre possibile creare gruppi di addetti alla manutenzione e associarvi gli addetti. Questa funzionalità è utile quando si esegue la programmazione semplice degli ordini di lavoro e si desidera programmare un gruppo di addetti alla manutenzione in un ordine di lavoro. È possibile utilizzare gli addetti alla manutenzione e i gruppi di addetti alla manutenzione per impostare addetti alla manutenzione preferiti e addetti alla manutenzione responsabili. 


## <a name="create-workers"></a>Crea lavoratori

1. Selezionare **Gestione cespiti** \> **Impostazione** \> **Lavoratori** \> **Lavoratori**.
2. Selezionare **Nuovo** per aggiungere un lavoratore all'elenco.
3. Selezionare il lavoratore nel campo **Lavoratore**.
4. Impostare **Attivo** su  **Sì** per la programmazione del lavoratore negli ordini di lavoro.

    Nella Scheda dettaglio **Generale**, i campi **Descrizione** e **Risorsa** vengono completati automaticamente se una risorsa è stata selezionata per il lavoratore. Il campo **Calendario** verrà anche compilato automaticamente, a condizione di avere impostato il lavoratore come risorsa e allocato un calendario a tale risorsa nella pagina **Risorse** (**Amministrazione organizzazione** \> **Risorse** \> **Risorse**).

5. Nella Scheda dettaglio **Gruppi**, selezionare **Aggiungi** e quindi selezionare un gruppo di addetti alla manutenzione per il lavoratore. Un lavoratore può essere associato a più di un gruppo.
6. Nell'impostazione standard, il rapporto di un lavoratore con un gruppo è valido a partire dalla data in cui è aggiunto al gruppo e non ha scadenza. Questa data viene visualizzata nel campo **Validità**. Per visualizzare il campo **Validità**, selezionare **Visualizza** \> **Tutti**. Se il rapporto del lavoratore con un gruppo deve essere limitato a un periodo specifico, utilizzare i campi **Validità** e **Scadenza** per definire il periodo.
7. Nella Scheda dettaglio **Unità funzionali**, selezionare **Aggiungi** e quindi selezionare un'unità funzionale per il lavoratore. Inoltre specificare quale ubicazione rappresenta l'unità funzionale principale per il lavoratore.

    > [!NOTE]
    > Quando si aggiungono le unità funzionali al lavoratore, tutti i cespiti attivi correlati alle unità funzionali vengono visualizzati nelle diverse voci di menu, ad esempio **Cespiti attivi personali** e **Unità funzionali attive**. Vengono inoltre visualizzati nelle ricerche cespiti che verranno visualizzate quando si crea un nuovo cespite, richiesta di intervento di manutenzione, o ordine di lavoro.

    I campi nella Scheda dettaglio **Dettagli** indicano il numero di gruppi di addetti alla manutenzione e delle unità funzionali a cui l'addetto alla manutenzione è correlato.

## <a name="create-worker-groups"></a>Creare gruppi di lavoratori

1. Selezionare **Gestione cespiti** \> **Impostazione** \> **Lavoratori** \> **Gruppi di addetti alla manutenzione**.
2. Selezionare **Nuovo** per aggiungere un gruppo di lavoratori all'elenco.
3. Nel campo **Gruppo di addetti alla manutenzione** immettere un ID gruppo.
4. Nel campo **Nome** immettere un nome.
5. Nella Scheda dettaglio **Lavoratori**, selezionare **Aggiungi** e quindi selezionare un addetto alla manutenzione per il gruppo di lavoratori. Per informazioni sui campi **Validità** e **Scadenza**, vedere il passaggio 6 nella procedura precedente.
6. Se un gruppo di risorse deve essere associato al gruppo di addetti alla manutenzione selezionato, selezionare **Copia dal gruppo di risorse**. Nel campo **Gruppo**, selezionare il gruppo di risorse da cui copiare le impostazioni dal calendario. Quindi , nel campo **Gruppo di lavoratori**, selezionare il gruppo di lavoratori in cui copiare le impostazioni del calendario del gruppo di risorse. Questo passaggio è rilevante solo se si desidera che gli addetti alla manutenzione utilizzino il calendario relativo a una risorsa (centro di lavoro) durante la programmazione dell'ordine di lavoro.

    Il campo nella Scheda dettaglio **Dettagli** mostra il numero di addetti alla manutenzione impostati nel gruppo di addetti alla manutenzione selezionato.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]