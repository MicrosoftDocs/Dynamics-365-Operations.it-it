--- 
title: Confermare ordini cliente
description: Questa procedura descrive come confermare gli ordini cliente.
author: omulvad
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 7cab69222c5004e6a62c632a9e85085403434ffd
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="confirm-sales-orders"></a>Confermare ordini cliente

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Questa procedura descrive come confermare gli ordini cliente. Verrà illustrato come confermare un singolo ordine e come confermare più ordini cliente contemporaneamente. Queste attività verranno in genere eseguite dal gestore degli ordini cliente. È possibile utilizzare questa procedura nella società di dati dimostrativi USMF oppure nei propri dati. Prima di iniziare, assicurarsi che siano presenti più ordini cliente aperti per lo stesso cliente. Se si utilizza USMF, è possibile utilizzare il cliente US-027.


## <a name="confirm-a-single-sales-order"></a>Confermare un unico ordine cliente
1. Passare a Vendite e marketing > Ordini cliente > Tutti gli ordini cliente.
2. Nell'elenco individuare e selezionare l'ordine che si desidera confermare.
3. Fare clic sul collegamento sul numero di ordine cliente per aprire l'ordine selezionato.
4. Nel riquadro azioni fare clic su Vendi.
5. Fare clic su Conferma ordine cliente.
6. Espandere o comprimere la sezione Parametri.
    * Assicurarsi che il campo Registrazione impostato su Sì sia attivo.  
7. Impostare l'opzione Stampa la conferma su Sì.
    * Il campo Verifica limite di credito specifica il metodo utilizzato per calcolare il credito residuo del cliente. Per impostazione predefinita il codice viene copiato dalla pagina dei parametri Contabilità clienti. Se si desidera ignorare la verifica del limite di credito quando si conferma un ordine cliente specifico, impostare Verifica limite di credito su Nessuna. Tuttavia, è necessario tenere presente che anche se questo campo è impostato su Nessuna, la verifica del limite di credito verrà comunque eseguita se l'opzione Limite di credito obbligatorio viene selezionata nell'anagrafica cliente.  
8. Fare clic su OK.
9. Fare clic su Sì.
10. Chiudere la pagina.
11. Nel riquadro azioni fare clic su Opzioni.
12. Fare clic su Cambia visualizzazione.
13. Fare clic su Visualizzazione intestazione.
    * Quando un ordine viene confermato, lo stato del documento viene impostato su Conferma.  
14. Nel riquadro azioni fare clic su Vendi.
15. Fare clic su Conferma ordine cliente.
16. Chiudere la pagina.

## <a name="confirm-multiple-sales-orders-at-once"></a>Confermare più ordini cliente contemporaneamente
1. Andare a Vendite e marketing > Ordini cliente > Conferma ordine > Conferma ordine cliente.
2. Fare clic su Seleziona.
3. Nell'elenco sulla scheda Intervallo individuare e selezionare il record che fa riferimento al campo Conto cliente.
4. Nel campo Criteri fare clic sul pulsante a discesa per aprire la ricerca.
5. Nell'elenco individuare e selezionare il conto cliente con più ordini per cui si desidera eseguire la conferma in massa.
    * Se si utilizza USMF, è possibile selezionare il conto US-027.  
6. Fare clic su OK.
    * Nella scheda Panoramica viene visualizzato un elenco di ordini che soddisfano i criteri di query. Tali ordini verranno inclusi nella conferma.  
    * Il campo Aggiorna riepilogo per specifica il parametro da cui più ordini devono essere riepilogati in un documento di conferma. Per impostazione predefinita, l'opzione viene copiata dai valori predefiniti per l'impostazione di aggiornamento riepilogativo nella pagina dei parametri della contabilità clienti.  
7. Nel campo Aggiorna riepilogo per selezionare "Ordine".
    * I parametri minimi necessari per creare gli aggiornamenti riepilogativi sono quelli relativi al conto fatture e alla valuta. Ciò significa che gli aggiornamenti di riepilogo con conti fatture e valute diversi non sono consentiti. I parametri aggiuntivi possono essere impostati nella pagina Parametri aggiornamento riepilogativo, a cui è possibile accedere dalla pagina Parametri contabilità clienti.  
8. Nel campo Ordine cliente fare clic sul pulsante a discesa per aprire la ricerca.
9. Nell'elenco selezionare il numero di ordine che si desidera come ordine riepilogativo.
10. Fare clic su Disponi.
11. Fare clic su OK.
12. Fare clic su OK.


