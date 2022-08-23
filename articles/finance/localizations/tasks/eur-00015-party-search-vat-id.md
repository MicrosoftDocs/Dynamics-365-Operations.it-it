---
title: EUR-00015 Ricerca della parte utilizzando l'ID IVA
description: In questa procedura verrà descritto come eseguire una ricerca di parti tramite un ID registrazione.
author: AdamTrukawka
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: atrukawk
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: DirPartyTable, DirPartTaxRegistrationSearch
ms.openlocfilehash: 0688de30327abe0925efe3daf44bcbab8a096c97
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9288477"
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
