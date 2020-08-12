---
title: Instalar e configurar nós do Inspetor
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7392e4f8-6e2d-447b-aaa3-878f73995f9d
description: 'Resumo: instalar e configurar nós do inspetor para transações sintéticas do Skype for Business Server.'
ms.openlocfilehash: 8efe291f72312b7634ae644d0e910cf58951b7a6
ms.sourcegitcommit: b72bf3827e7145b9b6a95c84e88a7879c6e8c337
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2020
ms.locfileid: "46640937"
---
# <a name="install-and-configure-watcher-nodes"></a>Instalar e configurar nós do Inspetor
 
**Resumo:** Instalar e configurar nós do inspetor para transações sintéticas do Skype for Business Server.
  
Os nós do Inspetor são computadores que executam periodicamente as transações sintéticas do Skype for Business Server. As transações sintéticas são cmdlets do Windows PowerShell que verificam se os principais cenários de usuário, como a capacidade de entrar ou para trocar mensagens instantâneas, estão funcionando conforme o esperado. Para o Skype for Business Server 2015, o System Center Operations Manager pode executar as transações sintéticas mostradas na tabela a seguir, que inclui três tipos de transações sintéticas:
  
- **Padrão** Transações sintéticas que um nó do Inspetor executa por padrão. Ao criar um novo nó do Inspetor, você pode especificar quais transações sintéticas esse nó executará. (Esse é o objetivo do parâmetro tests usado pelo cmdlet New-CsWatcherNodeConfiguration.) Se você não usar o parâmetro tests quando o nó do Inspetor for criado, ele executará automaticamente todas as transações sintéticas padrão e não executará qualquer uma das transações sintéticas não padrão. Isso significa, por exemplo, que o nó do Inspetor será configurado para executar o teste Test-CsAddressBookService, mas não será configurado para executar o teste Test-CsExumConnectivity.
    
