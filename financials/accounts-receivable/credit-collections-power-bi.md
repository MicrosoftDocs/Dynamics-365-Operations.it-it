---
title: Contenuto Power BI per crediti e riscossioni
description: "In questo argomento viene descritto cosa è incluso nel contenuto Power BI per la gestione di crediti e riscossioni. Descrive come accedere ai report di Power BI e fornisce informazioni sul modello dati e sulle entità utilizzati per costruire il contenuto."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations, UnifiedOperations. Core
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 63160b9473c7f45b0eb0ca7139f9ed47c8e1446f
ms.openlocfilehash: c066e1a190a5536ad67368b4e059ab6bc66718e6
ms.contentlocale: it-it
ms.lasthandoff: 06/20/2017

---

# <a name="credit-and-collections-management-power-bi-content"></a>Contenuto Power BI per crediti e riscossioni

In questo argomento viene descritto cosa è incluso nel contenuto **Gestione crediti e riscossioni** di Microsoft Power BI. Descrive come accedere ai report di Power BI e fornisce informazioni sul modello dati e sulle entità utilizzati per costruire il contenuto.

## <a name="overview"></a>Panoramica

Il contenuto di Power BI **Gestione crediti e riscossioni** è stato creato per i responsabili di riscossione e credito e per gli addetti alla riscossione. Fornisce importanti metriche di raccolta e credito, ad esempio il tempo medio di incasso, il saldo scaduto, l'esposizione di credito e i clienti che hanno superato il limite di credito. Usa i dati transazionali e fornisce visualizzazioni aggregate di crediti e riscossioni per tutte le società. Sono inoltre presenti le suddivisioni per società, gruppo di clienti e cliente.

Il contenuto di Power BI è composto da 10 pagine di report:

- Due pagine di panoramica (una pagina per la panoramica dei crediti e una pagina per la panoramica delle riscossioni)
- Otto pagine di dettagli che forniscono informazioni sulle metriche di riscossione e credito suddivise tra le varie dimensioni

Tutti gli importi verranno visualizzati nella valuta di sistema. È possibile impostare la valuta di sistema nella pagina **Paramenti di sistema**.

Per impostazione predefinita, vengono visualizzati i dati di crediti e riscossioni per la società corrente. Per visualizzare i dati di tutte le società, assegnare il diritto **CustCollectionsBICrossCompany** al ruolo.

## <a name="accessing-the-power-bi-content"></a>Accesso al contenuto Power BI
Se si utilizza l'aggiornamento di Luglio 2017 di Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, il contenuto Power BI **Gestione crediti e riscossioni** viene visualizzato nell'area di lavoro **Crediti e riscossioni cliente**.

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Report inclusi nel contenuto Power BI

Il contenuto di Power BI **CustCollectionsBICrossCompany** include un report costituito da un set di metriche. Queste metriche vengono visualizzate come grafici, riquadri e tabelle. Nella seguente tabella viene fornita una panoramica delle visualizzazioni nel contenuto Power BI per **CustCollectionsBICrossCompany**.

