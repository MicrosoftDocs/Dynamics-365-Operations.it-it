---
title: Creare un cespite
description: In questo articolo viene illustrato come creare un nuovo record di cespite dalla pagina elenco Cespite.
author: moaamer
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable, AssetBook
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 00c72081d20015737aa027cee9474a54e498cef4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8868491"
---
# <a name="create-a-fixed-asset"></a>Creare un cespite

[!include [banner](../../includes/banner.md)]

In questo articolo viene illustrato come creare un nuovo record di cespite dalla pagina elenco **Cespite**.

Il sistema assegna il numero di cespite, in base alla sequenza numerica assegnata al gruppo di cespiti. Se si utilizza il modello di cespite per importare cespiti tramite il componente aggiuntivo per Microsoft Excel o se si utilizza un altro processo di importazione, il sistema crea automaticamente record di cespiti e incrementa il numero di cespite.

Per creare manualmente un record di cespite, seguire questi passaggi.

1. Andare a **Pannello di navigazione \> Moduli \> Cespiti \> Cespiti \> Cespiti**.
2. Nel **Riquadro azioni** selezionare **Nuovo**.
3. Nel campo **Gruppo cespite** immettere o selezionare un valore. Il campo **Numero** verrà impostato come predefinito se è stata attivata la funzionalità **Numerazione automatica cespiti** nei parametri **Cespiti** e **Gruppo cespite**. In caso contrario, è necessario immettere un numero univoco per identificare il cespite.
4. Nel campo **Nome** immettere un valore. Immettere le informazioni aggiuntive relative al cespite necessarie per l'azienda.
5. Nel **riquadro azioni** selezionare **Libri**.
6. Immettere una data nel campo **Data di acquisizione**.
7. Immettere un numero nel campo **Prezzo di acquisizione**.

    - Immettere le informazioni aggiuntive relative al cespite necessarie per il libro.
    - Immettere le informazioni aggiuntive relative ai libri rimanenti necessarie per l'azienda.

8. Chiudere la pagina.

È inoltre possibile importare i cespiti utilizzando il componente aggiuntivo per Excel o eseguendo un processo di importazione dall'area di lavoro **Gestione dei dati**. Prima di eseguire l'importazione, immettere i valori nei campi obbligatori del modello.

Se non è stato definito il numero di cespite nel modello del componente aggiuntivo per Excel o in Gestione dei dati, il sistema crea un numero di cespite per ogni cespite importato e incrementa automaticamente la sequenza numerica per ciascuno di essi. Tuttavia, se si importano cespiti e si definiscono i numeri di cespite nel modello, il sistema **non** incrementa automaticamente la sequenza numerica. In questo caso, un amministratore potrebbe dover aggiornare manualmente la sequenza numerica. Se è stato definito il numero di cespite nel modello del componente aggiuntivo per Excel, il sistema utilizza il numero di cespite definito e incrementa la sequenza numerica.

> [!NOTE]                                                                                                         
> Dopo aver registrato l'ammortamento, i campi **Messa in servizio** e **Data di esecuzione ammortamento** verranno bloccati nella pagina **Libro**. Inoltre, entrambi i campi non verranno aggiornati dall'entità di dati.

> [!WARNING]
> Il record del cespite non verrà eliminato se le transazioni sono state registrate nel libro associato o se il cespite appena creato viene immesso in una riga di giornale di registrazione ma non registrato. 


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
