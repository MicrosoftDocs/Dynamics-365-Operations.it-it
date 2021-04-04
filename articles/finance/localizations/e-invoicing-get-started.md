---
title: Introduzione al componente aggiuntivo per la fatturazione elettronica
description: Questo argomento fornisce informazioni introduttive sul componente aggiuntivo per la fatturazione elettronica in Microsoft Dynamics 365 Finance e Dynamics 365 Supply Chain Management.
author: gionoder
manager: AnnBe
ms.date: 02/22/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 56227e031f8205836bcae9ce26006fc8091c2863
ms.sourcegitcommit: 543772ee97efe215cf6f2ec6e092cc1568919f20
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/13/2021
ms.locfileid: "5592552"
---
# <a name="get-started-with-the-electronic-invoicing-add-on"></a>Introduzione al componente aggiuntivo per la fatturazione elettronica

[!include [banner](../includes/banner.md)]

Questo argomento fornisce informazioni introduttive sul componente aggiuntivo per la fatturazione elettronica.

La tabella seguente elenca le funzionalità della fatturazione elettronica e i documenti aziendali a cui possono essere applicate.

| Nome funzionalità                         | Documento aziendale |
|--------------------------------------|-------------------|
| Fatture elettroniche austriache (AT)    | <p>Fattura di vendita</p><p>Fattura progetto</p> |
| Fattura elettronica belga (BE)      | <p>Fattura di vendita</p><p>Fattura progetto</p> |
| NF-e brasiliano (BR)                  | <p>Modello di documento fiscale 55</p><p>Lettera di correzione</p> |
| Brasiliano NFS-e ABRASF Curitiba (BR) | Documento fiscale di servizio |
| Fattura elettronica danese (DK)       | <p>Fattura di vendita</p><p>Fattura progetto</p> |
| Fattura elettronica egiziana (EG)     | <p>Fattura di vendita</p><p>Fattura progetto</p> |
| Fattura elettronica estone (EE)     | <p>Fattura di vendita</p><p>Fattura progetto</p> |
| Fattura elettronica finlandese (FI)       | <p>Fattura di vendita</p><p>Fattura progetto</p> |
| Fattura elettronica francese (FR)       | <p>Fattura di vendita</p><p>Fattura progetto</p> |
| Fattura elettronica tedesca (DE)       | <p>Fattura di vendita</p><p>Fattura progetto</p> |
| FatturaPA (IT)                       | <p>Fattura di vendita</p><p>Fattura progetto</p> |
| Messicano CFDI Interfactura (MX)       | <p>Fattura di vendita</p><p>Documento di trasporto</p><p>Trasferimento scorte</p><p>Complemento di pagamento</p> |
| Fattura elettronica olandese (NL)        | <p>Fattura di vendita</p><p>Fattura progetto</p> |
| Fattura elettronica norvegese (NO)    | <p>Fattura di vendita</p><p>Fattura progetto</p> |
| Fattura elettronica spagnola (ES)      | <p>Fattura di vendita</p><p>Fattura progetto</p> |
| Fattura elettroniche PEPPOL            | <p>Fattura di vendita</p><p>Fattura progetto</p> |

## <a name="prerequisites"></a>Prerequisiti

Prima di poter completare le procedure in questo argomento, è necessario soddisfare i seguenti prerequisiti:

