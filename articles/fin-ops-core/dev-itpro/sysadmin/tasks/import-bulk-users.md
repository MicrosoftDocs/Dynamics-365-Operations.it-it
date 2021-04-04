---
title: Importa utenti da Azure Active Directory
description: Questa procedura può essere utilizzata dagli amministratori di sistema per importare manualmente gli utenti selezionati o per importare un numero elevato di utenti da Azure Active Directory.
author: peakerbl
manager: AnnBe
ms.date: 07/07/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0c2600ad8f441e6b73b143c27afa08ad0a5c2748
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5571007"
---
# <a name="import-users-from-azure-active-directory"></a>Importa utenti da Azure Active Directory

[!include [banner](../../includes/banner.md)]

## <a name="import-select-users"></a>Importare seleziona utenti

Questa procedura può essere utilizzata dagli amministratori di sistema per importare seleziona utenti da Azure Active Directory (Azure AD).

1. L'utente verrà importato con la società della sessione corrente come società predefinita. Modificare la società attuale, se applicabile, prima di importare gli utenti.
2. Andare a **Amministrazione sistema > Utenti > Utent** i.
3. Fare clic su **Importa utenti**.
4. Selezionare gli utenti da importare e selezionare **Importa utenti**.

Una volta completata l'importazione, sarà necessario assegnare i ruoli agli utenti.

## <a name="import-users-in-bulk"></a>Importare utenti in blocco

Questa procedura può essere utilizzata dagli amministratori di sistema per importare un numero elevato di utenti da Azure Active Directory.
Notare che non è possibile selezionare gli utenti quando si utilizza l'opzione di importazione batch.

## <a name="run-the-import-as-a-batch-job"></a>Eseguire l'importazione come un processo batch
1. L'utente verrà importato con la società della sessione corrente come società predefinita. Modificare la società attuale, se applicabile, prima di importare gli utenti.
2. Andare a **Amministrazione sistema > Utenti > Utenti**.
3. Fare clic su **Importazione batch**.
4. Espandi la sezione **Esecuzione in background**.
4. Selezionare **Sì** nel campo **Elaborazione batch**.
6. Nel campo **Gruppo batch** immettere o selezionare un valore. Questo passaggio è facoltativo.  
7. Selezionare **Sì** nel campo **Privato**. Questo passaggio è facoltativo.  
8. Selezionare **Sì** nel campo **Processo critico**. Questo passaggio è facoltativo.  
9. Selezionare un'opzione nel campo **Categoria di monitoraggio**.
10. Fare clic su **OK**.

Una volta completata l'importazione, sarà necessario assegnare i ruoli agli utenti.

## <a name="run-in-a-sandbox-environment"></a>Eseguire l'operazione in un ambiente sandbox
1. Selezionare **Importazione in batch**.
2. Selezionare **OK**.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]