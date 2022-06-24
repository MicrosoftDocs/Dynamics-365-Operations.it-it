---
title: Impostare informazioni su gruppo TDS, PAN e TAN per clienti e fornitori
description: In questo articolo viene illustrato come impostare le informazioni sul gruppo TDS (Tax Deducted at Source, imposta dedotta all'origine), PAN (Permanent Account Number, numero di conto permanente) e TAN (Tax Account Number, numero di conto imposta) per fornitori e clienti.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 1a29f59e380360b6f828dcddbe84cad229b42d17
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8859768"
---
# <a name="tds-group-pan-and-tan-information-setup-for-vendors-and-customers"></a>Impostazione delle informazioni su gruppo TDS, PAN e TAN per clienti e fornitori

[!include [banner](../includes/banner.md)]

In questo articolo viene illustrato come impostare le informazioni sul gruppo TDS (Tax Deducted at Source, imposta dedotta all'origine), PAN (Permanent Account Number, numero di conto permanente) e TAN (Tax Account Number, numero di conto imposta) per fornitori e clienti.

1. Andare a **Contabilità fornitori \> Fornitori \> Tutti i fornitori** o **Contabilità clienti \> Clienti \> Tutti i clienti**.

    [![Pagina Tutti i fornitori.](./media/apac-ind-TDS-55.png)](./media/apac-ind-TDS-55.png)

2. Nel riquadro azioni selezionare **Nuovo** per creare un fornitore o un cliente e immettere i dettagli necessari. In alternativa, selezionare un fornitore o un cliente esistente.
3. Nella Scheda dettaglio **Fattura e consegna**, nella sezione **Ritenuta d'acconto**, impostare l'opzione **Calcola ritenuta d'acconto** su **Sì** per calcolare la ritenuta d'acconto, la TDS o la TCS del fornitore o del cliente.
4. La TDS per una fattura di acquisto viene calcolata in base al gruppo TDS predefinito definito per il fornitore o il cliente. Nel campo **Gruppo TDS**, selezionare il gruppo TDS predefinito.

    > [!NOTE]
    > Quando si seleziona un gruppo TDS nel campo **Gruppo TDS**, i campi **Gruppo ritenute d'acconto** e **Gruppo TCS** non sono più disponibili.

5. Nella Scheda dettaglio **Informazioni fiscali**, nella sezione **Informazioni PAN**, nel campo **Stato** selezionare lo stato del numero di conto permanente per il fornitore o il cliente:

    - **Non disponibile** - Il venditore o il cliente non dispone di un PAN.
    - **Ricevuto** - Il venditore o il cliente ha un PAN.
    - **Richiesto** - Il venditore o il cliente ha richiesto un PAN.
    - **Non valido** - Il venditore o il cliente ha un PAN, ma non è valido.

6. Se si è selezionato **Ricevuto** nel campo **Stato** per indicare che il fornitore o il cliente ha un PAN, immettere il PAN nel campo **Numero**. Il PAN deve essere composto da cinque caratteri alfabetici, quattro caratteri numerici e un carattere alfabetico. Ad esempio: **ABCDE1260A**.
7. Se si è selezionato **Richiesto** nel campo **Stato** per indicare che il fornitore o il cliente ha richiesto un PAN, immettere il numero di riferimento nel campo **Numero di riferimento**.
8. Nel campo **Natura soggetto valutato** selezionare la natura della categoria di soggetto valutato a cui appartiene il fornitore o il cliente:

    - Società
    - HUF
    - Stabilizza
    - Singolo
    - AOP
    - BOI
    - Autorità locale
    - Altro

    [![Scheda dettaglio Informazioni fiscali.](./media/apac-ind-TDS-56.png)](./media/apac-ind-TDS-56.png)

9. Nel riquadro azioni, nella scheda **Fornitore**, nel gruppo **Registrazione** , selezionare **ID registrazione** per aprire la pagina **Gestisci indirizzi**.
10. Nella pagina **Gestisci indirizzi**, nella Scheda dettaglio **Informazioni fiscali**, selezionare **Aggiungi** o **Modifica** per aprire la pagina **Gestisci informazioni fiscali**, in cui è possibile mantenere la voce di registrazione fiscale.
11. Nella pagina **Gestisci informazioni fiscali**, nella Scheda dettaglio **Ritenuta d'acconto**, nel campo **Numero conto imposta (TAN)**, immettere il TAN. Il TAN deve essere composto da quattro caratteri alfabetici, cinque caratteri numerici e un carattere alfabetico. Ad esempio: **AFGH54821T**.
12. Chiudi la pagina.
