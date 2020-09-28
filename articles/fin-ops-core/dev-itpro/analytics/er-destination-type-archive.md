---
title: Tipo di destinazione archivio ER
description: In questo argomento vengono fornite informazioni su come configurare una destinazione archivio per ogni componente CARTELLA o FILE di un formato ER configurato per generare documenti in uscita.
author: NickSelin
manager: AnnBe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 8797a68507a5116c6adbf1f2d805838fa507958c
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745587"
---
# <a name="archive-destination"></a>Destinazione archivio

[!include [banner](../includes/banner.md)]

È possibile configurare una destinazione archivio per ogni componente CARTELLA o FILE di un formato ER configurato per generare documenti in uscita. In base all'impostazione di destinazione, un documento generato viene archiviato come allegato di un record dell'elenco di processi ER.

È possibile utilizzare questa opzione per inviare il documento generato a una cartella di Microsoft SharePoint o Archiviazione di Microsoft Azure. Impostare **Abilitato** su **Sì** per inviare l'output a una destinazione definita dal tipo di documento selezionato. Solo tipi di documento in cui il gruppo è impostato su **File** sono disponibili per la selezione. I [tipi](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management#configure-document-types) di documento vengono definiti in **Amministrazione organizzazione** \> **Gestione documenti** \> **Tipi di documento**. La configurazione per le destinazioni ER è lo stessa della configurazione del sistema di gestione documenti.

[![Pagina Tipi di documento](./media/ER_Destinations-SharePointDocuType.png)](./media/ER_Destinations-SharePointDocuType.png)

Il percorso posizione determina dove viene salvato il file. Una volta abilitata la destinazione **Archivio**, i risultati possono essere salvati nell'archivio processi. È possibile visualizzare i risultati in **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Processi archiviati di creazione report elettronici**.

> [!NOTE]
> Selezionare un tipo di documento per l'archivio processi selezionando **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici** \> **Parametri per la creazione di report elettronici**. Per ulteriori informazioni, vedere [Configurare il framework di report elettronici (ER)](electronic-reporting-er-configure-parameters.md#prerequisites-for-er-setup).

## <a name="sharepoint"></a>SharePoint

È possibile salvare un file in una cartella designata di SharePoint. Per definire il server di SharePoint predefinito selezionare **Amministrazione organizzazione** \> **Gestione documenti** \> **Parametri di gestione documenti**. Nella scheda **SharePoint** configurare la cartella di SharePoint. Quindi, è possibile selezionarla come cartella in cui verrà salvato l'output ER. La posizione **SharePoint** deve essere selezionata in questo tipo di documento.

[![Selezione di una cartella SharePoint](./media/ER_Destinations-SharePointDocuTypeLocation.png)](./media/ER_Destinations-SharePointDocuTypeLocation.png)

## <a name="azure-storage"></a>Archiviazione di Azure

Quando il percorso del tipo di documento è impostato su **Archiviazione di Azure**, è possibile salvare un file in Archiviazione di Azure.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Panoramica dei report elettronici](general-electronic-reporting.md)
- [Destinazioni dei report elettronici](electronic-reporting-destinations.md)
- [Configurare la gestione dei documenti](../../fin-ops/organization-administration/configure-document-management.md)
