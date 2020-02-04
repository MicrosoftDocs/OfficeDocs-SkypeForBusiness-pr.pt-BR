---
title: 'Lync Server 2013: Procedimento de failover ABC do pool Front-End'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Front End pool ABC failover procedure
ms:assetid: 67763ad3-6796-45eb-a486-901f21ac1a95
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945635(v=OCS.15)
ms:contentKeyID: 51541486
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edf3d12aa519ab7746ccec92998995ed463aa9be
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739771"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="front-end-pool-abc-failover-procedure-in-lync-server-2013"></a>Procedimento de failover ABC do pool Front-End no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-05-22_

Use as etapas a seguir para executar o procedimento de failover do ABC. Este procedimento contém uma descrição de alto nível de cada etapa, seguida por comandos e cmdlets a serem executados para cada etapa.

Para executar os cmdlets, abra um shell de gerenciamento do Lync Server usando executar como administrador.

<div>

## <a name="to-perform-an-abc-failover"></a>Para executar um failover de ABC

1.  Verifique se o pool A é o host do servidor de gerenciamento central (CMS).
    
      - Execute o seguinte cmdlet:
        
            Get-CsService -CentralManagement
        
        Se o campo de identidade do CMS ativo apontar para o nome de domínio totalmente qualificado (FQDN) do pool A, use as etapas 2 e 3 deste procedimento para fazer o failover do servidor de gerenciamento central primeiro. Caso contrário, pule para a etapa 4.

2.  Reprovar o CMS para o pool B no modo de recuperação de desastre executando o seguinte cmdlet:
    
        Invoke-CsManagementServerFailover -BackupSqlServerFqdn <Pool B BE FQDN> -BackupSqlInstanceName <Pool B BE instance name> [-BackupMirrorSqlServerFqdn <Pool B Mirror BE FQDN> -BackupMirrorSqlInstanceName <Pool B Mirror BE Instance name>] -Force -Verbose
    
    Depois de fazer isso, recomendamos que você mova o CMS do pool B para outro pool emparelhado existente para obter resiliência extra. Para obter detalhes, consulte [mover-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/Move-CsManagementServer)..

3.  Se o pool A contém CMS, importe a configuração de LIS do pool A para o banco de dados LIS do pool B (LIS. MDF). Isso só funcionará se você tiver feito backup dos dados do LIS regularmente. Para importar a configuração de LIS, execute os seguintes cmdlets:
    
        Import-CsLisConfiguration -FileName <String> 
        Publish-CsLisConfiguration

4.  Importar fluxos de trabalho do serviço de grupo de resposta do Lync Server de backup do pool A para o pool B.
    
    <div>
    

    > [!NOTE]  
    > Atualmente, o cmdlet <STRONG>Import-CsRgsConfiguration</STRONG> requer que os nomes da fila e do fluxo de trabalho no pool A sejam distintos dos nomes da fila e do fluxo de trabalho no pool B. Se os nomes não forem distintos, você receberá um erro ao executar o cmdlet <STRONG>Import-CsRgsConfiguration</STRONG> , e as filas e os fluxos de trabalho precisarão ser renomeados no pool B antes de prosseguir com o cmdlet <STRONG>Import-CsRgsConfiguration</STRONG> .

    
    </div>
    
    Você tem duas opções para importar a configuração do grupo de resposta do pool A para o pool B. Qual opção você usa depende se você deseja substituir as configurações de nível de aplicativo do pool B pelas configurações de nível de aplicativo no pool A.
    
      - Se você deseja substituir as configurações do pool B, execute o cmdlet **Import-CsRgsConfiguration** com a opção **ReplaceExistingSettings** :
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - Se você não quiser substituir as configurações do pool B, use o cmdlet **Import-CsRgsConfiguration** sem a opção **ReplaceExistingSettings** .
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > Lembre-se de que se você não quiser substituir as configurações de nível de aplicativo do pool de backup (pool B) pelas configurações do pool primário (pool A), as configurações de nível de aplicativo do pool A serão perdidas se o pool A for perdido, porque o aplicativo do grupo de resposta pode armazenar apenas um conjunto de configurações no nível do aplicativo por pool. Quando o pool C é implantado para substituir o pool A, as configurações do nível do aplicativo devem ser reconfiguradas, incluindo o arquivo de áudio padrão de música em espera.

    
    </div>

