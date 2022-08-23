---
title: Panoramica di gestione dei benefit
description: Questo articolo fornisce una panoramica della funzione di gestione dei benefici in Dynamics 365 Human Resources.
author: twheeloc
ms.date: 12/06/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 261d71e955e4cb1a4a461d59725c631248e10b17
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2022
ms.locfileid: "9227899"
---
# <a name="benefits-management-overview"></a>Panoramica di gestione dei benefit


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Per rimanere competitivi, è necessario offrire una ricca gamma di benefit per attirare e trattenere i migliori dipendenti. Oltre ai benefit standard come la copertura medica e dentale, è possibile che si voglia offrire anche servizi estesi come assistenza all'adozione, programmi ricreativi e indennità per l'abbigliamento. La gestione dei benefici in Microsoft Dynamics 365 Human Resources fornisce una soluzione flessibile che supporta un'ampia varietà di opzioni di benefici. Human Resources include anche un'esperienza per i dipendenti di facile utilizzo che evidenzia le offerte proposte.

- I piani di benefit avanzati consentono di creare e gestire piani di benefit unici e supportare tabelle di tassi di benefit complesse e livelli nidificati. È possibile creare facilmente programmi di benefit, pacchetti e regole di iscrizione automatica per un'esperienza per i dipendenti più semplice.
- I programmi di crediti flessibili consentono una ripartizione per supportare il pensionamento e altri eventi della vita.
- Le regole di idoneità estese consentono di rendere disponibili i benefit appropriati per i dipendenti appropriati.
- L'iscrizione online ai benefit fornisce un'esperienza semplice per i dipendenti.
- L'elaborazione di eventi reali qualificati supporta eventi reali futuri.

Se si desidera accedere ai dati dimostrativi, sarà necessario ridistribuire l'ambiente sandbox.

> [!NOTE]
> Ora puoi personalizzare le pagine di gestione dei benefici. I campi personalizzati relativi ai tassi di copertura possono essere aggiunti alla pagina delle **opzioni di copertura** per i piani di benefici. Per ulteriori informazioni sull'uso dei campi personalizzati, vedere [Campi personalizzati](hr-developer-custom-fields.md).
>
> ![Campi personalizzati nei moduli Gestione benefit](media/hr-benefits-management-custom-fields.png)

## <a name="enable-benefits-management"></a>Abilitare Gestione benefit

In questo articolo viene descritto come attivare le funzionalità in Human Resources. Spiega anche quali funzioni esistenti in Human Resources sono sostituite da Benefits management e quali funzioni sono disabilitate dopo aver attivato Benefits management.

> [!IMPORTANT]
> Dopo aver abilitato Gestione benefit in un ambiente di **Produzione** non è possibile disabilitarlo. Si consiglia di abilitare e testare Gestione benefit in un ambiente **sandbox** prima di abilitarlo in un ambiente di **Produzione**. Sono presenti differenze significative tra la funzionalità dei benefit legacy e la nuova funzionalità di Gestione benefit che richiedono una configurazione aggiuntiva e devono essere testati prima di essere messi in produzione.

Per ulteriori informazioni, vedere [Gestire le funzionalità](hr-admin-manage-features.md).

## <a name="process-overview"></a>Panoramica processo

Il processo di configurazione dei benefit prevede le seguenti attività:

1.  Imposta le informazioni sui benefit obbligatorie.
2.  Imposta le informazioni sui benefit facoltative.
3.  Imposta i piani di benefit.
4.  Imposta i programmi di credito flessibile (facoltativo).
5.  Configura le informazioni sui dipendenti obbligatorie.
6.  Configura le informazioni sui dipendenti facoltative.
7.  Elabora i dipendenti per determinare l'idoneità.
8.  I dipendenti selezionano i piani tramite il self-service dipendenti (opzionale).
9.  Conferma le selezioni del piano dei dipendenti.
10. Elaborazione di eventi reali (facoltativo).
11. Aggiornamenti tariffari (facoltativo).

## <a name="set-up-required-benefit-information"></a>Impostare le informazioni sui benefit obbligatorie

Prima che i dipendenti possano essere iscritti ai piani, è necessario configurare più componenti:

