---
title: Relazioni oggetti assistenza
description: È possibile creare relazioni tra un oggetto assistenza e un contratto di assistenza o un ordine di assistenza.
author: ShylaThompson
manager: tfehr
ms.date: 02/21/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceObjectRelation
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 82e25c162a33dd8e6e1a0cc4f215a8693fc1080b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5266057"
---
# <a name="service-object-relations"></a>Relazioni oggetti assistenza 

[!include [banner](../includes/banner.md)]

È possibile creare relazioni tra un oggetto assistenza e un contratto di assistenza o un ordine di assistenza. Per creare una relazione, è necessario collegare l'oggetto assistenza al contratto o all'ordine di assistenza.

Una volta creata la relazione, sarà possibile collegare l'oggetto assistenza a qualsiasi riga nel contratto o ordine di assistenza.

## <a name="template-boms"></a>DBA modello

È inoltre possibile specificare una DBA modello per la relazione di oggetto. La DBA modello è una distinta base relativa all'oggetto sul quale si esegue l'attività di assistenza. Se nel corso di un intervento viene sostituito un componente dell'oggetto assistenza, è possibile registrare questa modifica nella DBA assistenza utilizzando il modulo Oggetti assistenza.

## <a name="example"></a>Esempio

Viene creato un contratto di assistenza per la riparazione di due ascensori presso la sede del cliente.
Il contratto di assistenza ha come identificazione (ID) il codice SAL-001.

Nel modulo Oggetti assistenza gli ascensori sono stati impostati come oggetti EL-S/1000 e EL-L/1000.

È possibile collegare gli oggetti assistenza EL-S/1000 e EL-L/1000 al contratto di assistenza.

Per registrare le modifiche nella DBA relativa all'oggetto assistenza man mano che si sostituiscono i componenti dell'oggetto, è possibile collegare una DBA assistenza alla relazione di oggetto, secondo quanto descritto nella seguente tabella.

| Oggetto assistenza | Relazione - Contratto di assistenza | DBA assistenza   |
|----------------|------------------------------|---------------|
| EL-S/1000      | ID SAL-001                   | DBA-EL-S/1000 |
| EL-L/1000      | ID SAL-001                   | DBA-EL-L/1000 |

Poiché sono disponibili relazioni di oggetti assistenza per il contratto, sarà possibile creare righe del contratto di assistenza con questi oggetti, secondo quanto descritto nella seguente tabella.

| Tipo di transazione | Categoria           | Oggetto assistenza |
|------------------|--------------------|----------------|
| Ora             | Ispezione         | EL-S/1000      |
| Ora             | Pulizia riduttore  | EL-S/1000      |
| Elemento             | Materiali pulizia | EL-S/1000      |
| Ora             | Ispezione         | EL-L/1000      |
| Ora             | Pulizia riduttore   | EL-L/1000      |
| Elemento             | Materiali pulizia | EL-L/1000      |

Durante un sopralluogo si presenta la necessità di sostituire il riduttore dell'ascensore EL-S/1000. Per sostituire un componente dell'oggetto, è possibile accedere a Designer DBA utilizzando la relazione di oggetti assistenza impostata per l'ordine di assistenza corrente.

Accedere a Designer DBA utilizzando una relazione di oggetti assistenza

1. Contratti di assistenza
2. Fare doppio clic su un contratto di assistenza oppure fare clic su Contratto di assistenza per crearne uno nuovo.
3. Fare clic sulla scheda Impostazioni.
4. Per collegare una DBA modello al contratto di assistenza, fare clic su Oggetti assistenza.
5. Nel modulo Oggetti assistenza fare clic su Progettazione per aprire il modulo Progettazione e modificare la DBA modello.

## <a name="automatically-created-service-orders"></a>Creazione automatica degli ordini di assistenza

Se gli ordini relativi a un contratto di assistenza vengono creati automaticamente, le relazioni di oggetti assistenza del contratto vengono riportate anche negli ordini di assistenza creati.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]