| Pagina di report                 | Visualizzazione |
|-----------------------------|---------------|
| Panoramica sulle riscossioni        | <ul><li>Attività clienti scadute</li><li>Clienti con limite di credito superato</li><li>Tempo medio di incasso 30 giorni</li><li>Casi aperti</li><li>Numero medio di giorni per chiusura caso</li><li>Attività aperte</li><li>Numero medio di giorni per chiusura attività</li><li>Note d'interesse aperte</li><li>Lettera di sollecito aperte</li><li>Sospensione cliente</li><li>Sospensione vendite</li><li>Saldi con aging</li><li>Importi stato riscossioni</li><li>Importi codice riscossioni</li><li>Motivo di annullamento</li><li>Saldo esigibile per stato/regione</li><li>Pagamenti previsti</li></ul> |
| Panoramica sul credito             | <ul><li>Attività clienti scadute</li><li>Limite di credito e saldo esigibile</li><li>Griglia dei clienti con limite di credito superato</li><li>Clienti con limite di credito superato per società</li><li>Credito utilizzato rispetto al limite di credito totale</li><li>Limite di credito rispetto al credito utilizzato per stato/regione</li><li>Clienti per posizione finanziaria</li></ul> |
| Limite di credito                | <ul><li>Limite di credito</li><li>Dettagli limite di credito</li><li>Limite di credito per cliente</li><li>Limite di credito per gruppo di clienti</li><li>Limite di credito per posizione finanziaria per società</li><li>Limite di credito rispetto credito utilizzato per stato/regione</li></ul> |
| Clienti con limite di credito superato | <ul><li>Clienti con limite di credito superato</li><li>Dettagli clienti con limite di credito superato</li><li>Clienti con limite di credito superato per società</li><li>Clienti con limite di credito superato per gruppo di clienti</li><li>Clienti con limite di credito superato per stato/regione</li></ul> |
| Attività clienti scadute          | <ul><li>Attività clienti scadute</li><li>Dettagli attività clienti scadute</li><li>Attività clienti scadute per società</li><li>Attività clienti scadute per gruppo di clienti</li><li>Attività clienti scadute per stato/regione</li></ul> |
| Saldi con aging               | <ul><li>Saldi con aging</li><li>Dettagli saldi con aging</li><li>Saldi con aging per società</li><li>Saldi con aging per gruppo di clienti</li></ul> |
| Pagamenti previsti           | <ul><li>Pagamenti previsti</li><li>Dettagli pagamenti previsti</li><li>Pagamenti previsti per società</li><li>Pagamenti previsti per gruppo di clienti</li><li>Pagamenti previsti per stato/regione</li></ul> |
| Annullamenti                  | <ul><li>Annullamenti per stato/regione</li><li>Dettagli annullamenti</li><li>Annullamenti per conto principale</li><li>Annullamenti per società</li><li>Annullamenti per gruppo di clienti</li><li>Annullamenti per stato/regione</li></ul> |
| Stato riscossioni          | <ul><li>In controversia</li><li>Promessa di pagamento non mantenuta</li><li>Promessa di pagamento</li><li>Dettagli stato riscossioni</li><li>Importi stato riscossioni</li><li>Casi aperti</li><li>Attività aperte</li></ul> |
| Lettere di sollecito         | <ul><li>Importi codice riscossioni</li><li>Dettagli importi codice riscossioni</li><li>Importo lettera di sollecito per società</li><li>Importo lettera di sollecito per gruppo di clienti</li><li>Importo lettera di sollecito per stato/regione</li></ul> |

I grafici e i riquadri in tutti i report possono essere filtrati e aggiunti al dashboard. Per ulteriori informazioni su come applicare filtri ed eseguire aggiunte in Power BI, vedere [Creare e configurare un dashboard](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards/). È inoltre possibile utilizzare la funzionalità di esportazione dati sottostanti per esportare i dati sottostanti riepilogati in una visualizzazione.

## <a name="extending-the-power-bi-content"></a>Estensione del contenuto Power BI
Utilizzando i pacchetti di contenuti disponibili in Microsoft Dynamics Lifecycle Services (LCS), è possibile fornire eccezionali analisi alle persone che non accedono a Finance and Operations. È possibile modificare i pacchetti di contenuti affinché siano inclusi altri report o rappresentazioni e quindi pubblicate i pacchetti contenuti nel tenant Power BI.com per l'analisi.

Puoi trovare il contenuto Power BI **Gestione crediti e riscossioni** nella raccolta delle risorse condivise in LCS. Per ulteriori informazioni su come scaricare il contenuto e implementarlo nell'organizzazione, vedere [Contenuto Power BI in LCS da Microsoft e dai partner](/dynamics365/unified-operations/dev-itpro/analytics/power-bi-content-microsoft-partners). Per guardare una demo che mostra come implementare il contenuto di Power BI, vedere [Contenuto di Power BI da Microsoft e partner in Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w) (Office Mix).

Assicurarsi di scaricare il contenuto di Power BI **Gestione crediti e riscossioni** applicabile alla versione di Finance and Operations in uso.

## <a name="understanding-the-data-model-and-entities"></a>Informazioni su modelli ed entità di dati