- Configura il tuo Regulatory Configuration Service (RCS) e il tuo Microsoft Dynamics 365 Finance o Dynamics 365 Supply Chain Management in modo da poter inviare al componente aggiuntivo Fatturazione elettronica.
- Crea un ambiente del servizio e pubblicalo nel componente aggiuntivo Fatturazione elettronica. Per ulteriori informazioni, vedi [Introduzione all'amministrazione del servizio del componente aggiuntivo per la fatturazione elettronica](e-invoicing-get-started-service-administration.md).
- Crea un'applicazione connessa. Per ulteriori informazioni, vedi [Introduzione all'amministrazione del servizio del componente aggiuntivo per la fatturazione elettronica](e-invoicing-get-started-service-administration.md).
- Crea un provider di configurazioni per la tua organizzazione. Per ulteriori informazioni, vedi [Creare provider di configurazioni e contrassegnarli come attivi](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="import-an-electronic-invoicing-feature-from-the-microsoft-configuration-provider"></a>Importa una funzionalità di fatturazione elettronica dal provider di configurazioni Microsoft 

1. Accedi al tuo account Regulatory Configuration Service (RCS).
2. Nell'area di lavoro **Funzionalità di globalizzazione**, nella sezione **Funzionalità**, seleziona il riquadro **Componente aggiuntivo per la fatturazione elettronica**.
3. Selezionare **Importa** e quindi selezionare **Sincronizza**.
4. Filtra la colonna **Provider di configurazioni** per il termine **Microsoft**.
5. Seleziona il nome di una funzione di fatturazione elettronica dalla tabella all'inizio di questo argomento, quindi seleziona **Importa**.

## <a name="create-an-electronic-invoicing-feature-under-your-organization-provider"></a>Crea una funzionalità di fatturazione elettronica nel provider dell'organizzazione

1. In RCS, nella sezione **Funzionalità** dell'area di lavoro **Funzionalità di globalizzazione**, selezionare il riquadro **Componente aggiuntivo per la fatturazione elettronica**.
2. Seleziona **Aggiungi** > **Basato su funzionalità esistente** e nel campo **Nome** immetti il nome della funzione di fatturazione elettronica.
3. Nel campo **Descrizione** immettere una descrizione della funzione.
4. Nel **campo funzione di base**, seleziona la funzionalità di fatturazione elettronica importata dal provider di configurazioni Microsoft.
5. Selezionare **Crea funzionalità**.

## <a name="configure-the-electronic-invoicing-feature"></a>Configurare la funzionalità di fatturazione elettronica

A seconda del paese o dell'area geografica, la funzione Fatturazione elettronica potrebbe richiedere una configurazione aggiuntiva. 

Per i passaggi specifici, vedi la documentazione "Introduzione" disponibile per il tuo paese o area geografica.

## <a name="configure-the-application-setup"></a>Configurare l'impostazione dell'applicazione

1. Seleziona la funzione Fatturazione elettronica che hai creato.
2. Nella scheda **Versione** verifica che la versione **Bozza** sia selezionata.
3. Nella scheda **Impostazioni**, selezionare **Impostazione applicazioni**.

    > [!NOTE]
    > Verifica che la tua organizzazione sia impostata come provider di configurazioni **attivo**. Per ulteriori informazioni, vedi [Creare provider di configurazioni e contrassegnarli come attivi](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).

4. Seleziona **Impostazione funzionalità** e quindi seleziona **Applicazione connessa**.
5. Nella sezione **Tipi di documento elettronico**, seleziona **Aggiungi**.
6. Per ogni documento aziendale supportato dalla funzione, seleziona e immetti un valore **Nome tabella** secondo la tabella seguente.

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

7. Per ogni documento aziendale supportato dalla funzione, seleziona e immetti un valore **Contesto** secondo la tabella seguente.

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

8. Per ogni documento aziendale supportato dalla funzione, seleziona e immetti un valore **Mapping di documento aziendale** secondo la tabella seguente.

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

A seconda del paese o dell'area geografica, la funzione Fatturazione elettronica potrebbe richiedere una configurazione aggiuntiva.

Per passaggi specifici, vedi la documentazione "Introduzione" disponibile per il tuo paese o area geografica.

## <a name="deploy-the-electronic-invoicing-feature"></a>Distribuire la funzionalità di fatturazione elettronica

1. Nella scheda **Versioni** seleziona la versione della funzione di fatturazione elettronica che vuoi distribuire.
2. Selezionare **Cambia stato** \> **Completato**.
3. Seleziona **Cambia stato** \> **Pubblica**.
4. Seleziona **Distribuisci**.
5. Imposta l'opzione **Distribuisci in applicazione connessa** su **Sì**.
6. Nella pagina **Connetti applicazione** seleziona la connessione associata all'istanza di Finance o Supply Chain Management.
7. Imposta l'opzione **Distribuisci in ambiente del servizio** su **Sì**.
8. Nel campo **Ambiente del servizio** seleziona l'ambiente del servizio componente aggiuntivo Fatturazione elettronica in cui vuoi distribuire la funzione Fatturazione elettronica.
9. Nel campo **Dal** seleziona la data in cui la funzione Fatturazione elettronica deve diventare effettiva nel componente aggiuntivo Fatturazione elettronica.
10. Selezionare **OK**.

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
2. Nella scheda dettaglio **Record da includere**, seleziona **Filtro**.
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

- [Panoramica del componente aggiuntivo per la fatturazione elettronica](e-invoicing-service-overview.md)
- [Introduzione all'amministrazione dei servizi del componente aggiuntivo per la fatturazione elettronica](e-invoicing-get-started-service-administration.md)
- [Introduzione al componente aggiuntivo per la fatturazione elettronica per il Brasile](e-invoicing-bra-get-started.md)
- [Introduzione al componente aggiuntivo per la fatturazione elettronica per il Messico](e-invoicing-mex-get-started.md)
- [Introduzione al componente aggiuntivo per la fatturazione elettronica per l'Italia](e-invoicing-ita-get-started.md)
- [Fatture elettroniche dei clienti in Egitto](emea-egy-e-invoices.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
