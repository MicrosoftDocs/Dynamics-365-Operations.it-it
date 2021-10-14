---
title: Verificare la qualità delle merci
description: In questo argomento viene descritto come elaborare ordini di controllo qualità.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventQualityOrderTable, InventQualityOrderLineResults, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cc2fbbedb608b38c6855fbd48ff0c3e26ee3e0bc
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7575850"
---
# <a name="inspect-the-quality-of-goods"></a>Verificare la qualità delle merci

[!include [banner](../../includes/banner.md)]

In questo argomento viene descritto come elaborare ordini di controllo qualità. Le ispezioni di controllo qualità sono in genere effettuati da un addetto al controllo qualità.

Se sono installati i dati demo standard, è possibile utilizzarli per completare le procedure in questo argomento. Per usare i dati demo, selezionare la persona giuridica *USMF* prima di iniziare. È quindi necessario confermare l'ordine fornitore *000016* e registrare una entrata prodotti. Viene generato automaticamente un ordine di controllo qualità.

## <a name="step-1-select-a-quality-order"></a>Passaggio 1: Selezionare un ordine di controllo qualità.

Per selezionare un ordine di controllo qualità, attieniti alla procedura seguente:

1. Andare a **Gestione inventario \> Attività periodiche \> Gestione qualità \> Ordini di controllo qualità**.
1. Selezionare l'ordine di controllo qualità generato prima di aver avviato questa procedura.

## <a name="step-2-record-test-results"></a>Passaggio 2: Registrazione dei risultati dei test

Per registrare i risultati dei test, eseguire i passaggi indicati di seguito:

1. Seleziona **Risultati**.
1. Seleziona **Modifica**.
1. Nel campo **Quantità risultante** immettere un numero.
1. Nel campo **Risultato**, selezionare il record desiderato. In questo esempio il risultato è basato su un risultato predefinito. In genere viene registrato un risultato del test più specifico, ad esempio una dimensione o un altro valore simile.
1. Selezionare **Salva**.
1. Chiudere la pagina.

## <a name="step-3-validate-the-quality-order"></a>Passaggio 3: Convalida l'ordine di controllo qualità

Per convalidare l'ordine di controllo qualità, attieniti alla procedura seguente:

1. Selezionare **Convalida**.
1. Nel campo **Convalidato da** selezionare l'utente che sta effettuando l'ispezione.
1. Selezionare **Select**.
1. Selezionare **OK**.
1. Chiudere la pagina.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
