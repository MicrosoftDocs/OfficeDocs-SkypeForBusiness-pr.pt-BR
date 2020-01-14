---
title: Instalar e configurar nós do inspetor
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7392e4f8-6e2d-447b-aaa3-878f73995f9d
description: 'Resumo: instalar e configurar nós do inspetor para transações sintéticas do Skype for Business Server.'
ms.openlocfilehash: 8c7ea0465d9a53bd8972c823ef7bfc7d7ee9b4bc
ms.sourcegitcommit: 208179a3dd166f53b5a3058242cb84207909f4ee
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2020
ms.locfileid: "41104480"
---
# <a name="install-and-configure-watcher-nodes"></a>Instalar e configurar nós do inspetor
 
**Resumo:** Instalar e configurar nós do inspetor para transações sintéticas do Skype for Business Server.
  
Nós de Inspetor são computadores que executam periodicamente transações sintéticas do Skype for Business Server. As transações sintéticas são cmdlets do Windows PowerShell que verificam se recursos básicos do usuário, como a capacidade de entrar no ou trocar mensagens instantâneas, estão funcionando conforme esperado. Para o Skype for Business Server 2015, o System Center Operations Manager pode executar as transações sintéticas mostradas na tabela a seguir, que inclui três tipos de transação sintética:
  
- **Padrão** Transações sintéticas que um nó do Inspetor executa por padrão. Ao criar um novo nó Inspetor, você pode especificar quais transações sintéticas o nó executará. (Essa é a finalidade do parâmetro testes usado pelo cmdlet New-CsWatcherNodeConfiguration.) Se você não usar o parâmetro tests quando o nó do Inspetor for criado, ele executará automaticamente todas as transações sintéticas padrão e não executará qualquer uma das transações sintéticas não padrão. Isso significa, por exemplo, que o nó do Inspetor será configurado para executar o teste Test-CsAddressBookService, mas não será configurado para executar o teste Test-CsExumConnectivity.
    
