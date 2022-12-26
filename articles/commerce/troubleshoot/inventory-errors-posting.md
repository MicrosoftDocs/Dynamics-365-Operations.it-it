---
title: Errori di registrazione dei rendiconti dovuti a inventario non disponibile o conflitti di aggiornamento
description: Questo articolo fornisce possibili soluzioni alternative per i problemi relativi all'inventario durante la registrazione dei rendiconti in Microsoft Dynamics 365 Commerce.
author: Shajain
ms.date: 12/19/2022
ms.topic: Troubleshooting
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: shajain
ms.search.validFrom: 2021-01-31
ms.openlocfilehash: cebb890b42def6e9b002b01be63266b88bfc35a4
ms.sourcegitcommit: 4ad87483ba0bfea3e04fdb7e578d8abc34e607a4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2022
ms.locfileid: "9887629"
---
# <a name="statement-posting-errors-due-to-unavailable-inventory-or-update-conflicts"></a>Errori di registrazione dei rendiconti dovuti a inventario non disponibile o conflitti di aggiornamento

[!include [banner](../../includes/banner.md)]

Questo articolo fornisce possibili soluzioni alternative per i problemi relativi all'inventario durante la registrazione dei rendiconti in Microsoft Dynamics 365 Commerce.

## <a name="description"></a>Description

Durante la registrazione delle transazioni commerciali, potresti ricevere messaggi di errore relativi a problemi di inventario o conflitti di aggiornamento.

### <a name="inventory-issues-error-message"></a>Messaggio di errore per problemi di inventario

Se riscontri problemi di inventario, il messaggio di errore che ricevi sarà simile a questo esempio:

> Impossibile prelevare xx. È disponibile solo una quantità di scorte pari a yy.

### <a name="update-conflict-error-messages"></a>Messaggi di errore di conflitto di aggiornamento

Un problema di conflitto di aggiornamento si può verificare quando il metodo di valutazione dell'inventario è *costo standard* o *media mobile*. Poiché entrambi questi metodi sono metodi di costi perpetuo, il costo finale viene determinato al momento della registrazione.

Se stai usando il metodo *media mobile*, il messaggio di errore di conflitto di aggiornamento che ricevi è simile a questo esempio:

> Il valore dell'inventario xx.xx non è previsto dopo il calcolo della spesa proporzionale

Se stai usando il metodo *costi standard*, il messaggio di errore di conflitto di aggiornamento che ricevi è simile a questo esempio:

> Il costo standard non corrisponde al valore dell'inventario finanziario dopo l'aggiornamento. Valore = xx.xx, Qtà = yy.yy, Costo standard = zz.zz

## <a name="resolutions"></a>Soluzioni

### <a name="workaround-for-the-inventory-error"></a>Soluzione alternativa per l'errore di inventario

È possibile mitigare l'errore di inventario aggiornando manualmente l'inventario per l'articolo o abilitando l'inventario fisico negativo per il gruppo di modelli articolo associato all'articolo in Commerce headquarters.

Per un'esperienza di registrazione coerente, Microsoft consiglia di abilitare l'inventario fisico negativo per il gruppo di modelli articolo. In alcuni scenari, i rendiconti potrebbero non essere registrati a meno che non sia abilitato un inventario fisico negativo.

Ad esempio, non è disponibile alcun inventario per un articolo, ma un cassiere restituisce l'articolo e lo aggiunge nuovamente alla stessa transazione a un prezzo ridotto per simulare una corrispondenza di prezzo. In questo caso, sia la transazione di reso che la transazione di vendita verranno inserite nello stesso estratto conto del singolo ordine cliente. Tuttavia, poiché non vi è alcuna garanzia che la riga di reso (che aumenta l'inventario) venga registrata prima della registrazione della riga di vendita (che riduce l'inventario), possono verificarsi errori di inventario. Se l'inventario fisico negativo è abilitato in questo scenario, la registrazione della transazione non viene alterata negativamente e il sistema riflette correttamente l'inventario.

#### <a name="enable-negative-physical-inventory-for-an-item-model-group"></a>Abilitare l'inventario fisico negativo per un gruppo di modelli articolo

Per abilitare l'inventario fisico negativo per un gruppo di modelli articolo in Commerce headquarters, attieniti alla seguente procedura.

1. Vai a **Gestione inventario \> Impostazioni \> Inventario**.
1. Seleziona il gruppo di modelli articolo nel pannello di navigazione a sinistra.
1. Nella sezione **Criteri di inventario**, sotto **Inventario negativo**, seleziona la casella di controllo **Inventario fisico negativo**.

![Inventario fisico negativo abilitato.](./media/Physical_Negative_Inventory.png)

### <a name="workaround-for-the-update-conflict-error"></a>Soluzione alternativa per l'errore di conflitto di aggiornamento

Per possibili soluzioni alternative per correggere l'errore di conflitto di aggiornamento, vedi [Si verifica un conflitto di aggiornamento quando il metodo di valutazione dell'inventario è costo standard o media mobile](/troubleshoot/dynamics-365/supply-chain/costing/update-conflict-standard-cost-moving-average-inventory-valuation).

> [!NOTE]
> Per l'errore di conflitto di aggiornamento, non è necessario eliminare gli ordini cliente generati utilizzando il passaggio di aggregazione della registrazione. Dopo aver implementato le soluzioni alternative suggerite, l'estratto conto dovrebbe essere registrato tenti nuovamente la registrazione dell'estratto conto.
