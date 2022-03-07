---
title: Applicare un contratto di acquisto quando si crea un ordine fornitore
description: Questa procedura mostra come utilizzare un contratto di acquisto quando si crea un ordine fornitore.
author: Henrikan
ms.date: 08/09/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 130524dc8e0c8724e35bf13c6b250ab721383711
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7570371"
---
# <a name="apply-a-purchase-agreement-when-creating-a-purchase-order"></a>Applicare un contratto di acquisto quando si crea un ordine fornitore

[!include [banner](../../includes/banner.md)]

Questa procedura mostra come utilizzare un contratto di acquisto quando si crea un ordine fornitore. Il contratto di acquisto deve essere applicato quando si crea l'ordine fornitore perché sono termini generali che devono essere copiati nell'intestazione dell'ordine fornitore. In genere questa attività sarà svolta da un addetto acquisti. Come prerequisito per la guida, è necessario disporre di un contratto di acquisto valido con un impegno quantità di prodotto per un fornitore e gli articoli. La stessa procedura può essere utilizzata se si dispone di un contratto di acquisto con altri tipi di impegni.

## <a name="create-a-purchase-order"></a>Creare un ordine fornitore

1. Vai a **Produzione e approvvigionamento \> Spazi di lavoro \> Preparazione ordine fornitore**.
1. Nel riquadro azioni, selezionare **Nuovo ordine fornitore**.
1. Viene visualizzata la finestra di dialogo **Crea ordine fornitore**. Seleziona un **conto fornitore**. Ispeziona e regola gli altri campi dell'indirizzo secondo le necessità.
1. Espandere la Scheda dettaglio **Generale**.
1. Nel campo **Contratto di acquisto** trova e seleziona il contratto effettivo che vuoi utilizzare. Tutti i contratti disponibili per il fornitore sono elencati in questo campo.  
1. Selezionare **Sì**.
1. Selezionare **OK**.

## <a name="add-a-line"></a>Aggiungi a riga

1. Nel campo **Numero articolo**, digitare un valore. Se sono presenti dimensioni inventariali o di ubicazione sull'impegno, è necessario immettere gli stessi valori nella riga ordine fornitore per utilizzare il contratto.
1. Nel campo **Sito**, seleziona il pulsante a discesa per aprire la ricerca. Il sito può già essere popolato con il valore predefinito dall'ordine o dal fornitore. In questo caso, ignorare questo passaggio.  
1. Nell'elenco trovare e selezionare il record desiderato.
1. Nell'elenco fare clic sul collegamento nella riga selezionata.
1. Nel campo **Quantità** immettere un numero. Verificare che il prezzo sia copiato dall'impegno.  

## <a name="look-up-the-commitment"></a>Cercare l'impegno

1. Seleziona **Aggiorna riga**.
1. Seleziona **Allegato**. In questo punto è possibile ottenere i dettagli del contratto di acquisto. Ad esempio, è possibile visualizzare il prezzo e se il prezzo e lo sconto sono fissi. Ciò significa che se si modifica il prezzo o lo sconto nell'ordine fornitore su un valore diverso di quello dell'impegno, il collegamento verrà rimosso in modo che la riga ordine fornitore non soddisfi l'impegno. È inoltre possibile visualizzare se l'opzione Valore massimo applicato è selezionata. In tal caso, la quantità relativa all'impegno non può essere superata sommando tutti gli acquisti correlati all'impegno.  
1. Chiudere la pagina.

## <a name="look-up-the-purchase-agreement"></a>Cercare il contratto di acquisto

1. Nel **riquadro azioni** fare clic su **Generale**.
1. Seleziona **Contratto di acquisto**.
1. Chiudere la pagina.
1. Chiudere la pagina.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]