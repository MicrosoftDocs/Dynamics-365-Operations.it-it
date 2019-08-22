---
title: Creare tipi di sollecito e criteri di assegnazione punteggi per RdO
description: Questa guida vi mostra come creare un tipo di sollecito ed associarlo a un metodo di assegnazione del punteggio.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchRFQSolicitationType, PurchRFQCaseTableListPage, PurchCreateRFQCase, PurchRFQCaseTable, PurchRFQScoringRFQCaseCriteria, PurchRFQScoringCriteriaCopy
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1a3e0d00d674af913953d7fd01183b0289c20d3d
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "1844110"
---
# <a name="create-solicitation-types-and-scoring-criteria-for-rfqs"></a>Creare tipi di sollecito e criteri di assegnazione punteggi per RdO

[!include [task guide banner](../../includes/task-guide-banner.md)]

Questa guida vi mostra come creare un tipo di sollecito ed associarlo a un metodo di assegnazione del punteggio. Inoltre mostra come usare il tipo di sollecito per una richiesta di offerta (RdO), che poi imposta il metodo di assegnazione del punteggio predefinito. Queste attività verranno in genere svolte da un responsabile degli acquisti. È necessario impostare le classificazioni del contratto di acquisto prima di iniziare. Dovete avere un metodo di assegnazione del punteggio disponibile prima che cominciate.


## <a name="create-a-solicitation-type"></a>Creare un tipo di sollecito.
1. Andare a Approvvigionamento > Impostazioni > Richiesta di offerta > Tipo di sollecito.
2. Fare clic su Nuovo.
3. Digitare un valore nel campo Nome.
4. Nel campo Descrizione digitare un valore.
5. Nel campo Metodo di assegnazione del punteggio selezionare il metodo che si desidera utilizzare per questo tipo di sollecito.
6. Fare clic su Salva.
7. Chiudere la pagina.

## <a name="use-the-solicitation-type"></a>Usare il tipo di sollecito
1. Andare ad Approvvigionamento > Richieste di offerta > Tutte le richieste di offerta.
2. Fare clic su Nuovo.
3. Nel campo Tipo di sollecito, selezionare il tipo di sollecito che avete creato appena. 
    *   
4. Fare clic su OK.
5. Fare clic su Criteri di assegnazione del punteggio.
    * I criteri di assegnazione del punteggio indicati sono quelli del metodo di assegnazione punteggio associato con il tipo di sollecito. Potete scegliere di aggiungere o eliminare i criteri in questa pagina. È inoltre possibile aggiungere nuovi criteri copiandoli da altri metodi di assegnazione del punteggio.  
6. Fare clic su Copia criteri.
7. Nel campo Metodo di assegnazione del punteggio immettere o selezionare un valore.
8. Fare clic su OK.
9. Chiudere la pagina.