I seguenti dati vengono utilizzati per compilare il report nel contenuto Power BI **Gestione crediti e riscossioni**. Questi dati vengono rappresentati come misure aggregate approntate nell'archivio entità. L'archivio entità è un database di Microsoft SQL Server che viene ottimizzato per l'analisi dei dati. Per ulteriori informazioni, vedere [Panoramica dell'integrazione di Power BI con l'archivio entità](/dynamics365/unified-operations/dev-itpro/analytics/power-bi-integration-entity-store).

| Entità                                      | Misure di aggregazione chiave           | Origine dati                                 | Campo                                                      | descrizione |
|---------------------------------------------|--------------------------------------|---------------------------------------------|------------------------------------------------------------|-------------|
| CustCollectionsBIActivitiesAverageCloseTime | NumOfActivities, AveragecClosedTime  | smmActivities                               | AverageOfChildren(AverageClosedTime) Count(ActivityNumber) | Numero di attività chiuse e tempo medio di chiusura delle attività. |
| CustCollectionsBIActivitiesOpen             | ActivityNumber                       | smmActivities                               | Count(ActivityNumber)                                      | Numero di attività aperte. |
| CustCollectionsBIAgedBalances               | AgedBalances                         | CustCollectionsBIAgedBalancesView           | Sum(SystemCurrencyBalance)                                 | Somma dei saldi con aging. |
| CustCollectionsBIBalancesDue                | SystemCurrencyAmount                 | CustCollectionsBIBalanceDueView             | Sum(SystemCurrencyAmount)                                  | Gli importi scaduti. |
| CustCollectionsBICaseAverageCloseTIme       | NumOfCases, CaseAverageClosedTime    | CustCollectionsCaseDetail                   | AverageOfChildren(CaseAverageClosedTime) Count(NumOfCases) | Numero di casi chiusi e tempo medio di chiusura dei casi. |
| CustCollectionsBICasesOpen                  | CaseId                               | CustCollectionsCaseDetail                   | Count(CaseId)                                              | Numero di casi aperti. |
| CustCollectionsBICollectionLetter           | CollectionLetterNum                  | CustCollectionLetterJour                    | Count(CollectionLetterNum)                                 | Numero di lettere di sollecito aperte. |
| CustCollectionsBICollectionLetterAmount     | CollectionLetterAmounts              | CustCollectionsBIAccountsReceivables        | Sum(SystemCurrencyAmount)                                  | Saldo delle lettere di sollecito registrate. |
| CustCollectionsBICollectionStatus           | CollectionStatusAmounts              | CustCollectionsBIAccountsReceivables        | Sum(SystemCurrencyAmount)                                  | Saldo delle transazioni con stato riscossione. |
| CustCollectionsBICredit                     | CreditExposed, AmountOverCreditLimit | CustCollectionsBICreditView                 | Sum(CreditExposed), Sum(AmountOverCreditLimit)             | Somma degli importi e dell'esposizione di credito con limite di credito superato dai clienti. |
| CustCollectionsBICustOnHold                 | Bloccata                              | CustCollectionsBICustTable                  | Count(Blocked)                                             | Numero dei clienti in attesa. |
| CustCollectionsBIDSO                        | DSO30                                | CustCollectionsBIDSOView                    | AverageOfChildren(DSO30)                                   | Tempo medio di incasso per 30 giorni. |
| CustCollectionsBIExpectedPayment            | ExpectedPayment                      | CustCollectionsBIExpectedPaymentView        | Sum(SystemCurrencyAmounts)                                 | Somma dei pagamenti previsti per il prossimo anno. |
| CustCollectionsBIInterestNote               | InterestNote                         | CustInterestJour                            | Count(InterestNote)                                        | Numero delle note di interesse create. |
| CustCollectionsBISalesOnHold                | SalesId                              | SalesTable                                  | Count(SalesId)                                             | Numero degli ordini cliente totali in attesa. |
| CustCollectionsBIWriteOff                   | WriteOffAmount                       | CustCollectionsBIWriteOffView               | Sum(SystemCurrencyAmount)                                  | Somma delle transazioni che sono state annullate. |

