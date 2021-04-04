---
title: Impostazioni fornitore aggiunte per Costo sbarcato
description: In questo argomento vengono descritti i nuovi campi che vengono aggiunti alla pagina Fornitori esistente quando si abilita il modulo Costo sbarcato. Questi campi sono utilizzati per configurare i fornitori che verranno utilizzati insieme alle funzionalità di Costo sbarcato.
author: sherry-zheng
manager: tfehr
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 8cc0622cd761a671ebb88addc36b777cfefb7dc7
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2021
ms.locfileid: "5500912"
---
# <a name="vendor-settings-added-for-landed-cost"></a>Impostazioni fornitore aggiunte per Costo sbarcato

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Quando si abilita il modulo **Costo sbarcato**, vari nuovi campi vengono aggiunti alla pagina **Fornitori** esistente. Questi campi sono utilizzati per configurare i fornitori che verranno utilizzati insieme alle funzionalità di Costo sbarcato.

Per impostare i campi pertinenti, selezionare **Approvvigionamento \> Fornitori \> Tutti i fornitori**. Aprire un fornitore esistente o crearne uno, quindi selezionare la Scheda dettaglio **Dettagli vari**. Tutti i nuovi campi che il modulo **Costo sbarcato** aggiunge vengono visualizzati nell'intestazione **Viaggi**. Nella seguente tabella vengono descritti questi campi.

| Campo | Descrizione |
|---|---|
| Tipo di spedizione | <p>Selezionare il ruolo del fornitore in relazione a Costo sbarcato:</p><ul><li>**Nessuno** - Il fornitore non ha un ruolo specifico correlato a Costo sbarcato. Questo valore è l'impostazione predefinita poiché la maggior parte dei fornitori probabilmente non avrà un ruolo specifico.</li><li>**Società di spedizioni** - Il fornitore è una società di spedizione. I fornitori che hanno questo tipo di spedizione sono selezionabili nel campo **Società di spedizione** nella pagina **Viaggi**.</li><li>**Broker doganale** - Il fornitore è un broker doganale. I fornitori che hanno questo tipo di spedizione sono selezionabili nel campo **Broker doganale** nella pagina **Registrazioni**.</li><li>**Agente** - Il fornitore è un agente. I fornitori che hanno questo tipo di spedizione sono selezionabili nel campo **Agente** nelle pagine **Fornitori** e **Ordini fornitore**.</li></ul> |
| Gruppo di tipi di costo | Assegnare il fornitore a un gruppo di tipi di costo ai fini della selezione dei [costi automatici](auto-cost-setup.md). |
| Porto di origine | Selezionare il porto di origine del viaggio. |
| Agente | L'agente predefinito quando gli acquisti vengono effettuati presso il venditore. |
| Fornitore determinazione costi di importazione | <p>Indica se il fornitore è un fornitore di Costo sbarcato.</p><p>**Suggerimento:** è possibile utilizzare questo campo insieme alla sicurezza a livello di record per limitare gli ordine fornitore visualizzati quando viene creato un viaggio.</p> |
| Società di spedizione | Selezionare la società di spedizione predefinita utilizzata quando vengono creati ordini fornitore per il fornitore. |
| Provider di servizi | Indica se il fornitore è un provider di servizi. |
| Gruppo di tolleranza eccesso/difetto | Selezionare il gruppo di tolleranza eccesso/difetto predefinito per il fornitore. |
