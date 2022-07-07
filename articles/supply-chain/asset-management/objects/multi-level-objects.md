---
title: Cespiti multilivello
description: In questo articolo viene descritto come creare ed eliminare i cespiti multilivello.
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5b13db8b8b12aaef2e067f9a55eb8754333eb16b
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2022
ms.locfileid: "9017147"
---
# <a name="multi-level-assets"></a>Cespiti multilivello

[!include [banner](../../includes/banner.md)]

 

In questo articolo viene descritto come creare ed eliminare i cespiti multilivello. È possibile creare i cespiti e cespiti secondari correlati in una struttura gerarchica. In questo modo, è possibile visualizzare le relazioni e le dipendenze tra i cespiti. I processi di manutenzione possono essere correlati a tutti i livelli della struttura. Possono inoltre essere create statistiche per un singolo livello o come somma di tutti i livelli dei cespiti secondari.

Nella pagina elenco **Tutti i cespiti** (**Gestione cespiti** \> **Cespiti** \> **Tutti i cespiti**), la colonna **Cespite** elenca i cespiti nell'ordine gerarchico. Nella colonna **Padre** viene visualizzato il padre correlato. Inoltre, se i cespiti e i cespiti secondari sono già stati creati, la sezione **Struttura cespiti** nel riquadro **Informazioni correlate** mostra i cespiti in una struttura.

Per informazioni sulla modalità di creazione dei cespiti, vedere [Creare un cespite](../objects/create-an-object.md). Per creare un cespite secondario, selezionare il cespite padre nel campo **Padre** della scheda dettaglio **Generale**.

## <a name="copy-an-asset-or-asset-structure"></a>Copiare un cespite o una struttura di cespiti

Se la società ha più strutture di cespiti simili, è possibile utilizzare la funzione di copia in Gestione cespiti per crearli rapidamente.

1. Seleziona **Gestione cespiti** \> **Cespiti** \> **Tutti i cespiti**.
2. Nella pagina elenco **Tutti i cespiti**, selezionare il cespite da copiare. Ad esempio, per copiare l'intera struttura di cespiti, inclusi i cespiti secondari, selezionare un cespite padre.
3. Selezionare **Copia cespite**. Nella sezione **Copia da**, il campo **Cespite** è impostato sul cespite selezionato nella pagina elenco.
4. Nella sezione **Copia in**, nel campo **Cespite**, immettere il nome del nuovo cespite.
5. Se il cespite che si sta creando deve fare parte di una struttura di cespiti esistente, nella sezione **Cespite padre**, nel campo **Cespite**, selezionare un ID padre.
6. Selezionare **OK**. La nuova struttura di cespiti viene visualizzata nella pagina elenco **Tutti i cespiti**. Tutti gli attributi cespite, piani di manutenzione e cicli di manutenzione relativi al cespite copiato verranno trasferiti al nuovo cespite o struttura del cespite.

Quando si copia una struttura di cespiti, i cespiti secondari nella nuova struttura hanno lo stesso nome dei cespiti secondari copiati. Al termine della procedura di copia, è possibile cambiare facilmente il nome e altre impostazioni di un cespite. Selezionare il cespite nella pagina elenco **Tutti i cespiti** e quindi fare clic sul pulsante **Modifica**.

> [!NOTE]
> Quando si copia un cespite o struttura di cespiti, lo stato del ciclo di vita di nuovi cespiti viene reimpostato su qualsiasi stato è definito come stato iniziale del ciclo di vita dei cespiti. L'unità funzionale viene reimpostata sull'unità funzionale predefinita.

## <a name="delete-an-asset-or-asset-structure"></a>Eliminare un cespite o una struttura di cespiti

Se un cespite ha cespiti secondari correlati, è possibile eliminarlo solo se non sono presenti richieste di intervento di manutenzione, processi di ordine di lavoro, registrazioni di problemi, o valutazioni delle condizioni registrate in uno dei cespiti.

1. Nella pagina elenco **Tutti i cespiti**, selezionare il cespite da eliminare.
2. Selezionare **Elimina**.

> [!NOTE]
> Se non è possibile eliminare un cespite utilizzando questa procedura, un altro metodo per gestire l'eliminazione è di impostare uno stato del ciclo di vita del cespite a questo scopo. Ad esempio, è possibile impostare uno stato del ciclo di vita su **Eliminato** o **Rottamato** nella pagina **Stati del ciclo di vita del cespite**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]