- **Não padrão** Testa se os nós do inspetor não são executados por padrão. (Para obter detalhes, consulte a descrição do tipo padrão.) No entanto, o nó do Inspetor pode ser habilitado para executar qualquer uma das transações sintéticas não padrão. Você pode fazer isso quando cria o nó do Inspetor (usando o cmdlet New-CsWatcherNodeConfiguration) ou a qualquer momento após a criação do nó do Inspetor. Observe que muitas das transações sintéticas não padrão exigem etapas adicionais de configuração. Para obter mais detalhes sobre essas etapas, consulte [instruções de configuração especial para transações sintéticas](test-users-and-settings.md#special_synthetictrans).
    
- **Maior** Um tipo especial de transação sintética não padrão. Diferentemente das outras transações sintéticas, os testes estendidos podem ser executados várias vezes durante cada fase. Isso pode ser útil, por exemplo, para verificações de várias rotas de voz de PSTN (rede telefônica pública comutada) de um pool. Isso pode ser configurado com a simples adição de várias instâncias de um teste estendido a um nó do inspetor.
    
Para obter detalhes sobre o processo de adição de outras transações sintéticas a um nó do inspetor, consulte [Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans). Você também pode usar o Shell de gerenciamento do Skype for Business Server para remover transações sintéticas de um nó do Inspetor.
  
As transações sintéticas disponíveis para os nós do inspetor incluem as seguintes:
  
|**Nome do cmdlet (nome do teste)**|**Descrição**|
|:-----|:-----|
|Test-CsAddressBookService (ABS)  <br/> |Confirma que os usuários podem procurar usuários que não estão na lista de contatos deles.  <br/> |
|Test-CsAddressBookWebQuery (ABWQ)  <br/> |Confirma que os usuários podem procurar usuários que não estão na lista de contatos via HTTP.  <br/> |
|Test-CsAVConference (AvConference)  <br/> |Confirma se os usuários podem criar e participar de uma conferência de áudio/vídeo.  <br/> |
|Test-Cs GroupIM (Conferência de IM)  <br/> |Confirma se os usuários podem enviar mensagens instantâneas em conferências e participar de conversas de mensagem instantânea com três ou mais pessoas.  <br/> |
|Test-CsIM (P2P IM)  <br/> |Confirma se os usuários podem enviar mensagens instantâneas ponto a ponto.  <br/> |
|Test-CsP2PAV (P2PAV)  <br/> |Confirma se os usuários podem realizar chamadas de áudio ponto a ponto (apenas sinalização).  <br/> |
|Test-CsPresence (Presence)  <br/> |Confirma que os usuários podem ver a presença de outros usuários.  <br/> |
|Test-CsRegistration (Registration)  <br/> |Confirma se os usuários podem entrar no Skype for Business.  <br/> |
|Test-CsPstnPeerToPeerCall (PSTN)  <br/> |Confirma se os usuários podem realizar e receber chamadas de pessoas de fora da organização (números PSTN).  <br/> |
|Test-CsASConference (ASConference)  <br/> |Confirma se os usuários podem criar e participar de uma conferência de compartilhamento de aplicativos.  <br/> |
|Test-CsAVEdgeConnectivity (AVEdgeConnectivity)  <br/> |Confirma se os servidores de borda A/V podem aceitar conexões para chamadas ponto a ponto e chamadas em conferência.  <br/> |
|Test-CsDataConference (DataConference)  <br/> |Confirma se os usuários podem participar de uma conferência com colaboração de dados, uma reunião online que inclui atividades como quadros de comunicações e votações.  <br/> |
|Test-CsDialinConferencing (DialinConferencing)  <br/> |Confirma se os usuários podem discar os números de telefone para participar de conferências.  <br/> |
|Test-CsDialinConferencing (DialinConferencing)  <br/> |Confirma se os usuários podem discar os números de telefone para participar de conferências.  <br/> |
|Test-CsExumConnectivity (ExumConnectivity)  <br/> |Confirma se um usuário pode se conectar à uma mensagem unificada do Exchange (UM).  <br/> |
|Test-CsGroupIM-TestJoinLauncher (JoinLauncher)  <br/> |Confirma se os usuários podem criar reuniões agendadas e ingressar nelas através de um link de endereço Web.  <br/> |
|Test-CsMCXP2PIM (MCXP2PIM)  <br/> |Confirma se usuários de dispositivos móveis podem registrar-se e enviar mensagens instantâneas.  <br/> |
|Test-CsP2PVideoInteropServerSipTrunkAV (P2PVideoInteropServerSipTrunkAV)  <br/> |Confirma que o servidor de interoperabilidade de vídeo está ativo e pode manipular conexões de entrada por meio de um tronco de vídeo SIP.  <br/> **Observação:** O suporte do MCX para clientes móveis herdados não está mais disponível no Skype for Business Server 2019. |
|Test-CsPersistentChatMessage (PersistentChatMessage)  <br/> |Confirma se os usuários podem trocar mensagens usando o serviço de chat persistente.  <br/> |
|Test-CsUcwaConference (UcwaConference)  <br/> |Confirma se os usuários podem participar de conferências via Web.  <br/> |
|Test-CsUnifiedContactStore (UnifiedContactStore)  <br/> |Confirma se os contatos de um usuário podem ser acessados por meio do repositório unificado de contatos. O repositório de contatos unificado fornece uma maneira para que os usuários mantenham um único conjunto de contatos que podem ser acessados usando o Skype for Business Server 2015, o cliente de colaboração e email do Outlook e/ou o Outlook Web Access.  <br/> |
|Test-CsXmppIM (XmppIM)  <br/> |Confirma se uma mensagem instantânea pode ser enviada através do gateway XMPP.  <br/> Os gateways e proxies XMPP estão disponíveis no Skype for Business Server 2015, mas não têm mais suporte no Skype for Business Server 2019.  |

Você não precisa instalar nós de inspetor para usar o System Center Operations Manager. Se você não instalar esses nós, ainda poderá obter alertas em tempo real dos componentes do Skype for Business Server 2015 sempre que ocorrer um problema. (O componente e o pacote de gerenciamento do usuário não usam nós do Inspetor.) No entanto, nós de Inspetor são necessários se você deseja monitorar cenários de ponta a ponta usando o pacote de gerenciamento de monitoramento ativo.
  
> [!NOTE]
> Os administradores também podem executar transações sintéticas manualmente, sem utilizar ou instalar o Operations Manager. Dependendo do tamanho da implantação do Skype for Business Server, as transações sintéticas podem usar uma grande quantidade de memória do computador e tempo do processador. Por esse motivo, é recomendável usar um computador dedicado como nó do inspetor. Por exemplo, você não deve configurar um servidor front-end do Skype for Business Server para atuar como um nó do Inspetor. Os nós de Inspetor devem atender aos mesmos requisitos básicos de hardware que qualquer outro computador na topologia do Skype for Business Server. 
  
> [!NOTE]
> Um nó de Inspetor do Lync Server 2013 herdado não pode ser posicionado na mesma máquina que um nó do Inspetor do Skype for Business Server 2015 porque os principais arquivos do sistema do Lync Server 2013 e do Skype for Business Server 2015 não podem ser instalados no mesmo computador. No entanto, os nós do Inspetor do Skype for Business Server 2015 podem monitorar simultaneamente o Skype for Business Server 2015 e o Lync Server 2013. Transações sintéticas padrão são suportadas para as duas versões do produto. 
  
Os nós do Inspetor do Lync Server 2013 podem ser implantados dentro ou fora de uma empresa para ajudar a verificar:
  
- A conectividade com pools para usuários internos da empresa.
    
- A conectividade através de redes de perímetro para usuários remotos que trabalham fora da empresa.
    
- A conectividade com dispositivos de filiais.
    
- Conectividade com o Lync Server 2013 dentro da empresa e através de redes de perímetro.
    
Para simplificar a administração, diferentes opções de autenticação estão disponíveis para dentro e fora da empresa. Para obter detalhes, consulte [Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans).
  
Para configurar um computador para atuar como um nó do inspetor, você deve primeiro satisfazer os seguintes pré-requisitos: 
  
- Instale o System Center Operations Manager e importe os pacotes de gerenciamento do Skype for Business Server 2015. Você também deve primeiro verificar se o computador do nó do Inspetor atende a todos os pré-requisitos para instalar o Skype for Business Server 2015.
    
- Instale os seguintes itens no computador do nó do inspetor:
    
  - A versão completa do .NET Framework 4,5
    
  - Windows Identity Foundation
    
  - Windows PowerShell 3.0
    
Depois que os pré-requisitos forem atendidos, você poderá configurar o nó do inspetor seguindo estas etapas:
  
1. Instale os arquivos principais do Skype for Business Server 2015 no computador do nó inspetor.
    
2. Instale o agente do System Center Operations Manager no computador do nó inspetor.
    
3. Execute o arquivo executável Watchernode.msi.
    
4. Use os cmdlets **CsWatcherNodeConfiguration** para configurar as contas de usuário de teste a serem empregadas pelo nó do inspetor.
    
## <a name="install-the-skype-for-business-server-2015-core-files-and-the-rtclocal-database"></a>Instalar os Arquivos de Núcleo de Skype for Business Server 2015 e o Banco de Dados RTCLocal

Para instalar os arquivos principais do Skype for Business Server 2015 em um computador, conclua o procedimento a seguir. O banco de dados RTCLocal é instalado automaticamente ao instalar os principais arquivos. Observe que você não precisa instalar o SQL Server nos nós do Inspetor. O SQL Server Express será instalado automaticamente.
  
Para instalar os arquivos principais do Skype for Business Server 2015 e o banco de dados do RTCLocal:
  
1. No computador de nó do inspetor, clique em Iniciar, em Todos os Programas, em Acessórios, clique com o botão direito do mouse em Prompt de Comando e clique em Executar como administrador.
    
2. Na janela de console, digite o seguinte comando e pressione ENTER. Certifique-se de digitar o caminho apropriado para os arquivos de instalação do Skype for Business Server: D:\Setup.exe/BootstrapLocalMgmtTo Verifique se os principais componentes do Skype for Business Server foram instalados com êxito, clique em **Iniciar**, clique em **todos os programas**, clique em **Skype for Business Server 2015**e, em seguida, clique em **Shell de gerenciamento do Skype for Business Server**. No Shell de gerenciamento do Skype for Business Server, digite o seguinte comando do Windows PowerShell e pressione ENTER:
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

> [!NOTE]
> Na primeira vez que você executa este comando, nenhum dado é retornado porque você ainda não configurou qualquer computador do nó do observador. Se o comando for executado sem retornar um erro, você pode presumir que a instalação do Skype for Business Server foi concluída com êxito. 
  
Se seu computador do nó do observador estiver localizada dentro da sua rede de perímetro, é possível executar o seguinte comando para verificar a instalação do Skype for Business Server 2015:
  
Get-CsPinPolicyYou receberá informações semelhantes a isso, dependendo do número de políticas de PIN configuradas para uso em sua organização:
  
Identidade: global
  
Descritivo
  
MinPasswordLength: 5
  
PINHistoryCount: 0
  
AllowCommonPatterns: false
  
PINLifetime: 0
  
MaximumLogonAttempts :
  
Se você vir informações sobre suas políticas de PIN, os principais componentes foram instalados com sucesso.
  
## <a name="install-the-operation-manager-agent-files-on-a-watcher-node"></a>Instalar os arquivos do agente do Operation Manager em um nó inspetor

Da mesma forma que a configuração do Skype for Business Server para relatar alertas de componente, um nó do Inspetor do Skype for Business Server 2015 requer a instalação dos arquivos do agente do System Center Operations Manager. Isso permite que as transações sintéticas sejam executadas e alertas sejam relatados para o servidor de gerenciamento raiz do System Center Operations Manager.
  
Para instalar os arquivos do agente, siga os procedimentos listados em [configurar os computadores do Skype for Business Server que serão monitorados](configure-computers-to-monitor.md).
  
## <a name="configure-a-watcher-node-to-run-synthetic-transactions"></a>Configurar um nó inspetor para executar transações sintéticas
<a name="enable_synthetic_trans"> </a>

Após a instalação dos arquivos do agente do System Center Operations Manager, você deve configurar o próprio nó do Inspetor. As etapas realizadas para isso variam dependendo se seu computador do nó do observador está dentro da sua rede de perímetro ou fora. 
  
Ao configurar um nó do observador, você também deve escolher o tipo de método de autenticação a ser implantado neste nó. O Skype for Business Server 2015 permite que você escolha um dos dois métodos de autenticação: servidor confiável ou autenticação de credenciais. As diferenças entre estes dois métodos são destacadas na tabela a seguir:
  
||**Descrição**|**Locais suportados**|
|:-----|:-----|:-----|
|TrustedServer  <br/> |Usa uma certificação para personificar um servidor interno e desafios de autenticação de bypass.  <br/> Útil para os administradores que preferem gerenciar um único certificado ao invés de várias senhas do usuário no nó do observador.  <br/> |Dentro da empresa.  <br/> Com este método, o nó do observador deve estar no mesmo domínio que os pools sendo monitorados. Se o nó do observador e os pools estão em domínios diferentes, use a Autenticação de Credencial.  <br/> |
|Negotiate  <br/> |Armazena os nomes de usuário e senhas com segurança no Gerenciador de Credencial do Windows no nó do observador.  <br/> Este modo exige mais gerenciamento de senha, mas é a única opção para nós do observador fora da empresa. Estes nós do observador não podem ser tratados como um ponto de extremidade confiável para autenticação.  <br/> |Fora da empresa.  <br/> Dentro da empresa.  <br/> |
   
## <a name="configure-a-watcher-node-to-use-trusted-server-authentication"></a>Configurar um nó inspetor para usar a autenticação de servidor confiável
<a name="enable_synthetic_trans"> </a>

Caso seu computador de nó do inspetor esteja dentro da rede de perímetro, utilizar uma autenticação de Servidor Confiável pode reduzir drasticamente as taxas de administração para manter um único certificado em vez de diversas senhas de conta de usuário.
  
Para configurar autenticação de Servidor Confiável, você deve primeiro criar um pool de aplicativo confiável para hospedar o computador de nó do inspetor. Depois de criar o pool de aplicativos confiável, você deve então configurar transações sintéticas nesse nó do inspetor para executar como aplicativos confiáveis.
  
> [!NOTE]
> Um aplicativo confiável é um aplicativo que recebe status de confiança para ser executado como parte do Skype for Business Server 2015, mas não é uma parte interna do produto. O status de confiável significa que o aplicativo não será desafiado para autenticação toda vez que executar.
  
Para criar um pool de aplicativos confiável, abra o Shell de gerenciamento do Skype for Business Server e execute um comando semelhante a este:
  
```PowerShell
New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond
```

> [!NOTE]
> Para obter detalhes sobre os parâmetros no comando anterior, digite o seguinte no prompt do Shell de gerenciamento do Skype for Business Server: 
  
```PowerShell
Get-Help New-CsTrustedApplicationPool -Full | more
```

Após criar o pool de aplicativo confiável, configure o computador de nó do inspetor para executar transações sintéticas como aplicativo confiável. Isso é feito utilizando o cmdlet **New-CsTrustedApplication** e um comando similar a este:
  
```PowerShell
New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061
```

Quando o comando estiver concluído e o aplicativo confiável for criado, você precisará executar o cmdlet **Enable-CsTopology** para certificar-se de que as alterações tenham efeito:
  
```PowerShell
Enable-CsTopology
```

A conta de computador do nó do Inspetor requer a capacidade de consultar o CMS para algumas transações sintéticas. Para permitir esse recurso, adicione a conta de computador do nó do Inspetor ao grupo de segurança RTCUniversalReadOnlyAdmins. Após a duplicação do anúncio, reinicie o computador.
  
Para verificar se o novo aplicativo confiável foi criado, digite o seguinte no prompt do Shell de gerenciamento do Skype for Business Server:
  
```PowerShell
Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"
```

## <a name="configure-a-default-certificate-on-the-watcher-node"></a>Configurar um certificado padrão no nó do inspetor
<a name="enable_synthetic_trans"> </a>

Cada nó de inspetor que usa a autenticação TrustedServer deve ter um certificado padrão atribuído usando o assistente de implantação do Skype for Business Server. 
  
Para atribuir um certificado padrão:
  
1. Clique em Iniciar, em todos os programas, em Skype for Business Server 2015 e, em seguida, clique em assistente de implantação do Skype for Business Server. 
    
2. No assistente de implantação do Skype for Business Server, clique em instalar ou atualizar o sistema do Skype for Business Server e, em seguida, clique em executar sob a solicitação de título, instalar ou atribuir certificado. 
    
> [!NOTE]
> Caso o botão Executar esteja inativo, talvez você precise clicar primeiro em Executar, em Instalar Repositório de Configuração Local. 
  
Siga um destes procedimentos:
  
- Se você já tiver um certificado que possa ser utilizado como certificado padrão, clique em Padrão no assistente de Certificado e, então, clique em Atribuir. Siga as etapas no assistente de Atribuição de Certificado para atribuí-lo.
    
- Se você precisar solicitar um certificado para utilizar o certificado padrão, clique em Solicitar e, então, siga as etapas no assistente de Solicitação de Certificado. Se você utilizar valores padrão para o certificado de Servidor da Web, você terá um certificado que pode ser atribuído como certificado padrão.
    
## <a name="install-and-configure-a-watcher-node"></a>Instalar e configurar um nó de inspetor
<a name="enable_synthetic_trans"> </a>

Depois de ter reiniciado o computador de nó do inspetor e configurado o certificado, você precisará executar o arquivo Watchernode.msi. (Você deve executar o Watchernode. msi em qualquer computador onde os arquivos de agente do Operations Manager e os componentes principais do Skype for Business Server 2015 estejam instalados.) 
  
Para instalar e configurar um nó de inspetor:
  
1. Para abrir o Shell de gerenciamento do Skype for Business Server, clique em Iniciar, em todos os programas, em Skype for Business Server 2015 e, em seguida, clique em Shell de gerenciamento do Skype for Business Server. 
    
2. No Shell de Gerenciamento, digite o seguinte comando e pressione ENTER (tenha certeza e especifique o caminho real até sua cópia de Watchernode.msi):
    
```PowerShell
C:\Tools\Watchernode.msi Authentication=TrustedServer
```

> [!NOTE]
> Você também pode executar o Watchernode.msi de uma janela de comando. Para abrir uma janela de comando, clique em Iniciar, clique com o botão direito do mouse em Prompt de comando e, então, em Executar como administrador. Quando a janela de comando abrir, digite o mesmo comando da etapa 2 anterior. 
  
> [!IMPORTANT]
> No comando anterior, o par de valor/nome Authentication=TrustedServer diferencia maiúscula de minúscula. Ele deve ser digitado exatamente como mostrado. Por exemplo, este comando falhará porque não utiliza a formatação correta: 
  
```PowerShell
C:\Tools\Watchernode.msi authentication=trustedserver
```

O modo TrustedServer pode ser usado apenas com computadores que ficam dentro da rede de perímetro. Quando um nó de inspetor é executado no modo TrustedServer, os administradores não precisam manter senhas de usuário de teste no computador.
  
## <a name="configure-a-watcher-node-to-use-negotiate"></a>Configurar um nó do inspetor para usar Negociar
<a name="enable_synthetic_trans"> </a>

Se seu computador no nó do inspetor estiver fora da rede de perímetro, será necessário seguir um procedimento um pouco diferente para configurar o nó do inspetor a fim de executar transações sintéticas: especificamente, você não deve criar um pool de aplicativos confiáveis ou um aplicativo confiável. Isso significa que será necessário concluir as próximas duas tarefas.
  
### <a name="update-membership-in-the-rtc-local-read-only-administrators-group"></a>Atualizar a associação no grupo Administradores locais somente leitura RTC

Se seu nó de inspetor estiver fora da rede de perímetro, será necessário adicionar a conta Serviço de Rede ao grupo Administradores locais somente leitura RTC no computador no nó do inspetor. Para fazer isso, complete o seguinte procedimento no nó do inspetor:
  
1. Clique em Iniciar, clique com o botão direito do mouse em Computador e clique em Gerenciar.
    
2. No Gerenciador de Servidores, expanda Configuração, Usuários e Grupos Locais e clique em Grupos.
    
3. No painel Grupos, clique duas vezes em Administradores locais somente leitura RTC.
    
4. Na caixa de diálogo Propriedades de Administradores Locais Somente Leitura RTC, clique em Adicionar.
    
5. Na caixa de diálogo Selecionar Usuários, Computadores, Contas de Serviço ou Grupos, clique em Locais.
    
6. Na caixa de diálogo Locais, selecione o nome do computador no nó de inspetor e clique em OK.
    
7. Na caixa Digite os nomes de objeto a serem selecionados, digite Serviço de Rede e clique em OK.
    
8. Na caixa de diálogo Propriedades de Administradores Locais Somente Leitura RTC, clique em OK e feche o Gerenciador de Servidor.
    
9. Reinicie o computador no nó do inspetor.
    
### <a name="install-the-watcher-node-configuration-files"></a>Instalar os Arquivos de Configuração no Nó do Inspetor

Sua próxima etapa será executar o arquivo Watchernode.msi: 
  
1. Abra o Shell de Gerenciamento do Microsoft Skype for Business Server. Clique em Iniciar, em Todos os Programas, em Microsoft Skype for Business Server 2015 e em Shell de Gerenciamento do Skype for Business Server. 
    
2. No Shell de Gerenciamento do Skype for Business Server, digite o seguinte comando e pressione ENTER (tenha certeza e especifique o caminho real até sua cópia de Watchernode.msi):
    
   ```PowerShell
   c:\Tools\Watchernode.msi Authentication=Negotiate
   ```

> [!NOTE]
> Conforme indicado anteriormente, Watchernode.msi também pode ser executado a partir de uma janela de comando. Para abrir uma janela de comando, clique em **Iniciar**, clique com o botão direito do mouse em **Prompt de Comando** e clique em **Executar como administrador**. Quando a janela de comando for aberta, digite o mesmo comando exibido na etapa 2 acima. 
  
O modo Negociar é usado sempre que o nó de inspetor não podem ser configurado como um pool de aplicativos confiável. Nesse modo, os administradores precisarão gerenciar as senhas do usuário de teste no nó de inspetor.
  

