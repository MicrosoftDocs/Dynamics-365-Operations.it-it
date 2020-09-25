---
title: Paese di origine
description: Molte organizzazioni rilasciano certificati ai propri fornitori per garantire che i prodotti soddisfino specifici standard di certificazione. Questi certificati dipendono spesso dal paese di origine. Questo argomento fornisce informazioni sulla funzionalità del paese di origine, che consente di collegare un prodotto al relativo paese di origine e di tenere traccia delle certificazioni del prodotto.
author: dasani-madipalli
manager: tfehr
ms.date: 07/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-07-15
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: d0d93a02817bab8e188818862c1bb7f84b498fc1
ms.sourcegitcommit: 5bb36b74935ffe140367fd6ecf956b4857ad12e5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2020
ms.locfileid: "3802799"
---
# <a name="country-of-origin"></a>Paese di origine

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Molte organizzazioni rilasciano certificati ai propri fornitori per garantire che i prodotti soddisfino specifici standard di certificazione. Questi certificati dipendono spesso dal paese di origine. La funzionalità del paese di origine consente di collegare un prodotto al relativo paese di origine e di tenere traccia delle certificazioni del prodotto.

## <a name="turn-on-the-country-of-origin-feature"></a>Attivare la funzionalità del paese di origine

Prima di poter utilizzare questa funzione, è necessario attivarla nel sistema. Gli amministratori possono utilizzare le impostazioni della [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e abilitarla. Nell'area di lavoro **Gestione funzionalità**, la funzione è elencata nel modo seguente:

- **Modulo:** *Gestione informazioni sul prodotto*
- **Nome funzionalità:** *Funzionalità di gestione del paese di origine*

## <a name="configure-source-and-destination-countries"></a>Configura i paesi di origine e di destinazione

Prima di emettere un certificato per un prodotto, è necessario collegare il prodotto al relativo paese di destinazione e a quello di origine.

1. Andare a **Gestione informazioni sul prodotto \> Impostazione \> Conformità prodotto \> Paese d'origine \> Regole del paese di origine**.
2. Selezionare l'impostazione di un paese esistente da modificare oppure selezionare **Nuovo** nel riquadro azioni per creare una nuova impostazione del paese.
3. Impostare i seguenti valori per il paese selezionato o nuovo.

    | Campo | descrizione |
    |---|---|
    | Numero articolo | Selezionare il numero di articolo del prodotto. |
    | Paese di destinazione | Selezionare il paese a cui si sta inviando il prodotto. |
    | Paese di origine | Selezionare il paese da cui si sta spedendo il prodotto. |

Lo scopo di questa impostazione è di consentire la generazione di un report distinta base (DBA) in cui è possibile includere il paese di origine per ogni parte per cui sono specificati i paesi di origine e destinazione. Questo report consentirà di ottenere un quadro olistico di dove provengono le parti e dove stanno andando.

## <a name="keep-track-of-vendor-certificates"></a>Tenere traccia dei certificati del fornitore

È possibile usare la pagina **Certificati fornitori del paese di origine** per tenere traccia dei certificati rilasciati ai fornitori.

È necessario decidere quali documenti del certificato emettere e come verranno segnalati ai clienti. Questa funzionalità consente di tenere traccia dei certificati. Inoltre, consente di scegliere se visualizzare i numeri di certificato pertinenti su fatture, documenti di trasporto e/o conferme di ordini.

Per configurare l'impostazione dei certificati, procedere come descritto di seguito.

1. Andare a **Gestione informazioni sul prodotto \> Impostazione \> Conformità prodotto \> Paese d'origine \> Certificati fornitori del paese di origine**.
2. Selezionare un'impostazione del certificato esistente da modificare o selezionare **Nuovo** nel riquadro azioni per creare una nuova impostazione del certificato.
3. Impostare le seguenti impostazioni per il certificato selezionato o nuovo.

    | Campo | descrizione |
    |---|---|
    | Account fornitore | Selezionare il fornitore a cui è stato rilasciato il certificato. |
    | Numero articolo | Selezionare l'articolo per il quale è stato rilasciato il certificato. |
    | Paese | Il paese in cui è necessario utilizzare questo certificato. |
    | Numero certificato | Immettere il numero di identificazione del certificato emesso. |
    | Validità | Selezionare la data di inizio della validità del certificato corrente.|
    | Scadenza | Selezionare la data di fine della validità del certificato corrente. |
    | Stampa su fattura | Selezionare questa casella di controllo per stampare il numero di certificato sulle fatture indirizzate al paese specificato durante l'intervallo di date specificato. |
    | Stampa su documento di trasporto | Selezionare questa casella di controllo per stampare il numero di certificato sui documenti di trasporto indirizzati al paese specificato durante l'intervallo di date specificato. |
    | Stampa su ordine cliente | Selezionare questa casella di controllo per stampare il numero di certificato su ordini cliente indirizzati al paese specificato durante l'intervallo di date specificato. |

## <a name="include-the-country-of-origin-on-bom-reports"></a>Includere il paese di origine nei report DBA

Quando si genera un report DBA, è possibile includere il paese di origine per ciascuna parte per la quale sono stati specificati i paesi di origine e destinazione nella pagina **Regole del Paese di origine**.

1. Fare clic su **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.
1. Selezionare o creare un prodotto per aprire la relativa pagina **Dettagli prodotto rilasciato**.
1. Nel riquadro azioni, scheda **Progetta**, gruppo **DBA**, selezionare **Progettazione**.
1. Nella pagina visualizzata, nel riquadro azioni, selezionare **DBA \> Stampa**.
1. Nella finestra di dialogo **Righe della distinta base**, impostare il campo **Paese di destinazione** nel paese di destinazione che si desidera visualizzare nel report.
1. Selezionare **OK**.

Viene generato e visualizzato un report con informazioni sul paese di origine di ciascuna parte. Di seguito è riportato un esempio del report.

![Report del paese di origine](media/country-of-origin-report.png "Report del paese di origine")
