---
title: Impostare il delimitatore del piano dei conti come univoco
description: In questo argomento viene descritto perché non è possibile avere lo stesso delimitatore per il piano dei conti e i valori delle dimensioni. Dopo l'aggiornamento, è necessario cambiare i valori del delimitatore.
author: ryansandness
manager: AnnBe
ms.date: 03/30/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: 8
ms.openlocfilehash: 2622245c7ce7213665ab32f4020c282df28cb886
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2019
ms.locfileid: "2248782"
---
# <a name="make-the-chart-of-accounts-delimiter-unique"></a>Impostare il delimitatore del piano dei conti come univoco

[!include [banner](../includes/banner.md)]

In Microsoft Dynamics AX 2012, è possibile utilizzare lo stesso delimitatore per il piano dei conti e i valori delle dimensioni. Nelle versioni correnti di Finance and Operations, non è possibile avere lo stesso delimitatore per il piano dei conti e i valori delle dimensioni. L'eventuale delimitatore duplicato può essere sostituito dopo l'aggiornamento. 

Questa funzionalità è disponibile nelle seguenti versioni:
- Finance and Operations versione 8.0
- Finance and Operations versione 7.1, KB 4094701 Non è possibile immettere le dimensioni finanziarie quando i valori delle dimensioni contengono il delimitatore del piano dei conti
- Finance and Operations versione 7.2, KB 4092967 Non è possibile scegliere un sottoprogetto come dimensione quando il formato del sottoprogetto contiene il delimitatore delle dimensioni

## <a name="update-delimiter"></a>Aggiornare il delimitatore
In presenza di un conflitto con il piano dei conti, è possibile cambiare il delimitatore del piano dei conti e il formato ID del progetto/sottoprogetto. Non è possibile cambiare alcun altro delimitatore delle dimensioni. 
- È possibile cambiare il delimitatore del piano dei conti dopo l'aggiornamento in **Parametri di contabilità generale** > **Piano dei conti e dimensioni** > **Modifica delimitatore**. 
- Se il conflitto è presente solo con il formato ID del progetto/sottoprogetto, è possibile modificare il valore in **Parametri Gestione progetti e contabilità** > **Generale** > **Modifica formato sottoprogetto**. 

## <a name="how-to-determine-if-your-environment-requires-updated-delimiters"></a>Come determinare se l'ambiente richiede delimitatori aggiornati 
Se i delimitatori nell'ambiente aggiornato sono in conflitto, è possibile avvertire l'instabilità quando si immettono i valori in un controllo di immissione segmentato o in un controllo di immissione delle dimensioni. Ciò significa che è sempre necessario utilizzare le ricerche o un menu a comparsa quando si immettono combinazioni di piano dei conti e dimensioni.
