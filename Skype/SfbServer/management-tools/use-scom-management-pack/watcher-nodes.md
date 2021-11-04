---
title: Como instalar e configurar nós do watcher
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 11/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 7392e4f8-6e2d-447b-aaa3-878f73995f9d
description: Como instalar e configurar nós do watcher para Skype for Business Server transações sintéticas.
ms.openlocfilehash: aca051b005c3ec9a901c5366a7788af5e95d06f0
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60766209"
---
# <a name="how-to-install-and-configure-watcher-nodes"></a>Como instalar e configurar nós do watcher
 
**Resumo:** Instale e configure nós do watcher para Skype for Business Server transações sintéticas.
  
Nós do watcher são computadores que periodicamente Skype for Business Server transações sintéticas. As transações sintéticas Windows PowerShell cmdlets que verificam se os principais cenários do usuário, como a capacidade de entrar ou trocar mensagens instantâneas, estão funcionando conforme o esperado. Para Skype for Business Server 2015, o System Center Operations Manager pode executar as transações sintéticas mostradas na tabela a seguir, que inclui três tipos de transação sintéticas:
  
- **Padrão** Transações sintéticas que um nó do watcher executa por padrão. Ao criar um novo nó do watcher, você pode especificar quais transações sintéticas esse nó executará. (Essa é a finalidade do parâmetro Tests usado pelo cmdlet New-CsWatcherNodeConfiguration.) Se você não usar o parâmetro Tests quando o nó do watcher for criado, ele executará automaticamente todas as transações sintéticas padrão e não executará nenhuma das transações sintéticas não padrão. Isso significa, por exemplo, que o nó do Test-CsAddressBookService será configurado para executar o teste de Test-CsAddressBookService, mas não será configurado para executar o Test-CsExumConnectivity teste.
    
