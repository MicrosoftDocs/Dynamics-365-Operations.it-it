---
title: Panoramica dell'integrazione fiscale per i canali Commerce
description: In questo articolo viene fornita una panoramica delle funzionalità di integrazione fiscale disponibili in Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 03/04/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 0a56df2a463153c6c3986ce84907e25ea7d965b8
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9286501"
---
# <a name="fiscal-integration-overview-for-commerce-channels"></a>Panoramica dell'integrazione fiscale per i canali Commerce

[!include [banner](../includes/banner.md)]

In questo articolo viene fornita una panoramica delle funzionalità di integrazione fiscale disponibili in Dynamics 365 Commerce. 

L'integrazione fiscale include l'integrazione con vari servizi e dispositivi fiscali che consentono la registrazione fiscale delle vendite in conformità con le leggi fiscali locali intese a impedire la frode fiscale nel settore della vendita al dettaglio. Di seguito sono riportati alcuni scenari comuni che possono essere coperti utilizzando l'integrazione fiscale:

- Registrare una vendita in un dispositivo fiscale collegato al POS, ad esempio una stampante fiscale, e stampare una ricevuta fiscale per il cliente.
- Inviare in modo sicuro informazioni relative a vendite e resi completati in Retail POS a un servizio Web esterno gestito dall'ufficio tributario competente.
- Assicura l'inalterabilità dei dati delle transazioni di vendita mediante firme digitali.

La funzionalità di integrazione fiscale è un framework che fornisce una soluzione comune per un ulteriore sviluppo e personalizzazione dell'integrazione tra Retail POS e i servizi e i dispositivi fiscali. La funzionalità include inoltre campioni di integrazione fiscale che supportano scenari di base per specifici paesi o aree geografiche e utilizzabili con specifici servizi o dispositivi fiscali. Un esempio di integrazione fiscale è costituito da più estensioni di componenti di Commerce ed è incluso nel kit SDK. Per maggiori informazioni sugli esempi di integrazione fiscale, vedi [Esempi di integrazione fiscale nel Commerce SDK](#fiscal-integration-samples-in-the-commerce-sdk). Per informazioni su come installare e usare il Commerce SDK, vedi [Architettura del kit di sviluppo software (SDK) per la vendita al dettaglio](../dev-itpro/retail-sdk/retail-sdk-overview.md).

Per supportare altri scenari non supportati da un esempio di integrazione fiscale, integrare Retail Retail POS con altri servizi o dispositivi fiscali o soddisfare i requisiti di altri paesi o aree geografiche, è necessario estendere un esempio di integrazione fiscale esistente o creare un nuovo esempio utilizzando un esempio esistente.

## <a name="fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services"></a>Processo di registrazione fiscale ed esempi di integrazione fiscale per dispositivi fiscali e servizi

Un processo di registrazione fiscale in Retail POS può essere costituito da una o più fasi. Ogni fase comporta la registrazione fiscale di specifici eventi o transazioni in un servizio o dispositivo fiscale. I componenti seguenti contribuiscono alla registrazione fiscale in un dispositivo fiscale collegato a una stazione hardware o servizio:

- **Provider documenti fiscali:**- Questo componente serializza i dati di evento/transazione nel formato utilizzato anche per l'interazione con il dispositivo fiscale o servizio, analizza le risposte del dispositivo fiscale o servizio e le archivia nel database del canale. L'estensione inoltre definisce le transazioni e gli eventi specifici che è necessario registrare.
- **Connettore fiscale** - Questo componente inizializza la comunicazione con il dispositivo fiscale o servizio, invia le richieste e i comandi al dispositivo fiscale o servizio in base ai dati di evento/transazione estratti dal documento fiscale e riceve le risposte dal dispositivo fiscale o servizio

Un esempio di integrazione fiscale potrebbe contenere le estensioni Commerce Runtime (CRT), stazione hardware e POS per un fornitore di documenti fiscali e un connettore fiscale. Include inoltre le configurazioni di componente seguenti:

- **Configurazione fornitore di documenti fiscali** - Questa configurazione definisce un metodo di output e un formato per i documenti fiscali. Include inoltre un mapping dei dati per le imposte e i metodi di pagamento, per rendere i dati di Retail POS compatibili con i valori predefiniti nel firmware del dispositivo fiscale o servizio.
- **Configurazione di connettore fiscale** - Questa configurazione definisce la comunicazione fisica con il dispositivo fiscale o servizio.

