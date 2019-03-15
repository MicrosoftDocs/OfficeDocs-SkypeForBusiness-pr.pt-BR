---
title: Instalar e configurar nós do inspetor
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 11/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7392e4f8-6e2d-447b-aaa3-878f73995f9d
description: 'Resumo: Instalar e configurar nós do Inspetor do Skype para transações sintéticas do Business Server.'
ms.openlocfilehash: 6719826515954290f30eac272f638b846f45142a
ms.sourcegitcommit: 27f1ecb730355dcfac2f4be3f5642f383d5532ad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2019
ms.locfileid: "25375983"
---
# <a name="install-and-configure-watcher-nodes"></a>Instalar e configurar nós do inspetor
 
**Resumo:** Instale e configure nós do Inspetor para Skype para transações sintéticas do Business Server.
  
Nós do Inspetor são computadores que executam periodicamente Skype para transações sintéticas do Business Server. As transações sintéticas são cmdlets do Windows PowerShell que verificam se recursos básicos do usuário, como a capacidade de entrar no ou trocar mensagens instantâneas, estão funcionando conforme esperado. Para Skype para Business Server 2015, o System Center Operations Manager pode executar as transações sintéticas mostradas na tabela a seguir, que inclui três tipos de transação sintética:
  
- **Padrão** Transações sintéticas que um nó de inspetor é executado por padrão. Quando você cria um novo nó do observador, você pode especificar qual sintética transações esse nó será executado. (Essa é a finalidade do parâmetro Tests utilizada pelo cmdlet New-CsWatcherNodeConfiguration.) Se você não usar o parâmetro testes quando o nó do Inspetor é criado, ele será executado automaticamente todas as transações sintéticas de padrão e não executará qualquer uma das transações sintéticas não padrão. Isso significa, por exemplo, se o nó do Inspetor estará configurado para executar o teste de Test-CsAddressBookService, mas não estará configurado para executar o teste de Test-CsExumConnectivity.
    
