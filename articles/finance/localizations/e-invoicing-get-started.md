---
title: Introduzione alla fatturazione elettronica
description: Questo argomento fornisce informazioni introduttive sulla fatturazione elettronica in Microsoft Dynamics 365 Finance e Dynamics 365 Supply Chain Management.
author: gionoder
ms.date: 08/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 3ba0b68ee61b130b8d0304d0bac6d1d720af8139
ms.sourcegitcommit: baf82100f0aa7d5f5f47c7f54bc155d8a07beab5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2021
ms.locfileid: "7463842"
---
# <a name="get-started-with-electronic-invoicing"></a>Introduzione alla fatturazione elettronica

[!include [banner](../includes/banner.md)]

Questo argomento fornisce informazioni introduttive sulla fatturazione elettronica. Questo argomento guida l'utente attraverso i passaggi di configurazione comuni in Regulatory Configuration Services (RCS) e Dynamics 365 Finance e fornisce i passaggi da seguire per inviare documenti commerciali e rivedere i risultati dell'elaborazione.

## <a name="prerequisites"></a>Prerequisiti

Prima di poter completare le procedure in questo argomento, è necessario soddisfare i seguenti prerequisiti:

- Configura il tuo ambiente Microsoft Dynamics Lifecycle Services (LCS), Regulatory Configuration Service (RCS) e Microsoft Dynamics 365 Finance o Dynamics 365 Supply Chain Management. Per ulteriori informazioni, vedi [Introduzione all'amministrazione del servizio della fatturazione elettronica](e-invoicing-get-started-service-administration.md).
- Crea un provider di configurazioni per la tua organizzazione. Per ulteriori informazioni, vedi [Creare un provider di configurazioni e contrassegnarlo come attivo](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="import-an-electronic-invoicing-feature-from-the-microsoft-configuration-provider"></a>Importa una funzionalità di fatturazione elettronica dal provider di configurazioni Microsoft 

1. Accedi al tuo account Regulatory Configuration Service (RCS).
2. Nell'area di lavoro **Funzionalità di globalizzazione**, nella sezione **Funzionalità**, seleziona il riquadro **Fatturazione elettronica**.
3. Selezionare **Importa** e quindi selezionare **Sincronizza**.
4. Filtra la colonna **Provider di configurazioni** per il termine **Microsoft**.
5. Selezionare il nome di una funzione di fatturazione elettronica dalla tabella, quindi selezionare **Importa**.

## <a name="create-an-electronic-invoicing-feature-under-your-organization-provider"></a>Crea una funzionalità di fatturazione elettronica nel provider dell'organizzazione

1. In RCS, nell'area di lavoro **Funzionalità di globalizzazione** della sezione **Funzionalità**, selezionare il riquadro **Fatturazione elettronica**.
2. Seleziona **Aggiungi** > **Basato su funzionalità esistente** e nel campo **Nome** immetti il nome della funzione di fatturazione elettronica.
3. Nel campo **Descrizione** immettere una descrizione della funzione.
4. Nel **campo funzione di base**, seleziona la funzionalità di fatturazione elettronica importata dal provider di configurazioni Microsoft.
5. Selezionare **Crea funzionalità**.

## <a name="country-specific-configuration-for-electronic-invoicing-feature"></a>Configurazione specifica del paese per la funzionalità di fatturazione elettronica

A seconda del paese o dell'area geografica, la funzione Fatturazione elettronica potrebbe richiedere una configurazione specifica. 

Per i passaggi specifici, vedi la documentazione "Introduzione" disponibile per il tuo paese o area geografica.

## <a name="import-the-model-mapping-configurations-from-electronic-reporting"></a>Importare le configurazioni di mapping modello dalla creazione di report elettronici

1. In RCS, seleziona l'area di lavoro **Creazione di report elettronici**.
2. Nell'elenco di provider di configurazioni **Microsoft** seleziona **Repository**.
3. Seleziona **Globale** e nel riquadro azioni seleziona **Apri**.
4. Importa le configurazioni del mapping di modello secondo la seguente tabella in base al nome della funzione.

| Nome funzionalità                         | Configurazione del mapping di modello |
|--------------------------------------|-----------------------------|
| Fatture elettroniche austriache (AT)    | <p>Modello contesto fattura cliente</p><p>Modello di fattura</p> |
| Fattura elettronica belga (BE)      | <p>Modello contesto fattura cliente</p><p>Modello di fattura</p> |
| NF-e brasiliano (BR)                  | <p>Modello contesto fattura cliente</p><p>Documenti fiscali</p><p>Modello messaggio di risposta</p> |
| Brasiliano NFS-e ABRASF Curitiba (BR) | <p>Modello contesto fattura cliente</p><p>Documenti fiscali</p><p>Modello messaggio di risposta</p> |
| Fattura elettronica danese (DK)       | <p>Modello contesto fattura cliente</p><p>Modello di fattura</p> |
| Fattura elettronica egiziana (EG)     | <p>Modello contesto fattura cliente</p><p>Modello di fattura</p><p>Modello messaggio di risposta</p> |
| Fattura elettronica estone (EE)     | <p>Modello contesto fattura cliente</p><p>Modello di fattura</p> |
| Fattura elettronica finlandese (FI)       | <p>Modello contesto fattura cliente</p><p>Modello di fattura</p> |
| Fattura elettronica francese (FR)       | <p>Modello contesto fattura cliente</p><p>Modello di fattura</p> |
| Fattura elettronica tedesca (DE)       | <p>Modello contesto fattura cliente</p><p>Modello di fattura</p> |
| FatturaPA (IT)                       | <p>Modello contesto fattura cliente</p><p>Modello di fattura</p> |
| Messicano CFDI Interfactura (MX)       | <p>Modello contesto fattura cliente</p><p>Modello di fattura</p><p>Modello messaggio di risposta</p> |
| Fattura elettronica olandese (NL)        | <p>Modello contesto fattura cliente</p><p>Modello di fattura</p> |
| Fattura elettronica norvegese (NO)    | <p>Modello contesto fattura cliente</p><p>Modello di fattura</p> |
| Fattura elettronica spagnola (ES)      | <p>Modello contesto fattura cliente</p><p>Modello di fattura</p> |
| Fattura elettroniche PEPPOL            | <p>Modello contesto fattura cliente</p><p>Modello di fattura</p> |


## <a name="configure-the-application-setup"></a>Configurare l'impostazione dell'applicazione

1. Seleziona la funzione Fatturazione elettronica che hai creato.
2. Nella scheda **Impostazioni**, selezionare **Impostazione applicazioni**.
3. Nel campo **Connetti applicazione** seleziona la connessione associata all'istanza di Finance o Supply Chain Management.
4. Nella sezione **Tipi di documento elettronico**, seleziona **Aggiungi**.
5. Seleziona e inserisci un valore **Nome tabella** secondo la tabella seguente.

    | Nome funzionalità                         | Documento aziendale | Nome tabella |
    |--------------------------------------|-------------------|------------|
    | Fatture elettroniche austriache (AT)    | <p>Fattura di vendita</p><p>Fattura progetto</p> | <p>Giornale di registrazione fatture cliente</p><p>Fattura progetto</p> |
    | Fattura elettronica belga (BE)      | <p>Fattura di vendita</p><p>Fattura progetto</p> | <p>Giornale di registrazione fatture cliente</p><p>Fattura progetto</p> |
    | NF-e brasiliano (BR)                  | <p>Documento fiscale</p><p>Lettera di correzione</p> | Documento fiscale |
    | Brasiliano NFS-e ABRASF Curitiba (BR) | Documento fiscale di servizio | Documento fiscale |
    | Fattura elettronica danese (DK)       | <p>Fattura di vendita</p><p>Fattura progetto</p> | <p>Giornale di registrazione fatture cliente</p><p>Fattura progetto</p> |
    | Fattura elettronica egiziana (EG)     | <p>Fattura di vendita</p><p>Fattura progetto</p> | <p>Giornale di registrazione fatture cliente</p><p>Fattura progetto</p> |
    | Fattura elettronica estone (EE)     | <p>Fattura di vendita</p><p>Fattura progetto</p> | <p>Giornale di registrazione fatture cliente</p><p>Fattura progetto</p> |
    | Fattura elettronica finlandese (FI)       | <p>Fattura di vendita</p><p>Fattura progetto</p> | <p>Giornale di registrazione fatture cliente</p><p>Fattura progetto</p> |
    | Fattura elettronica francese (FR)       | <p>Fattura di vendita</p><p>Fattura progetto</p> | <p>Giornale di registrazione fatture cliente</p><p>Fattura progetto</p> |
    | Fattura elettronica tedesca (DE)       | <p>Fattura di vendita</p><p>Fattura progetto</p> | <p>Giornale di registrazione fatture cliente</p><p>Fattura progetto</p> |
    | FatturaPA (IT)                       | <p>Fattura di vendita</p><p>Fattura progetto | <p>Giornale di registrazione fatture cliente</p><p>Fattura progetto</p> |
    | Messicano CFDI Interfactura (MX)       | <p>Fattura di vendita</p><p>Documento di trasporto</p><p>Trasferimento scorte</p><p>Complemento di pagamento</p> | Giornale di registrazione fatture cliente |
    | Fattura elettronica olandese (NL)        | <p>Fattura di vendita</p><p>Fattura progetto</p> | <p>Giornale di registrazione fatture cliente</p><p>Fattura progetto</p> |
    | Fattura elettronica norvegese (NO)    | <p>Fattura di vendita</p><p>Fattura progetto</p> | <p>Giornale di registrazione fatture cliente</p><p>Fattura progetto</p> |
    | Fattura elettronica spagnola (ES)      | <p>Fattura di vendita</p><p>Fattura progetto</p> | <p>Giornale di registrazione fatture cliente</p><p>Fattura progetto</p> |
    | Fattura elettroniche PEPPOL            | <p>Fattura di vendita</p><p>Fattura progetto</p> | <p>Giornale di registrazione fatture cliente</p><p>Fattura progetto</p> |

6. Per ogni nome di tabella creato, seleziona e inserisci un valore contesto secondo la tabella seguente.

    | Nome funzionalità                         | Documento aziendale | Contesto |
    |--------------------------------------|-------------------|---------|
    | Fatture elettroniche austriache (AT)    | <p>Fattura di vendita</p><p>Fattura progetto</p> | <p>Modello di contesto della fattura cliente - Contesto della fattura cliente</p><p>Modello di contesto della fattura cliente - Contesto della fattura di progetto</p> |
    | Fattura elettronica belga (BE)      | <p>Fattura di vendita</p><p>Fattura progetto</p> | <p>Modello di contesto della fattura cliente - Contesto della fattura cliente</p><p>Modello di contesto della fattura cliente - Contesto della fattura di progetto</p> |
    | NF-e brasiliano (BR)                  | <p>Documento fiscale</p><p>Lettera di correzione</p> | <p>Modello di contesto della fattura cliente - Contesto documento fiscale</p><p>Modello di contesto della fattura cliente - Contesto di lettera di correzione FD</p> |
    | Brasiliano NFS-e ABRASF Curitiba (BR) | Documento fiscale di servizio| Modello di contesto della fattura cliente - Contesto documento fiscale |
    | Fattura elettronica danese (DK)       | <p>Fattura di vendita</p><p>Fattura progetto</p> | <p>Modello di contesto della fattura cliente - Contesto della fattura cliente</p><p>Modello di contesto della fattura cliente - Contesto della fattura di progetto</p> |
    | Fattura elettronica egiziana (EG)     | <p>Fattura di vendita</p><p>Fattura progetto</p> | <p>Modello di contesto della fattura cliente - Contesto della fattura cliente</p><p>Modello di contesto della fattura cliente - Contesto della fattura di progetto</p> |
    | Fattura elettronica estone (EE)     | <p>Fattura di vendita</p><p>Fattura progetto</p> | <p>Modello di contesto della fattura cliente - Contesto della fattura cliente</p><p>Modello di contesto della fattura cliente - Contesto della fattura di progetto</p> |
    | Fattura elettronica finlandese (FI)       | <p>Fattura di vendita</p><p>Fattura progetto</p> | <p>Modello di contesto della fattura cliente - Contesto della fattura cliente</p><p>Modello di contesto della fattura cliente - Contesto della fattura di progetto</p> |
    | Fattura elettronica francese (FR)       | <p>Fattura di vendita</p><p>Fattura progetto</p> | <p>Modello di contesto della fattura cliente - Contesto della fattura cliente</p><p>Modello di contesto della fattura cliente - Contesto della fattura di progetto</p> |
    | Fattura elettronica tedesca (DE)       | <p>Fattura di vendita</p><p>Fattura progetto</p> | <p>Modello di contesto della fattura cliente - Contesto della fattura cliente</p><p>Modello di contesto della fattura cliente - Contesto della fattura di progetto</p> |
    | FatturaPA (IT)                       | <p>Fattura di vendita</p><p>Fattura progetto</p> | <p>Modello di contesto della fattura cliente - Contesto della fattura cliente</p><p>Modello di contesto della fattura cliente - Contesto della fattura di progetto</p> |
    | Messicano CFDI Interfactura (MX)       | <p>Fattura di vendita</p><p>Documento di trasporto</p><p>Trasferimento scorte</p><p>Complemento di pagamento</p> | Modello di contesto della fattura cliente - Contesto della fattura cliente |
    | Fattura elettronica olandese (NL)        | <p>Fattura di vendita</p><p>Fattura progetto</p> | <p>Modello di contesto della fattura cliente - Contesto della fattura cliente</p><p>Modello di contesto della fattura cliente - Contesto della fattura di progetto</p> |
    | Fattura elettronica norvegese (NO)    | <p>Fattura di vendita</p><p>Fattura progetto</p> | <p>Modello di contesto della fattura cliente - Contesto della fattura cliente</p><p>Modello di contesto della fattura cliente - Contesto della fattura di progetto</p> |
    | Fattura elettronica spagnola (ES)      | <p>Fattura di vendita</p><p>Fattura progetto</p> | <p>Modello di contesto della fattura cliente - Contesto della fattura cliente</p><p>Modello di contesto della fattura cliente - Contesto della fattura di progetto</p> |
    | Fattura elettroniche PEPPOL            | <p>Fattura di vendita</p><p>Fattura progetto</p> | <p>Modello di contesto della fattura cliente - Contesto della fattura cliente</p><p>Modello di contesto della fattura cliente - Contesto della fattura di progetto</p> |

7. Per ogni nome di tabella e contesto, seleziona e immetti un valore mapping documento aziendale secondo la tabella seguente.

    | Nome funzionalità                         | Documento aziendale | Mapping di documento aziendale |
    |--------------------------------------|-------------------|---------------------------|
    | Fatture elettroniche austriache (AT)    | <p>Fattura di vendita</p><p>Fattura progetto</p> | <p>Mapping di modello di fattura - Fattura cliente</p><p>Mapping di modello di fattura - Fattura di progetto</p> |
    | Fattura elettronica belga (BE)      | <p>Fattura di vendita</p><p>Fattura progetto</p> | <p>Mapping di modello di fattura - Fattura cliente</p><p>Mapping di modello di fattura - Fattura di progetto</p> |
    | NF-e brasiliano (BR)                  | <p>Documento fiscale</p><p>Lettera di correzione</p> | <p>Mapping di documento fiscale - Mapping di documento fiscale</p><p>Mapping di documento fiscale - Mapping di lettera di correzione</p> |
    | Brasiliano NFS-e ABRASF Curitiba (BR) | Documento fiscale di servizio | Mapping di documento fiscale - Mapping di documento fiscale |
    | Fattura elettronica danese (DK)       | <p>Fattura di vendita</p><p>Fattura progetto</p> | <p>Mapping di modello di fattura - Fattura cliente</p><p>Mapping di modello di fattura - Fattura di progetto</p> |
    | Fattura elettronica egiziana (EG)     | <p>Fattura di vendita</p><p>Fattura progetto</p> | <p>Mapping di modello di fattura - Fattura cliente</p><p>Mapping di modello di fattura - Fattura di progetto</p> |
    | Fattura elettronica estone (EE)     | <p>Fattura di vendita</p><p>Fattura progetto</p> | <p>Mapping di modello di fattura - Fattura cliente</p><p>Mapping di modello di fattura - Fattura di progetto</p> |
    | Fattura elettronica finlandese (FI)       | <p>Fattura di vendita</p><p>Fattura progetto</p> | <p>Mapping di modello di fattura - Fattura cliente</p><p>Mapping di modello di fattura - Fattura di progetto</p> |
    | Fattura elettronica francese (FR)       | <p>Fattura di vendita</p><p>Fattura progetto</p> | <p>Mapping di modello di fattura - Fattura cliente</p><p>Mapping di modello di fattura - Fattura di progetto</p> |
    | Fattura elettronica tedesca (DE)       | <p>Fattura di vendita</p><p>Fattura progetto</p> | <p>Mapping di modello di fattura - Fattura cliente</p><p>Mapping di modello di fattura - Fattura di progetto</p> |
    | FatturaPA (IT)                       | <p>Fattura di vendita</p><p>Fattura progetto</p> | <p>Mapping di modello di fattura - Fattura cliente</p><p>Mapping di modello di fattura - Fattura di progetto</p> |
    | Messicano CFDI Interfactura (MX)       | <p>Fattura di vendita</p><p>Documento di trasporto</p><p>Trasferimento scorte</p><p>Complemento di pagamento</p> | Mapping di modello di fattura - Fattura cliente |
    | Fattura elettronica olandese (NL)        | <p>Fattura di vendita</p><p>Fattura progetto</p> | <p>Mapping di modello di fattura - Fattura cliente</p><p>Mapping di modello di fattura - Fattura di progetto</p> |
    | Fattura elettronica norvegese (NO)    | <p>Fattura di vendita</p><p>Fattura progetto</p> | <p>Mapping di modello di fattura - Fattura cliente</p><p>Mapping di modello di fattura - Fattura di progetto</p> |
    | Fattura elettronica spagnola (ES)      | <p>Fattura di vendita</p><p>Fattura progetto</p> | <p>Mapping di modello di fattura - Fattura cliente</p><p>Mapping di modello di fattura - Fattura di progetto</p> |
    | Fattura elettroniche PEPPOL            | <p>Fattura di vendita</p><p>Fattura progetto</p> | <p>Mapping di modello di fattura - Fattura cliente</p><p>Mapping di modello di fattura - Fattura di progetto</p> |


## <a name="country-specific-configuration-of-application-setup"></a>Configurazione specifica del paese dell'impostazione dell'applicazione

A seconda del paese o dell'area geografica, l'impostazione dell'applicazione potrebbe richiedere una configurazione specifica. 

Per i passaggi specifici, vedi la documentazione "Introduzione" disponibile per il tuo paese o area geografica.

## <a name="deploy-the-electronic-invoicing-feature-to-service-environment"></a>Distribuire la funzionalità di fatturazione elettronica nell'ambiente del servizio

1. Nella scheda **Versioni** seleziona la versione della funzione di fatturazione elettronica che vuoi distribuire.
2. Selezionare **Cambia stato** \> **Completato**.
3. Seleziona **Cambia stato** \> **Pubblica**.
4. Seleziona **Distribuisci**.
5. Imposta l'opzione **Distribuisci in applicazione connessa** su **No**.
6. Imposta l'opzione **Distribuisci in ambiente del servizio** su **Sì**.
7. Nel campo **Ambiente del servizio** seleziona l'ambiente della Fatturazione elettronica in cui vuoi distribuire la funzione Fatturazione elettronica.
8. Nel campo **Dal** seleziona la data in cui la funzione Fatturazione elettronica deve diventare effettiva nella Fatturazione elettronica.
9. Selezionare **OK**.

## <a name="deploy-the-electronic-invoicing-feature-to-connected-application"></a>Distribuire la funzionalità di fatturazione elettronica nell'applicazione connessa

1. Nella scheda **Versioni** seleziona una versione della funzione di fatturazione elettronica che vuoi distribuire.
2. Seleziona **Distribuisci**.
3. Imposta l'opzione **Distribuisci in applicazione connessa** su **Sì**.
4. Nel campo **Connetti applicazione** seleziona la connessione associata all'istanza di Finance o Supply Chain Management.
5. Imposta l'opzione **Distribuisci in ambiente del servizio** su **No**.
6. Selezionare **OK**.

## <a name="turn-on-the-electronic-invoicing-feature-in-finance-or-supply-chain-management"></a>Attivare la funzione per la fatturazione elettronica in Finance o Supply Chain Management

1. Accedi a Finance o Supply Chain Management e verifica di essere nella persona giuridica corretta.
2. Vai a **Amministrazione organizzazione** \> **Impostazione** \> **Parametri documento elettronico**.
3. Nella scheda **Funzionalità** selezionare la funzionalità specifica del paese/dell'area geografica per attivare la funzionalità Fatturazione elettronica per Finance o Supply Chain Management. La tabella seguente fornisce un elenco di funzionalità di fatturazione elettronica disponibili per paesi/aree geografiche specifici. 

    | Nome funzionalità                                          | Paese/area geografica  |
    |-------------------------------------------------------|-----------------|
    | Fatture elettroniche austriache (AT)                     | Austria         |
    | Fattura elettronica belga (BE)                       | Belgio         |
    | CFDI - Fattura elettronica messicana (MX)                  | Messico          |
    | Fattura elettronica danese (DK)                        | Danimarca         |
    | Fattura elettronica olandese (NL)                         | Paesi Bassi |
    | Fattura elettronica egiziana (EG)                      | Egitto           |
    | Fattura elettronica estone (EE)                      | Estonia         |
    | Fattura elettronica finlandese (FI)                       | Finlandia         |
    | Fattura elettronica francese (FR)                        | Francia          |
    | Fattura elettronica tedesca (DE)                        | Germania         |
    | Fattura elettronica italiana (IT)                       | Italia           |
    | NF-e federale - Fattura elettronica brasiliana (BR)      | Brasile          |
    | NFS-e - Fattura elettronica del servizio brasiliano (città)   | Brasile          |
    | Fattura elettronica norvegese (NO)                     | Norvegia          |
    | Fattura elettroniche PEPPOL                             | Globali          |
    | Fattura elettronica spagnola (ES)                       | Spagna           |

4. Selezionare **Salva**.

## <a name="issue-electronic-invoices"></a>Emissione di fatture elettroniche

1. Vai a **Amministrazione organizzazione** \> **Periodico** \> **Documenti elettronici** \> **Invia documenti elettronici**.
2. Nella scheda dettaglio **Record da includere**, selezionare **Filtro**.
3. Seleziona **Aggiungi** per aggiungere un nome di tabella al filtro di query.
4. Seleziona la tabella che contiene le fatture.

    > [!NOTE]
    > Il nome della tabella deve essere elencato nella tabella nella sezione [Configurare l'impostazione dell'applicazione](#configure-the-application-setup) precedente in questo argomento.

5. Seleziona il nome del campo nella tabella in cui vuoi eseguire la query.
6. Immetti il nome della tabella e il nome del campo per i criteri di esecuzione della query.
7. Ripeti i passaggi 5 e 6 per aggiungere più campi e criteri alla query, quindi seleziona **OK**.
8. Selezionare **OK**.

## <a name="view-submission-logs"></a>Visualizzare i registri di invio

1. Vai a **Amministrazione organizzazione** \> **Periodico** \> **Documenti elettronici** \> **Registro di invio documenti elettronici**.
2. Nel campo **Tipo di documento** seleziona la tabella che contiene le fatture.

    > [!NOTE]
    > Il nome della tabella deve essere elencato nella tabella nella sezione [Configurare l'impostazione dell'applicazione](#configure-the-application-setup) precedente in questo argomento.

3. Seleziona una fattura nella griglia, quindi seleziona **Richiedi informazioni** \> **Dettagli invio**.


## <a name="related-topics"></a>Argomenti correlati

- [Panoramica della fatturazione elettronica](e-invoicing-service-overview.md)
- [Introduzione all'amministrazione dei servizi per la fatturazione elettronica](e-invoicing-get-started-service-administration.md)
- [Introduzione alla fatturazione elettronica per il Brasile](e-invoicing-bra-get-started.md)
- [Introduzione alla fatturazione elettronica per il Messico](e-invoicing-mex-get-started.md)
- [Introduzione alla fatturazione elettronica per l'Italia](e-invoicing-ita-get-started.md)
- [Fatture elettroniche dei clienti in Egitto](emea-egy-e-invoices.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