Un processo di registrazione fiscale per un registro POS specifico viene definito tramite un'impostazione corrispondente nel profilo funzionalità POS. Per ulteriori informazioni su come configurare un processo di registrazione fiscale, caricare le configurazioni di fornitore di documenti fiscali e di connettore fiscale e modificarne i parametri di configurazione, vedere [Configurazione di un processo di registrazione fiscale](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process).

> [!NOTE]
> Se hai bisogno di dispositivi per operazioni non fiscali, come la ricerca nel catalogo prodotti, la ricerca di clienti o la creazione di bozze di transazione, puoi selezionarli come registri con restrizioni di processo fiscale. Per ulteriori informazioni, vedi [Configurare registri con vincoli di registrazione fiscale](setting-up-fiscal-integration-for-retail-channel.md#set-up-registers-with-fiscal-registration-restrictions).

Il seguente flusso di registrazione fiscale tipico inizia con un evento nel POS (ad esempio, la conclusione di una transazione di vendita) e implementa una sequenza predefinita di passaggi che coinvolge altre componenti di Commerce (come CRT e la stazione hardware).

1. Il POS richiede un documento fiscale dal framework di integrazione fiscale (FIF).
1. FIF determina se l'evento corrente richiede la registrazione fiscale.
1. In base alle impostazioni del processo di registrazione fiscale, FIF identifica un connettore fiscale e un fornitore di documenti fiscali corrispondente da utilizzare per la registrazione fiscale.
1. FIF esegue il fornitore di documenti fiscali che genera un documento fiscale (ad esempio, un documento XML) che rappresenta l'evento o la transazione di vendita al dettaglio.
1. FIF restituisce al POS il documento fiscale generato.
1. Il POS richiede che FIF presenti il documento fiscale al dispositivo o servizio fiscale.
1. FIF esegue il connettore fiscale che elabora il documento fiscale e lo invia al servizio o al dispositivo fiscale.
1. FIF restituisce la risposta fiscale (ovvero la risposta del dispositivo o servizio fiscale) al POS.
1. Il POS analizza la risposta fiscale per determinare se la registrazione fiscale è stata eseguita correttamente. Come richiesto, il POS richiede che FIF gestisca gli eventuali errori che si sono verificati. 
1. Il POS richiede che FIF elabori e salvi la risposta fiscale.
1. Il provider del documento fiscale elabora la risposta fiscale. Nell'ambito di tale elaborazione, il provider del documento fiscale analizza la risposta e ne estrae i dati estesi.
1. FIF salva la risposta e i dati estesi nel database del canale.
1. Se necessario, il POS stampa una ricevuta tramite una normale stampante per ricevute collegata alla stazione hardware. La ricevuta può contenere i dati richiesti dalla risposta fiscale.
 
Nell'esempio seguente viene illustrato un flusso di esecuzione di registrazione fiscale tipico per un dispositivo fiscale o servizio.
 
### <a name="fiscal-registration-is-done-via-a-device-connected-to-the-hardware-station"></a>La registrazione fiscale avviene tramite un dispositivo collegato alla stazione Hardware

Questa configurazione viene utilizzata quando un dispositivo fiscale fisico, come una stampante fiscale, è collegato alla stazione hardware. È applicabile anche quando la comunicazione con un dispositivo o servizio fiscale avviene tramite un software installato sulla stazione Hardware. In questo caso, il provider del documento fiscale si trova sul CRT e il connettore fiscale si trova sulla stazione hardware.

![La registrazione fiscale avviene tramite un dispositivo collegato alla stazione Hardware.](media/FIF-CRT-HWS.png)

### <a name="fiscal-registration-is-done-via-an-external-service"></a>La registrazione fiscale avviene tramite un servizio esterno

Questa configurazione viene utilizzata quando la registrazione fiscale viene effettuata tramite un servizio esterno, ad esempio un servizio Web gestito dall'autorità fiscale. In questo caso, sia il provider del documento fiscale che il connettore fiscale si trovano sul CRT.

![La registrazione fiscale avviene tramite un servizio esterno.](media/FIF-CRT-CRT.png)
 
### <a name="fiscal-registration-is-done-internally-in-the-crt"></a>La registrazione fiscale viene effettuata internamente al CRT

Questa configurazione viene utilizzata quando non è richiesto alcun dispositivo o servizio fiscale esterno per la registrazione fiscale. Ad esempio, viene utilizzato quando la registrazione fiscale viene eseguita tramite la firma digitale delle transazioni di vendita. In questo caso, sia il provider del documento fiscale che il connettore fiscale si trovano sul CRT.

![La registrazione fiscale viene effettuata internamente al CRT.](media/FIF-CRT-CRT-SGN.png)

### <a name="fiscal-registration-is-done-via-a-device-or-service-in-the-local-network"></a>La registrazione fiscale avviene tramite un dispositivo o servizio nella rete locale

Questa configurazione viene utilizzata quando un dispositivo fiscale fisico o un servizio fiscale è presente nella rete locale del punto vendita e fornisce un'API (Application Programming Interface) HTTPS. In questo caso, il provider del documento fiscale si trova sul CRT e il connettore fiscale si trova sul POS.

![La registrazione fiscale avviene tramite un dispositivo o servizio nella rete locale.](media/FIF-CRT-POS.png)

## <a name="error-handling"></a>Gestione errori

Il framework di integrazione fiscale fornisce le seguenti opzioni per gestire gli errori durante la registrazione fiscale:

- **Riprova** - Gli operatori possono utilizzare questa opzione quando l'errore può essere risolto rapidamente e la registrazione fiscale può essere eseguita di nuovo. Ad esempio, questa opzione può essere utilizzata quando il dispositivo fiscale non è collegato, la carta è esaurita o inceppata nella stampante fiscale.
- **Annulla** - Questa opzione consente agli operatori di posticipare la registrazione fiscale della transazione o dell'evento corrente se questo ha esito negativo. Dopo che la registrazione è stata posticipata, l'operatore può continuare a utilizzare il POS e completare le operazioni per le quali la registrazione fiscale non è necessaria. Quando si verifica un evento che richiede la registrazione fiscale nel POS (ad esempio, viene aperta una nuova transazione), la finestra di dialogo di gestione degli errori viene automaticamente visualizzata per informare l'operatore che la transazione precedente non è stata registrata correttamente e per fornire le opzioni di gestione degli errori.
- **Ignora** - Gli operatori possono utilizzare questa opzione quando la registrazione fiscale può essere omessa in determinate condizioni e le operazioni normali possono essere eseguite nel POS. Ad esempio, questa opzione può essere utilizzata se una transazione di vendita per la quale la registrazione fiscale non è riuscita può essere registrata in un giornale speciale.
- **Contrassegna come registrato** - Gli operatori possono utilizzare questa opzione quando la transazione è stata effettivamente registrata nel dispositivo fiscale (ad esempio, è stata stampata una ricevuta fiscale), ma si è verificato un errore durante il salvataggio della risposta fiscale nel database del canale.
- **Posticipa** – Gli operatori possono utilizzare questa opzione quando la transazione non è stata registrata perché il servizio di registrazione non era disponibile. 

> [!NOTE]
> Le opzioni **Ignora**, **Contrassegna come registrato** e **Posticipa** devono essere attivate nel processo di registrazione fiscale prima di essere utilizzate. Inoltre, le autorizzazioni corrispondenti devono essere concesse agli operatori.

Le opzioni **Ignora**, **Contrassegna come registrato** e **Posticipa** attivano codici informativi per acquisire alcune informazioni specifiche sull'errore, ad esempio la causa dell'errore o il motivo per aver ignorato la registrazione fiscale o contrassegnato la transazione come registrata. Per ulteriori informazioni su come impostare i parametri di gestione degli errori, vedere [Configurare le impostazioni di gestione degli errori](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).

### <a name="optional-fiscal-registration"></a>Registrazione fiscale facoltativa

La registrazione fiscale può essere obbligatoria per alcune operazioni ma facoltativa per altre. Ad esempio, la registrazione fiscale di vendite e resi normali potrebbe essere obbligatoria, ma la registrazione fiscale delle operazioni correlate ai depositi cliente potrebbe essere facoltativa. In questo caso, il mancato completamento della registrazione fiscale di una vendita deve bloccare ulteriori vendite, ma il mancato completamento della registrazione fiscale di deposito cliente non deve bloccare ulteriori vendite. Per distinguere le operazioni obbligatorie e facoltative, si consiglia di gestirle tramite differenti fornitori di documenti e di configurare passaggi distinti nel processo di registrazione fiscale per quei fornitori. Il parametro **Continua in caso di errore** deve essere abilitato per qualsiasi passaggio correlato alla registrazione fiscale facoltativa. Per ulteriori informazioni su come impostare i parametri di gestione degli errori, vedere [Configurare le impostazioni di gestione degli errori](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).

### <a name="manually-rerun-fiscal-registration"></a>Esecuzione manuale della registrazione fiscale

Se la registrazione fiscale di una transazione o di un evento è stata posticipata dopo un errore (ad esempio se l'operatore ha selezionato **Annulla** nella finestra di dialogo di gestione degli errori), è possibile rieseguire manualmente la registrazione fiscale invocando un'operazione corrispondente. Per ulteriori dettagli, vedere [Abilitare l'esecuzione manuale della registrazione fiscale posticipata](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration).

### <a name="postpone-option"></a>Opzione Posticipa

L'opzione **Posticipa** consente di continuare il processo di registrazione fiscale se il passaggio corrente non riesce. Può essere utilizzato quando è disponibile un'opzione di backup della registrazione fiscale.

### <a name="fiscal-registration-health-check"></a>Verifica integrità della registrazione fiscale

La procedura di verifica integrità per le registrazioni fiscali verifica la disponibilità del dispositivo o del servizio fiscale quando si verificano specifici eventi. Se la registrazione fiscale non può essere completata sul momento, l'operatore viene avvisato in anticipo.

Il POS esegue la verifica integrità quando si verificano i seguenti eventi:

- Viene aperta una nuova transazione.
- Viene richiamata una transazione sospesa.
- Viene finalizzata una transazione di vendita o reso.

Se la verifica integrità non riesce, il POS visualizza la finestra di dialogo della verifica integrità. Questa finestra di dialogo fornisce i pulsanti seguenti:

- **OK** - Questo pulsante consente all'operatore di ignorare l'errore della verifica integrità e di continuare a elaborare l'operazione. Gli operatori possono selezionare questo pulsante solo se l'autorizzazione **Consenti di ignorare l'errore di verifica integrità** è attivata.
- **Annulla** - Se l'operatore seleziona questo pulsante, il POS annulla l'ultima azione (ad esempio un articolo non viene aggiunto a una nuova transazione).

> [!NOTE]
> La verifica integrità viene eseguita solo se l'operazione corrente richiede la registrazione fiscale e se il parametro **Continua in caso di errore** è disabilitata per il passaggio corrente del processo di registrazione fiscale. Per ulteriori informazioni, vedere [Configurare le impostazioni di gestione degli errori](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).

## <a name="storing-fiscal-response-in-fiscal-transaction"></a>Archiviazione della risposta fiscale nella transazione fiscale

Quando la registrazione fiscale di una transazione o di un evento ha esito positivo, una transazione fiscale viene creata nel database del canale e collegata alla transazione o all'evento originale. Analogamente, se l'opzione **Ignora** o **Contrassegna come registrato** è selezionata per una registrazione fiscale non riuscita, queste informazioni vengono archiviate in una transazione fiscale. Una transazione fiscale include la risposta fiscale del dispositivo o del servizio fiscale. Se il processo di registrazione fiscale comporta varie fasi, una transazione fiscale viene creata per ogni fase del processo che ha generato una registrazione riuscita o non riuscita.

Le transazioni fiscali vengono trasferite a Headquarters dal *processo P*, insieme alle transazioni. Nella scheda Dettaglio **Transazioni fiscali** della pagina **Transazioni punto vendita**, è possibile visualizzare le transazioni fiscali collegate alle transazioni di vendita al dettaglio.

Una transazione fiscale archivia i seguenti dettagli:

- Dettagli del processo di registrazione fiscale (processo, gruppo di connettori, connettore e così via). Archivia inoltre il numero di serie del dispositivo fiscale nel campo **Numero registratore di cassa**, se queste informazioni sono incluse nella risposta fiscale.
- Lo stato della registrazione fiscale: **Completata** per una registrazione fiscale riuscita, **Ignorata** se l'operatore ha selezionato l'opzione **Ignora** per una registrazione non riuscita o **Contrassegnata come registrata** se l'operatore ha selezionato l'opzione **Contrassegna come registrata** o **Posticipata** se l'operatore ha selezionato l'opzione **Posticipa**.
- Transazioni codice informativo correlate a una transazione fiscale selezionata. Per visualizzare le transazioni codice informativo, nella scheda Dettaglio **Transazioni fiscali**, selezionare una transazione fiscale con stato **Ignorata**, **Contrassegnata come registrata** o **Posticipata** e quindi selezionare **Transazioni codice informativo**.

Selezionando i **dati estesi**, si possono anche visualizzare alcune proprietà della transazione fiscale. La lista delle proprietà che possono essere visualizzate è specifica della funzionalità di registrazione fiscale che ha generato la transazione fiscale. Per esempio, puoi visualizzare la firma digitale, il numero sequenziale, l'impronta del certificato, l'identificazione dell'algoritmo di hash e altre proprietà della transazione fiscale per la funzionalità di firma digitale per la Francia.

## <a name="fiscal-texts-for-discounts"></a>Testi fiscali per sconti

Alcuni paesi o aree geografiche hanno requisiti speciali su testi aggiuntivi che devono essere stampati sulle ricevute fiscali quando diversi tipi di sconti vengono applicati. La funzionalità di integrazione fiscale consente di impostare un testo speciale per uno sconto che viene stampato dopo una riga di sconto su una ricevuta fiscale. Per gli sconti manuali, è possibile configurare un testo fiscale per il codice informativo specificato come codice informativo **Sconto prodotti** nel profilo funzionalità POS. Per ulteriori informazioni su come impostare testi fiscali per gli sconti, vedere [Impostare testi fiscali per sconti](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-texts-for-discounts).

## <a name="printing-fiscal-x-and-fiscal-z-reports"></a>Stampa di report X e Z fiscali

La funzionalità di integrazione fiscale supporta la generazione di rendiconti giornalieri specifici al dispositivo o al servizio fiscale integrato:

- I nuovi pulsanti che eseguono le operazioni corrispondenti devono essere aggiunti al layout dello schermo POS. Per ulteriori informazioni, vedere [Configurare report X/Z fiscali dal POS](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-xz-reports-from-the-pos).
- Nell'esempio di integrazione fiscale, queste operazioni devono corrispondere alle relative operazioni del dispositivo fiscale.

## <a name="fiscal-integration-samples-in-the-commerce-sdk"></a>Esempi di integrazione fiscale nel Commerce SDK

I seguenti esempi di integrazione fiscale sono attualmente disponibili nel Commerce SDK:

- [Esempio di integrazione di stampante fiscale per l'Italia](./emea-ita-fpi-sample.md)
- [Esempio di integrazione di stampante fiscale per la Polonia](./emea-pol-fpi-sample.md)
- [Esempio di integrazione del servizio di registrazione fiscale per l'Austria](./emea-aut-fi-sample.md)
- [Esempio di integrazione del servizio di registrazione fiscale per la Repubblica Ceca](./emea-cze-fi-sample.md)
- [Esempio di integrazione di un'unità di controllo per la Svezia](./emea-swe-fi-sample.md)
- [Esempio di integrazione del servizio di registrazione fiscale per la Germania](./emea-deu-fi-sample.md)
- [Esempio di integrazione di stampante fiscale per la Russia](./rus-fpi-sample.md)

La seguente funzionalità di integrazione fiscale è anche implementata utilizzando il framework di integrazione fiscale, ma è disponibile fuori dalla scatola e non è inclusa nel Commerce SDK:

- [Registrazione fiscale per il Brasile](./latam-bra-commerce-localization.md#fiscal-registration-for-brazil)
- [Firma digitale per la Francia](./emea-fra-cash-registers.md)

La seguente funzionalità di integrazione fiscale è disponibile anche nell'SDK Commerce, ma attualmente non sfrutta il framework di integrazione fiscale. La migrazione di questa funzionalità al framework di integrazione fiscale è prevista negli aggiornamenti successivi.

- [Firma digitale per la Norvegia](./emea-nor-cash-registers.md)

La seguente funzionalità di integrazione fiscale legacy che è disponibile nel Commerce SDK non usa il framework di integrazione fiscale e sarà deprecata negli aggiornamenti successivi:

- [Esempio di integrazione di un'unità di controllo per la Svezia (legacy)](./retail-sdk-control-unit-sample.md)
- [Firma digitale per la Francia (legacy)](./emea-fra-deployment.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
