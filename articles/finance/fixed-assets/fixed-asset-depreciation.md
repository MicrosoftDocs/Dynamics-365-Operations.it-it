---
title: Ammortamento cespiti
description: In questo articolo viene fornita una panoramica dell'ammortamento dei cespiti.
author: moaamer
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 3121
ms.assetid: 98ff891f-e0e2-4184-b618-28107a50851f
ms.search.form: AssetBonus, AssetBookTable
ms.openlocfilehash: 9761fc9846324d1c165274b72033e195bf4ea3e0
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275297"
---
# <a name="fixed-asset-depreciation"></a>Ammortamento cespiti

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

In questo articolo viene fornita una panoramica dell'ammortamento dei cespiti.

Per ammortamento si intende una transazione periodica che di solito determina una riduzione del valore dei cespiti nello stato patrimoniale e viene addebitata come spesa in un conto profitti e perdite. Di conseguenza, per l'accredito dell'ammortamento periodico nello stato patrimoniale viene in genere utilizzato un conto principale. Un conto di contropartita è un conto nella parte profitti e perdite del piano dei conti.

A partire dalla versione 10.0.24, l'opzione di configurazione del libro cespiti **Calcola ammortamento positivo** nella pagina **Libri** consente all'ammortamento dell'addebito di un cespite acquisito con un valore contabile negativo (avere).

## <a name="depreciation-adjustment"></a>Rettifica ammortamento
In genere, viene registrata come rettifica dell'ammortamento solo una correzione apportata a una transazione di ammortamento già registrata. Di conseguenza, sia il conto principale che il conto di contropartita vengono impostati analogamente ai conti per l'ammortamento. Una rettifica dell'ammortamento può essere costituita da un importo positivo o negativo, ma la funzionalità del conto principale (come conto dello stato patrimoniale) e del conto di contropartita (solitamente come conto profitti e perdite) rimane la stessa.

## <a name="extraordinary-depreciation"></a>Ammort. straordinario
L'ammortamento straordinario funziona come l'ammortamento normale. Di conseguenza, un conto principale viene utilizzato per accreditare l'importo di ammortamento nello stato patrimoniale e ridurre il valore del cespite. Un conto di contropartita è un conto profitti e perdite, in cui l'ammortamento calcolato per il periodo fiscale viene addebitato come spesa. 

L'ammortamento straordinario è indipendente dall'ammortamento normale. Poiché è considerato un tipo di transazione separato, è possibile registrarlo e dichiararlo in modo distinto dall'ammortamento normale.

## <a name="special-depreciation-allowance"></a>Fondo di ammortamento speciale
I fondi di ammortamento speciale consentono di applicare importi di ammortamento aggiuntivi durante il primo anno in cui un cespite viene messo in servizio e ammortizzato. I fondi di ammortamento speciale devono essere applicati prima di qualsiasi altro calcolo dell'ammortamento. Poiché i fondi di ammortamento speciale sono spesso sconosciuti fino a una fase successiva nella vita utile del cespite, è preferibile utilizzare questo tipo di ammortamento con un libro che non viene registrato nella contabilità generale. È possibile utilizzare la funzione periodica Elimina transazioni non registrate nella contabilità generale per eliminare lo storico transazioni per questi libri. È quindi possibile eliminare lo storico di ammortamento per il libro cespiti, registrare il fondo di ammortamento speciale quando è noto e quindi registrare le transazioni di ammortamento rimanenti per l'anno. 

È possibile creare un numero illimitato di record di fondo di ammortamento speciale. Una volta assegnati tali record a un libro gruppo cespite, questi record vengono applicati al libro cespiti. 

Un fondo di ammortamento speciale viene immesso sotto forma di percentuale o di importo fisso. Quando si registrano le proposte di ammortamento, le transazioni relative a questo tipo di ammortamento vengono registrate nel libro come transazioni distinte dalle altre.

## <a name="depreciation-calendars"></a>Calendari di ammortamento
Ciascun libro è associato a un calendario utilizzato per l'ammortamento dei cespiti. Il libro utilizzerà il calendario fiscale per la contabilità generale per impostazione predefinita se non si specifica un calendario per il libro. È necessario selezionare un calendario fiscale per un libro quando il profilo di ammortamento associato al libro utilizza un anno fiscale di ammortamento. 

È possibile creare calendari condivisi utilizzando la pagina **Calendari fiscali** nella contabilità generale.

Per ulteriori informazioni, vedere [Metodi e convenzioni di ammortamento](depreciation-methods-conventions.md).





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
