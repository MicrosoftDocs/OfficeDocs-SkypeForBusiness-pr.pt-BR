---
title: 'Lync Server 2013: procedimento de failover ABC do pool Front-end'
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
ms.openlocfilehash: aa82180853e8835782d1e39d56fe595e5c7b09b2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500798"
---
# <a name="front-end-pool-abc-failover-procedure-in-lync-server-2013"></a>Procedimento de failover ABC do pool de front-ends no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-05-22_

Use as etapas a seguir para executar o procedimento de failover ABC. Este procedimento contém uma descrição de alto nível de cada etapa, seguida por comandos e cmdlets a serem executados para cada etapa.

Para executar os cmdlets, abra um shell de gerenciamento do Lync Server usando executar como administrador.

<div>

## <a name="to-perform-an-abc-failover"></a>Para executar um failover ABC

1.  Verifique se o pool A é o host para o servidor de gerenciamento central (CMS).
    
      - Execute o seguinte cmdlet:
        
            Get-CsService -CentralManagement
        
        Se o campo Identity do CMS ativo apontar para o FQDN (nome de domínio totalmente qualificado) do pool A, você usará as etapas 2 e 3 deste procedimento para fazer o failover do servidor de gerenciamento central primeiro. Caso contrário, pule para a etapa 4.

2.  Faça o failover do CMS para o pool B no modo de recuperação de desastre executando o seguinte cmdlet:
    
        Invoke-CsManagementServerFailover -BackupSqlServerFqdn <Pool B BE FQDN> -BackupSqlInstanceName <Pool B BE instance name> [-BackupMirrorSqlServerFqdn <Pool B Mirror BE FQDN> -BackupMirrorSqlInstanceName <Pool B Mirror BE Instance name>] -Force -Verbose
    
    Depois de fazer isso, recomendamos que você mova o CMS do pool B para outro pool emparelhado existente para obter resiliência extra. Para obter detalhes, consulte [move-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/Move-CsManagementServer)..

3.  Se o pool A contém CMS, importe a configuração do LIS do pool A no banco de dados LIS do pool B (LIS. MDF). Isso funcionará somente se você tiver feito backup de dados de LIS regularmente. Para importar a configuração do LIS, execute os seguintes cmdlets:
    
        Import-CsLisConfiguration -FileName <String> 
        Publish-CsLisConfiguration

4.  Importe fluxos de trabalho de serviço do grupo de resposta do Lync Server de backup do pool A no pool B.
    
    <div>
    

    > [!NOTE]  
    > Atualmente, o cmdlet <STRONG>Import-CsRgsConfiguration</STRONG> exige que os nomes de fila e fluxo de trabalho no pool A sejam distintos dos nomes de fila e fluxo de trabalho no pool B. Se os nomes não forem distintos, você receberá um erro ao executar o cmdlet <STRONG>Import-CsRgsConfiguration</STRONG> e as filas e fluxos de trabalho precisarão ser renomeados no pool B antes de prosseguir com o cmdlet <STRONG>Import-CsRgsConfiguration</STRONG> .

    
    </div>
    
    Você tem duas opções para importar a configuração do grupo de resposta do pool A para o pool B. A opção que você usa depende se você deseja substituir as configurações de nível de aplicativo do pool B pelas configurações de nível de aplicativo do pool A.
    
      - Se você quiser substituir as configurações do pool B, execute o cmdlet **Import-CsRgsConfiguration** com a opção **ReplaceExistingSettings** :
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - Se você não quiser substituir as configurações do pool B, use o cmdlet **Import-CsRgsConfiguration** sem a opção **ReplaceExistingSettings** .
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > Lembre-se de que se você não quiser substituir as configurações de nível de aplicativo do pool de backup (pool B) pelas configurações do pool primário (pool A), as configurações de nível de aplicativo do pool A serão perdidas se o pool A for perdido, porque o aplicativo do grupo de resposta pode armazenar somente um conjunto de configurações no nível do aplicativo por pool. Quando o pool C é implantado para substituir o pool A, as configurações no nível do aplicativo devem ser reconfiguradas, incluindo o arquivo de áudio de música em espera padrão.

    
    </div>

5.  Verifique se a importação da configuração do grupo de resposta foi bem-sucedida executando os seguintes cmdlets para exibir os grupos de resposta importados. Observe que os grupos de resposta importados ainda pertencem ao pool A.
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"
        
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>"