5.  Verifique se a importação de configuração de grupo de resposta foi bem-sucedida executando os seguintes cmdlets para exibir os grupos de resposta importados. Observe que os grupos de resposta importados ainda são pertencentes ao pool A.
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"

6.  Para números não atribuídos, mova os intervalos numéricos não atribuídos que estão usando "Announcement" como o serviço de anúncio selecionado do pool A para o pool B. Para fazer isso:
    
      - Crie novamente todos os comunicados que foram implantados no pool A no pool B. Se algum arquivo de áudio foi usado ao implantar os comunicados no pool A, esses arquivos serão necessários para recriar os comunicados no pool B. Para recriar os comunicados no pool B, use os cmdlets **New-CsAnnouncement** , com o pool B como o serviço pai.
    
      - Redirecione todos os intervalos de números não atribuídos que estão direcionando um comunicado no pool A para os comunicados recém implantados no pool B. Execute o seguinte cmdlet para cada intervalo de números não atribuído direcionando um anúncio do pool A:
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool B FQDN>" -AnnouncementName "<New Announcement in pool B>"
    
    <div>
    

    > [!NOTE]  
    > Esta etapa não é necessária para intervalos de números não atribuídos que usam "Exchange UM" como o serviço de anúncio selecionado.

    
    </div>

7.  Failover do pool A para o pool B no modo de recuperação de desastres (DR), executando o seguinte cmdlet:
    
        Invoke-CsPoolFailover -PoolFqdn <Pool A FQDN> -DisasterMode

8.  Construa o pool C, mas não inicie serviços no pool C.
    
    Observe que esta etapa pode ser executada simultaneamente com as etapas 5 e 6.

