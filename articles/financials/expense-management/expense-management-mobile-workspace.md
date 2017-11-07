---
title: Area di lavoro mobile di gestione spese
description: In questo argomento vengono fornite informazioni sull'area di lavoro mobile per la gestione della spesa. Questa area di lavoro consente agli utenti di acquisire e caricare una ricevuta, in modo che possono successivamente collegarla a una nota spese. Gli utenti possono inoltre creare rapidamente una riga di spesa utilizzando una ricevuta collegata e creare e gestire le loro note spese.
author: KimANelson
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.custom: 274023
ms.assetid: 3605eda1-a7ed-4675-8031-5279c5a8f5e4
ms.search.region: Global
ms.author: knelson
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: 69eeb90387ca5765c163c7d482295ea104cc078c
ms.openlocfilehash: 7ce4c9d13a8686c82af8acad39d68858e52ba520
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="expense-management-mobile-workspace"></a>Area di lavoro mobile di gestione spese

[!include[banner](../includes/banner.md)]

In questo argomento vengono fornite informazioni sull'area di lavoro mobile per **Gestione spese**. Questa area di lavoro consente agli utenti di acquisire e caricare una ricevuta, in modo che possono successivamente collegarla a una nota spese. Gli utenti possono inoltre creare rapidamente una riga di spesa utilizzando una ricevuta collegata e creare e gestire le loro note spese. Inoltre, gli approvatori possono utilizzare l'area di lavoro mobile **Gestione spese** per visualizzare le note spese loro assegnate e per approvare o rifiutare tali note spese.


Questa area di lavoro mobile può essere utilizzata con l'app mobile Microsoft Dynamics 365 for Unified Operations.


## <a name="overview"></a>Panoramica

In molte organizzazioni è necessario che una copia della ricevuta venga allegata a un report spese correlato al business che un dipendente inoltra per il rimborso. L'area di lavoro mobile **Gestione spese** consente agli utenti di creare rapidamente nuove righe di spesa nel dispositivo mobile preferito utilizzando una foto allegata di una ricevuta. In alternativa, è possibile acquisire una foto di una ricevuta e quindi successivamente allegarla a una nota spese. I dipendenti possono creare e gestire le loro note spese e quindi inviarle per l'approvazione e il rimborso utilizzando il dispositivo mobile.


Nello specifico l'area di lavoro mobile **Gestione spese** consente agli utenti di eseguire queste attività:

- Scattare la foto di una ricevuta e caricarla in Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition. È possibile quindi allegare la foto a una nota spese in un secondo momento.
- Caricare un file come ricevuta acquisita. È possibile quindi allegare il file a una nota spese in un secondo momento.
- Creare una nuova riga di spesa utilizzando una ricevuta collegata. È possibile quindi aggiungere la voce a una nota spese successivamente e inviarla per l'approvazione e il rimborso.

Se si utilizza Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, (luglio 2017) è anche possibile effettuare quanto segue:

- Creare una nuova nota spese.
- Collegare le transazioni della carta di credito e altre spese create in precedenza a una nota spese.
- Creare nuove spese per una nota spese.
- Collegare una ricevuta a una spesa di una nota spese, scattando una foto della ricevuta o caricando un file come ricevuta acquisita.
- A seconda dei criteri di spesa della società, aggiungere l'elenco degli ospiti a una spesa.
- A seconda dei criteri di spesa della società, dettagliare le spese.
- Inviare una nota spese per l'approvazione e il rimborso.
- Approvare o rifiutare le note spese di cui si è un approvatore assegnato.

## <a name="prerequisites"></a>Prerequisiti
I prerequisiti variano a seconda della versione di Microsoft Dynamics 365 che è stata installata nell'organizzazione.

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-finance-and-operations-enterprise-edition-july-2017"></a>Prerequisiti se si usa l'Aggiornamento di Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (luglio 2017) 
Se nell'organizzazione è stato distribuito Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (luglio 2017) l'amministratore di sistema deve pubblicare l'area di lavoro mobile **Gestione spese**. Per istruzioni, vedere [Pubblicare un'area di lavoro mobile](../../dev-itpro/mobile-apps/publish-mobile-workspace.md).