6.  Para números não atribuídos, mova os intervalos de números não atribuídos que estão usando "Announcement" como o serviço de anúncio selecionado do pool A para o pool B. Para fazer isso:
    
      - Recrie todos os comunicados que foram implantados no pool A no pool B. Se qualquer arquivo de áudio foi usado durante a implantação dos comunicados no pool A, esses arquivos serão necessários para recriar os comunicados no pool B. Para recriar os comunicados no pool B, use os cmdlets **New-CsAnnouncement** , com o pool B como o serviço pai.
    
      - Redirecionar todos os intervalos de números não atribuídos que estão direcionados para um comunicado no pool A para os anúncios recentemente implantados no pool B. Execute o cmdlet a seguir para cada intervalo de números não atribuídos direcionado para um anúncio do pool A:
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool B FQDN>" -AnnouncementName "<New Announcement in pool B>"
    
    <div>
    

    > [!NOTE]  
    > Esta etapa não é necessária para intervalos de números não atribuídos que usam "UM do Exchange" como o serviço de anúncio selecionado.

    
    </div>

7.  Failover do pool A para o pool B no modo de recuperação de desastres (DR), executando o seguinte cmdlet:
    
        Invoke-CsPoolFailover -PoolFqdn <Pool A FQDN> -DisasterMode

8.  Construa o pool C, mas não inicie nenhum serviço no pool C.
    
    Observe que esta etapa pode ser executada simultaneamente com as etapas 5 e 6.