9.  Forçar usuários hospedados no pool A para mover-se para o pool C executando o seguinte cmdlet:
    
        Get-csuser -Filter {RegistrarPool -eq "<Pool A FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force
    
    Nesse momento, os usuários hospedados no pool A começarão a sofrer uma falha de serviço. Essa interrupção continuará até a etapa 16, em que os serviços de ponto são iniciados no pool C.

10. Force o diretório de conferência do pool A para mover-se para o pool C executando o seguinte cmdlet:
    
        Move-CsConferenceDirectory -Identity <Conference Directory ID of Pool A> -TargetPool <Pool C FQDN> -Force

11. Force o objeto de contato do atendedor automático da conferência (CAA) para mover do pool A para o pool C executando o seguinte cmdlet:
    
        Move-csApplicationEndpoint -Identity "<Pool A CAA Uri>" -targetApplicationPool <Pool C FQDN> -force

12. Copie o conteúdo da conferência do pool B para o pool C.

13. Exportar dados do usuário do pool B e importar os dados do usuário para o pool C executando os seguintes cmdlets:
    
        Export-CsUserData -PoolFqdn <Pool B Fqdn> -FileName <String>
        Import-CsUserData -PoolFqdn <Pool C Fqdn> -FileName <String>

14. Restaurar os dados de aplicativo de estacionamento de chamada com backup do pool A no pool C e atribuir os intervalos de estacionamento de chamada do pool A ao pool C.
    
      - Você pode reatribuir um intervalo de linha de estacionamento de chamada do pool a ao pool C por meio do painel de controle do Lync Server ou do Shell de gerenciamento do Lync Server. Para o Shell de gerenciamento do Lync Server, execute o seguinte cmdlet para cada intervalo de órbita de linha de chamada atribuído ao pool A (Observe que o parâmetro Identity refere-se à faixa de opções de estacionamento em barra de chamada que pertence ao pool A):
        
            Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Pool C FQDN>"
    
      - Se uma música em espera personalizada tiver sido configurada para estacionamento de chamadas no pool A, restaure o arquivo de música em espera personalizado do parque de chamadas no pool C.
        
            Xcopy <Source> <Destination: Pool C CPS File Store Path>
        
        Por exemplo:
        
            Xcopy "Source Path" "<Pool C File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"
    
      - Por fim, redefina as configurações do estacionamento de chamadas no pool C usando o cmdlet **set-CsCpsConfiguration** . O aplicativo de estacionamento de chamadas pode armazenar apenas um conjunto de configurações e um arquivo de áudio de música em espera personalizado por pool, e essas configurações não são comparadas nem preservadas no caso de um desastre.

15. Se o próximo pool de saltos para chats persistentes estiver apontando para o pool A, faça e publique alterações de topologia para que o servidor de salto seguinte aponte para o pool C.
    
      - Em Construtor de topologia, altere o pool de chat persistente para apontar para o pool C como o próximo salto. Para fazer isso, clique com o botão direito do mouse no pool de chat persistente e, em seguida, clique na guia **geral** e digite o nome do pool C no **próximo pool de saltos**.
    
      - Inicie os serviços no pool C executando o seguinte cmdlet:
        
            Start-csWindowsService
    
    Nesse ponto, a interrupção do serviço termina para os usuários hospedados originalmente no pool A.

16. Exportar fluxos de trabalho do serviço de grupo de resposta do Lync Server do pool B pertencentes ao pool A para importação no pool C executando o seguinte cmdlet:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" 

17. Importar fluxos de trabalho do serviço de grupo de resposta do Lync Server para o pool C do pool B.
    
    Você tem duas opções para importar a configuração do grupo de resposta do pool B para o pool C. Qual opção você usa depende se você deseja substituir as configurações de nível de aplicativo do pool C pelas configurações de nível de aplicativo no pool B.
    
      - Se você quiser substituir as configurações de grupo C, execute o cmdlet **Import-CsRgsConfiguration** com a opção **ReplaceExistingSettings** :
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool C FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - Se você não quiser substituir as configurações de grupo C, use o cmdlet **Import-CsRgsConfiguration** sem a opção **ReplaceExistingSettings** .
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > Lembre-se de que se você não quiser substituir as configurações de nível de aplicativo do pool C pelas configurações do pool de backup (pool B), as configurações de aplicativo do pool B serão perdidas porque o aplicativo do grupo de resposta pode armazenar apenas um conjunto de nível de aplicativo configurações por pool.

    
    </div>

18. Verifique se a importação de configuração de grupo de resposta foi bem-sucedida executando os seguintes cmdlets para exibir os grupos de resposta que foram importados para o pool C.
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
         Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll

19. Quando a configuração importada tiver sido verificada no pool C, remova os grupos de resposta pertencentes ao pool primário do pool B. Isso minimiza o tempo de inatividade dos grupos de resposta.
    
    Esta etapa cria um novo arquivo com a configuração exportada e, em seguida, remove o arquivo do pool B.
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration

20. Mover para o pool C os intervalos de números não atribuídos que foram movidos do pool A para o pool B.
    
      - Recrie no pool C todos os anúncios que foram recriados do pool A no pool B. Se você tiver usado arquivos de áudio ao implantar os comunicados a serem movidos, será necessário usar esses arquivos para recriar os comunicados no pool C. Para recriar os comunicados no pool C, use os cmdlets **New-CsAnnouncement** , com o pool C como o serviço pai.
    
      - Redirecionar para o pool C todos os intervalos de números não atribuídos que foram redirecionados do pool A para o pool B. Execute o cmdlet a seguir para cada intervalo de números não atribuído que precisa ser redirecionado:
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool C FQDN>" -AnnouncementName "<New Announcement in pool C>"
    
      - Adicionais Remover do pool B os comunicados que foram criados novamente no pool C se não estiverem mais em uso no pool B. Para remover anúncios, use o cmdlet **Remove-CsAnnouncement** .
        
        <div>
        

        > [!NOTE]  
        > Esta etapa não é necessária para intervalos de números não atribuídos que usam "Exchange UM" como o serviço de anúncio.

        
        </div>

21. Limpe os dados de usuário do pool A no pool B executando o seguinte cmdlet:
    
        Remove-CsUserStoreBackupData -PoolFqdn <Pool B FQDN> -Verbose

22. Faça o seguinte no construtor de topologias:
    
      - Desemparelhar o pool A e o pool B. pool de par B e pool C. Em seguida, remova o pool A da topologia e publique-o. Para fazer isso:
        
          - No construtor de topologias, clique com o botão direito do mouse no pool B e, em seguida, clique em **Editar propriedades**.
        
          - Clique em **resiliência** no painel esquerdo.
        
          - Na caixa abaixo de **pool de backup associado**, selecione pool C. Observe que a caixa de seleção do pool de backup associado inicialmente exibirá o pool A porque o pool B estava anteriormente associado a esse pool.
        
          - Selecione **Failback e failover automático para Voz** e clique em **OK**.
            
            Quando você exibir os detalhes sobre este pool, o pool associado agora aparecerá no painel direito em **Resiliência**. 
        
          - Na árvore do console, clique com o botão direito do mouse em pool A e, em seguida, clique em excluir.
        
          - Publique a topologia.

23. Execute o aplicativo de inicialização no pool C para instalar o aplicativo de serviço de backup e, em seguida, inicie o aplicativo de serviço de backup executando o seguinte na pasta de implantação em um computador local no pool C:
    
        Run "%SYSTEMROOT%\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe"
        Start-CsWindowsService -name LyncBackup

24. Reinicie o aplicativo de serviço de backup no pool B executando os seguintes cmdlets:
    
        Stop-CsWindowsService -name LyncBackup
        Start-CsWindowsService -name LyncBackup

25. Se o pool C for um pool padrão da edição (SE) e o pool B tiver o CMS, instale o banco de dados CMS manualmente no pool C executando o seguinte cmdlet:
    
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <Pool C FQDN> -SqlInstanceName rtc

26. Chame o serviço de backup para sincronizar o conteúdo de conferência antigo do pool B para o pool C que foi gerado antes de emparelhar B e C juntos e sincronizar o novo conteúdo de conferência do pool C com o pool B que foi gerado após iniciar o pool C e antes de B e C terem sido emparelhados juntos. Para fazer isso, execute os seguintes cmdlets:
    
        Invoke-CsBackupServiceSync -PoolFqdn <Pool C FQDN>
        Invoke-CsBackupServiceSync -PoolFqdn <Pool B FQDN>

27. Para cada aparelho de ramificação sobreviventes X associado ao pool A:
    
      - Desligue SBA X executando o seguinte cmdlet:
        
            Stop-CsWindowsService
    
      - Crie um arquivo que contenha uma lista de usuários hospedados no SBA X. A lista será necessária quando os usuários forem movidos de volta para SBA X na etapa 30. Para fazer isso, execute o seguinte cmdlet:
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Export-Csv d:\sbaxusers.txt
    
      - Forçar usuários hospedados no SBA X para mover-se para o pool C executando o seguinte cmdlet:
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force -Verbose
    
      - Atualize os dados desses usuários executando primeiro os seguintes cmdlets:
        
            Convert-csUserData -InputFile <Data file exported from PoolB> -OutputFile c:\Logs\ExportedUserData.xml -TargetVersionLync2010 
            $a=get-csuser -Filter {RegistrarPool -eq "FQDN of SBA X"} | select SipAddress
            foreach($x in $a) {$x.SipAddress.Substring(4) >> users.txt}
        
        Em seguida, execute este script:
        
            $users=gc c:\logs\users.txt
            foreach ($user in $users)
            {
            Update-CsUserData -FileName c:\logs\exportedUserDAta.xml -UserFilter $user - 
            }
        
        <div>
        

        > [!NOTE]  
        > Ocorrerá uma falha de serviço para os usuários que estiverem hospedados no SBAs associados ao pool A até que esses usuários sejam movidos para o pool C.

        
        </div>

28. No construtor de topologia, para cada SBA X associado ao pool A, faça o seguinte:
    
      - Altere a associação para o pool C. Para fazer isso, clique no site da ramificação, expanda o nó utensílios ou servidores da ramificação sobreviventes e clique em **ramificação da ramificação sobreviventes**. Em seguida, selecione o **pool de front-end, o pool de serviços do usuário** para o qual este aparelho de ramificação sobreviventes será conectado como pool C e clique em **Avançar**.
    
      - Publique a topologia. Para fazer isso, na árvore de console, clique com o botão direito do mouse no novo **aplicativo de ramificação sobreviventes**, clique em **topologia**e, em seguida, clique em **publicar**.

29. Para cada SBA X agora associado ao pool C:
    
      - Inicie o SBA X executando o seguinte cmdlet no aparelho da ramificação sobreviventes:
        
            Start-CsWindowsService
    
      - Mova os usuários que estavam originalmente hospedados no SBA X do pool C para o SBA X executando o cmdlet a seguir.
        
            Import-Csv d:\sbaxusers.txt | Move-CsUser -Target <SBA X FQDN> -Force

</div>

</div>

<span> </span>

</div>

</div>

</div>

