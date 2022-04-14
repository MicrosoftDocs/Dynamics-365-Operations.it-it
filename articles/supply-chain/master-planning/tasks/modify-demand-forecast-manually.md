---
title: 'Guida: modificare una previsione della domanda manualmente'
description: Questo argomento descrive come modificare la previsione per un articolo
author: t-benebo
ms.date: 08/12/2019
ms.topic: business-process
ms.search.form: EcoResProductDetailsExtended, ForecastSales
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1e5030bf97bee8dc475f22473ecc87e900298b6f
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2022
ms.locfileid: "8469378"
---
# <a name="guide-modify-a-demand-forecast-manually"></a>Guida: modificare una previsione della domanda manualmente

[!include [banner](../../includes/banner.md)]

Questa procedura illustra come modificare la previsione per un articolo. Questa procedura è destinata al responsabile pianificazione produzione.

## <a name="modify-the-forecast-for-a-selected-item"></a>Modificare la previsione per un articolo selezionato

Per modificare la previsione per un articolo selezionato:

1. Selezionare **Moduli \> Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.
1. Nell'elenco trovare e selezionare il record desiderato. Selezionare l'articolo per cui si desidera modificare la previsione.
1. Nel riquadro azioni aprire la scheda **Piano** e selezionare **Previsione della domanda**.
1. Nell'elenco selezionare una riga. Se non sono presenti righe di previsione, creare una nuova riga selezionando **Nuova** nel riquadro azioni.  
1. Nel campo **Quantità di vendita** immettere un numero positivo. Questo numero rappresenta la quantità prevista per l'articolo. Se si inserisce un numero negativo, verrà visualizzato un errore.
1. Compilare gli altri campi come necessario.
1. Nel riquadro azioni selezionare **Salva**.

## <a name="modify-the-forecast-for-one-or-more-items-with-microsoft-excel"></a>Modificare la previsione per uno o più elementi con Microsoft Excel

Per modificare la previsione per uno o più elementi con Microsoft Excel:

1. Effettuare una delle seguenti operazioni:
    - Aprire la pagina **Previsione della domanda** per qualsiasi articolo (non importa quale) come descritto nella sezione precedente.
    - Selezionare **Pianificazione generale \> Previsioni \> Voce di previsione \> Righe di previsione della domanda**.
1. Nel riquadro azioni selezionare **Apri in Microsoft Office \> Voci di previsione della domanda**.
1. Selezionare un percorso di download, salvare e quindi aprire il file scaricato in Excel.
1. Se viene visualizzato un avviso, scegliere **Abilita modifica**.
1. In Excel, accedere a Supply Chain Management utilizzando il riquadro attività Microsoft Dynamics. È necessario accedere con l'opzione **Mantieni connesso** abilitata e considerare attendibile l'app per la connessione dati.
1. Il foglio di calcolo Excel ora mostra tutte le righe di previsione della domanda corrente per l'azienda.  Aggiungere, eliminare e modificare le righe di previsione della domanda come necessario.
1. Selezionare **Pubblica** nel riquadro delle attività di Microsoft Dynamics per caricare nuovamente le modifiche in Supply Chain Management.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
