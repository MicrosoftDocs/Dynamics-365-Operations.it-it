---
title: Tipo di destinazione archivio ER
description: Questo articolo fornisce informazioni su come configurare una destinazione di archivio per ogni componente FOLDER o FILE di un formato di creazione di report elettronici (ER).
author: kfend
ms.date: 11/30/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.custom: 97423
ms.assetid: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
ms.openlocfilehash: d907bf391c0629d62da489cea90a05eabaf69ef1
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9285457"
---
# <a name="archive-er-destination-type"></a>Tipo di destinazione archivio ER

[!include [banner](../includes/banner.md)]

È possibile configurare una destinazione archivio per ogni componente **Cartella** o **File** di un formato ER configurato per generare documenti in uscita. In base all'impostazione di destinazione, un documento generato viene archiviato come allegato di un record dell'elenco di processi ER. Per visualizzare i risultati, andare su **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Processi di creazione report elettronici**.

È possibile utilizzare questa opzione per inviare il documento generato a una cartella di Microsoft SharePoint o Archiviazione di Microsoft Azure. Impostare **Abilitato** su **Sì** per inviare l'output a una destinazione definita dal tipo di documento selezionato. Solo tipi di documento in cui il gruppo è impostato su **File** sono disponibili per la selezione. I [tipi](../../fin-ops/organization-administration/configure-document-management.md#configure-document-types) di documento vengono definiti in **Amministrazione organizzazione** \> **Gestione documenti** \> **Tipi di documento**. La configurazione per le destinazioni ER è lo stessa della configurazione del sistema di gestione documenti.

[![Pagina Tipi di documento.](./media/ER_Destinations-SharePointDocuType.png)](./media/ER_Destinations-SharePointDocuType.png)

Il percorso posizione determina dove viene salvato il file. Una volta abilitata la destinazione **Archivio**, i risultati possono essere salvati nell'archivio processi. È possibile visualizzare i risultati in **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Processi archiviati di creazione report elettronici**.

> [!NOTE]
> Selezionare un tipo di documento per l'archivio processi selezionando **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici** \> **Parametri per la creazione di report elettronici**. Per ulteriori informazioni, vedere [Configurare il framework di report elettronici (ER)](electronic-reporting-er-configure-parameters.md#prerequisites-for-er-setup).

## <a name="sharepoint"></a>SharePoint

È possibile salvare un file in una cartella designata di SharePoint. Per definire il server di SharePoint predefinito selezionare **Amministrazione organizzazione** \> **Gestione documenti** \> **Parametri di gestione documenti**. Nella scheda **SharePoint** configurare la cartella di SharePoint. Quindi, è possibile selezionarla come cartella in cui verrà salvato l'output ER. La posizione **SharePoint** deve essere selezionata in questo tipo di documento.

[![Selezione di una cartella di SharePoint.](./media/ER_Destinations-SharePointDocuTypeLocation.png)](./media/ER_Destinations-SharePointDocuTypeLocation.png)

## <a name="azure-storage"></a>Archiviazione di Azure

Quando il percorso del tipo di documento è impostato su **Archiviazione di Azure**, è possibile salvare un file in Archiviazione di Azure.

> [!NOTE] 
> Il framework ER archivia in modo permanente i file nell'archiviazione BLOB di Azure a differenza del Framework di gestione dei dati che applica i criteri di conservazione di sette giorni per i documenti che devono essere elaborati. Per ulteriori informazioni, vedere [API per ottenere lo stato del messaggio](../data-entities/recurring-integrations.md#api-for-getting-message-status) e [API di controllo dello stato](../data-entities/data-management-api.md#status-check-api). I file correlati a ER verranno archiviati nell'archivio BLOB di Azure come allegati dei record della tabella dell'applicazione per tutto il tempo necessario. Un singolo file verrà eliminato dall'archiviazione BLOB di Azure insieme al record della tabella dell'applicazione a cui era allegato il file.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Panoramica dei report elettronici](general-electronic-reporting.md)
- [Destinazioni dei report elettronici](electronic-reporting-destinations.md)
- [Configurare la gestione dei documenti](../../fin-ops/organization-administration/configure-document-management.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