### <a name="prerequisites-if-you-use-microsoft-dynamics-365-for-operations-version-1611-with-platform-update-3-or-later"></a>Prerequisiti se si usa Microsoft Dynamics 365 for Operations versione 1611 con Aggiornamento piattaforma 3 o versione successiva
Se nell'organizzazione è stato distribuito Microsoft Dynamics 365 for Operations versione 1611 con Aggiornamento piattaforma 3 o versione successiva, l'amministratore di sistema deve soddisfare i prerequisiti seguenti. 

<table>
<thead>
<tr class="header">
<th>Prerequisito</th>
<th>Ruolo</th>
<th>descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Implementare l'articoloo KB 4019015.</td>
<td>Amministratore di sistema</td>
<td>L'articolo KB 4019015 è un aggiornamento X++ o un aggiornamento rapido dei metadati contenente l'area di lavoro mobile <strong>Gestione spese</strong>. Per implementare l'articolo KB 4019015, l'amministratore di sistema deve completare i passaggi seguenti:
<ol>
<li><a href="../../dev-itpro/migration-upgrade/download-hotfix-lcs.md">Scaricare l'hotfix metadati da Microsoft Dynamics Lifecycle Services (LCS)</a>.</li>
<li><a href="../../dev-itpro/migration-upgrade/install-metadata-hotfix-package.md">Installare l'aggiornamento rapido dei metadati</a>.</li>
<li><a href="../../dev-itpro/deployment/create-apply-deployable-package.md">Creare un pacchetto distribuibile</a> contenente i modelli <strong>ApplicationSuite</strong> e <strong>ExpenseMobile</strong> e quindi caricare il pacchetto distribuibile in LCS.</li>
<li><a href="../../dev-itpro/deployment/apply-deployable-package-system.md">Applicare il pacchetto distribuibile</a>.</li>
</ol></td>
</tr>
<tr class="even">
<td>Pubblicare l'area di lavoro mobile <strong>Gestione spese</strong>.</td>
<td>Amministratore di sistema</td>
<td>Vedere <a href="../../dev-itpro/mobile-apps/publish-mobile-workspace.md">Pubblicare un'area di lavoro mobile</a>.</td>
</tr>
</tbody>
</table>

## <a name="download-and-install-the-dynamics-365-for-operations-mobile-app"></a>Scaricare e installare l'app mobile Microsoft Dynamics 365 for Operations.
Scaricare e installare l'app mobile Dynamics 365 for Unified Operations:

