---
title: Impostazioni fornitore aggiunte per Costo sbarcato
description: In questo argomento vengono descritti i nuovi campi che vengono aggiunti alla pagina Fornitori esistente quando si abilita il modulo Costo sbarcato. Questi campi sono utilizzati per configurare i fornitori che verranno utilizzati insieme alle funzionalità di Costo sbarcato.
author: Weijiesa
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: VendTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: b4e02397f7a4cdeaa21b451268b16e4fbe773612
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2022
ms.locfileid: "8690528"
---
# <a name="vendor-settings-added-for-landed-cost"></a>Impostazioni fornitore aggiunte per Costo sbarcato

[!include [banner](../../includes/banner.md)]

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
