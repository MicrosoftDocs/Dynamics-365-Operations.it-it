---
title: Pulizia della migrazione ER
description: Questo articolo spiega come è possibile utilizzare la funzione di pulizia della migrazione ER per risolvere i problemi con i modelli ER.
author: kfend
ms.date: 04/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2018-01-01
ms.dyn365.ops.version: AX 8.0.0
ms.custom: ''
ms.assetid: ''
ms.search.form: ERSolutionTable, ERWorkspace, ERParameters, ERMigrationCleanup
ms.openlocfilehash: bf32981ed5f43647038018bf2cd98e55ce233b3f
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9285093"
---
# <a name="er-migration-cleanup"></a>Pulizia della migrazione ER 

[!include[banner](../includes/banner.md)]

Quando si gestiscono le istanze di Finance, è possibile decidere di migrare l'istanza corrente in un'altra posizione. Ad esempio, si potrebbe migrare l'istanza di produzione a un nuovo ambiente sandbox. Se il framework di creazione di report elettronici (ER) è stato configurato per archiviare modelli in Archiviazione BLOB di Microsoft Azure, la tabella **DocuValue** nel nuovo ambiente sandbox fa riferimento all'istanza di archiviazione BLOB nell'ambiente di produzione. Tuttavia, non è possibile accedere a questa istanza dall'ambiente sandbox, in quanto il processo di migrazione non supporta la migrazione di elementi nell'archiviazione BLOB. È invece necessario che nel nuovo ambiente sandbox si faccia riferimento all'istanza di archiviazione BLOB nell'ambiente sandbox che non ottiene ancora i modelli ER.

Se si tenta di eseguire un formato ER che utilizza un modello per generare documenti aziendali, si verifica un'eccezione e si riceve una notifica relativa al modello mancante. Vengono inoltre fornite informazioni sull'utilizzo dell'opzione di pulizia della migrazione ER per eliminare e quindi reimportare la configurazione di formato ER che contiene il modello.

[![Esecuzione di un formato ER.](./media/er-migration-cleanup-run.png)](./media/er-migration-cleanup-run.png)

Verrà restituito un errore simile se si accede alla pagina **Configurazioni** (**Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**). Nella struttura delle configurazioni provare dunque a eliminare una configurazione di formato ER che utilizza un modello.

[![Eliminazione di un formato ER.](./media/er-migration-cleanup-delete.png)](./media/er-migration-cleanup-delete.png)

Completare i seguenti passaggi per risolvere i problemi con i modelli ER a cui non è possibile accedere.

1.  Andare alla pagina **Amministrazione organizzazione** \> **Periodico** \> **Pulizia migrazione**.
2.  Selezionare una configurazione di formato ER che non può essere eseguita o eliminata.
3.  Selezionare **Elimina**.
4.  Confermare l'eliminazione della configurazione di formato ER selezionata.
5.  [Importare](download-electronic-reporting-configuration-lcs.md) la configurazione di formato ER eliminata nell'istanza Finance corrente.

## <a name="applicability"></a>Applicabilità

> [Importante] L'opzione di **pulizia della migrazione** è destinata solo alle configurazioni di formato ER che contengono modelli ER non accessibili. Quando si elimina una configurazione di formato ER utilizzando l'opzione di **pulizia della migrazione**, ER elimina i modelli correlati agli elementi di configurazione nell'unico database dell'applicazione. L'esistenza dei file fisici appropriati nell'archiviazione BLOB non viene convalidata. Si presuppone invece che non siano presenti tali file. Non utilizzare pertanto l'opzione di **pulizia della migrazione** in alternativa all'opzione di eliminazione della configurazione ER nella pagina **Configurazioni**. Utilizzare l'opzione di **pulizia della migrazione** solo se l'uso dell'opzione di eliminazione della configurazione ER nella pagina **Configurazioni** ha esito negativo.
>
> Se si utilizza l'opzione di **pulizia della migrazione** per eliminare una configurazione di formato ER quando il modello a cui viene fatto riferimento è disponibile nell'archiviazione BLOB, vengono eliminati solo gli elementi di configurazione correlati nel database dell'applicazione. Il file fisico del modello nell'archivio BLOB viene mantenuto. La sovrascrittura dei file nell'archiviazione BLOB non è più consentita. Per ulteriori informazioni, vedere [KB4557217](https://fix.lcs.dynamics.com/Issue/Details?kb=4557217). Non sarà inoltre più possibile reimportare le configurazioni eliminate utilizzando la pulizia della migrazione in questo ambiente. Per risolvere questo problema, è necessario trovare il file corrispondente nell'archiviazione BLOB ed eliminarlo manualmente.

[![Importazione di un formato ER.](./media/er-migration-cleanup-import.png)](./media/er-migration-cleanup-import.png)

Un problema simile può verificarsi se si esegue la migrazione dell'istanza dell'applicazione in un'altra posizione utilizzata più volte come destinazione della migrazione e per la quale l'archiviazione BLOB contiene già file modello ER.

Poiché è possibile disporre di più configurazioni di formato ER, questo processo può richiedere molto tempo. È pertanto preferibile utilizzare la funzionalità [Archiviazione di backup di modelli ER](er-backup-storage-templates.md) per ripristinare automaticamente i modelli con riferimenti interrotti.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
