---
title: Gruppi oggetti assistenza
description: I gruppi di oggetti sono utili per ordinare e filtrare i dati relativi a oggetti per scopi statistici e di report.
author: ShylaThompson
ms.date: 05/11/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceObjectGroups
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a559bdc8f7851e38274d9d23070f969502942ad8
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5835872"
---
# <a name="service-object-groups"></a>Gruppi oggetti assistenza 

[!include [banner](../includes/banner.md)]

I gruppi di oggetti sono utili per ordinare e filtrare i dati relativi a oggetti per scopi statistici e di report. È possibile, ad esempio, raggruppare oggetti in base alla posizione geografica o in base al tipo.

## <a name="group-by-geographical-location"></a>Raggruppare per posizione geografica

È possibile utilizzare questo metodo di raggruppamento per visualizzare l'ubicazione dei diversi oggetti per i quali la società fornisce assistenza. Il raggruppamento di oggetti per posizione geografica può essere utile anche nel caso in cui sia ad esempio necessario identificare gli oggetti per i quali viene già fornita assistenza in un determinato paese.

## <a name="example"></a>Esempio

Un cliente belga contatta il centro assistenza della società perché desidera stipulare un contratto di assistenza per un oggetto, denominato ABC. A tutti gli oggetti per i quali viene fornita assistenza tecnica in Belgio è stato collegato un gruppo di oggetti di tipo posizione geografica, denominato Belgio. Utilizzando questo gruppo come filtro è possibile determinare rapidamente se l'oggetto ABC è già presente come record nel programma o se è necessario impostare un nuovo oggetto. 

## <a name="group-by-type"></a>Raggruppare per tipo

È possibile utilizzare questo metodo di raggruppamento per visualizzare i tipi di oggetti per i quali la società fornisce assistenza. Il raggruppamento di oggetti per tipo può essere utile anche nel caso in cui sia ad esempio necessario creare un nuovo oggetto in base a oggetti simili già presenti nel programma.

## <a name="example"></a>Esempio

Un cliente contatta la società perché desidera stipulare un contratto di assistenza per un sistema di condizionamento, denominato HIJ. Sebbene questo sistema non sia già presente nei record della società, è stato definito un gruppo di oggetti denominato Condizionatori e a questo gruppo sono stati collegati tutti gli oggetti condizionatore. Sarà pertanto possibile cercare e identificare rapidamente tutti i sistemi di climatizzazione e utilizzarne il modello di informazioni per creare righe di contratto di assistenza per gli articoli HIJ. Questo metodo di utilizzo dei gruppi di oggetti consente di ridurre i tempi necessari per l'impostazione di nuovi oggetti e la determinazione delle attività di assistenza da eseguire. 

## <a name="create-service-object-groups"></a>Creare gruppi di oggetti assistenza

Creare gruppi a cui è possibile assegnare oggetti assistenza. Gli oggetti assistenza sono articoli di magazzino e altri prodotti per cui vengono eseguiti i servizi. Raggruppando gli oggetti assistenza, è possibile creare report per oggetti assistenza simili e correlati. Ad esempio, un gruppo di oggetti assistenza potrebbe essere costituito da due oggetti assistenza: un oggetto assistenza è un kit e il secondo oggetto assistenza è l'assistenza per installare il kit.

Per creare gruppi di oggetti assistenza, effettuare le operazioni seguenti:

1. Fare clic su **Gestione assistenza > Impostazione > Oggetti assistenza > Oggetti assistenza**.

2. Fare clic su **Nuovo** per creare un nuovo gruppo di oggetti assistenza.

3. Immettere il nome univoco per il gruppo di oggetti assistenza e, facoltativamente, immettere una descrizione.

È possibile assegnare gli oggetti assistenza al gruppo utilizzando il modulo **Oggetti assistenza**. 

## <a name="see-also"></a>Vedere anche

[Creare oggetti assistenza](create-service-objects.md)




[!INCLUDE[footer-include](../../includes/footer-banner.md)]