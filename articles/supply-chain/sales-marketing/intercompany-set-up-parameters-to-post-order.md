---
title: Impostare i parametri per la registrazione di un ordine interaziendale
description: In questo argomento viene illustrato come impostare parametri per registrare un ordine interaziendale
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: c728f2f491948ae1c8550396ba4d72f76f46fe85
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548353"
---
# <a name="set-up-parameters-to-post-an-intercompany-order"></a>Impostare i parametri per la registrazione di un ordine interaziendale

[!include [banner](../../includes/banner.md)]

Quando si registra una fattura cliente interaziendale, è possibile impostare anche la registrazione automatica dell'ordine fornitore interaziendale e della fattura cliente originaria.

> [!NOTE]
> Prima di eseguire questa procedura, impostare la gestione della stampa dell'organizzazione per selezionare la stampante corretta per la stampa della fattura dell'ordine cliente originario.

A tale scopo è necessario impostare i seguenti parametri:

1. Seleziona **Vendite e marketing \> Ordini cliente \> Tutti gli ordini cliente**. Selezionare l'ordine cliente che si desidera utilizzare.
1. Nel riquadro Azioni dell'ordine cliente selezionare **Visualizzazione intestazione**, quindi selezionare la Scheda dettaglio **Impostazioni interaziendali** per aprirla.
1. Andare al riquadro Azioni, sulla scheda **Ordine cliente**, quindi selezionare **Modifica**.
1. Tornare alla Scheda dettaglio **Impostazioni interaziendali** e selezionare **Consegna diretta** per consentire la consegna diretta attraverso la catena interaziendale per tutti gli ordini.
1. Selezionare **Salva** per salvare l'ordine cliente con la nuova impostazione. Quindi, selezionare **Chiudi** per chiudere l'ordine cliente.
1. Andare ad **Approvvigionamento \> Fornitori \> Tutti i fornitori**. Sulla scheda **Generale**, selezionare **Interaziendale**.
1. Nella pagina **Interaziendale**, selezionare il collegamento **Criteri ordine fornitore**. Nel gruppo di campi **Ordine fornitore interaziendale (consegna diretta)**, selezionare **Registra fattura automaticamente** e rimuovere il segno di spunta dal campo **Stampa fattura automaticamente**.
1. Nel gruppo di campi **Ordine cliente originario (consegna diretta)**, selezionare il campo **Registra fattura automaticamente** e il campo **Stampa fattura automaticamente**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
