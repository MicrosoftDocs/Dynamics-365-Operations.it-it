---
title: Impostare le autorizzazioni per ordinare prodotti per conto di altri
description: In questo articolo viene illustrato come concedere ai lavoratori l'autorizzazione a preparare richieste di acquisto per conto di altri lavoratori.
author: GalynaFedorova
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchReqAuthorization, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3053f28fdf97637b1da5f644f64676bfd10fb6a0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8854212"
---
# <a name="set-up-permissions-for-ordering-products-on-behalf-of-someone-else"></a>Impostare le autorizzazioni per ordinare prodotti per conto di altri

[!include [banner](../../includes/banner.md)]

In questo articolo viene illustrato come concedere ai lavoratori l'autorizzazione a preparare richieste di acquisto per conto di altri lavoratori. In altre parole, un "preparatore" di richieste di acquisto può creare una richiesta per un altro "richiedente". La procedura inoltre mostra come concedere a un lavoratore l'autorizzazione a ordinare articoli e servizi in persone giuridiche o unità operative differenti. Queste attività vengono in genere svolte da un responsabile degli acquisti. È possibile utilizzare questa procedura sui dati della società di dati dimostrativi USMF oppure sui propri dati.


## <a name="grant-permission-to-enter-purchase-requisitions-on-behalf-of-another-worker"></a>Concedere l'autorizzazione a immettere richieste di acquisto per conto di un altro lavoratore
1. Nel pannello di navigazione andare a **Moduli > Approvvigionamento > Impostazioni > Criteri > Autorizzazioni richiesta di acquisto**. Assicurarsi che il campo **Visualizzazione corrente** sia impostato su **Per preparatore**. L'elenco nel riquadro sinistro mostra le persone a cui è possibile concedere l'autorizzazione a preparare le richieste per conto di altre persone.  
2. Selezionare la persona a cui concedere l'autorizzazione (il preparatore).
3. Selezionare **Aggiungi**.
4. Trovare e selezionare la persona da aggiungere come richiedente.
    - Il richiedente è la persona per conto della quale il preparatore può creare le richieste.  
    - Nel campo **Autorizzazione**, selezionare **Specifico** se il preparatore deve essere in grado di creare le richieste di acquisto per conto del lavoratore selezionato. Selezionare **Report** se il preparatore deve anche essere in grado di creare le richieste di acquisto a nome di tutti i lavoratori subordinati a quel lavoratore.  
5. Nel campo **Validità** immettere una data.
6. Nel campo **Scadenza** immettere una data.

## <a name="view-preparers-who-have-permission-to-create-purchase-requisitions-for-a-selected-worker"></a>Visualizzare i preparatori che hanno l'autorizzazione a creare le richieste di acquisto per un lavoratore selezionato
1. Nel campo **Visualizzazione corrente**, selezionare **Per richiedente**. Questa visualizzazione mostra un elenco dei preparatori a cui sono state concesse autorizzazioni per creare richieste di acquisto per conto di un lavoratore selezionato.  
2. Utilizzare il filtro rapido per trovare il lavoratore appena aggiunto come richiedente.
3. Selezionare il richiedente. L'elenco Preparatore mostra le persone che hanno l'autorizzazione a ordinare articoli per conto del richiedente che è selezionato nel riquadro sinistro.  Potete aggiungere preparatori supplementari qui. Questa visualizzazione inoltre vi consente di concedere al richiedente l'autorizzazione a creare le richieste in persone giuridiche e unità operative che non sono la persona giuridica o l'unità operativa primaria di quella persona.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]