- **Parametri di gestione dei benefit** – Queste impostazioni sono condivise tra le società. È possibile impostare codici motivo predefiniti, abilitare l'opzione **Benefit stipendio annuo**, impostare una frequenza di pagamento predefinita per i nuovi assunti e abilitare gli eventi reali. Per ulteriori informazioni, vedi [Impostare i parametri di gestione benefit](hr-benefits-setup-parameters.md).
- **Opzioni di idoneità per i contatti personali** – I contatti personali sono le persone a carico o beneficiarie dei piani impostati. In genere, sono figli, coniugi o organizzazioni di fiducia. Per ulteriori informazioni, vedere [Configurare le opzioni di idoneità del contatto personale](hr-benefits-setup-contact-eligibility-options.md).
- **Opzioni di copertura** – Imposta i tipi di copertura che saranno disponibili per un piano. In particolare, definisci chi deve essere coperto o quanta copertura è disponibile. Per ulteriori informazioni vedi [Creare le opzioni di copertura](hr-benefits-setup-coverage-options.md).
- **Tipi di piano** – Imposta i tipi di piani che saranno disponibili quando crei un piano di benefit. Esempi di tipi di piano includono **Dentale**, **Visione**, e **Risparmio**. Alcune impostazioni importanti sul tipo di piano determinano le impostazioni disponibili nel piano di benefit. Per ulteriori informazioni, vedere [Creazione tipi di piani](hr-benefits-setup-plan-types.md).
- **Regole di idoneità** – Le regole di idoneità vengono utilizzate per determinare se il dipendente è idoneo per un piano. Ad ogni piano di benefit deve essere associata almeno una regola di idoneità. Per ulteriori informazioni, vedi [Configurare le opzioni e le regole di idoneità](hr-benefits-setup-eligibility-rules.md).
- **Frequenze di pagamento** – Le frequenze di pagamento sono richieste quando vengono configurati i tassi di benefit. La frequenza di pagamento utilizzata su una tariffa aiuta a identificare l'importo che il dipendente e/o il datore di lavoro devono su base settimanale, mensile o annuale. Per ulteriori informazioni, vedi [Impostare frequenze di pagamento](hr-benefits-setup-payment-frequencies.md).
- **Tariffe** – Le tariffe definiscono quanto costerà un benefit al dipendente o al datore di lavoro. Se il denaro deve essere riassegnato a un dipendente (ad esempio, un credito per un abbonamento a una palestra), viene inserita una tariffa negativa. Per ulteriori informazioni, vedere [Configurare le tariffe](hr-benefits-setup-rates.md).
- **Tassi a livelli** – I tassi a livelli vengono utilizzati quando una tariffa deve cambiare in base ad alcuni criteri. Il livello più comune è il singolo livello basato sull'età. Tuttavia, è anche possibile impostare tassi a doppio livello, in cui la tariffa può cambiare in base al sesso, all'età o ad altri criteri.
- **Detrazioni** – Le detrazioni sono fondamentalmente le informazioni/codici di intestazione che verranno trasmessi al sistema retribuzioni per identificare la detrazione per il benefit. È necessario impostare queste detrazioni, perché saranno richieste sul piano di benefit. Per ulteriori informazioni, vedi [Configurare le detrazioni](hr-benefits-setup-deductions.md).
- **Periodi di benefit** – Un periodo di benefit è il periodo in cui i dipendenti avranno una copertura di benefit. È anche noto come anno del piano. Anche i periodi di iscrizione aperti sono stabiliti qui.

## <a name="set-up-optional-benefit-information"></a>Impostare le informazioni sui benefit facoltative

I seguenti componenti non devono essere impostati per creare un piano di benefit:

- **Programmi** – Un programma è un insieme di benefit disciplinati dalle stesse regole di idoneità. Ad esempio, chiunque nel reparto vendite può ottenere un telefono cellulare.
- **Aggregazioni** – Un'aggregazione è un gruppo di benefit, in cui è necessario selezionare un piano prima che sia disponibile l'opzione per selezionare piani aggiuntivi. Ad esempio, un piano medico altamente deducibile può essere abbinato a un piano di risparmio sanitario (HSA).
- **Tipi di eventi reali** – Gli eventi reali sono eventi che consentono di modificare la copertura di un dipendente. I tipi di eventi reali sono collegati a un tipo di piano. Ad esempio, un tipo di piano medico può consentire modifiche ai piani a causa di una nascita o un'adozione o a causa di un cambiamento nello stato civile. Tuttavia, un tipo di piano assicurativo potrebbe non consentire alcuna modifica a causa di eventi reali. Per ulteriori informazioni, vedi [Configurare i tipi di eventi reali](hr-benefits-setup-life-event-types.md).
- **Giorni di attesa e periodi di attesa** – È possibile impostare un periodo di attesa della copertura su un piano di benefit. Ad esempio, un dipendente appena assunto potrebbe essere in grado di iscriversi a un 401(k) solo dopo tre mesi di lavoro. In questo caso, il periodo di attesa è di tre mesi. I giorni di attesa vengono utilizzati nel periodo di attesa se le nuove iscrizioni possono essere elaborate e inviate al provider solo in un giorno specifico del mese. Ad esempio, se le iscrizioni 401(k) possono essere evase solo il quindici del mese, dopo tre mesi di assunzione, il periodo di attesa che si imposta è di tre mesi, e il giorno di attesa è il quindicesimo. Per ulteriori informazioni, vedi [Configurare i giorni di attesa](hr-benefits-setup-waiting-days.md) e [Configurare i periodi di attesa](hr-benefits-setup-waiting-periods.md).
- **Codici motivo** – I codici motivo vengono utilizzati per spiegare perché un benefit potrebbe cambiare per un dipendente. Per ulteriori informazioni, vedi [Impostare i codici motivo](hr-benefits-setup-reason-codes.md).

