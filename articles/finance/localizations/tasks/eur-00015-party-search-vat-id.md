---
title: EUR-00015 Ricerca della parte utilizzando l'ID IVA
description: In questa procedura verrà descritto come eseguire una ricerca di parti tramite un ID registrazione.
author: v-oloski
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DirPartyTable, DirPartTaxRegistrationSearch
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 401971b6f146f1df028291ba0f691ccac5f1966d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4408069"
---
# <a name="eur-00015-party-search-using-vat-id"></a>EUR-00015 Ricerca della parte utilizzando l'ID IVA

[!include [banner](../../includes/banner.md)]

In questa procedura verrà descritto come eseguire una ricerca di parti tramite un ID registrazione. Prima di poter eseguire la procedura, è necessario impostare gli ID IVA e immettere tutti gli ID IVA per i fornitori, clienti, o persone giuridiche.

Questa procedura si applica a tutti i paesi europei. La procedura è stata creata utilizzando la società di dati dimostrativi DEMF con un indirizzo principale in Germania. Questa procedura è progettata per un responsabile della contabilità fornitori, o un responsabile della contabilità clienti. Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.

1. Scegliere Amministrazione organizzazione > Rubrica globale > Rubrica globale.
2. Fare clic su Ricerca ID registrazione.
3. Scegliere Aggiungi.
4. Nel campo Tipo di registrazione, immettere o selezionare un valore.
    * Ad esempio, per trovare parti con un ID registrazione di tipo ID IVA, selezionare ID IVA.  
5. Nel campo Paese/regione, immettere o selezionare un valore.
    * Ad esempio, immettere DEU.  
6. Nel campo Numero di registrazione digitare un valore.
7. Fare clic su Trova.
    * Tutte le parti con tale ID registrazione verranno visualizzate.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]