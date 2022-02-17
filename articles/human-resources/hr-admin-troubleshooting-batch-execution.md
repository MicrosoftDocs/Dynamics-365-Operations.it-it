---
title: Reimpostare i processi batch bloccati
description: Questo argomento spiega come risolvere i problemi con processi batch bloccati.
author: andreabichsel
ms.date: 03/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2021-03-19
ms.dyn365.ops.version: Platform update 42
ms.openlocfilehash: 859f039a928cdc57c9f227885d0f00ef79980f28
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/31/2022
ms.locfileid: "8070402"
---
# <a name="reset-stuck-batch-jobs"></a>Reimpostare i processi batch bloccati


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

## <a name="issue"></a>Uscita

In Microsoft Dynamics 365 Human Resources possono verificarsi problemi con i processi batch bloccati in uno stato **In esecuzione** o **Annullamento** che non vengono completati.

## <a name="resolution"></a>Risoluzione

Quando un processo batch è bloccato in uno stato **In esecuzione** o **Annullamento** puoi reimpostare lo stato forzando l'annullamento del processo. Dopo averlo annullato, è possibile ripristinare il processo batch impostandolo su uno stato **In attesa**. Verrà quindi nuovamente prelevato per l'esecuzione nella successiva esecuzione batch pianificata.

1. Nell'area di lavoro **Amministrazione di sistema** seleziona la pagina **Collegamenti** e seleziona **Processi batch**.

2. Nella pagina elenco **Processo batch** seleziona il processo che deve essere ripristinato.

3. Sulla barra multifunzione seleziona **Forza annullamento** e conferma l'azione.

   > [!NOTE]
   > L'azione **Forza annullamento** è disponibile solo quando il processo batch selezionato ha lo stato **In esecuzione** o **Annullamento** e nessun processo di esecuzione o annullamento batch è in esecuzione per il processo.

4. Nella barra multifunzione seleziona **Cambia stato**.

5. Nella pagina **Seleziona nuovo stato** seleziona **In attesa** e quindi seleziona **OK**.

   ![Selezionare un nuovo stato del processo batch.](./media/hr-admin-reset-batch-job-status.png)

## <a name="see-also"></a>Vedere anche

[Ottimizzare le prestazioni programmando i processi batch dopo ore](hr-admin-troubleshooting-batch-jobs.md)<br>
[Ottimizzare le prestazioni con attività di pulizia automatica](hr-admin-troubleshooting-batch-history.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
