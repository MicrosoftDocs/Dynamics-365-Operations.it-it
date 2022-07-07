---
title: Creare un ordine fornitore disciplinato dal budget
description: Utilizzare questa procedura per creare un ordine fornitore controllato in relazione al budget disponibile.
author: JennySong-SH
ms.date: 06/15/2020
ms.topic: business-process
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: aa9777ad3aa487dfb558879335f93f347b8ac749
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2022
ms.locfileid: "9016190"
---
# <a name="create-a-purchase-order-governed-by-budget"></a>Creare un ordine fornitore disciplinato dal budget

[!include [banner](../../includes/banner.md)]

Utilizzare questa procedura per creare un ordine fornitore controllato in relazione al budget disponibile.

## <a name="review-the-budget-control-configuration"></a>Esaminare la configurazione di controllo del budget

1. Vai a **Impostazioni budget > Setup > Controllo del budget > Configurazione controllo del budget**.
1. Fai clic sulla scheda **Fondi budget disponibili**.
1. Fai clic sulla scheda **Documenti e giornali di registrazione**.
1. Fai clic sulla scheda **Definisci regole di controllo del budget**.
1. Fai clic sulla scheda **Definisci i gruppi di budget**.
1. Chiudi la pagina.

## <a name="create-a-purchase-order"></a>Creare un ordine fornitore

1. Vai ad **Approvvigionamento > Ordini fornitore> Tutti gli ordini fornitore**.
1. Selezionare **Nuovo**.
1. Nel campo **Conto fornitore**, immettere o selezionare un valore.
1. Espandere la Scheda dettaglio **Generale**.
1. Nel campo **Data di registrazione** imposta la data.
1. Scegli **OK** per chiudere la finestra di dialogo e aprire il nuovo ordine fornitore.
1. Sulla Scheda dettaglio **Righe ordine fornitore**, seleziona **Aggiungi riga** dalla barra degli strumenti per aggiungere una nuova riga, quindi compila la riga secondo le necessità per aggiungere un articolo all'ordine.
1. Nella barra degli strumenti della Scheda dettaglio **Righe ordine fornitore**, seleziona **Dati finanziari \> Importi distribuzione**.
1. Nel campo **Conto CoGe** specifica un conto.
1. Chiudi la pagina.

## <a name="perform-budget-checking"></a>Esegui verifica budget

1. Continua a lavorare con l'ordine fornitore a cui hai appena aggiunto una riga.
1. Nella barra degli strumenti della Scheda dettaglio **Righe ordine fornitore**, seleziona **Dati finanziari \> Esegui verifica budget**.
1. Nella barra degli strumenti della Scheda dettaglio **Righe ordine fornitore**, seleziona **Dati finanziari \> Errori o avvisi verifica budget**.
1. Viene visualizzata la finestra di dialogo **Errori o avvisi verifica budget**. Controlla i risultati della verifica e quindi seleziona **Chiudi** per chiudere la finestra di dialogo.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]