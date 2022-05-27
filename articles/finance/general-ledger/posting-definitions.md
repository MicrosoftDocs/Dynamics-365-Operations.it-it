---
title: Definizioni di registrazione
description: Questo argomento fornisce informazioni sulle definizioni di registrazione e sul modo in cui definirle e collegarle. Per i tipi di registrazione e i documenti supportati è possibile utilizzare definizioni di registrazione anziché profili di registrazione per classificare i conti principali e le dimensioni finanziarie nelle voci contabili.
author: kweekley
ms.date: 09/03/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JournalizingDefinition, JournalizingDefinitionTrans, LedgerParameters
audience: Application User
ms.reviewer: kfend
ms.custom: 15741
ms.assetid: 1495e7e0-2e39-464c-8da9-f55b1ca1c6bb
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 056300768aa0bc5e1981e1d43de03fabba21a5fa
ms.sourcegitcommit: 602a319f4720b39a56b7660b530236912d484391
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2022
ms.locfileid: "8722012"
---
# <a name="posting-definitions"></a>Definizioni di registrazione

[!include [banner](../includes/banner.md)]

Questo argomento fornisce informazioni sulle definizioni di registrazione e sul modo in cui definirle e collegarle.
Per i tipi di registrazione e i documenti supportati è possibile utilizzare definizioni di registrazione anziché profili di registrazione per classificare i conti principali e le dimensioni finanziarie nelle voci contabili. È possibile visualizzare i documenti e i tipi di registrazione supportati nella pagina **Definizioni di registrazione transazioni**. 

Per iniziare a utilizzare le definizioni di registrazione, selezionare l'opzione **Usa definizioni di registrazione** nella pagina **Parametri di contabilità generale**. Anche quando si utilizzano le definizioni di registrazione, è ancora necessario definire i profili di registrazione per le voci di origine e i documenti e i tipi di registrazione non supportati. 

Le definizioni di registrazione devono essere utilizzate per consentire la contabilità degli impegni di spesa per gli ordini fornitore e la contabilità degli impegni preliminari di spesa per le richieste di acquisto.

## <a name="defining-posting-definitions"></a>Definizioni di registrazione
Utilizzare la pagina **Definizioni di registrazione** per specificare i criteri di corrispondenza e definire le voci che devono essere generate quando una corrispondenza si verifica. I criteri di corrispondenza vengono valutati per le voci di origine come distribuzioni contabili. 

Nella pagina **Definizioni di registrazione** è possibile anche assegnare numeri di priorità alle righe di immissione per definire l'ordine in cui vengono valutate le righe. Le righe con il numero di priorità inferiore vengono valutate per prime. Ad esempio, vengono valutate tutte le righe con priorità 1, quindi le righe con priorità 2 e così via. Quando viene rilevata una corrispondenza, gli altri criteri di corrispondenza vengono ignorati. Inoltre, solo per i criteri del gruppo corrispondenti alla transazione di origine vengono create voci generate. 

È possibile convalidare le definizioni di registrazione utilizzando **Test guidato definizione di registrazione**. Dopo aver definito una voce di origine di esempio per una definizione di registrazione, saranno visibili le voci generate. 

È possibile utilizzare le versioni delle definizioni di registrazione insieme alle date di validità. È possibile creare, ad esempio, una versione futura di una definizione di registrazione per la registrazione in un conto CoGe diverso in un nuovo anno fiscale. 

Utilizzare la pagina **Definizioni di registrazione transazioni** per assegnare le definizioni di registrazione ai tipi di transazioni.

## <a name="linking-posting-definitions"></a>Collegamento delle definizioni di registrazione
Quando si creano le definizioni di registrazione, è possibile collegarne una all'altra. I criteri per la definizione alla quale è stato effettuato il collegamento sono quindi considerati in aggiunta a quelli per la definizione di registrazione corrente. Questa funzionalità consente di risparmiare tempo, perché non è necessario immettere di nuovo i criteri nella scheda dettaglio **Voci** della pagina **Definizioni di registrazione** per la definizione di registrazione corrente, se tali righe sono già state immesse per un'altra definizione. 

Includere nei diagrammi o nelle tabelle tutti i collegamenti che potrebbero essere utilizzati. Per evitare conflitti con la definizione di registrazione corrente, verificare che le righe in tutte le definizioni di registrazione alle quali si sta effettuando il collegamento siano univoche. 

Quando si creano collegamenti nelle definizioni di registrazione vengono applicate le restrizioni seguenti:

-   È possibile stabilire un collegamento da o verso una determinata definizione di registrazione da un'altra definizione di registrazione, ma non in entrambe le direzioni. Tuttavia, una definizione di registrazione può collegare a più definizioni di registrazione.
-   È possibile impostare i collegamenti solo tra definizioni di registrazione incluse nello stesso modulo.
-   È possibile assegnare una definizione di registrazione a qualsiasi tipo di transazione, tuttavia tale tipo di transazione deve trovarsi nello stesso modulo della definizione di registrazione. Utilizzare la pagina **Definizioni di registrazione transazioni** per visualizzare in quale modulo si trova un tipo di transazione.


Per ulteriori informazioni, vedere [Esempi di definizione di registrazione](example-posting-definitions.md). 




[!INCLUDE[footer-include](../../includes/footer-banner.md)]