## <a name="set-up-benefit-plans"></a>Impostare i piani di benefit

Quando imposti un piano di benefit, devi completare i seguenti passaggi prima che i dipendenti possano essere iscritti:

- Assegna un periodo di benefit.
- Collega le opzioni di copertura.
- Imposta una data di inizio e di fine validità nella scheda **Generale**.
- Assegna almeno una regola di idoneità.
- Imposta il campo **Consenti/continua iscrizione** nella scheda **Impostazioni**.

Per ulteriori informazioni su come impostare i piani di benefit, vedi [Impostare i piani di benefit](hr-benefits-plans-setup.md).

## <a name="set-up-flex-credit-programs-optional"></a>Impostare i programmi di credito flessibile (facoltativo)

È possibile utilizzare programmi di crediti flessibili per iscrivere i dipendenti ai benefit secondo un numero prestabilito di crediti flessibili. I dipendenti possono scegliere il modo in cui allocare i propri crediti flessibili. Ad esempio, se i dipendenti sono già coperti dal piano di assicurazione sanitaria del coniuge, non devono utilizzare i loro crediti per la copertura sanitaria. Pertanto, potrebbero volerli utilizzare invece per altri benefit. Per ulteriori informazioni sui programmi di credito flessibile, vedi [Impostare programmi di credito flessibile](hr-benefits-plans-flex-credit-programs.md).

## <a name="configure-required-employee-information"></a>Configurare le informazioni sui dipendenti obbligatorie

Prima di poter iscrivere dipendenti nei benefit, è necessario fornire le informazioni richieste. 

Il dipendente deve avere una **Posizione** assegnata. Una **Posizione** può essere assegnata al dipendente nella pagina **Lavoratore** o **Posizione** aggiornando **Assegnazione lavoratore**. 

Quindi i dipendenti devono essere iscritti a un piano di retribuzione fissa alla data di inizio oppure disporre di un importo di **stipendio annuale per benefit**. Prima di assegnare **Retribuzione fissa** a un dipendente, una **Posizione** deve essere assegnata. 

> [!NOTE] 
> La **Data di inizio retribuzione fissa** non può essere precedente alla **Data assegnazione posizione**.

In alternativa, se un dipendente riceve un compenso supplementare come le commissioni, è possibile aggiungere un importo **Retribuzione annuale benefit** dal record dipendente. Le risorse umane useranno l'importo **Retribuzione annuale benefit** nel determinare gli importi di copertura, anziché l'**importo annuale di retribuzione fissa**. La **Retribuzione annuale benefit** deve essere valida a partire dalla data di inizio dell'impiegato o di quella del periodo di benefit, a seconda di quale è più recente. Tuttavia, non è richiesta una posizione per assegnare la **Retribuzione annuale benefit**. Per abilitare la funzionalità **Retribuzione annuale benefit** vai alla pagina **Parametri condivisi risorse umane** nella scheda **Gestione benefit**. Questa funzione è disattivata per impostazione predefinita.

> [!IMPORTANT]
> Se per un dipendente viene registrato sia una **retribuzione fissa** sia un importo di **retribuzione annuale benefit**, la **retribuzione annuale benefit** sarà utilizzata per determinare gli importi della copertura. Nella sezione **Dettagli impiego** della pagina **Lavoratore** è necessario selezionare un valore nel campo **Frequenza di pagamento benefit**.

## <a name="configure-optional-employee-information"></a>Configurare le informazioni sui dipendenti facoltative
Quando si crea un piano di benefit che utilizza tariffe basate sul genere o sull'età, è necessario immettere una data di nascita e un genere affinché il dipendente possa calcolare il costo del benefit.

