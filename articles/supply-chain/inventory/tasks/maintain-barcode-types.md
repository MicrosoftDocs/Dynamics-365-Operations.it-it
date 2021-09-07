---
title: Gestire i tipi di codice a barre
description: Questa procedura vi mostra come impostare una nuova definizione di codice a barre che può poi essere usata come parte del rapporto della lista di prelievo.
author: perlynne
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: BarcodeSetup, InventParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 052311e15aeb20b927cbed217a2bda600dad60a5
ms.sourcegitcommit: b9c2798aa994e1526d1c50726f807e6335885e1a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2021
ms.locfileid: "7345652"
---
# <a name="maintain-bar-code-types"></a>Gestire i tipi di codice a barre

[!include [banner](../../includes/banner.md)]

Questa procedura vi mostra come impostare una nuova definizione di codice a barre che può poi essere usata come parte del rapporto della lista di prelievo. È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure utilizzando i propri dati. Se si utilizza USMF è possibile utilizzare i valori di esempio visualizzati. Queste attività verranno in genere svolte da un responsabile del magazzino.

1. Vai a **Codici a barre**.
1. Selezionare **Nuovo**.
1. Nel campo di **impostazione del codice a barre** , digitate un valore.
1. Digitare un valore nel campo **Descrizione**
1. Nel campo **Tipo di codice a barre** , selezionate un'opzione.
    * Se si utilizza USMF, è possibile selezionare 'Code 39'.  
1. Nel campo **Dimensione** , inserite un numero.
1. Nel campo **Lunghezza massima** , inserite un numero.
1. Selezionare **Salva**.
1. Chiudere la pagina.
1. Vai ai **parametri di gestione dell'inventario e del magazzino**.
1. Nel campo di **impostazione del codice a barre** , inserire o selezionare un valore.
    * Seleziona l'impostazione del codice a barre che hai creato prima, ma tieni presente che il formato del codice a barre deve corrispondere al formato dell'identificatore unico per il tipo di record usato nel processo. Ad esempio, per i cicli di prelievo, il formato di codice a barre deve corrispondere al formato di riferimento del ciclo di prelievo, che è in genere una sequenza numerica.  
1. Selezionare **Salva**.
1. Chiudere la pagina.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]