---
title: Conti di registrazione acquisizione cespiti
description: Questo articolo illustra come impostare i conti di registrazione della contabilità generale per l'acquisizione dei cespiti.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetPosting
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 23021
ms.assetid: d7e86f72-95db-4423-9b04-761e9536a959
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8fea6b1cd79b5536341a7cb50e5592ea38a7392d
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "1840507"
---
# <a name="fixed-asset-acquisition-posting-accounts"></a>Conti di registrazione acquisizione cespiti

[!include [banner](../includes/banner.md)]

Questo articolo illustra come impostare i conti di registrazione della contabilità generale per l'acquisizione dei cespiti.

I conti utilizzati per registrare le acquisizioni cespiti possono variare in base al metodo utilizzato per l'acquisizione del cespite. Nella pagina Profili registrazione cespiti, nella scheda Conti CoGe selezionare Acquisizione e Rettifica acquisizione per impostare i conti cespiti per la registrazione nella contabilità generale. 

Nei giornali di registrazione e negli ordini fornitore il conto COGE costituisce in genere il conto dello stato patrimoniale, dove viene addebitato il valore di acquisizione dei nuovi cespiti. Questo conto non viene visualizzato nel giornale di registrazione e non può essere sostituito nelle transazioni. 

Anche il conto di contropartita è un conto dello stato patrimoniale. Nel giornale di registrazione generale e nel giornale cespiti questo conto corrisponde spesso al conto bancario utilizzato per pagare l'acquisizione del cespite. Il conto di contropartita è un conto utilizzato come predefinito nei giornali di registrazione, dove può essere sostituito da qualsiasi altro conto del piano dei conti o da un conto fornitore se il cespite è stato acquistato da un fornitore. 

Se per le acquisizioni dei cespiti si utilizza il giornale di registrazione fattura o gli ordini fornitore nella Contabilità fornitori, il conto di contropartita per la transazione cespiti viene sostituito dal conto fornitore selezionato per la transazione.

Per le acquisizioni registrate in Contabilità generale utilizzando il giornale di registrazione Scorte a cespiti, il cespite non viene acquistato da origini esterne ma trasferito dalle scorte della società. Di conseguenza, il conto di contropartita per l'articolo di magazzino presente in Gestione articoli è costituito da un conto uscite da magazzino.

Per ulteriori informazioni, vedere [Acquisire cespiti tramite approvvigionamento](acquire-assets-procurement.md).