## <a name="process-employees-to-determine-eligibility"></a>Elaborare i dipendenti per determinare l'idoneità
Prima che i dipendenti possano essere iscritti ai piani, viene eseguita l'elaborazione dell'idoneità per determinare a quali piani sono idonei. È possibile visualizzare i risultati del processo di idoneità nel **visualizzatore dei risultati del processo**. Per ulteriori informazioni, vedi [Elaborare l'idoneità di iscrizione](hr-benefits-process-enrollment-eligibility.md).

## <a name="employees-select-plans-using-employee-self-service-optional"></a>I dipendenti selezionano i piani tramite il **self-service dipendenti** (opzionale)

Quando si verifica un'iscrizione aperta, i dipendenti vengono assunti di recente o si verifica un evento reale, i dipendenti possono selezionare o aggiornare i propri benefit tramite il **self-service dipendenti**. Per ulteriori informazioni, vedi [Configurare il self-service dipendenti](hr-benefits-setup-employee-self-service.md).

## <a name="confirm-employee-plan-selections"></a>Confermare le selezioni del piano dei dipendenti

I benefit che i dipendenti selezionano devono essere confermati prima che i dipendenti vengano considerati iscritti. I benefit possono essere selezionati anche per conto di un dipendente. Per selezionare o confermare i benefit, nella pagina **Dipendente** nella scheda **Benefit** seleziona **Piani di benefit per lavoratori**. Per selezionare o confermare i benefit per più dipendenti, utilizza la pagina **Aggiornamento in blocco dei piani di benefit per lavoratori**.

## <a name="life-event-processing-optional"></a>Elaborazione di eventi reali (facoltativo)

Durante il ciclo di vita del dipendente, ogni dipendente potrebbe sperimentare vari eventi reali, come il matrimonio, i cambiamenti nell'occupazione o i cambiamenti nelle persone a carico o nei beneficiari. Per utilizzare gli eventi reali, è necessario abilitarli nella pagina **Parametri condivisi risorse umane**. Imposta i tipi di eventi reali e le opzioni degli eventi reali per i tipi di piano.

Prima di poter elaborare gli eventi reali, è necessario aver eseguito l'iscrizione aperta almeno una volta durante un periodo di assunzione. Negli Stati Uniti, l'iscrizione aperta si verifica in genere una volta all'anno. Al di fuori degli Stati Uniti, l'iscrizione aperta può verificarsi al momento dell'assunzione. L'elaborazione di eventi reali non richiede che i lavoratori selezionino un piano di benefit. Tuttavia, i lavoratori devono essere inclusi nel processo di iscrizione aperto. Per ulteriori informazioni, vedere gli argomenti seguenti:

- [Elaborare gli eventi reali](hr-benefits-process-life-events.md)
- [Elaborare le modifiche agli eventi reali](hr-benefits-process-life-event-changes.md)
- [Elaborare l'idoneità degli eventi reali](hr-benefits-process-life-event-eligibility.md)

Dopo il completamento dell'elaborazione dell'evento di vita e finché il periodo di iscrizione all'evento di vita è aperto, i dipendenti possono apportare modifiche alle opzioni del piano interessate dall'evento di vita. Gli amministratori possono apportare le modifiche per conto dei dipendenti. Al termine del periodo di iscrizione e se nessun tipo di piano non confermato è correlato alla transazione dell'evento di vita, la transazione viene chiusa.

Tutti i piani interessati dall'evento di vita devono essere selezionati o annullati e quindi confermati. Se un piano non viene selezionato, non viene annullato e quindi non viene confermato, la transazione dell'evento di vita non viene chiusa.

Gli amministratori possono chiudere manualmente la transazione di un evento di vita selezionandola e quindi selezionando **Chiudi**. Se nella transazione sono presenti piani non confermati e un amministratore desidera chiuderla, la chiusura dell'evento di vita potrebbe limitare le modifiche a tali piani.

Gli eventi di vita chiusi non possono essere eliminati.

Gli amministratori possono riaprire la transazione di un evento di vita selezionandola e quindi selezionando **Riapri**.

## <a name="rate-updates-optional"></a>Aggiornamenti tariffari (facoltativo)

A volte, il tasso di un benefit cambia durante il periodo del piano. Per aggiornare le tariffe per i dipendenti già iscritti al piano, è necessario elaborare le modifiche alle tariffe. Per ulteriori informazioni, vedere [Elaborare le modifiche alle tariffe](hr-benefits-process-rate-changes.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
