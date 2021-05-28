---
title: Parametri di approvvigionamento per Costo sbarcato
description: In questo argomento viene descritto come impostare i parametri di approvvigionamento quando si utilizza il modulo Costo sbarcato.
author: sherry-zheng
ms.date: 12/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SrmParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-09
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: ccda3bd769a646e2390711883b8e40bec50e4d6a
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020985"
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
