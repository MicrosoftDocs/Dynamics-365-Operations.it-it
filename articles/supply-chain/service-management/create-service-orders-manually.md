---
title: Creare ordini di assistenza manualmente
description: È possibile creare ordini di assistenza manualmente utilizzando un contratto di assistenza oppure il modulo **Ordini di assistenza**.
author: sorenva
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1764d97d4492e7b982a5d2c9f7e7f1c15380be1d
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2022
ms.locfileid: "9014853"
---
# <a name="create-service-orders-manually"></a>Creare ordini di assistenza manualmente    

[!include [banner](../includes/banner.md)]


È possibile creare ordini di assistenza manualmente utilizzando un contratto di assistenza oppure il modulo **Ordini di assistenza**. È inoltre possibile creare un ordine di assistenza a partire da un progetto.

> [!TIP]
> <P>Gli ordini di assistenza possono essere creati utilizzando processi automatizzati. 

## <a name="create-a-service-order-manually-from-a-service-agreement"></a>Creare un ordine di assistenza manualmente da un contratto di assistenza

1.  Seleziona **Gestione assistenza** \> **Contratti di assistenza** \> **Contratti di assistenza**.

2.  Selezionare un contratto di assistenza oppure crearne uno nuovo.

3.  Selezionare la scheda **Consegna** e nel gruppo **Creare** selezionare **Ordini di assistenza pianificati** per aprire il modulo **Crea ordini di assistenza**.

## <a name="create-a-service-order-manually-in-the-service-orders-form"></a>Creare un ordine di assistenza manualmente nel modulo Ordini di assistenza

1.  Seleziona **Gestione assistenza** \> **Ordini di assistenza** \> **Ordini di assistenza**.

2.  Selezionare **Nuovo** per creare un nuovo ordine di assistenza.

3.  Creare le righe dell'ordine di assistenza.

> [!NOTE]
> <P>Se la casella di controllo <STRONG>Consenti senza contratto di assistenza</STRONG> del modulo <STRONG>Parametri di gestione assistenza</STRONG> è selezionata, è possibile registrare le transazioni dalle righe dell'ordine di assistenza senza collegare l'ordine a un contratto di assistenza. Se la casella di controllo è deselezionata, prima di registrare le righe dell'ordine di assistenza è necessario almeno collegare l'ordine creato manualmente a un progetto.</P>

## <a name="create-a-service-order-from-a-project"></a>Creare un ordine di assistenza da un progetto

1.  Passare a **Gestione progetti e contabilità** \> **Progetti** \> **Tutti i progetti**.

2.  Nel **riquadro azioni** del modulo **Progetti**, selezionare la scheda **Gestisci** \> **Assistenza** \> **Ordini di assistenza**.

3.  Utilizzare la procedura precedente per la creazione manuale di un ordine di assistenza nel modulo **Ordini di assistenza**. Nel campo **ID progetto** verrà visualizzato il riferimento del progetto.

> [!NOTE]
> <P>Se la casella di controllo <STRONG>Consenti senza contratto di assistenza</STRONG> del modulo <STRONG>Parametri di gestione assistenza</STRONG> è selezionata, è possibile registrare le transazioni dalle righe dell'ordine di assistenza senza collegare l'ordine a un contratto di assistenza. Se la casella di controllo è deselezionata, prima di registrare le righe dell'ordine di assistenza è necessario almeno collegare l'ordine creato manualmente a un progetto.</P>

## <a name="create-a-service-order-from-the-sales-order-form"></a>Creare un ordine di assistenza dal modulo Ordine cliente

È possibile creare un ordine di assistenza dal modulo **Ordini cliente** utilizzando la procedura guidata **Crea un nuovo ordine di assistenza in base all'ordine cliente**.

1.  Andare a **Vendite e marketing** \> **Ordini cliente** \> **Tutti gli ordini cliente**.

2.  Apri l'ordine cliente rilevante.

3.  Nella scheda **Ordine cliente**, selezionare **Ordine di assistenza** per avviare la procedura guidata **Crea un nuovo ordine di assistenza in base all'ordine cliente**.

4.  Selezionare **Avanti \>** e quindi completare i passaggi seguenti nella pagina **Seleziona contratto per ordine di assistenza**:
    
      - Utilizzare il campo **Contratto di assistenza** per selezionare il contratto di assistenza a cui associare il nuovo ordine di assistenza.
    
      - Facoltativo: utilizzare il campo **ID progetto** per associare l'ordine di assistenza a un determinato progetto.

5.  Selezionare **Avanti \>** e quindi completare i passaggi seguenti nella pagina **Crea riga ordine di assistenza**:
    
      - Immettere una data e un'ora in cui iniziare la chiamata di assistenza nel campo **Ora assistenza preferita**.
    
      - Facoltativo: modificare il testo nel campo **Descrizione**. Per impostazione predefinita, questo campo contiene la descrizione del contratto di assistenza selezionato nella finestra precedente.
    
      - Nel campo **Responsabile** selezionare l'ID del dipendente responsabile del contratto e, se conosciuto, l'ID del tecnico preferito dal cliente per l'esecuzione della chiamata di assistenza.
    
      - Nel campo **ID contatto** selezionare la persona all'interno della società del cliente che deve essere contattata riguardo all'ordine di assistenza specificato.

6.  Selezionare **Avanti \>** e quindi **Fine**.


## <a name="see-also"></a>Vedere anche

[Ordini di assistenza](service-orders.md)

[Creare ordini di assistenza automaticamente](create-service-orders-automatically.md)

[Crea ordini di assistenza (modulo di classe)](https://technet.microsoft.com/library/aa553901\(v=ax.60\)) 



[!INCLUDE[footer-include](../../includes/footer-banner.md)]