---
title: Impostazione guidata sequenze numeriche
description: In questo argomento viene illustrato come impostare contemporaneamente tutte le sequenze numeriche richieste utilizzando la procedura guidata.
author: sericks007
manager: AnnBe
ms.date: 07/18/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: NumberSequenceTableListPage, NumberSequenceWizard
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b79924e2c8d94b5e5e160a123e9b0cde0971fd96
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5560485"
---
# <a name="set-up-number-sequences-using-a-wizard"></a>Impostazione guidata sequenze numeriche

[!include [banner](../../includes/banner.md)]

Le sequenze numeriche vengono utilizzate per generare identificatori univoci e leggibili per record anagrafica e record transazioni che li richiedono. Un record transazioni o dati master che richiede un identificatore viene definito riferimento. Prima di poter creare nuovi record per un riferimento, è necessario impostare una sequenza numerica e associarla al riferimento. In questo argomento viene illustrato come impostare contemporaneamente tutte le sequenze numeriche richieste utilizzando la procedura guidata. La società di dati dimostrativi utilizzata per creare questa procedura è USMF.

1. Andare a **Pannello di navigazione > Moduli > Amministrazione organizzazione > Sequenze numeriche > Sequenze numeriche**.
2. Selezionare **Genera**.
3. Selezionare **Avanti**.

   - Da questa pagina è possibile modificare il codice identificativo, il valore minimo e il valore massimo. Inoltre, è possibile Indicare se la sequenza numerica deve essere continua.   
   - Non selezionare l'opzione **Continua** se si devono preallocare numeri per la sequenza numerica. Per aggiungere un segmento ambito al formato di una sequenza numerica, selezionare il formato nell'elenco, quindi selezionare **Includi ambito nel formato**. Per eliminare un segmento ambito dal formato di una sequenza numerica, selezionare il formato nell'elenco, quindi selezionare **Rimuovi ambito dal formato**. Per escludere una sequenza numerica dalla generazione automatica, selezionare la sequenza numerica nell'elenco, quindi selezionare **Elimina**.  

4. Selezionare **Avanti**.
5. Selezionare **Fine**.



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]