- **Não padrão** Testes que os nós do inspetor não são executados por padrão. (Para obter detalhes, consulte a descrição do tipo padrão.) No entanto, o nó do Inspetor pode ser habilitado para executar qualquer uma das transações sintéticas não padrão. Você pode fazer isso ao criar o nó do Inspetor (usando o cmdlet New-CsWatcherNodeConfiguration) ou a qualquer momento depois que o nó do Inspetor tiver sido criado. Observe que muitas das transações sintéticas não padrão exigem etapas de configuração adicionais. Para obter mais detalhes sobre essas etapas, consulte [instruções de configuração especial para transações sintéticas](test-users-and-settings.md#special_synthetictrans).
    
- **Estendido** Um tipo especial de transação sintética não padrão. Diferentemente das outras transações sintéticas, os testes estendidos podem ser executados várias vezes durante cada fase. Isso é útil ao verificar o comportamento, como várias rotas de voz de rede telefônica pública comutada (PSTN) para um pool. Você pode configurar isso simplesmente adicionando várias instâncias de um teste estendido a um nó do Inspetor.
    
Para obter detalhes sobre o processo de adição de outras transações sintéticas a um nó do Inspetor, consulte [configurar um nó do inspetor para executar transações sintéticas](watcher-nodes.md#enable_synthetic_trans). Você também pode usar o Shell de gerenciamento do Skype for Business Server para remover as transações sintéticas de um nó do Inspetor.
  
As transações sintéticas disponíveis para os nós do inspetor incluem as seguintes:
  
|**Nome do cmdlet (nome do teste)**|**Descrição**|
|:-----|:-----|
|Test-CsAddressBookService (ABS)  <br/> |Confirma se os usuários podem pesquisar usuários que não estão em sua lista de contatos.  <br/> |
|Test-CsAddressBookWebQuery (ABWQ)  <br/> |Confirma se os usuários podem pesquisar usuários que não estão em sua lista de contatos via HTTP.  <br/> |
|Test-CsAVConference (AvConference)  <br/> |Confirma se os usuários podem criar e participar de uma conferência de áudio/vídeo.  <br/> |
|Test-CsGroupIM (conferência de mensagens instantâneas)  <br/> |Confirma se os usuários podem enviar mensagens instantâneas em conferências e participar de conversas de mensagem instantânea com três ou mais pessoas.  <br/> |
|Test-CsIM (mensagens instantâneas P2P)  <br/> |Confirma se os usuários podem enviar mensagens instantâneas ponto a ponto.  <br/> |
|Test-CsP2PAV (P2PAV)  <br/> |Confirma se os usuários podem realizar chamadas de áudio ponto a ponto (apenas sinalização).  <br/> |
|Test-CsPresence (Presence)  <br/> |Confirma se os usuários podem exibir a presença de outros usuários.  <br/> |
|Test-CsRegistration (Registration)  <br/> |Confirma se os usuários podem entrar no Skype for Business.  <br/> |
|Test-CsPstnPeerToPeerCall (PSTN)  <br/> |Confirma se os usuários podem realizar e receber chamadas de pessoas de fora da organização (números PSTN).  <br/> |
|Test-CsASConference (asconferência)  <br/> |Confirma se os usuários podem criar e participar de uma conferência de compartilhamento de aplicativos.  <br/> |
|Test-CsAVEdgeConnectivity (AVEdgeConnectivity)  <br/> |Confirma se os servidores de borda de vídeo de áudio podem aceitar conexões para chamadas ponto a ponto e chamadas de conferência.  <br/> |
|Test-CsDataConference (dataconferência)  <br/> |Confirma se os usuários podem participar de uma conferência de colaboração de dados (uma reunião online que inclui atividades como quadros de comunicações e sondas).  <br/> |
|Test-CsDialinConferencing (DialinConferencing)  <br/> |Confirma se os usuários podem discar números de telefone para participar de conferências.  <br/> |
|Test-CsDialinConferencing (DialinConferencing)  <br/> |Confirma se os usuários podem discar números de telefone para participar de conferências.  <br/> |
|Test-CsExumConnectivity (exumconnectivity)  <br/> |Confirma se um usuário pode se conectar à UM (Unificação de mensagens) do Exchange.  <br/> |
|Test-CsGroupIM-TestJoinLauncher (JoinLauncher)  <br/> |Confirma se os usuários podem criar e ingressar em reuniões agendadas (por meio de um link de endereço da Web).  <br/> |
|Test-CsMCXP2PIM (MCXP2PIM)  <br/> |Confirma se usuários de dispositivos móveis podem registrar-se e enviar mensagens instantâneas.  <br/> |
|Test-CsP2PVideoInteropServerSipTrunkAV (P2PVideoInteropServerSipTrunkAV)  <br/> |Confirma se o servidor de interoperabilidade de vídeo está ativo e pode lidar com conexões de entrada através de um tronco SIP de vídeo.  <br/> **Observação:** O suporte do MCX para clientes móveis herdados não está mais disponível no Skype for Business Server 2019. |
|Test-CsPersistentChatMessage (PersistentChatMessage)  <br/> |Confirma se os usuários podem trocar mensagens usando o serviço de chat persistente.  <br/> |
|Test-CsUcwaConference (UcwaConference)  <br/> |Confirma se os usuários podem participar de conferências via Web.  <br/> |
|Test-CsUnifiedContactStore (UnifiedContactStore)  <br/> |Confirma se os contatos de um usuário podem ser acessados por meio do repositório unificado de contatos. O repositório unificado de contatos oferece uma maneira de que os usuários mantenham um único conjunto de contatos que podem ser acessados usando o Skype for Business Server 2015, o cliente de mensagens e colaboração do Outlook e/ou o Outlook Web Access.  <br/> |
|Test-CsXmppIM (XmppIM)  <br/> |Confirma se uma mensagem instantânea pode ser enviada através do Gateway XMPP (Extensible Messaging and Presence Protocol).  <br/> Os gateways e proxies do XMPP estão disponíveis no Skype for Business Server 2015, mas não têm mais suporte no Skype for Business Server 2019.  |

Não é necessário instalar nós do inspetor para usar o System Center Operations Manager. Se você não instalar esses nós, ainda poderá obter alertas em tempo real dos componentes do Skype for Business Server 2015 sempre que ocorrer um problema. (O pacote de gerenciamento de componente e usuário não usa nós do Inspetor.) No entanto, os nós do Inspetor serão necessários se você quiser monitorar cenários de ponta a ponta usando o pacote de gerenciamento de monitoramento ativo.
  
> [!NOTE]
> Os administradores também podem executar transações sintéticas manualmente, sem usar ou instalar o Operations Manager. Dependendo do tamanho da implantação do Skype for Business Server, as transações sintéticas podem usar uma grande quantidade de memória do computador e o tempo do processador. Por causa disso, recomendamos que você use um computador dedicado como um nó do Inspetor. Por exemplo, você não deve configurar um servidor front-end do Skype for Business Server para atuar como um nó do Inspetor. Os nós do Inspetor devem atender aos mesmos requisitos básicos de hardware que qualquer outro computador na topologia do Skype for Business Server. 
  
> [!NOTE]
> Um nó de Inspetor do Lync Server 2013 herdado não pode ser colocado no mesmo computador que um nó do Inspetor do Skype for Business Server 2015 porque os principais arquivos do sistema para o Lync Server 2013 e o Skype for Business Server 2015 não podem ser instalados no mesmo computador. No entanto, os nós do Inspetor do Skype for Business Server 2015 podem monitorar simultaneamente o Skype for Business Server 2015 e o Lync Server 2013. As transações sintéticas padrão têm suporte para as duas versões do produto. 
  
Os nós do Inspetor do Lync Server 2013 podem ser implantados dentro ou fora de uma empresa para ajudar a verificar:
  
- A conectividade com pools para usuários internos da empresa.
    
- Conectividade através de redes de perímetro para usuários remotos que trabalham fora da empresa.
    
- A conectividade com dispositivos de filiais.
    
- Conectividade com o Lync Server 2013 dentro da empresa e através de redes de perímetro.
    
Para ajudar a simplificar a administração, as diferentes opções de autenticação estão disponíveis para dentro e fora da empresa. Para obter detalhes, consulte [configurar um nó do inspetor para executar transações sintéticas](watcher-nodes.md#enable_synthetic_trans).
  
Para configurar um computador para atuar como um nó do Inspetor, você deve primeiro concluir os seguintes pré-requisitos: 
  
- Instale o System Center Operations Manager e importe os pacotes de gerenciamento do Skype for Business Server 2015. Você também deve primeiro verificar se o computador do nó do Inspetor atende a todos os pré-requisitos para instalar o Skype for Business Server 2015.
    
- Instale os seguintes itens no computador do nó do inspetor:
    
  - A versão completa do .NET Framework 4,5
    
  - Windows Identity Foundation
    
  - Windows PowerShell 3.0
    
Depois que os pré-requisitos forem atendidos, você poderá configurar o nó do Inspetor seguindo estas etapas:
  
1. Instale os arquivos principais do Skype for Business Server 2015 no computador do nó do Inspetor.
    
2. Instale o agente do System Center Operations Manager no computador do nó do Inspetor.
    
3. Execute o arquivo executável Watchernode.msi.
    
4. Use o cmdlet **New-CsWatcherNodeConfiguration** para configurar as contas de usuário de teste para serem empregadas pelo nó do Inspetor.
    
## <a name="install-the-skype-for-business-server-2015-core-files-and-the-rtclocal-database"></a>Instalar os arquivos principais do Skype for Business Server 2015 e o banco de dados RTCLocal

Para instalar os arquivos principais do Skype for Business Server 2015 em um computador, conclua o procedimento a seguir. O banco de dados do RTCLocal será instalado automaticamente quando você instalar os arquivos principais. Observe que não é necessário instalar o SQL Server nos nós do Inspetor. O SQL Server Express será instalado automaticamente.
  
Para instalar os arquivos principais do Skype for Business Server 2015 e o banco de dados RTCLocal:
  
1. No computador de nó do inspetor, clique em Iniciar, em Todos os Programas, em Acessórios, clique com o botão direito do mouse em Prompt de Comando e clique em Executar como administrador.
    
2. Na janela do console, digite o seguinte comando e pressione ENTER. Certifique-se de inserir o caminho apropriado para seus arquivos de instalação do Skype for Business Server: D:\Setup.exe/BootstrapLocalMgmtTo verificar se os principais componentes do Skype for Business Server foram instalados com êxito, clique em **Iniciar**, em **todos os programas**, em **Skype for Business Server 2015**e em **Shell de gerenciamento do Skype for Business Server**. No Shell de gerenciamento do Skype for Business Server, digite o seguinte comando do Windows PowerShell e pressione ENTER:
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

> [!NOTE]
> Na primeira vez que você executar este comando, nenhum dado será retornado porque você ainda não configurou nenhum computador do nó do observador. Se o comando for executado sem retornar um erro, você poderá supor que a instalação do Skype for Business Server foi concluída com êxito. 
  
Se seu computador do nó do observador estiver localizado dentro de sua rede de perímetro, você poderá executar o comando a seguir para verificar a instalação do Skype for Business Server 2015:
  
O Get-CsPinPolicyYou receberá informações semelhantes a estas, dependendo do número de políticas de PIN configuradas para uso na organização:
  
Identity: global
  
Descrição
  
MinPasswordLength: 5
  
PINHistoryCount: 0
  
AllowCommonPatterns: falso
  
PINLifetime: 0
  
MaximumLogonAttempts :
  
Se você vir informações sobre suas políticas de PIN, os componentes principais foram instalados com êxito.
  
## <a name="install-the-operation-manager-agent-files-on-a-watcher-node"></a>Instalar os arquivos do agente do Operation Manager em um nó do Inspetor

Semelhante à configuração do Skype for Business Server para relatar alertas de componente, um nó do Inspetor do Skype for Business Server 2015 requer a instalação dos arquivos de agente do System Center Operations Manager. Isso permite que as transações sintéticas sejam executadas e que os alertas sejam relatados para o servidor de gerenciamento raiz do System Center Operations Manager.
  
Para instalar os arquivos de agente, siga os procedimentos listados em [Configure the Skype for Business Server Computers que serão monitorados](configure-computers-to-monitor.md).
  
## <a name="configure-a-watcher-node-to-run-synthetic-transactions"></a>Configurar um nó do inspetor para executar transações sintéticas
<a name="enable_synthetic_trans"> </a>

Depois que os arquivos do agente do Operations Manager System Center tiverem sido instalados, você deve configurar o próprio nó do Inspetor. As etapas que você seguir para fazer isso irão variar, dependendo do seu computador do nó do Inspetor estar dentro da sua rede de perímetro ou fora da rede de perímetro. 
  
Ao configurar um nó do observador, você também deve escolher o tipo de método de autenticação a ser implantado neste nó. O Skype for Business Server 2015 permite que você escolha um dos dois métodos de autenticação: servidor confiável ou autenticação de credencial. A tabela a seguir mostra as diferenças entre esses dois métodos:
  
||**Descrição**|**Locais com suporte**|
|:-----|:-----|:-----|
|TrustedServer  <br/> |Usa uma certificação para personificar um servidor interno e desafios de autenticação de bypass.  <br/> Útil para administradores que preferem gerenciar um único certificado, em vez de muitas senhas de usuário em cada nó do Inspetor.  <br/> |Dentro da empresa.  <br/> Com esse método, o nó do Inspetor deve estar no mesmo domínio que os pools sendo monitorados. Se o nó do Inspetor e os pools estiverem em domínios diferentes, use a autenticação de credencial.  <br/> |
|Negocia  <br/> |Armazena os nomes de usuário e senhas com segurança no Gerenciador de Credencial do Windows no nó do observador.  <br/> Este modo requer mais gerenciamento de senha, mas é a única opção para nós de Inspetor fora da empresa. Estes nós do observador não podem ser tratados como um ponto de extremidade confiável para autenticação.  <br/> |Fora da empresa.  <br/> Dentro da empresa.  <br/> |
   
## <a name="configure-a-watcher-node-to-use-trusted-server-authentication"></a>Configurar um nó do inspetor para usar autenticação de servidor confiável
<a name="enable_synthetic_trans"> </a>

Se o seu computador do nó do observador estiver dentro da rede de perímetro, usar a autenticação de servidor confiável poderá reduzir significativamente as tarefas de administração, mantendo um único certificado, em vez de usar várias senhas de conta de usuário.
  
Para configurar a autenticação de servidor confiável, você deve primeiro criar um pool de aplicativos confiáveis para hospedar o computador do nó do Inspetor. Depois de criar o pool de aplicativos confiáveis, você deve configurar transações sintéticas no nó do inspetor para executar como aplicativos confiáveis.
  
> [!NOTE]
> Um aplicativo confiável é um aplicativo que recebe status confiável para ser executado como parte do Skype for Business Server 2015, mas não é uma parte interna do produto. O status de confiável significa que o aplicativo não será desafiado para autenticação toda vez que executar.
  
Para criar um pool de aplicativos confiáveis, abra o Shell de gerenciamento do Skype for Business Server e execute um comando semelhante a este:
  
```PowerShell
New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond
```

> [!NOTE]
> Para obter detalhes sobre os parâmetros no comando anterior, digite o seguinte no prompt do Shell de gerenciamento do Skype for Business Server: 
  
```PowerShell
Get-Help New-CsTrustedApplicationPool -Full | more
```

Depois de criar o pool de aplicativos confiáveis, você pode configurar o computador do nó do inspetor para executar transações sintéticas como um aplicativo confiável usando o cmdlet **New-CsTrustedApplication** e um comando semelhante a este:
  
```PowerShell
New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061
```

Quando o comando for concluído e o aplicativo confiável for criado, você deverá executar o cmdlet **Enable-CsTopology** para garantir que as alterações entrem em vigor:
  
```PowerShell
Enable-CsTopology
```

A conta de computador do nó do observador requer a capacidade de consultar o CMS em algumas transações sintéticas. Para permitir essa capacidade, adicione a conta de computador do nó do Inspetor ao grupo de segurança RTCUniversalReadOnlyAdmins. Depois que a replicação do AD ocorrer, reinicie o computador.
  
Para verificar se o novo aplicativo confiável foi criado, digite o seguinte no prompt do Shell de gerenciamento do Skype for Business Server:
  
```PowerShell
Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"
```

## <a name="configure-a-default-certificate-on-the-watcher-node"></a>Configurar um certificado padrão no nó do Inspetor
<a name="enable_synthetic_trans"> </a>

Cada nó do inspetor que usa a autenticação TrustedServer deve ter um certificado padrão atribuído usando o assistente de implantação do Skype for Business Server. 
  
Para atribuir um certificado padrão:
  
1. Clique em Iniciar, em todos os programas, em Skype for Business Server 2015 e em assistente de implantação do Skype for Business Server. 
    
2. No assistente de implantação do Skype for Business Server, clique em instalar ou atualizar o sistema do Skype for Business Server e clique em executar sob a solicitação de título, instalar ou atribuir certificado. 
    
> [!NOTE]
> Caso o botão Executar esteja inativo, talvez você precise clicar primeiro em Executar, sob Instalar Repositório de Configuração Local. 
  
Siga um destes procedimentos:
  
- Se você já tiver um certificado que possa ser usado como o certificado padrão, clique em padrão no assistente de certificado e clique em atribuir. Siga as etapas no assistente de Atribuição de Certificado para atribuí-lo.
    
- Se você precisar solicitar um certificado para usar o certificado padrão, clique em solicitar e siga as etapas no Assistente para solicitação de certificados para solicitar esse certificado. Se você utilizar valores padrão para o certificado de Servidor da Web, você terá um certificado que pode ser atribuído como certificado padrão.
    
## <a name="install-and-configure-a-watcher-node"></a>Instalar e configurar um nó do Inspetor
<a name="enable_synthetic_trans"> </a>

Depois de reiniciar o computador do nó do Inspetor e configurar um certificado, você deve executar o arquivo Watchernode.msi. (Você deve executar Watchernode.msi em qualquer computador onde os arquivos do agente do Operations Manager e os componentes principais do Skype for Business Server 2015 estejam instalados.) 
  
Para instalar e configurar um nó do inspetor:
  
1. Abra o Shell de gerenciamento do Skype for Business Server clicando em Iniciar, em todos os programas, em Skype for Business Server 2015 e, em seguida, em Shell de gerenciamento do Skype for Business Server. 
    
2. No Shell de gerenciamento, digite o seguinte comando e pressione ENTER (tenha certeza e especifique o caminho real para a sua cópia do Watchernode.msi):
    
```PowerShell
C:\Tools\Watchernode.msi Authentication=TrustedServer
```

> [!NOTE]
> Você também pode executar Watchernode.msi n de uma janela de comando. Para abrir uma janela de comando, clique em Iniciar, clique com o botão direito do mouse em Prompt de Comando e clique em Executar como administrador. Quando a janela de comando abrir, digite o mesmo comando mostrado na etapa 2, acima. 
  
> [!IMPORTANT]
> No comando anterior, a autenticação do par nome/valor = TrustedServer diferencia maiúsculas de minúsculas. Ele deve ser digitado exatamente como mostrado. Por exemplo, esse comando falhará porque não usa a letra de maiúscula correta: 
  
```PowerShell
C:\Tools\Watchernode.msi authentication=trustedserver
```

O modo TrustedServer pode ser usado apenas com computadores que estejam dentro da rede de perímetro. Quando um nó do Inspetor é executado no modo TrustedServer, os administradores não precisam manter as senhas do usuário de teste no computador.
  
## <a name="configure-a-watcher-node-to-use-negotiate"></a>Configurar um nó do inspetor para usar Negotiate
<a name="enable_synthetic_trans"> </a>

Se o computador do nó do observador estiver fora da rede de perímetro, você deverá seguir um procedimento levemente diferente para configurar esse nó do inspetor para executar as transações sintéticas: em particular, você não deve criar um pool de aplicativos confiável ou um aplicativo confiável. Isso significa que você precisará concluir as próximas duas tarefas.
  
### <a name="update-membership-in-the-rtc-local-read-only-administrators-group"></a>Atualizar a associação no grupo de administradores locais somente leitura RTC

Se o nó do Inspetor estiver fora da rede de perímetro, você deve adicionar a conta de serviço de rede ao grupo de administradores locais somente leitura RTC no computador do nó do Inspetor, concluindo o seguinte procedimento no nó do inspetor:
  
1. Clique em Iniciar, clique com o botão direito do mouse em Computador e clique em Gerenciar.
    
2. No Gerenciador de Servidores, expanda Configuração, Usuários e Grupos Locais e clique em Grupos.
    
3. No painel Grupos, clique duas vezes em Administradores locais somente leitura RTC.
    
4. Na caixa  de diálogo Propriedades de Administradores Locais Somente Leitura RTC, clique em Adicionar.
    
5. Na caixa de diálogo Selecionar Usuários, Computadores, Contas de Serviço ou Grupos, clique em Locais
    
6. Na caixa de diálogo Locais, selecione o nome do computador no nó de inspetor e clique em OK.
    
7. Na caixa Digite os nomes de objeto a serem selecionados, digite Serviço de Rede e clique em OK.
    
8. Na caixa  de diálogo Propriedades de Administradores Locais Somente Leitura RTC, clique em OK e feche o Gerenciador de Servidor.
    
9. Reinicie o computador no nó do inspetor.
    
### <a name="install-the-watcher-node-configuration-files"></a>Instalar os arquivos de configuração do nó do Inspetor

A próxima etapa é executar o arquivo Watchernode.msi: 
  
1. Abra o Shell de gerenciamento do Microsoft Skype for Business Server 2015. Clique em Iniciar, em todos os programas, em Microsoft Skype for Business Server 2015 e, em seguida, clique em Shell de gerenciamento do Skype for Business Server. 
    
2. No Shell de gerenciamento do Skype for Business Server, digite o seguinte comando e pressione ENTER (Lembre-se de especificar o caminho real para a sua cópia do Watchernode.msi):
    
   ```PowerShell
   c:\Tools\Watchernode.msi Authentication=Negotiate
   ```

> [!NOTE]
> Como mencionado anteriormente, Watchernode.msi também pode ser executado a partir de uma janela de comando. Para abrir uma janela de comando, clique em **Iniciar**, clique com o botão direito do mouse em **Prompt de Comando** e clique em **Executar como administrador**. Quando a janela de comando abrir, digite o mesmo comando mostrado na etapa 2, acima. 
  
O modo Negociar é usado sempre que o nó de inspetor não podem ser configurado como um pool de aplicativos confiável. Nesse modo, os administradores precisarão gerenciar as senhas do usuário de teste no nó de inspetor.
  

