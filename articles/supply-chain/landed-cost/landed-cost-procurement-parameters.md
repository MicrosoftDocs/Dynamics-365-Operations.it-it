---
title: Parametri di approvvigionamento per Costo sbarcato
description: In questo articolo viene descritto come impostare i parametri di approvvigionamento quando si utilizza il modulo Costo sbarcato.
author: Weijiesa
ms.date: 12/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SrmParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2020-12-09
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 92ce3e3d09bed15970375735f680b1b8348bbca8
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8905981"
---
# <a name="procurement-and-sourcing-parameters-for-landed-cost"></a>Parametri di approvvigionamento per Costo sbarcato

[!include [banner](../../includes/banner.md)]

La pagina **Parametri di approvvigionamento** ha alcune impostazioni che sono particolarmente pertinenti quando si utilizza il modulo **Costo sbarcato**. Utilizzare la finestra di dialogo **Aggiorna righe ordine** che viene aperta dalla pagina **Parametri di approvvigionamento** per specificare se le righe dell'ordine fornitore devono essere aggiornate automaticamente quando vengono apportate modifiche all'intestazione dell'ordine fornitore.

Per completare questa impostazione, attenersi alla procedura seguente.

1. Passare a **Approvvigionamento \> Impostazione \> Parametri di approvvigionamento**.
1. Nella scheda **Generale**, selezionare il collegamento **Aggiorna righe ordine**.
1. La finestra di dialogo **Aggiorna righe ordine** elenca i campi nell'intestazione dell'ordine che possono anche applicare aggiornamenti automatici ai campi correlati nelle righe ordine. Impostare ogni campo nell'elenco su uno dei seguenti valori:

    - **Sempre** - Le righe ordine devono essere aggiornate automaticamente quando l'intestazione ordine viene aggiornata.
    - **Mai** - Le righe ordine non devono mai essere aggiornate quando l'intestazione dell'ordine viene aggiornata.
    - **Richiesta** - All'utente verrà chiesto se le righe ordine devono essere aggiornate.