9.  Forçar usuários hospedados no pool A para mover para o pool C executando o seguinte cmdlet:
    
        Get-csuser -Filter {RegistrarPool -eq "<Pool A FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force
    
    Neste ponto, os usuários hospedados no pool A começarão a enfrentar uma interrupção de serviço. Essa interrupção continuará até a etapa 16, em que os serviços de ponto são iniciados no pool C.

10. Force o diretório de conferência do pool A para mover para o pool C executando o seguinte cmdlet:
    
        Move-CsConferenceDirectory -Identity <Conference Directory ID of Pool A> -TargetPool <Pool C FQDN> -Force

11. Force o objeto de contato do atendedor automático da conferência (CAA) para mover do pool A para o pool C executando o seguinte cmdlet:
    
        Move-csApplicationEndpoint -Identity "<Pool A CAA Uri>" -targetApplicationPool <Pool C FQDN> -force

12. Copie o conteúdo da conferência do pool B para o pool C.

13. Exportar dados do usuário do pool B e importar os dados do usuário para o pool C executando os seguintes cmdlets:
    
        Export-CsUserData -PoolFqdn <Pool B Fqdn> -FileName <String>
        Import-CsUserData -PoolFqdn <Pool C Fqdn> -FileName <String>

14. Restaurar dados de aplicativo de estacionamento de chamada com backup do pool A no pool C e atribuir os intervalos de órbita de estacionamento de chamada do pool A ao pool C.
    
      - Você pode reatribuir um intervalo de órbita de estacionamento de chamada do pool A para o pool C por meio do painel de controle do Lync Server ou do Shell de gerenciamento do Lync Server. Para o Shell de gerenciamento do Lync Server, execute o seguinte cmdlet para cada intervalo de órbita de estacionamento de chamadas atribuído ao pool A (Observe que o parâmetro Identity se refere aos intervalos de órbita de estacionamento de chamada que pertencem ao pool A):
        
            Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Pool C FQDN>"
    
      - Se uma música em espera personalizada tiver sido configurada para estacionamento de chamada no pool A, restaure o arquivo de música-em espera personalizado do estacionamento de chamada no pool C.
        
            Xcopy <Source> <Destination: Pool C CPS File Store Path>
        
        Por exemplo:
        
            Xcopy "Source Path" "<Pool C File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"
    
      - Por fim, reconfigure as configurações de estacionamento de chamadas no pool C usando o cmdlet **set-CsCpsConfiguration** . O aplicativo de estacionamento de chamada pode armazenar somente um conjunto de configurações e um arquivo de áudio de música em espera personalizado por pool, e essas configurações não são compartilhadas ou mantidas em caso de desastre.

15. Se o pool de próximo salto para chat persistente estiver apontando para o pool A, faça e publique as alterações de topologia para que o servidor de próximo salto aponte para o pool C.
    
      - No construtor de topologias, altere o pool de chat persistente para apontar para o pool C como seu próximo salto. Para fazer isso, clique com o botão direito do mouse no pool de chat persistente e, em seguida, clique na guia **geral** e digite o nome do pool C no **pool de próximo salto**.
    
      - Inicie os serviços no pool C executando o seguinte cmdlet:
        
            Start-csWindowsService
    
    Neste ponto, a interrupção do serviço termina para os usuários hospedados originalmente no pool A.

16. Exportar fluxos de trabalho do serviço grupo de resposta do Lync Server do pool B pertencente ao pool A para importar para o pool C executando o seguinte cmdlet:
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" 

17. Importe fluxos de trabalho do serviço grupo de resposta do Lync Server no pool C do pool B.
    
    Você tem duas opções para a importação da configuração do grupo de resposta do pool B para o pool C. A opção que você usa depende se você deseja substituir as configurações de nível de aplicativo do pool C com as configurações no nível do aplicativo no pool B.
    
      - Se você quiser substituir as configurações do pool C, execute o cmdlet **Import-CsRgsConfiguration** com a opção **ReplaceExistingSettings** :
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool C FQDN>" -FileName "C:\RgsExportPrimary.zip"  -ReplaceExistingRgsSettings
    
      - Se você não quiser substituir as configurações do pool C, use o cmdlet **Import-CsRgsConfiguration** sem a opção **ReplaceExistingSettings** .
        
            Import-CsRgsConfiguration -Destination "service:ApplicationServer:<Pool B FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    <div>
    

    > [!WARNING]  
    > Tenha em mente que se você não quiser substituir as configurações de nível de aplicativo do pool C com as configurações do pool de backup (pool B), as configurações de nível de aplicativo do pool B serão perdidas porque o aplicativo de grupo de resposta pode armazenar somente um conjunto de configurações no nível do aplicativo por pool.

    
    </div>

18. Verifique se a importação da configuração do grupo de resposta foi bem-sucedida executando os seguintes cmdlets para exibir os grupos de resposta que foram importados para o pool C.
    
        Get-CsRgsWorkflow -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
         Get-CsRgsQueue -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll
        Get-CsRgsAgentGroup -Identity "service:ApplicationServer:<Pool C FQDN>" -ShowAll

19. Quando a configuração importada tiver sido verificada no pool C, remova os grupos de resposta pertencentes ao pool primário do pool B. Isso minimizará o tempo de inatividade dos grupos de resposta.
    
    Esta etapa cria um novo arquivo com a configuração exportada e, em seguida, remove o arquivo do pool B.
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool B FQDN>" -Owner "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimaryUpdated.zip" -RemoveExportedConfiguration

20. Mover para o pool C os intervalos de números não atribuídos que foram movidos do pool A para o pool B.
    
      - Recrie no pool C todos os anúncios que foram recriados do pool A no pool B. Se qualquer arquivo de áudio foi usado durante a implantação dos comunicados a serem movidos, será necessário usar esses arquivos para recriar os comunicados no pool C. Para recriar os comunicados no pool C, use os cmdlets **New-CsAnnouncement** , com o pool C como o serviço pai.
    
      - Redirecionar para o pool C todos os intervalos de números não atribuídos que foram redirecionados do pool A para o pool B. Execute o cmdlet a seguir para cada intervalo de número não atribuído que precisa ser redirecionado:
        
            Set-CsUnassignedNumber -Identity "<Range Name>" -AnnouncementService "<Pool C FQDN>" -AnnouncementName "<New Announcement in pool C>"
    
      - Opcion Remover do pool B os anúncios que foram recriados no pool C se não estiverem mais em uso no pool B. Para remover comunicados, use o cmdlet **Remove-CsAnnouncement** .
        
        <div>
        

        > [!NOTE]  
        > Esta etapa não é necessária para intervalos de números não atribuídos que usam "UM do Exchange" como serviço de anúncio.

        
        </div>

21. Limpe os dados do usuário do pool A no pool B executando o seguinte cmdlet:
    
        Remove-CsUserStoreBackupData -PoolFqdn <Pool B FQDN> -Verbose

22. No construtor de topologias, faça o seguinte:
    
      - Desemparelhar pool A e pool B. pool de par B e pool C. Em seguida, remova o pool A da topologia e publique-o. Para fazer isso:
        
          - No construtor de topologias, clique com o botão direito do mouse no pool B e, em seguida, clique em **Editar propriedades**.
        
          - Clique em **resiliência** no painel esquerdo.
        
          - Na caixa abaixo **pool de backup associado**, selecione pool C. Observe que a caixa de seleção pool de backup associado exibirá inicialmente o pool A, porque o pool B estava anteriormente associado a esse pool.
        
          - Selecione **Failover automático e failback para voz** e clique em **OK**.
            
            Ao exibir os detalhes sobre este pool, o pool associado agora aparece no painel direito em **Resiliência**.
        
          - Na árvore do console, clique com o botão direito do mouse em pool A e clique em excluir.
        
          - Publique a topologia.

23. Execute o aplicativo de inicialização no pool C para instalar o aplicativo de serviço de backup e, em seguida, inicie o aplicativo de serviço de backup executando o seguinte na pasta de implantação em um computador local no pool C:
    
        Run "%SYSTEMROOT%\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe"
        Start-CsWindowsService -name LyncBackup

24. Reinicie o aplicativo de serviço de backup no pool B executando os seguintes cmdlets:
    
        Stop-CsWindowsService -name LyncBackup
        Start-CsWindowsService -name LyncBackup

25. Se o pool C for um pool Standard Edition (SE) e o pool B tiver o CMS, instale o banco de dados CMS manualmente no pool C executando o seguinte cmdlet:
    
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <Pool C FQDN> -SqlInstanceName rtc

26. Invocar o serviço de backup para sincronizar o conteúdo antigo da conferência do pool B para o pool C que foi gerado antes de emparelhar B e C juntos e sincronizar o novo conteúdo de conferência do pool C para o pool B que foi gerado após iniciar o pool C e antes de o B e o C terem sido emparelhados juntos. Para fazer isso, execute os seguintes cmdlets:
    
        Invoke-CsBackupServiceSync -PoolFqdn <Pool C FQDN>
        Invoke-CsBackupServiceSync -PoolFqdn <Pool B FQDN>

27. Para cada aparelho de filial persistente X associado ao pool A:
    
      - Desligue o SBA X executando o seguinte cmdlet:
        
            Stop-CsWindowsService
    
      - Criar um arquivo que contém uma lista de usuários hospedados no SBA X. A lista será necessária quando os usuários forem movidos de volta para o SBA X na etapa 30. Para fazer isso, execute o seguinte cmdlet:
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Export-Csv d:\sbaxusers.txt
    
      - Forçar usuários hospedados no SBA X para mover para o pool C executando o seguinte cmdlet:
        
            Get-CsUser -Filter {RegistrarPool -eq "<SBA X FQDN>"} | Move-CsUser -Target <Pool C FQDN> -Force -Verbose
    
      - Atualize os dados desses usuários primeiro executando os seguintes cmdlets:
        
            Convert-csUserData -InputFile <Data file exported from PoolB> -OutputFile c:\Logs\ExportedUserData.xml -TargetVersionLync2010 
            $a=get-csuser -Filter {RegistrarPool -eq "FQDN of SBA X"} | select SipAddress
            foreach($x in $a) {$x.SipAddress.Substring(4) >> users.txt}
        
        E, em seguida, execute este script:
        
            $users=gc c:\logs\users.txt
            foreach ($user in $users)
            {
            Update-CsUserData -FileName c:\logs\exportedUserDAta.xml -UserFilter $user - 
            }
        
        <div>
        

        > [!NOTE]  
        > Ocorrerá uma interrupção de serviço para usuários hospedados no SBAs que estão associados ao pool A até que estes usuários sejam movidos para o pool C.

        
        </div>

28. No construtor de topologia, para cada SBA X previamente associado ao pool A, faça o seguinte:
    
      - Altere a associação para o pool C. Para fazer isso, clique no site de filial, expanda o nó dispositivos ou servidores de filial persistente e clique em **aparelho de filial persistente**. Em seguida, selecione o **pool de front-ends, o pool de serviços de usuário** ao qual esse aparelho de filial persistente será conectado como pool C e clique em **Avançar**.
    
      - Publique a topologia. Para fazer isso, na árvore de console, clique com o botão direito do mouse no novo **dispositivo de filial persistente**, clique em **topologia**e em **publicar**.

29. Para cada SBA X agora associado ao pool C:
    
      - Inicie o SBA X executando o seguinte cmdlet no aparelho de filial persistente:
        
            Start-CsWindowsService
    
      - Mova os usuários que estavam originalmente hospedados no SBA X do pool C para o SBA X executando o seguinte cmdlet.
        
            Import-Csv d:\sbaxusers.txt | Move-CsUser -Target <SBA X FQDN> -Force

</div>

</div>

<span> </span>

</div>

</div>

</div>

