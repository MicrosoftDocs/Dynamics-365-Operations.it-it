---
title: Configurare il mapping per le colonne dello stato dell'ordine cliente
description: In questo argomento viene illustrato come configurare le colonne di stato dell'ordine cliente per la doppia scrittura.
author: dasani-madipalli
ms.date: 06/25/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: damadipa
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-06-25
ms.openlocfilehash: 6eafd9b14d02dec3455b73aeee1264629331a57b8ce760b7db6f6ddbaa7406b8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6741656"
---
# <a name="set-up-the-mapping-for-the-sales-order-status-columns"></a>Configurare il mapping per le colonne dello stato dell'ordine cliente

[!include [banner](../../includes/banner.md)]

Le colonne che indicano lo stato dell'ordine cliente hanno valori di enumerazione diversi in Microsoft Dynamics 365 Supply Chain Management e Dynamics 365 Sales. È necessaria una configurazione aggiuntiva per mappare queste colonne in doppia scrittura.

## <a name="columns-in-supply-chain-management"></a>Colonne in Supply Chain Management

In Supply Chain Management, due colonne riflettono lo stato dell'ordine cliente. Le colonne che devi mappare sono **Stato** e **Stato documento**.

L'enumerazione **Stato** specifica lo stato generale dell'ordine. Questo stato è mostrato nell'intestazione dell'ordine.

L'enumerazione **Stato** include i seguenti valori:

- Ordine aperto
- Consegnata
- Fatturate
- Operazione annullata

L'enumerazione **Stato documento** specifica il documento più recente che è stato generato per l'ordine. Ad esempio, se l'ordine è confermato, questo documento è una conferma dell'ordine cliente. Se un ordine cliente viene fatturato parzialmente e la riga rimanente viene confermata, lo stato del documento rimane **Fattura**, perché la fattura viene generata in un secondo momento nel processo.

L'enumerazione **Stato documento** include i seguenti valori:

- Conferma
- Distinta di prelievo
- Documento di trasporto
- Fattura

## <a name="columns-in-sales"></a>colonne in Sales

In Sales, due colonne indicano lo stato dell'ordine. Le colonne che devi mappare sono **Stato** e **Stato elaborazione**.

L'enumerazione **Stato** specifica lo stato generale dell'ordine. Include i valori seguenti:

- Attive
- Inviate
- Soddisfatto
- Fatturate
- Operazione annullata

L'enumerazione **Stato di elaborazione** è stata introdotta in modo che lo stato possa essere mappato in modo più accurato con Supply Chain Management.

La tabella seguente mostra la mappatura di **Stato di elaborazione** in Supply Chain Management.

| Stato di elaborazione   | Stato in Supply Chain Management | Stato documento in Supply Chain Management |
|---------------------|-----------------------------------|--------------------------------------------|
| Attive              | Ordine aperto                        | Nessuna priorità                                       |
| Confermata           | Ordine aperto                        | Conferma                               |
| Prelevato              | Ordine aperto                        | Distinta di prelievo                               |
| Consegnato in parte | Ordine aperto                        | Documento di trasporto                               |
| Consegnata           | Consegnata                         | Documento di trasporto                               |
| Parzialmente fatturato  | Consegnata                         | Fattura                                    |
| Fatturate            | Fatturate                          | Fattura                                    |
| Operazione annullata           | Operazione annullata                         | Non applicabile                             |

La tabella seguente mostra la mappatura di **Stato di elaborazione** tra Sales e Supply Chain Management.

| Stato di elaborazione   | Stato in Sales | Stato in Supply Chain Management |
|---------------------|-----------------|-----------------------------------|
| Attive              | Attive          | Ordine aperto                        |
| Confermata           | Inviate       | Ordine aperto                        |
| Prelevato              | Inviate       | Ordine aperto                        |
| Consegnato in parte | Attive          | Ordine aperto                        |
| Parzialmente fatturato  | Attive          | Ordine aperto                        |
| Parzialmente fatturato  | Soddisfatto       | Consegnata                         |
| Fatturate            | Fatturate        | Fatturate                          |
| Operazione annullata           | Operazione annullata       | Operazione annullata                         |

## <a name="setup"></a>Attrezzaggio

Per configurare il mapping per le colonne di stato dell'ordine cliente, è necessario abilitare gli attributi **IsSOPIntegrationEnabled** e **isIntegrationUser**.

Per abilitare l'attributo **IsSOPIntegrationEnabled**, segui questi passaggi.

1. In un browser, passa a `https://<test-name>.crm.dynamics.com/api/data/v9.0/organizations`. Sostituisci **\<test-name\>** con il collegamento della tua azienda in Sales.
2. Nella pagina che viene aperta, trova **organizationid** e prendi nota del valore.

    ![Ricerca di organizationid.](media/sales-map-orgid.png)

3. In Sales, apri la console del browser ed esegui il seguente script. Utilizza il valore **organizationid** del passaggio 2.

    ```javascript
    Xrm.WebApi.updateRecord("organization",
    "d9a7c5f7-acbf-4aa9-86e8-a891c43f748c", {"issopintegrationenabled" :
    true}).then(
        function success(result) {
            console.log("Account updated");
            // perform operations on row update
        },
        function (error) {
            console.log(error.message);
            // handle error conditions
        }
    );
    ```

    ![Codice JavaScript nella console del browser.](media/sales-map-script.png)

4. Verifica che **IsSOPIntegrationEnabled** sia impostato su **true**. Utilizza l'URL del passaggio 1 per controllare il valore.

    ![IsSOPIntegrationEnabled impostato su true.](media/sales-map-integration-enabled.png)

Per abilitare l'attributo **isIntegrationUser**, segui questi passaggi.

1. In Sales, vai a **Impostazione \> Personalizzazione \> Personalizza il sistema**, seleziona **Tabella utente** e quindi apri **Modulo \> Utente**.

    ![Apertura del modulo utente.](media/sales-map-user.png)

2. In Esplora campi, trova **Modalità utente integrazione** e fai doppio clic su di esso per aggiungerlo al modulo. Salva le modifiche.

    ![Aggiunta della colonna Modalità utente integrazione al modulo.](media/sales-map-field-explorer.png)

3. In Sales, vai a **Impostazione \> Sicurezza \> Utenti** e cambia la visualizzazione da **Utenti abilitati** a **Utenti dell'applicazione**.

    ![Modifica della visualizzazione da Utenti abilitati a Utenti dell'applicazione.](media/sales-map-enabled-users.png)

4. Seleziona le due voci per **DualWrite IntegrationUser**.

    ![Elenco di utenti dell'applicazione.](media/sales-map-user-mode.png)

5. Cambi il valore della colonna **Modalità utente integrazione** su **Sì**.

    ![Modifica del valore della colonna Modalità utente integrazione.](media/sales-map-user-mode-yes.png)

I tuoi ordini cliente sono ora mappati.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]