- **Não padrão** Testes que nós do Inspetor não execute por padrão. (Para obter detalhes, consulte a descrição do tipo padrão.) No entanto, o nó do Inspetor pode ser habilitado para executar qualquer uma das transações sintéticas não padrão. Você pode fazer isso quando você criar o nó do Inspetor (usando o cmdlet New-CsWatcherNodeConfiguration) ou qualquer momento após o nó do Inspetor foi criado. Observe que muitas das transações sintéticas padrão não exigem etapas adicionais de configuração. Para obter detalhes sobre essas etapas, consulte as instruções de configuração especial para transações sintéticas. Para obter mais detalhes sobre essas etapas, consulte [As instruções de instalação especiais para transações sintéticas ](test-users-and-settings.md#special_synthetictrans).
    
- **Estendido** Um tipo especial de transação sintética de não-padrão. Diferentemente das outras transações sintéticas, os testes estendidos podem ser executados várias vezes durante cada fase. Isso pode ser útil, por exemplo, para verificações de várias rotas de voz de PSTN (rede telefônica pública comutada) de um pool. Isso pode ser configurado com a simples adição de várias instâncias de um teste estendido a um nó do inspetor.
    
Para obter detalhes sobre o processo de adição de outras transações sintéticas a um nó do inspetor, consulte [Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans). Você também pode usar o Skype para Business Server Management Shell para remover as transações sintéticas de um nó do Inspetor.
  
As transações sintéticas disponíveis para os nós do inspetor incluem as seguintes:
  
|**Nome do cmdlet (nome do teste)**|**Descrição**|
|:-----|:-----|
|Test-CsAddressBookService (ABS)  <br/> |Confirma se os usuários podem pesquisar outros usuários que não estão em sua lista de contatos.  <br/> |
|Test-CsAddressBookWebQuery (ABWQ)  <br/> |Confirma se os usuários podem pesquisar outros usuários que não estão em sua lista de contatos via HTTP.  <br/> |
|Test-CsAVConference (AvConference)  <br/> |Confirma se os usuários podem criar e participar de uma conferência de áudio/vídeo.  <br/> |
|Test-Cs GroupIM (Conferência de IM)  <br/> |Confirma se os usuários podem enviar mensagens instantâneas em conferências e participar de conversas de mensagem instantânea com três ou mais pessoas.  <br/> |
|Test-CsIM (P2P IM)  <br/> |Confirma se os usuários podem enviar mensagens instantâneas ponto a ponto.  <br/> |
|Test-CsP2PAV (P2PAV)  <br/> |Confirma se os usuários podem realizar chamadas de áudio ponto a ponto (apenas sinalização).  <br/> |
|Test-CsPresence (Presence)  <br/> |Confirma se os usuários podem exibir a presença de outros usuários.  <br/> |
|Test-CsRegistration (Registration)  <br/> |Confirma se os usuários podem entrar no Skype para negócios.  <br/> |
|Test-CsPstnPeerToPeerCall (PSTN)  <br/> |Confirma se os usuários podem realizar e receber chamadas de pessoas de fora da organização (números PSTN).  <br/> |
|Test-CsASConference (ASConference)  <br/> |Confirma se os usuários podem criar e participar de uma conferência de compartilhamento de aplicativos.  <br/> |
|Test-CsAVEdgeConnectivity (AVEdgeConnectivity)  <br/> |Confirma se os servidores de borda A/V podem aceitar conexões para chamadas ponto a ponto e chamadas em conferência.  <br/> |
|Test-CsDataConference (DataConference)  <br/> |Confirma se os usuários podem participar de uma conferência com colaboração de dados, uma reunião online que inclui atividades como quadros de comunicações e votações.  <br/> |
|Test-CsDialinConferencing (DialinConferencing)  <br/> |Confirma se os usuários podem discar os números de telefone para participar de conferências.  <br/> |
|Test-CsDialinConferencing (DialinConferencing)  <br/> |Confirma se os usuários podem discar os números de telefone para participar de conferências.  <br/> |
|Test-CsExumConnectivity (ExumConnectivity)  <br/> |Confirma se um usuário pode se conectar ao Exchange Unified Messaging (UM).  <br/> |
|Test-CsGroupIM - TestJoinLauncher (JoinLauncher)  <br/> |Confirma se os usuários podem criar reuniões agendadas e ingressar nelas através de um link de endereço Web.  <br/> |
|Test-CsMCXP2PIM (MCXP2PIM)  <br/> |Confirma se usuários de dispositivos móveis podem registrar-se e enviar mensagens instantâneas.  <br/> |
|Test-CsP2PVideoInteropServerSipTrunkAV (P2PVideoInteropServerSipTrunkAV)  <br/> |Confirma que o servidor de interoperabilidade de vídeo está atualizado e pode lidar com conexões de entrada em um tronco SIP de vídeo.  <br/> **Observação:** Suporte MCX para clientes móveis herdados não está mais disponível no Skype para Business Server 2019. |
|Test-CsPersistentChatMessage (PersistentChatMessage)  <br/> |Confirma se os usuários podem trocar mensagens usando o serviço de chat persistente.  <br/> |
|Test-CsUcwaConference (UcwaConference)  <br/> |Confirma se os usuários podem participar de conferências via Web.  <br/> |
|Test-CsUnifiedContactStore (UnifiedContactStore)  <br/> |Confirma se os contatos de um usuário podem ser acessados por meio do repositório unificado de contatos. O armazenamento unificado de contatos fornece uma maneira para que os usuários manter um único conjunto de contatos que podem ser acessados por meio do Skype para Business Server 2015, Outlook mensagens e cliente de colaboração e/ou Outlook Web Access.  <br/> |
|Test-CsXmppIM (XmppIM)  <br/> |Confirma se uma mensagem instantânea pode ser enviada através do gateway XMPP.  <br/> Gateways de XMPP e proxies estão disponíveis no Skype para Business Server 2015, mas não são mais suportados no Skype para Business Server 2019.  |

Você não precisará instalar nós do Inspetor para usar o System Center Operations Manager. Se você não instalar esses nós, você pode ainda obter alertas em tempo real do Skype para componentes de negócios Server 2015 sempre que ocorre um problema. (O componente e o pacote de gerenciamento do usuário não usa nós do observador.) No entanto, nós do Inspetor são necessários se você deseja monitorar cenários de ponta a ponta usando o pacote de gerenciamento de monitoramento ativo.
  
> [!NOTE]
> Os administradores também podem executar transações sintéticas manualmente, sem utilizar ou instalar o Operations Manager. Dependendo do tamanho do seu Skype para implantação de servidor de negócios, as transações sintéticas podem usar uma grande quantidade de memória e processador do computador. Por esse motivo, é recomendável usar um computador dedicado como nó do inspetor. Por exemplo, você não deve configurar um Skype para Business Server servidor Front-End agir como um nó do Inspetor. Nós do Inspetor devem atender os mesmos requisitos básicos de hardware qualquer outro computador no seu Skype para a topologia de servidor de negócios. 
  
> [!NOTE]
> Um nó de Inspetor herdado do Lync Server 2013 não pode ser colocado na mesma máquina como um Skype para nó do observador Business Server 2015 porque os arquivos de sistema principais para o Lync Server 2013 e Skype para Business Server 2015 não podem ser instalados no mesmo computador. No entanto, Skype para nós do observador Business Server 2015 pode monitorar simultaneamente Skype para Business Server 2015 e Lync Server 2013. Transações sintéticas padrão são suportadas para as duas versões do produto. 
  
Nós do Inspetor de Lync Server 2013 podem ser implantados dentro ou fora de uma empresa para ajudar a verificar:
  
- A conectividade com pools para usuários internos da empresa.
    
- A conectividade através de redes de perímetro para usuários remotos que trabalham fora da empresa.
    
- A conectividade com dispositivos de filiais.
    
- Conectividade com o Lync Server 2013 dentro da empresa e através de redes de perímetro.
    
Para simplificar a administração, diferentes opções de autenticação estão disponíveis para dentro e fora da empresa. Para obter detalhes, consulte [Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans).
  
Para configurar um computador para atuar como um nó do inspetor, você deve primeiro satisfazer os seguintes pré-requisitos: 
  
- Instale o System Center Operations Manager e importar o Skype para pacotes de gerenciamento de negócios Server 2015. Você deve também verificar que o computador do nó do observador atenda todos os pré-requisitos para instalar o Skype for Business Server 2015.
    
- Instale os seguintes itens no computador do nó do inspetor:
    
  - A versão completa do .NET Framework 4.5
    
  - Windows Identity Foundation
    
  - Windows PowerShell 3.0
    
Depois que os pré-requisitos forem atendidos, você poderá configurar o nó do inspetor seguindo estas etapas:
  
1. Instale o Skype para Business Server 2015 principais arquivos no computador do nó do Inspetor.
    
2. Instale o agente do System Center Operations Manager no computador de nó do Inspetor.
    
3. Execute o arquivo executável Watchernode.msi.
    
4. Use os cmdlets **CsWatcherNodeConfiguration** para configurar as contas de usuário de teste a serem empregadas pelo nó do inspetor.
    
## <a name="install-the-skype-for-business-server-2015-core-files-and-the-rtclocal-database"></a>Instalar os Arquivos de Núcleo de Skype for Business Server 2015 e o Banco de Dados RTCLocal

Para instalar o Skype para Business Server 2015 arquivos de núcleo em um computador, conclua o procedimento a seguir. O banco de dados RTCLocal é instalado automaticamente ao instalar os principais arquivos. Observe que você não precisará instalar o SQL Server em todos os nós do observador. SQL Server Express será instalado automaticamente.
  
Para instalar o Skype para arquivos de núcleo de negócios Server 2015 e o banco de dados RTCLocal:
  
1. No computador de nó do inspetor, clique em Iniciar, em Todos os Programas, em Acessórios, clique com o botão direito do mouse em Prompt de Comando e clique em Executar como administrador.
    
2. Na janela de console, digite o seguinte comando e pressione ENTER. Certifique-se inserir o caminho adequado para sua Skype para arquivos de instalação do servidor de negócios: D:\Setup.exe /BootstrapLocalMgmtTo verificar que o núcleo Skype para componentes Business Server forem instalados com êxito, clique em **Iniciar**, clique em **Todos os programas**, Clique em **Skype para Business Server 2015**e clique em **Skype do Shell de gerenciamento do servidor de negócios**. No Skype do Shell de gerenciamento do servidor de negócios, digite o seguinte comando do Windows PowerShell e pressione ENTER:
  
```
Get-CsWatcherNodeConfiguration
```

> [!NOTE]
> Na primeira vez que você executa este comando, nenhum dado é retornado porque você ainda não configurou qualquer computador do nó do observador. Se o comando é executado sem retornando um erro, você pode assumir o Skype para a instalação do Business Server foi concluída com êxito. 
  
Se seu computador do nó do observador estiver localizada dentro da sua rede de perímetro, é possível executar o seguinte comando para verificar a instalação do Skype for Business Server 2015:
  
Get-CsPinPolicyYou irá receber informações semelhantes ao seguinte, dependendo do número de diretivas PIN configuradas para uso em sua organização:
  
Identidade: Global
  
Descrição:
  
MinPasswordLength: 5
  
PINHistoryCount: 0
  
AllowCommonPatterns: falso
  
PINLifetime: 0
  
MaximumLogonAttempts :
  
Se você vir informações sobre suas políticas de PIN, os principais componentes foram instalados com sucesso.
  
## <a name="install-the-operation-manager-agent-files-on-a-watcher-node"></a>Instalar os arquivos do agente do Operation Manager em um nó inspetor

Semelhante ao Skype para a instalação do servidor de negócios para alertas de componente de geração de relatórios, um Skype para nó do observador Business Server 2015 requer os arquivos do agente do System Center Operations Manager será instalado. Isso permite que as transações sintéticas sejam executados e os alertas a ser relatado no servidor de gerenciamento System Center Operations Manager raiz.
  
Para instalar os arquivos do agente, siga os procedimentos listados em [Configure o Skype para computadores Business Server que serão monitorados](configure-computers-to-monitor.md).
  
## <a name="configure-a-watcher-node-to-run-synthetic-transactions"></a>Configurar um nó inspetor para executar transações sintéticas
<a name="enable_synthetic_trans"> </a>

Depois que os arquivos de agente do System Center Operations Manager forem instalados, você deve configurar o nó do Inspetor em si. As etapas realizadas para isso variam dependendo se seu computador do nó do observador está dentro da sua rede de perímetro ou fora. 
  
Ao configurar um nó do observador, você também deve escolher o tipo de método de autenticação a ser implantado neste nó. Skype para Business Server 2015 permite que você escolha um dos dois métodos de autenticação: servidor confiável ou autenticação de credencial. As diferenças entre estes dois métodos são destacadas na tabela a seguir:
  
||**Descrição**|**Locais suportados**|
|:-----|:-----|:-----|
|TrustedServer  <br/> |Usa uma certificação para personificar um servidor interno e desafios de autenticação de bypass.  <br/> Útil para os administradores que preferem gerenciar um único certificado ao invés de várias senhas do usuário no nó do observador.  <br/> |Dentro da empresa.  <br/> Com este método, o nó do observador deve estar no mesmo domínio que os pools sendo monitorados. Se o nó do observador e os pools estão em domínios diferentes, use a Autenticação de Credencial.  <br/> |
|Negotiate  <br/> |Armazena os nomes de usuário e senhas com segurança no Gerenciador de Credencial do Windows no nó do observador.  <br/> Este modo exige mais gerenciamento de senha, mas é a única opção para nós do observador fora da empresa. Estes nós do observador não podem ser tratados como um ponto de extremidade confiável para autenticação.  <br/> |Fora da empresa.  <br/> Dentro da empresa.  <br/> |
   
## <a name="configure-a-watcher-node-to-use-trusted-server-authentication"></a>Configurar um nó inspetor para usar a autenticação de servidor confiável
<a name="enable_synthetic_trans"> </a>

Caso seu computador de nó do inspetor esteja dentro da rede de perímetro, utilizar uma autenticação de Servidor Confiável pode reduzir drasticamente as taxas de administração para manter um único certificado em vez de diversas senhas de conta de usuário.
  
Para configurar autenticação de Servidor Confiável, você deve primeiro criar um pool de aplicativo confiável para hospedar o computador de nó do inspetor. Depois que você criou o pool de aplicativos confiáveis, você deve configurar, em seguida, as transações sintéticas nesse nó de inspetor para executar aplicativos confiáveis.
  
> [!NOTE]
> Um aplicativo confiável é um aplicativo que recebe o status confiável seja executado como parte do Skype para Business Server 2015, mas não é uma parte interna do produto. O status de confiável significa que o aplicativo não será desafiado para autenticação toda vez que executar.
  
Para criar um pool de aplicativos confiáveis, abra o Skype do Shell de gerenciamento do servidor de negócios e execute um comando semelhante a esta:
  
```
New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond
```

> [!NOTE]
> Para obter detalhes sobre os parâmetros no comando anterior, digite o seguinte a partir do Skype para o prompt do Shell de gerenciamento do servidor de negócios: 
  
```
Get-Help New-CsTrustedApplicationPool -Full | more
```

Após criar o pool de aplicativo confiável, configure o computador de nó do inspetor para executar transações sintéticas como aplicativo confiável. Isso é feito utilizando o cmdlet **New-CsTrustedApplication** e um comando similar a este:
  
```
New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061
```

Quando o comando estiver concluído e o aplicativo confiável for criado, você precisará executar o cmdlet **Enable-CsTopology** para certificar-se de que as alterações tenham efeito:
  
```
Enable-CsTopology
```

Após executar o Enable-CsTopology, reinicie o computador.
  
Para verificar que o novo aplicativo confiável foi criado, digite o seguinte no Skype para o prompt do Shell de gerenciamento do servidor de negócios:
  
```
Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"
```

## <a name="configure-a-default-certificate-on-the-watcher-node"></a>Configurar um certificado padrão no nó do inspetor
<a name="enable_synthetic_trans"> </a>

Nó do observador que usa autenticação TrustedServer deve ter um certificado padrão atribuído utilizando o Skype para o Assistente de implantação de servidor de negócios. 
  
Para atribuir um certificado padrão:
  
1. Clique em Iniciar, clique em todos os programas, clique em Skype para Business Server 2015 e clique em Skype para o Assistente de implantação de servidor de negócios. 
    
2. No Skype para o Assistente de implantação do Business Server, clique em instalar ou atualizar Skype para Business Server System e clique em Executar, sob o título de solicitação, instalar ou atribuir certificado. 
    
> [!NOTE]
> Caso o botão Executar esteja inativo, talvez você precise clicar primeiro em Executar, em Instalar Repositório de Configuração Local. 
  
Siga um destes procedimentos:
  
- Se você já tiver um certificado que possa ser utilizado como certificado padrão, clique em Padrão no assistente de Certificado e, então, clique em Atribuir. Siga as etapas no assistente de Atribuição de Certificado para atribuí-lo.
    
- Se você precisar solicitar um certificado para utilizar o certificado padrão, clique em Solicitar e, então, siga as etapas no assistente de Solicitação de Certificado. Se você utilizar valores padrão para o certificado de Servidor da Web, você terá um certificado que pode ser atribuído como certificado padrão.
    
## <a name="install-and-configure-a-watcher-node"></a>Instalar e configurar um nó de inspetor
<a name="enable_synthetic_trans"> </a>

Depois de ter reiniciado o computador de nó do inspetor e configurado o certificado, você precisará executar o arquivo Watchernode.msi. (Você deve executar watchernode em qualquer computador onde os arquivos de agente do Operations Manager e o Skype para componentes principais do Business Server 2015 estão instalados.) 
  
Para instalar e configurar um nó de inspetor:
  
1. Abra o Skype do Shell de gerenciamento do servidor de negócios clicando em Iniciar, clicando em todos os programas, clicando em Skype para Business Server 2015 e clicando em Skype do Shell de gerenciamento do servidor de negócios. 
    
2. No Shell de Gerenciamento, digite o seguinte comando e pressione ENTER (tenha certeza e especifique o caminho real até sua cópia de Watchernode.msi):
    
```
C:\Tools\Watchernode.msi Authentication=TrustedServer
```

> [!NOTE]
> Você também pode executar o Watchernode.msi de uma janela de comando. Para abrir uma janela de comando, clique em Iniciar, clique com o botão direito do mouse em Prompt de comando e, então, em Executar como administrador. Quando a janela de comando abrir, digite o mesmo comando da etapa 2 anterior. 
  
> [!IMPORTANT]
> No comando anterior, o par de valor/nome Authentication=TrustedServer diferencia maiúscula de minúscula. Ele deve ser digitado exatamente como mostrado. Por exemplo, este comando falhará porque não utiliza a formatação correta: 
  
```
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
    
   ```
   c:\Tools\Watchernode.msi Authentication=Negotiate
   ```

> [!NOTE]
> Conforme indicado anteriormente, Watchernode.msi também pode ser executado a partir de uma janela de comando. Para abrir uma janela de comando, clique em **Iniciar**, clique com o botão direito do mouse em **Prompt de Comando** e clique em **Executar como administrador**. Quando a janela de comando for aberta, digite o mesmo comando exibido na etapa 2 acima. 
  
O modo Negociar é usado sempre que o nó de inspetor não podem ser configurado como um pool de aplicativos confiável. Nesse modo, os administradores precisarão gerenciar as senhas do usuário de teste no nó de inspetor.
  

