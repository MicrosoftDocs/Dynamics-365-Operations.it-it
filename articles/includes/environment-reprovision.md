Quando si copia un database tra due ambient, è necessario eseguire lo strumento di provisioning dell'ambiente prima che il database copiato sia completamente operativo per verificare che tutti i componenti Retail siano aggiornati.

> [!IMPORTANT]
> Si consiglia di eseguire questa procedura indipendentemente dal fatto che si stiano utilizzando componenti Retail o meno, poiché la funzionalità Retail è inclusa in tutti gli ambienti. 

Prima di continuare, assicurarsi di soddisfare i seguenti prerequisiti:
1. Se si esegue l'aggiornamento alla versione 7.2.11792.56024 di luglio 2017 (anche nota come 7.2), applicare i seguenti aggiornamenti rapidi per l'applicazione X++ nell'ambiente di destinazione prima di eseguire un aggiornamento dei dati in tale ambiente. Quanto indicato di seguito eviterà che si verifichino diversi errori durante l'aggiornamento dei dati.

    - KB 4036156 - Aggiornamento della versione secondaria di Retail - "Sequenza numerica varianti non impostata." Questo pacchetto di aggiornamento rapido include anche le correzioni KB 4035399 e KB 4035751. Tenere presente che per utilizzare questo pacchetto, è necessario disporre almeno del platform update 9. In caso di dubbio, installare i file binari più recenti.
    
2. Se si esegue l'aggiornamento da Microsoft Dynamics AX 2012, prima di aggiornare i dati, installare nell'ambiente di destinazione le seguenti correzioni per l'applicazione X++:
    - KB 4033183 - Dynamics AX 2012 R2 o Dynamics AX 2012 R3 Pre-CU8: errore dell'aggiornamento non-Retail relativo all'oggetto non trovato per dbo.RETAILTILLLAYOUTZONE.
    - KB 4040692 - Da Dynamics AX 2012 R3 a Microsoft Dynamics 365 for Operations 7.2: errore dell'aggiornamento relativo all'indice duplicato RetailSalesLine in SalesLineIdx.
    - KB 4035490 - Problema di prestazioni relativo allo script di aggiornamento del campo MainAccount di GeneralJournalAccountEntry.


Per eseguire lo strumento di reprovisioning dell'ambiente, attenersi a questi passaggi:

1. Nella raccolta di risorse condivise selezionare **Pacchetto software distribuibile**.
2. Scaricare lo strumento di reprovisioning dell'ambiente.
3. Nella raccolta di risorse per il progetto selezionare **Pacchetto software distribuibile**.
4. Selezionare **Nuovo** per creare un nuovo pacchetto.
5. Immettere un nome e una descrizione per il pacchetto. Come nome del pacchetto, è possibile utilizzare **Strumento di reprovisioning dell'ambiente**.
6. Caricare il pacchetto scaricato in precedenza.
7. Nella pagina **Dettagli ambiente** per l'ambiente di destinazione, selezionare **Gestisci** > **Applica aggiornamenti**.
8. Selezionare lo strumento di reprovisioning dell'ambiente caricato in precedenza e quindi selezionare **Applica** per applicare il pacchetto.
9. Monitorare l'avanzamento della distribuzione del pacchetto. 

Per ulteriori informazioni su come applicare un pacchetto distribuibile, vedere [Applicare un pacchetto distribuibile](../deployment/create-apply-deployable-package.md). Per ulteriori informazioni su come applicare manualmente un pacchetto distribuibile, vedere [Installare un pacchetto distribuibile](../deployment/install-deployable-package.md).
