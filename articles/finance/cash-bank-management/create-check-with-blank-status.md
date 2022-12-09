---
title: Creazione di assegni con stato In bianco
description: In questo articolo viene illustrato come creare assegni in bianco per un conto bancario.
author: angelad116
ms.date: 10/24/2022
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: BankChequeTable
audience: Application User
ms.reviewer: twheeloc
ms.custom: 21941
ms.assetid: d7e22bd8-fd0d-47e1-843f-45ab0193ff8d
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2019-09-17
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 86020d9088d8135c83716128a77090608536a78f
ms.sourcegitcommit: 81bb8e51951395be3f18f45212e47e6c41656f6a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2022
ms.locfileid: "9804020"
---
# <a name="create-checks-that-have-blank-status"></a>Creazione di assegni con stato In bianco

[!include [banner](../includes/banner.md)]

In questo articolo viene illustrato come creare assegni in bianco. Ad esempio, è possibile creare un assegno in bianco per registrare un assegno danneggiato che non può essere utilizzato per il pagamento.

Nella pagina **Assegni**, eseguire le attività di manutenzione per gli assegni. Ad esempio, è possibile creare nuovi numeri di assegno ed eliminare gli assegni. È inoltre possibile creare assegni con stato **In bianco**. Dopo aver creato gli assegni in bianco, non è possibile eliminarli o riutilizzarli nel sistema.

> [!NOTE]
> Questa funzionalità è disponibile nella pagina **Assegni** solo se viene attivata la funzionalità **Creare assegni in bianco nella pagina Assegni** nella pagina **Gestione funzionalità**. Se la funzionalità non viene attivata, gli assegni con stato **In bianco** possono essere creati solo dalla finestra di dialogo **Pagamento con assegno** durante il processo di generazione del pagamento in Contabilità fornitori.

Per aprire la pagina **Assegni**, passare a **Gestione cassa e banche \> Conti bancari \> Conti bancari**, quindi nel riquadro Azioni, nella scheda **Gestione di pagamenti**, nel gruppo **Informazioni correlate**, selezionare **Assegni**. In alternativa, passare a **Gestione cassa e banche \> Richieste di informazioni e report \> Assegni**.

Quindi, per creare assegni con stato **In bianco**, selezionare **Crea assegni in bianco** nel riquadro Azioni. Quando vengono creati assegni in bianco, il conto bancario associato è temporaneamente disattivato. In questo modo si riduce il rischio di generare pagamenti nello stesso momento in cui vengono creati assegni in bianco. Al completamento dell'elaborazione, il conto bancario associato viene riattivato.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