- [Per telefoni Android](https://go.microsoft.com/fwlink/?linkid=850662)
- [Per iPhone](https://go.microsoft.com/fwlink/?linkid=850663)

## <a name="sign-in-to-the-mobile-app"></a>Accedere all'app mobile
1. Avviare l'app sul dispositivo mobile.
2. Immettere il proprio URL Dynamics 365.
4. La prima volta che si accede viene richiesto di inserire il proprio nome utente e la password. Immettere le proprie credenziali.
5. Dopo avere effettuato l'accesso, vengono visualizzate le aree di lavoro disponibili per la società. Nota: se l'amministratore di sistema pubblica una nuova area di lavoro in seguito, è necessario aggiornare l'elenco delle aree di lavoro mobili.


[![Effettuare il pull per l'aggiornamento](./media/pull-to-refresh-list-of-workspaces-183x300.png)](./media/pull-to-refresh-list-of-workspaces.png)

## <a name="capture-a-receipt-by-using-the-expense-management-mobile-workspace"></a>Acquisire una ricevuta tramite l'area di lavoro mobile di Gestione spese

1. Sul dispositivo mobile aprire l'area di lavoro **Gestione spese**.
2. Selezionare **Acquisisci ricevuta**.
3. Selezionare **Scatta foto** o **Scegli immagine**.
4. Eseguire uno dei passaggi riportati di seguito.

    - Se selezionata l'opzione **Scatta foto**, effettuare le seguenti operazioni:

        1. Viene aperta la macchina fotografica sul dispositivo mobile, in modo che sia possibile scattare una foto della ricevuta. Al termine, selezionare **OK** per accettare la foto.
        2. Facoltativo: immettere un nome per la foto ed eventuali note.

    - Se si seleziona l'opzione **Scegli immagine**, effettuare le seguenti operazioni:

        1. Selezionare un'immagine nell'elenco.
        2. Facoltativo: immettere un nome per l'immagine ed eventuali note.

5. Selezionare **Fine**.

## <a name="quickly-enter-expenses-by-using-the-expense-management-mobile-workspace"></a>Immettere rapidamente le spese tramite l'area di lavoro mobile Gestione spese
1. Sul dispositivo mobile aprire l'area di lavoro **Gestione spese**.
2. Selezionare **Immissione rapida spese**.
3. Selezionare la categoria di spesa per la spesa. Viene visualizzato un elenco delle categorie di spesa caricate nell'app per l'utilizzo offline. Per impostazione predefinita, vengono caricati 50 articoli, ma è possibile cambiare questo numero. Per ulteriori informazioni, gli sviluppatori devono visualizzare [Piattaforma mobile](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md). Se la categoria non è in elenco, selezionare **Cerca** per eseguire una ricerca online. Ricercare per categoria di spesa o selezionare la ricerca per tipo di spesa.
4. Immettere la data della transazione per la spesa.
5. Facoltativo: registrare l'esercente per la spesa.
6. Consente di immettere l'importo della spesa.
7. Consente di selezionare la valuta della spesa. Viene visualizzato un elenco dei codici valuta caricati nell'app per l'utilizzo offline. Per impostazione predefinita, vengono caricate 400 valute, ma uno sviluppatore può cambiare questo numero. Per ulteriori informazioni, gli sviluppatori devono visualizzare [Piattaforma mobile](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md). Se la valuta non è in elenco, selezionare **Cerca** per eseguire una ricerca online. Ricerca in base alla valuta o ricerca per nome.
8. Selezionare **Scatta foto** o **Scegli immagine**.
9. Eseguire uno dei passaggi riportati di seguito.

    - Se si è selezionato **Scatta foto**, viene aperta la macchina fotografica sul dispositivo mobile, in modo che sia possibile scattare una foto della ricevuta. Al termine, selezionare **OK** per accettare la foto.
    - Se viene selezionata **Scegli immagine**, selezionare un'immagine nell'elenco.

10. Selezionare **Fine**.

## <a name="approve-an-expense-report-by-using-the-expense-management-mobile-workspace-if-you-use-the-july-2017-update"></a>Approvare una nota spese utilizzando l'area di lavoro mobile Gestione spese (se si usa l'aggiornamento di luglio 2017)
1. Sul dispositivo mobile aprire l'area di lavoro **Gestione spese**.
2. **Approvazioni spesa** indica il numero di note spese assegnate all'utente per l'approvazione. Il numero viene aggiornato approssimativamente ogni 30 minuti. Selezionare **Approvazioni spesa**.

    Viene visualizzato l'elenco di note spese assegnate per l'approvazione.
    
3. Selezionare una nota spese per visualizzare i dettagli relativi alle spese.
4. Selezionare una spesa per visualizzare i relativi dettagli. Le informazioni visualizzate per una spesa includono le ricevute, gli ospiti e la definizione dei dettagli.
5. Tornando alla pagina **Nota spese** selezionare per approvare o rifiutare la nota spese.
6. Immettere i commenti per l'azione di approvazione.
7. Selezionare **Fine**.

## <a name="create-a-new-expense-report-and-submit-it-for-approval-by-using-the-expense-management-mobile-workspace-if-you-use-the-july-2017-update"></a>Creare una nuova nota spese e inviarla per l'approvazione utilizzando l'area di lavoro mobile Gestione spese (se si usa l'aggiornamento di luglio 2017)
1. Sul dispositivo mobile aprire l'area di lavoro **Gestione spese**.
2. Selezionare **Inserimento delle spese**.
3. Selezionare **Nuovo report** oppure una nota spese esistente nell'elenco.
4. Per le nuove nota spese, immettere lo scopo ed eventuali informazioni aggiuntive che saranno disponibili. Queste informazioni variano in base al modo in cui la gestione spese viene configurata per la società.
5. Selezionare **Fine**.
6. Per aggiungere spese esistenti, ad esempio le transazioni con carta di credito, alla nota spese, selezionare **Allega**.
7. Selezionare una o più spese nell'elenco.
8. Selezionare **Fine**.
9. Per aggiungere una nuova spesa alla nota spese, selezionare **Nuova spesa**.
10. Selezionare la categoria di spesa per la spesa. Viene visualizzato un elenco delle categorie di spesa caricate nell'app per l'utilizzo offline. Per impostazione predefinita, vengono caricati 50 articoli, ma è possibile cambiare questo numero. Per ulteriori informazioni, gli sviluppatori devono visualizzare [Piattaforma mobile](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md). Se la categoria non è in elenco, selezionare **Cerca** per eseguire una ricerca online. Ricercare per categoria di spesa o selezionare la ricerca per tipo di spesa.
11. Facoltativo: registrare l'esercente per la spesa.
12. Immettere la data della transazione per la spesa.
13. Consente di immettere l'importo della spesa.
14. Consente di selezionare la valuta della spesa. Viene visualizzato un elenco dei codici valuta caricati nell'app per l'utilizzo offline. Per impostazione predefinita, vengono caricate 400 valute, ma uno sviluppatore può cambiare questo numero. Per ulteriori informazioni, gli sviluppatori devono visualizzare [Piattaforma mobile](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md). Se la valuta non è in elenco, selezionare **Cerca** per eseguire una ricerca online. Ricerca in base alla valuta o ricerca per nome.
15. Selezionare **Fine**.
16. Per aggiungere ulteriori dettagli alla spesa, selezionare **Aggiungi ulteriori dettagli**. I campi disponibili dipendono dalla configurazione della gestione spese della società.
17. Se i criteri aziendali richiedono una ricevuta per la spesa, selezionare **Ricevute**, quindi procedere come segue:

    1. Selezionare **Acquisisci ricevuta** o **Collega ricevuta**.
    2. Eseguire uno dei passaggi riportati di seguito.

        - Se si seleziona l'opzione **Acquisisci ricevuta**, effettuare le seguenti operazioni:

            1. Selezionare **Scatta foto** o **Scegli immagine**.
            2. Eseguire uno dei passaggi riportati di seguito.

                - Se selezionata l'opzione **Scatta foto**, effettuare le seguenti operazioni:

                    1. Viene aperta la macchina fotografica sul dispositivo mobile, in modo che sia possibile scattare una foto della ricevuta. Al termine, selezionare **OK** per accettare la foto.
                    2. Facoltativo: immettere un nome per la foto ed eventuali note.

                - Se si seleziona l'opzione **Scegli immagine**, effettuare le seguenti operazioni:

                    1. Selezionare un'immagine nell'elenco.
                    2. Facoltativo: immettere un nome per l'immagine ed eventuali note.

            3.  Selezionare **Fine**.

        - Se si seleziona l'opzione **Collega ricevuta**, effettuare le seguenti operazioni:

            1.  Selezionare una o più immagini nell'elenco.
            2.  Selezionare **Fine**.

    3. Selezionare il pulsante **Indietro** per tornare ai dettagli della spesa.

18. Se i criteri aziendali richiedono ospiti per la spesa, selezionare **Ospiti**, quindi procedere come segue:

    1. Selezionare **Ospite**, **Ospiti precedenti** o **Collaboratori**.
    2. Eseguire uno dei passaggi riportati di seguito.

        - Se è stata selezionata l'opzione **Ospite**, effettuare le seguenti operazioni:

            1. Immettere il nome dell'ospite.
            2. Facoltativo: immettere l'organizzazione e/o il paese dell'ospite.
            3. Facoltativo: immettere il titolo professionale dell'ospite.
            4. Selezionare **Fine**.

        - Se si seleziona l'opzione **Ospiti precedenti**, effettuare le seguenti operazioni:

            1. Selezionare uno o più ospiti precedenti nell'elenco. Viene visualizzato un elenco degli ospiti precedenti aggiunti ai report preliminari di spesa caricati nell'app per l'utilizzo offline. Per impostazione predefinita, vengono caricati 50 articoli, ma è possibile cambiare questo numero. Per ulteriori informazioni, gli sviluppatori devono visualizzare [Piattaforma mobile](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md). Se l'ospite precedente non è in elenco, selezionare **Cerca** per eseguire una ricerca online. Eseguire la ricerca per nome o impostare la ricerca per organizzazione, paese o titolo.
            2. Selezionare **Fine**.

        - Se è stata selezionata l'opzione **Collaboratori**, effettuare le seguenti operazioni:

            1. Selezionare uno o più collaboratori nell'elenco. Viene visualizzato un elenco dei collaboratori caricati nell'app per l'utilizzo offline. Per impostazione predefinita, vengono caricati 50 articoli, ma è possibile cambiare questo numero. Per ulteriori informazioni, gli sviluppatori devono visualizzare [Piattaforma mobile](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md). Se il collaboratore non è in elenco, selezionare **Cerca** per eseguire una ricerca online. Eseguire la ricerca per nome o impostare la ricerca per società o titolo.
            2. Selezionare **Fine**.

    3. Selezionare il pulsante **Indietro** per tornare ai dettagli della spesa.

19. Se i criteri aziendali richiedono il dettaglio della spesa, selezionare **Dettagli**, quindi procedere come segue:

    1. Selezionare la prima data da dettagliare.
    2. Selezionare **Aggiungi dettagli**.
    3. Selezionare la sottocategoria per il dettaglio della spesa. Viene visualizzato un elenco delle sottocategorie di spesa caricate nell'app per l'utilizzo offline. Per impostazione predefinita, vengono caricati 50 articoli, ma è possibile cambiare questo numero. Per ulteriori informazioni, gli sviluppatori devono visualizzare [Piattaforma mobile](../../dev-itpro/mobile-apps/platform/mobile-platform-home-page.md). Se la sottocategoria non è in elenco, selezionare **Cerca** per eseguire una ricerca online. Eseguire la ricerca per il nome della sottocategoria spese.
    4. Inserire l'importo della transazione per il dettaglio.
    5. Modificare la data della transazione se necessario.
    6. Selezionare **Fine**.
    7. Ripetere i passaggi precedenti fino a quando non si avrà finito di aggiungere tutti i dettagli per la data selezionata.
    8. Per i giorni aggiuntivi, è possibile selezionare **Copia al giorno successivo** per copiare i dettagli nel giorno successivo. In alternativa, è possibile selezionare la data di cui specificare i dettagli e aggiungere i dettagli come è stato effettuato per la prima data.
    9. Al termine, selezionare il pulsante **Indietro** per tornare ai dettagli della spesa.

20. Selezionare il pulsante **Indietro** per tornare alla pagina **Nota spese**.
21. Ripetere i passaggi precedenti fino a quando non saranno state aggiunte tutte le spese.
22. Selezionare **Invia**.
23. Immettere i commenti per l'approvatore.
24. Selezionare **Fine**.

