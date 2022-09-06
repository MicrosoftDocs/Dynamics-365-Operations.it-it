---
title: Condivisione dati interaziendali per gift card
description: In questo articolo viene descritto come configurare Microsoft Dynamics 365 Commerce per utilizzare la funzionalità di condivisione dati di Dynamics 365 Finance tra aree dati per sincronizzare i dati delle gift card.
author: BrianShook
ms.date: 08/26/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.custom: 141393
ms.assetid: e23e944c-15de-459d-bcc5-ea03615ebf4c
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2022-06-20
ms.openlocfilehash: b56890b546c3cd74b75cf447e62495733ea8d288
ms.sourcegitcommit: 09d4805aea6d148de47c8ca38d8244bbce9786ce
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387068"
---
# <a name="cross-company-data-sharing-for-gift-cards"></a>Condivisione dati interaziendali per gift card

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

In questo articolo viene descritto come configurare Microsoft Dynamics 365 Commerce di modo che utilizzi la funzionalità di condivisione dati di Dynamics 365 Finance per sincronizzare i dati delle gift card. La funzionalità di condivisione dei record di dati può quindi essere utilizzata per condividere i dati tra aziende tra due aree di dati. In questo modo, la tabella delle gift card interna di Commerce può condividere i dati tra due entità aziendali. Per ulteriori informazioni sulla condivisione dati interaziendali di Dynamics 365 Finance, vedi [Condivisione dati interaziendali](/dynamics365/fin-ops-core/dev-itpro/sysadmin/cross-company-data-sharing).

## <a name="key-terms"></a>Termini importanti

| Termine | Description |
|---|---|
| Società | La persona giuridica nell'ambiente Dynamics 365 Finance. |
| Gift card | Il prodotto gift card interno di Dynamics 365 Commerce. |

## <a name="prerequisites"></a>Prerequisiti

Gli utenti devono configurare il proprio ambiente per la condivisione dati interaziendali come descritto in [Condivisione dati interaziendali](/dynamics365/fin-ops-core/dev-itpro/sysadmin/cross-company-data-sharing).

**RetailGiftCardTable** deve avere il campo **DataSharingType** impostato su **Duplica** per abilitare la condivisione di record duplicati per la tabella delle gift card. Per ulteriori informazioni, vedi [Condivisione dati interaziendali per sviluppatori](/dynamics365/fin-ops-core/dev-itpro/sysadmin/drs-srs-dev).

## <a name="configure-cross-company-data-sharing-for-gift-cards"></a>Configurare la condivisione dati interaziendali per gift card

Per configurare la condivisione dati interaziendali per gift card, procedi come segue.

1. In Commerce headquarters, vai a **Amministrazione sistema \> Impostazione \> Configura condivisione dati interaziendali**.
1. Per aggiungere un record di configurazione dati, seleziona **Nuovo** nel riquadro Azioni.
1. Nel campo **Nome**, immetti un nome per il record di condivisione dati (ad esempio,**Gift card**).
1. Nella sezione **Tabelle e campi da condividere**, seleziona **Aggiungi**.
1. Nella finestra di dialogo **Condividi nuova tabella**, nel campo **Nome tabella**, immetti **RETAILGIFTCARDTABLE** (la tabella per gift card al dettaglio). Il campo **Etichetta tabella** deve essere impostato automaticamente su **Tabella gift card**.
1. Assicurati che le caselle di controllo **Salva dati per società**, **Con indice univoco** e **Non ancora condiviso** sono tutte selezionate. La selezione di queste caselle di controllo attiva le convalide relative alla funzionalità di condivisione dati.
1. Selezionare **Aggiungi tabella**. Il record **Tabella gift card (RetailGiftCardTable)** deve ora apparire sotto **Tabelle e campi da condividere**. Seleziona l'accento circonflesso (^) per visualizzare tutti i campi della tabella automaticamente associati alla tabella per la condivisione.
1. Nella sezione **Società che condividono i record in queste tabelle**, seleziona **Aggiungi** per aggiungere un'azienda con cui condividere i dati.
1. Nella riga sotto **Società**, seleziona una società nell'elenco a discesa.
1. Nel campo **Nome**, immetti il nome della società.
1. Ripeti i passaggi da 8 a 10 per aggiungere altre righe.
1. Quando hai finito di aggiungere le righe della società, nel riquadro azioni seleziona **Abilita**.
1. Viene visualizzato il messaggio di avviso seguente: "Si consiglia di eseguire questa azione solo durante l'orario non lavorativo. Le operazioni simultanee non verranno eseguite per le tabelle nei criteri. Continuare?" Seleziona **Sì** per confermare.
1. Viene visualizzato il messaggio di avviso seguente: "Copiare adesso tutti i dati esistenti tra tutte le società condivise?" Seleziona **Sì** per confermare.

Dopo aver accettato entrambi i messaggi, le tabelle inizieranno a copiare i dati tra le società configurate. I saldi che si verificano rispetto a una gift card aziendale saranno quindi visibili all'altra società.

## <a name="additional-resources"></a>Risorse aggiuntive

[Domande frequenti sui pagamenti](payments-retail.md)

[Modulo checkout](../add-checkout-module.md)

[Modulo pagamento](../payment-module.md)
