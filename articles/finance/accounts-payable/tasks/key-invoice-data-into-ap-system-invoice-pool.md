---
title: Inserire dati fattura nel sistema di contabilità fornitore tramite un pool di fatture
description: In questo argomento viene descritto come utilizzare il registro fatture per creare fatture.
author: abruer
ms.date: 07/31/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b9c54f610e45d288ed58fd209d290d73bfe1ff2f
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5820667"
---
# <a name="key-invoice-data-into-the-ap-system-using-invoice-pool"></a>Inserire dati fattura nel sistema di contabilità fornitore tramite un pool di fatture

[!include [banner](../../includes/banner.md)]

In questo argomento viene descritto come utilizzare il registro fatture per creare fatture. Utilizzare quindi il pool di fatture per abbinare la fattura a un ordine fornitore e per finalizzare la spesa nella pagina della fattura fornitore.


## <a name="create-a-purchase-order"></a>Creare un ordine fornitore
1. Nel pannello di navigazione, andare a **Moduli > Contabilità fornitori > Ordini fornitore > Ordini fornitore**.
2. Selezionare **Nuovo** per creare un ordine fornitore.
3. Nel campo **Conto fornitore** selezionare un fornitore per l'elenco a discesa. Selezionare, ad esempio, il fornitore **1001**.
4. Selezionare **OK**.
5. Nel campo **Numero articolo** selezionare il numero di articolo servizi nell'elenco a discesa. Selezionare, ad esempio **S0001**. L'importo netto è 75,00.  Si tratta dell'importo previsto nella fattura.  
6. Nel riquadro azioni selezionare **Acquisto**.
7. Selezionare **Conferma**.

## <a name="create-and-post-and-invoice"></a>Creare e registrare una fattura
1. Nel pannello di navigazione andare a **Moduli > Contabilità fornitori > Fatture > Registro fatture**.
2. Selezionare **Nuovo**.
3. Aprire la ricerca per selezionare il nome del registro fatture che si desidera utilizzare.
4. Selezionare il nome del registro fatture che si desidera utilizzare.
5. Selezionare **Righe** per aprire il registro e immettere le righe di spesa.
6. Nella ricerca selezionare un fornitore. Selezionare, ad esempio, il fornitore **1001**.
7. Nel campo **Fattura** immettere il numero di fattura.
8. Digitare un valore nel campo **Descrizione**
9. Nel campo **Credito** immettere un numero.
10. Nel campo **Ordine fornitore**, aprire l'elenco a discesa per selezionare l'ordine fornitore creato in precedenza.
11. Nel campo **Approvata da**, evidenziare un approvatore nell'elenco a discesa e fare clic su **Seleziona** per selezionare tale approvatore.
12. Selezionare **Registra**.

## <a name="open-an-invoice-from-the-pool-and-match-it-to-a-purchase-order-to-complete-the-invoice-process"></a>Aprire una fattura dal pool e abbinarla a un ordine fornitore per completare il processo di fatturazione
1. Nel pannello di navigazione andare a **Moduli > Contabilità fornitori > Fatture > Pool fatture**.
2. Selezionare **Ordine fornitore** per creare una fattura fornitore dalla fattura nel pool.
3. Selezionare la fattura che si desidera rivedere.
4. Selezionare **Aggiorna stato di abbinamento** per completare l'abbinamento.
5. Nel riquadro azioni selezionare **Opzioni**.
6. Selezionare **Cambia visualizzazione**.
7. Selezionare **Visualizzazione griglia**.
8. Selezionare **Registra**.
9. Chiudere il modulo.
10. Nel pannello di navigazione andare a **Moduli > Contabilità fornitori > Fornitori > Fornitori**.
11. Selezionare il fornitore dell'ordine fornitore. Selezionare, ad esempio, il fornitore **1001**.
12. Nel riquadro azioni, selezionare **Fornitore**.
13. Selezionare **Transazioni**.
14. Selezionare la fattura creata. Il rateo del registro fatture è stato stornato e registrato nel conto spese appropriato.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]