- **Não padrão** Testes que nós do watcher não são executados por padrão. (Para obter detalhes, consulte a descrição do tipo Padrão.) No entanto, o nó do watcher pode ser habilitado para executar qualquer uma das transações sintéticas não padrão. Você pode fazer isso ao criar o nó do watcher (usando o cmdlet New-CsWatcherNodeConfiguration) ou a qualquer momento após a criação do nó do watcher. Observe que muitas das transações sintéticas não padrão exigem etapas de configuração extras. Para obter mais detalhes sobre essas etapas, consulte [Instruções especiais de instalação para transações sintéticas.](test-users-and-settings.md#special_synthetictrans)
    
- **Estendido** Um tipo especial de transação sintética não padrão. Diferentemente das outras transações sintéticas, os testes estendidos podem ser executados várias vezes durante cada fase. Isso é útil ao verificar o comportamento, como várias rotas de voz PSTN (rede telefônica pública comutado) para um pool. Você pode configurar isso simplesmente adicionando várias instâncias de um teste estendido a um nó do watcher.
    
Para obter detalhes sobre o processo de adição de outras transações sintéticas a um nó do [watcher, consulte Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans). Você também pode usar Skype for Business Server Shell de Gerenciamento para remover transações sintéticas de um nó do watcher.
  
As transações sintéticas disponíveis para os nós do inspetor incluem as seguintes:
  
|**Nome do cmdlet (nome do teste)**|**Descrição**|
|:-----|:-----|
|Test-CsAddressBookService (ABS)  <br/> |Confirma se os usuários podem procurar usuários que não estão na lista de contatos.  <br/> |
|Test-CsAddressBookWebQuery (ABWQ)  <br/> |Confirma se os usuários podem procurar usuários que não estão na lista de contatos por meio de HTTP.  <br/> |
|Test-CsAVConference (AvConference)  <br/> |Confirma se os usuários podem criar e participar de uma conferência de áudio/vídeo.  <br/> |
|Test-CsGroupIM (Conferência de IM)  <br/> |Confirma se os usuários podem enviar mensagens instantâneas em conferências e participar de conversas de mensagem instantânea com três ou mais pessoas.  <br/> |
|Test-CsIM (IM P2P)  <br/> |Confirma se os usuários podem enviar mensagens instantâneas ponto a ponto.  <br/> |
|Test-CsP2PAV (P2PAV)  <br/> |Confirma se os usuários podem realizar chamadas de áudio ponto a ponto (apenas sinalização).  <br/> |
|Test-CsPresence (Presence)  <br/> |Confirma se os usuários podem exibir a presença de outros usuários.  <br/> |
|Test-CsRegistration (Registration)  <br/> |Confirma se os usuários podem entrar Skype for Business.  <br/> |
|Test-CsPstnPeerToPeerCall (PSTN)  <br/> |Confirma se os usuários podem realizar e receber chamadas de pessoas de fora da organização (números PSTN).  <br/> |
|Test-CsASConference (ASConference)  <br/> |Confirma se os usuários podem criar e participar de uma conferência de compartilhamento de aplicativos.  <br/> |
|Test-CsAVEdgeConnectivity (AVEdgeConnectivity)  <br/> |Confirma se os servidores de Borda de Vídeo de Áudio são capazes de aceitar conexões para chamadas ponto a ponto e chamadas de conferência.  <br/> |
|Test-CsDataConference (DataConference)  <br/> |Confirma se os usuários podem participar de uma conferência de colaboração de dados (uma reunião online que inclui atividades como whiteboards e votações).  <br/> |
|Test-CsDialinConferencing (DialinConferencing)  <br/> |Confirma se os usuários podem discar números de telefone para ingressar em conferências.  <br/> |
|Test-CsDialinConferencing (DialinConferencing)  <br/> |Confirma se os usuários podem discar números de telefone para ingressar em conferências.  <br/> |
|Test-CsExumConnectivity (ExumConnectivity)  <br/> |Confirma se um usuário pode se conectar Exchange Unificação de Mensagens (UM).  <br/> |
|Test-CsGroupIM -TestJoinLauncher (JoinLauncher)  <br/> |Confirma se os usuários podem criar e ingressar em reuniões agendadas (por um link de endereço da Web).  <br/> |
|Test-CsMCXP2PIM (MCXP2PIM)  <br/> |Confirma se usuários de dispositivos móveis podem registrar-se e enviar mensagens instantâneas.  <br/> |
|Test-CsP2PVideoInteropServerSipTrunkAV (P2PVideoInteropServerSipTrunkAV)  <br/> |Confirma se o Servidor de Interop de Vídeo está em cima e pode manipular as conexões de entrada em um tronco SIP de vídeo.  <br/> **Observação:** O suporte mcx para clientes móveis herdado não está mais disponível no Skype for Business Server 2019. |
|Test-CsPersistentChatMessage (PersistentChatMessage)  <br/> |Confirma se os usuários podem trocar mensagens usando o serviço de Chat Persistente.  <br/> |
|Test-CsUcwaConference (UcwaConference)  <br/> |Confirma se os usuários podem participar de conferências por meio da Web.  <br/> |
|Test-CsUnifiedContactStore (UnifiedContactStore)  <br/> |Confirma se os contatos de um usuário podem ser acessados por meio do repositório unificado de contatos. O armazenamento unificado de contatos fornece uma maneira para os usuários manterem um único conjunto de contatos que podem ser acessados usando o Skype for Business Server 2015, o cliente de colaboração e mensagens do Outlook e/ou o Outlook Web Access.  <br/> |
|Test-CsXmppIM (XmppIM)  <br/> |Confirma se uma mensagem instantânea pode ser enviada através do gateway XMPP (Extensible Messaging and Presence Protocol).  <br/> Gateways XMPP e proxies estão disponíveis no Skype for Business Server 2015, mas não são mais suportados no Skype for Business Server 2019.  |

Você não precisa instalar nós do watcher para usar System Center Operations Manager. Se você não instalar esses nós, ainda poderá receber alertas em tempo real dos componentes Skype for Business Server 2015 sempre que ocorrer um problema. (O Component and User Management Pack não usa nós do watcher.) No entanto, nós do watcher são necessários se você quiser monitorar cenários de ponta a ponta usando o pacote Gerenciamento de Monitoramento Ativo.
  
> [!NOTE]
> Os administradores também podem executar transações sintéticas manualmente, sem usar ou instalar o Operations Manager. Dependendo do tamanho da implantação Skype for Business Server, as transações sintéticas podem usar uma grande quantidade de memória do computador e tempo do processador. Devido a isso, recomendamos que você use um computador dedicado como nó do watcher. Por exemplo, você não deve configurar um servidor Skype for Business Server front-end para atuar como um nó do watcher. Nós do watcher devem atender aos mesmos requisitos básicos de hardware que qualquer outro computador em sua topologia Skype for Business Server de segurança. 
  
> [!NOTE]
> Um nó do watcher herdado do Lync Server 2013 não pode ser colocado no mesmo computador que um nó do watcher do Skype for Business Server 2015 porque os arquivos principais do sistema para o Lync Server 2013 e o Skype for Business Server 2015 não podem ser instalados no mesmo computador. No entanto, Skype for Business Server nós do watcher 2015 podem monitorar simultaneamente Skype for Business Server 2015 e Lync Server 2013. As transações sintéticas padrão são suportadas para ambas as versões do produto. 
  
Os nós do watcher do Lync Server 2013 podem ser implantados dentro ou fora de uma empresa para ajudar a verificar:
  
- A conectividade com pools para usuários internos da empresa.
    
- Conectividade por meio de redes de perímetro para usuários remotos que trabalham fora da empresa.
    
- A conectividade com dispositivos de filiais.
    
- Conectividade com o Lync Server 2013 dentro da empresa e por meio de redes de perímetro.
    
Para ajudar a simplificar a administração, diferentes opções de autenticação estão disponíveis para dentro e fora da empresa. Para obter detalhes, [consulte Configure a Watcher Node to Run Synthetic Transactions](watcher-nodes.md#enable_synthetic_trans).
  
Para configurar um computador para atuar como um nó do watcher, você deve primeiro concluir os seguintes pré-requisitos: 
  
- Instale System Center Operations Manager e importe os Skype for Business Server de gerenciamento 2015. Você também deve primeiro verificar se o computador do nó do watcher atende a todos os pré-requisitos para instalar o Skype for Business Server 2015.
    
- Instale os seguintes itens no computador do nó do watcher:
    
  - A versão completa do .NET Framework 4.5
    
  - Windows Identity Foundation
    
  - Windows PowerShell 3.0
    
Depois que os pré-requisitos são atendidos, você pode configurar o nó do watcher seguindo estas etapas:
  
1. Instale os Skype for Business Server principais arquivos de 2015 no computador do nó do watcher.
    
2. Instale System Center agente do Operations Manager no computador do nó do watcher.
    
3. Execute o Watchernode.msi executável.
    
4. Use o cmdlet **New-CsWatcherNodeConfiguration** para configurar contas de usuário de teste a serem empregadas pelo nó do watcher.
    
## <a name="install-the-skype-for-business-server-2015-core-files-and-the-rtclocal-database"></a>Instalar os arquivos Skype for Business Server 2015 Core e o banco de dados RTCLocal

Para instalar os arquivos Skype for Business Server 2015 principais em um computador, conclua o procedimento a seguir. O banco de dados RTCLocal será instalado automaticamente quando você instalar os arquivos principais. Observe que você não precisa instalar SQL Server nos nós do watcher. SQL Server Express será instalado automaticamente.
  
Para instalar os arquivos Skype for Business Server 2015 principais e o banco de dados RTCLocal:
  
1. No computador de nó do inspetor, clique em Iniciar, em Todos os Programas, em Acessórios, clique com o botão direito do mouse em Prompt de Comando e clique em Executar como administrador.
    
2. Na janela do console, digite o seguinte comando e pressione ENTER. Insira o caminho apropriado para seus arquivos de instalação do Skype for Business Server: D:\Setup.exe /BootstrapLocalMgmtTo verificar se os principais componentes do Skype for Business Server estão instalados com êxito, clique em **Iniciar**, clique em Todos os **Programas,** clique em **Skype for Business Server 2015**, e clique em Skype for Business Server **Shell de Gerenciamento.** No Shell de Gerenciamento Skype for Business Server, digite o seguinte comando Windows PowerShell e pressione ENTER:
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

> [!NOTE]
> Na primeira vez que você executar esse comando, nenhum dado será retornado porque você ainda não configurou nenhum computador nó do watcher. Se o comando for executado sem retornar um erro, você poderá supor que a Skype for Business Server foi concluída com êxito. 
  
Se o computador do nó do watcher estiver localizado dentro da rede de perímetro, você poderá executar o seguinte comando para verificar a instalação do Skype for Business Server 2015:
  
Get-CsPinPolicyYou receberão informações semelhantes a essa, dependendo do número de políticas de PIN configuradas para uso em sua organização:
  
Identidade : Global
  
Descrição :
  
MinPasswordLength : 5
  
PINHistoryCount : 0
  
AllowCommonPatterns : False
  
PINLifetime : 0
  
MaximumLogonAttempts :
  
Se você vir informações sobre suas políticas de PIN, os componentes principais foram instalados com êxito.
  
## <a name="install-the-operation-manager-agent-files-on-a-watcher-node"></a>Instalar os Arquivos de Agente do Gerenciador de Operações em um Nó do Watcher

Semelhante à Skype for Business Server configuração para alertas de componentes de relatório, um nó do Skype for Business Server do Skype for Business Server 2015 requer System Center arquivos de agente do Operations Manager para serem instalados. Isso permite que as transações sintéticas sejam executados e os alertas sejam relatados ao servidor de gerenciamento raiz System Center Operations Manager.
  
Para instalar os arquivos de agente, siga os procedimentos listados em [Configure the Skype for Business Server computers that will be monitored](configure-computers-to-monitor.md).
  
## <a name="configure-a-watcher-node-to-run-synthetic-transactions"></a>Configurar um nó do Watcher para executar transações sintéticas
<a name="enable_synthetic_trans"> </a>

Depois que os System Center de agente do Operations Manager foram instalados, você deve configurar o nó do watcher em si. As etapas que você tomar para fazer isso variarão, dependendo se o computador do nó do watcher está dentro da rede de perímetro ou fora da rede de perímetro. 
  
Ao configurar um nó do observador, você também deve escolher o tipo de método de autenticação a ser implantado neste nó. Skype for Business Server 2015 permite que você escolha um dos dois métodos de autenticação: Servidor Confiável ou Autenticação de Credenciais. A tabela a seguir mostra as diferenças entre esses dois métodos:
  
|&nbsp;|**Descrição**|**Locais com suporte**|
|:-----|:-----|:-----|
|TrustedServer  <br/> |Usa uma certificação para personificar um servidor interno e desafios de autenticação de bypass.  <br/> Útil para administradores que preferem gerenciar um único certificado, em vez de muitas senhas de usuário em cada nó do watcher.  <br/> |Dentro da empresa.  <br/> Com esse método, o nó do watcher deve estar no mesmo domínio que os pools que estão sendo monitorados. Se o nó do watcher e os pools estão em domínios diferentes, use Autenticação de Credencial em vez disso.  <br/> |
|Negociar  <br/> |Armazena os nomes de usuário e senhas com segurança no Gerenciador de Credencial do Windows no nó do observador.  <br/> Esse modo requer mais gerenciamento de senha, mas é a única opção para nós do watcher fora da empresa. Estes nós do observador não podem ser tratados como um ponto de extremidade confiável para autenticação.  <br/> |Fora da empresa.  <br/> Dentro da empresa.  <br/> |
   
## <a name="configure-a-watcher-node-to-use-trusted-server-authentication"></a>Configurar um nó do watcher para usar a autenticação de servidor confiável
<a name="enable_synthetic_trans"> </a>

Se o computador do nó do seu watcher estiver dentro da rede de perímetro, o uso da autenticação do Servidor Confiável pode reduzir consideravelmente as tarefas de administração mantendo um único certificado, em vez de usar várias senhas de conta de usuário.
  
Para configurar a autenticação do Servidor Confiável, primeiro você deve criar um pool de aplicativos confiável para hospedar o computador do nó do watcher. Depois de criar o pool de aplicativos confiáveis, você deve configurar transações sintéticas nesse nó do watcher para ser executado como aplicativos confiáveis.
  
> [!NOTE]
> Um aplicativo confiável é um aplicativo que recebe status confiável para ser executado como parte do Skype for Business Server 2015, mas não é uma parte interno do produto. O status de confiável significa que o aplicativo não será desafiado para autenticação toda vez que executar.
  
Para criar um pool de aplicativos confiáveis, abra o Shell de Gerenciamento Skype for Business Server e execute um comando semelhante a este:
  
```PowerShell
New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond
```

> [!NOTE]
> Para obter detalhes sobre os parâmetros no comando anterior, digite o seguinte no prompt Skype for Business Server Shell de Gerenciamento: 
  
```PowerShell
Get-Help New-CsTrustedApplicationPool -Full | more
```

Depois de criar o pool de aplicativos confiáveis, você pode configurar o computador do nó do watcher para executar transações sintéticas como um aplicativo confiável usando o cmdlet **New-CsTrustedApplication** e um comando semelhante a este:
  
```PowerShell
New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061
```

Quando esse comando for concluído e o aplicativo confiável for criado, você deverá executar o cmdlet **Enable-CsTopology** para garantir que as alterações entre em vigor:
  
```PowerShell
Enable-CsTopology
```

A conta do computador do nó do watcher requer a capacidade de consultar CMS para algumas transações sintéticas. Para permitir essa capacidade, adicione a conta do computador do nó do watcher ao grupo de segurança RTCUniversalReadOnlyAdmins. Depois que a replicação do AD tiver ocorrido, reinicie o computador.
  
Para verificar se o novo aplicativo confiável foi criado, digite o seguinte no prompt Skype for Business Server Shell de Gerenciamento:
  
```PowerShell
Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"
```

## <a name="configure-a-default-certificate-on-the-watcher-node"></a>Configurar um Certificado Padrão no Nó do Watcher
<a name="enable_synthetic_trans"> </a>

Cada nó do watcher que usa a autenticação TrustedServer deve ter um certificado Padrão atribuído usando o assistente Skype for Business Server implantação. 
  
Para atribuir um certificado padrão:
  
1. Clique em Iniciar, em Todos os Programas, Skype for Business Server 2015 e clique Skype for Business Server Assistente de Implantação. 
    
2. No Assistente Skype for Business Server de Implantação, clique em Instalar ou Atualizar Skype for Business Server Sistema e clique em Executar sob o título Solicitar, Instalar ou Atribuir Certificado. 
    
> [!NOTE]
> Caso o botão Executar esteja inativo, talvez você precise clicar primeiro em Executar, sob Instalar Repositório de Configuração Local. 
  
Faça um dos seguintes:
  
- Se você já tiver um certificado que possa ser usado como o certificado Padrão, clique em Padrão no assistente De certificado e clique em Atribuir. Siga as etapas no assistente de Atribuição de Certificado para atribuí-lo.
    
- Se você precisar solicitar um certificado para usar o certificado Padrão, clique em Solicitar e siga as etapas no assistente de Solicitação de Certificado para solicitar esse certificado. Se você utilizar valores padrão para o certificado de Servidor da Web, você terá um certificado que pode ser atribuído como certificado padrão.
    
## <a name="install-and-configure-a-watcher-node"></a>Instalar e configurar um nó do watcher
<a name="enable_synthetic_trans"> </a>

Depois de reiniciar o computador do nó do watcher e configurar um certificado, você deve executar o arquivo Watchernode.msi. (Você deve executar Watchernode.msi em qualquer computador onde os arquivos de agente do Operations Manager e os componentes principais do Skype for Business Server 2015 estão instalados.) 
  
Para instalar e configurar um nó do watcher:
  
1. Abra o Shell Skype for Business Server Gerenciamento clicando em Iniciar, clicando em Todos os Programas, Skype for Business Server 2015 e clicando em Skype for Business Server Gerenciamento. 
    
2. No Shell de Gerenciamento, digite o seguinte comando e pressione ENTER (certifique-se de especificar o caminho real para a cópia do Watchernode.msi):
    
```PowerShell
C:\Tools\Watchernode.msi Authentication=TrustedServer
```

> [!NOTE]
> Você também pode executar Watchernode.msi n de uma janela de comando. Para abrir uma janela de comando, clique em Iniciar, clique com o botão direito do mouse em Prompt de Comando e clique em Executar como administrador. Quando a janela de comando for aberta, digite o mesmo comando mostrado na etapa 2, acima. 
  
> [!IMPORTANT]
> No comando anterior, o par nome/valor Authentication=TrustedServer é sensível a minúsculas. Ele deve ser digitado exatamente como mostrado. Por exemplo, esse comando falhará porque não usa a caixa de texto correta: 
  
```PowerShell
C:\Tools\Watchernode.msi authentication=trustedserver
```

O modo TrustedServer só pode ser usado com computadores que estão dentro da rede de perímetro. Quando um nó do watcher é executado no modo TrustedServer, os administradores não têm que manter senhas de usuário de teste no computador.
  
## <a name="configure-a-watcher-node-to-use-negotiate"></a>Configurar um nó do watcher para usar negociar
<a name="enable_synthetic_trans"> </a>

Se o computador do nó do seu watcher estiver fora da rede de perímetro, você deverá seguir um procedimento ligeiramente diferente para configurar esse nó do watcher para executar transações sintéticas: em particular, você não deve criar um pool de aplicativos confiável ou um aplicativo confiável. Isso significa que você precisará concluir as próximas duas tarefas.
  
### <a name="update-membership-in-the-rtc-local-read-only-administrators-group"></a>Atualizar Associação no Grupo de Administradores locais Read-Only RTC

Se o nó do seu watcher estiver fora da rede de perímetro, você deverá adicionar a conta de Serviço de Rede ao grupo Administradores somente leitura RTC local no computador do nó do watcher concluindo o seguinte procedimento no nó do watcher:
  
1. Clique em Iniciar, clique com o botão direito do mouse em Computador e clique em Gerenciar.
    
2. No Gerenciador de Servidores, expanda Configuração, Usuários e Grupos Locais e clique em Grupos.
    
3. No painel Grupos, clique duas vezes em Administradores locais somente leitura RTC.
    
4. Na caixa  de diálogo Propriedades de Administradores Locais Somente Leitura RTC, clique em Adicionar.
    
5. Na caixa de diálogo Selecionar Usuários, Computadores, Contas de Serviço ou Grupos, clique em Locais
    
6. Na caixa de diálogo Locais, selecione o nome do computador no nó de inspetor e clique em OK.
    
7. Na caixa Digite os nomes de objeto a serem selecionados, digite Serviço de Rede e clique em OK.
    
8. Na caixa  de diálogo Propriedades de Administradores Locais Somente Leitura RTC, clique em OK e feche o Gerenciador de Servidor.
    
9. Reinicie o computador no nó do inspetor.
    
### <a name="install-the-watcher-node-configuration-files"></a>Instalar os Arquivos de Configuração do Nó do Watcher

Sua próxima etapa é executar o arquivo Watchernode.msi: 
  
1. Abra o Shell de Gerenciamento do Microsoft Skype for Business Server 2015. Clique em Iniciar, em Todos os Programas, em Microsoft Skype for Business Server 2015 e em Skype for Business Server Shell de Gerenciamento. 
    
2. Em Skype for Business Server Shell de Gerenciamento, digite o seguinte comando e pressione ENTER (certifique-se de especificar o caminho real para a cópia do Watchernode.msi):
    
   ```PowerShell
   c:\Tools\Watchernode.msi Authentication=Negotiate
   ```

> [!NOTE]
> Como mencionado anteriormente, Watchernode.msi também pode ser executado de uma janela de comando. Para abrir uma janela de comando, clique em **Iniciar**, clique com o botão direito do mouse em **Prompt de Comando** e clique em **Executar como administrador**. Quando a janela de comando for aberta, digite o mesmo comando mostrado na etapa 2, acima. 
  
O modo Negociar é usado sempre que o nó de inspetor não podem ser configurado como um pool de aplicativos confiável. Nesse modo, os administradores precisarão gerenciar as senhas do usuário de teste no nó de inspetor.
  

