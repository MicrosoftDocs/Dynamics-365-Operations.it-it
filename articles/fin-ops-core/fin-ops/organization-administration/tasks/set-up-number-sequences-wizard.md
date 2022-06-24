---
title: Impostazione guidata sequenze numeriche
description: In questo articolo viene illustrato come impostare contemporaneamente tutte le sequenze numeriche richieste utilizzando la procedura guidata.
author: SunilGarg
ms.date: 07/18/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: NumberSequenceTableListPage, NumberSequenceWizard
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cae739aad1166eee1abebe3c0adc7939bca55bc4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8847065"
---
# <a name="set-up-number-sequences-using-a-wizard"></a>Impostazione guidata sequenze numeriche

[!include [banner](../../includes/banner.md)]

Le sequenze numeriche vengono utilizzate per generare identificatori univoci e leggibili per record anagrafica e record transazioni che li richiedono. Un record transazioni o dati master che richiede un identificatore viene definito riferimento. Prima di poter creare nuovi record per un riferimento, è necessario impostare una sequenza numerica e associarla al riferimento. In questo articolo viene illustrato come impostare contemporaneamente tutte le sequenze numeriche richieste utilizzando la procedura guidata. La società di dati dimostrativi utilizzata per creare questa procedura è USMF.

1. Andare a **Pannello di navigazione > Moduli > Amministrazione organizzazione > Sequenze numeriche > Sequenze numeriche**.
2. Selezionare **Genera**.
3. Selezionare **Avanti**.

   - Da questa pagina è possibile modificare il codice identificativo, il valore minimo e il valore massimo. Inoltre, è possibile Indicare se la sequenza numerica deve essere continua.   
   - Non selezionare l'opzione **Continua** se si devono preallocare numeri per la sequenza numerica. Per aggiungere un segmento ambito al formato di una sequenza numerica, selezionare il formato nell'elenco, quindi selezionare **Includi ambito nel formato**. Per eliminare un segmento ambito dal formato di una sequenza numerica, selezionare il formato nell'elenco, quindi selezionare **Rimuovi ambito dal formato**. Per escludere una sequenza numerica dalla generazione automatica, selezionare la sequenza numerica nell'elenco, quindi selezionare **Elimina**.  

4. Selezionare **Avanti**.
5. Selezionare **Fine**.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
