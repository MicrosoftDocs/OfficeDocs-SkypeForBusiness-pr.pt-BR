---
title: Configurar a Unificação de Mensagens do Exchange Server para a caixa postal do Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/11/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
description: 'Resumo: Configurar a Unificação de Mensagens do Exchange Server para a caixa postal do Skype for Business Server.'
ms.openlocfilehash: 68cf4a11deccac9ad71bdb6216c4126362787498
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834031"
---
# <a name="configure-exchange-server-unified-messaging-for-skype-for-business-server-voice-mail"></a>Configurar a Unificação de Mensagens do Exchange Server para a caixa postal do Skype for Business Server
 
**Resumo:** Configurar a Unificação de Mensagens do Exchange Server para a caixa postal do Skype for Business Server.
  
O Skype for Business Server permite que você tenha mensagens de caixa postal armazenadas no Exchange Server 2016 ou no Exchange Server 2013; essas mensagens de caixa postal aparecerão como mensagens de email nas Caixas de Entrada dos usuários. 

> [!NOTE]
> A Unificação de Mensagens do Exchange como anteriormente conhecida não está mais disponível no Exchange 2019, mas você ainda pode usar o Sistema de Telefonia para gravar mensagens de caixa postal e deixar a gravação na caixa de correio do Exchange de um usuário. Consulte [Planejar o serviço de Caixa Postal na Nuvem](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) para obter mais informações.
  
Se você já configurou a autenticação de servidor para servidor entre o Skype for Business Server e o Exchange Server 2016 ou o Exchange Server 2013, está pronto para configurar a unificação de mensagens. Para fazer isso, você deve primeiro criar e atribuir um novo plano de discagem de unificação de mensagens em seu Exchange Server. Por exemplo, esses dois comandos (executados a partir do Shell de Gerenciamento do Exchange) configuram um novo plano de discagem de 3 dígitos para o Exchange:
  
```powershell
New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"
```

No primeiro comando no exemplo, o parâmetro VoIPSecurity e o valor de parâmetro "Secured" indica que o canal de sinalização é criptografado usando tLS (Transport Layer Security). O URIType "SipName" indica que as mensagens serão enviadas e recebidas usando o protocolo SIP e o CountryOrRegionCode de 1 indica que o plano de discagem se aplica aos EUA.
  
No segundo comando, o valor do parâmetro para o parâmetro ConfiguredInCountryOrRegionGroups especifica os grupos no país que podem ser usados com este plano de discagem. O valor do parâmetro \* "Anywhere, , " define o \* \* seguinte:
  
- Nome do grupo ("Anywhere")
    
- AllowedNumberString ( \* , um caractere curinga indicando que qualquer cadeia de caracteres de número é permitida)
    
- DialNumberString ( \* , um caractere curinga indicando que qualquer número discado é permitido)
    
- TextComment ( \* , um caractere curinga indicando que qualquer comando de texto é permitido)
    
> [!NOTE]
> Criar um novo plano de discagem também criará uma Política de Caixa de Correio Padrão. 
  
Após criar e configurar o novo plano de discagem, você deve adicionar o novo plano de discagem ao seu servidor do unified messaging e modificar o modo de inicialização do servidor; em particular, você deve definir o modo de inicialização para "Dual". Você pode executar essas duas tarefas no Shell de Gerenciamento do Exchange:
  
```powershell
Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"
```

Depois de configurar o servidor de unificação de mensagens, você deve executar o cmdlet Enable-ExchangeCertificate para garantir que seu certificado do Exchange seja aplicado ao serviço de unificação de mensagens:
  
```powershell
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"
```

Após o certificado ter sido atribuído corretamente, você deve parar e reiniciar o serviço MsExchangeUM no servidor do unified messaging. Este serviço deve ser parado e reiniciado a qualquer momento que você alterar o modo de inicialização.
  
Após finalizar a configuração do servidor do unified messaging, é possível configurar o Roteador de Chamada UM:
  
```powershell
Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"
```

Como o modo de inicialização foi alterado, você deve parar e reiniciar o serviço do MsExchangeUMCR no computador hospedando o Roteador de Chamada UM.
  
Para concluir a configuração do unified messaging, você precisa criar uma política de caixa de correio do UM e usar essa política para habilitar os usuários para o unified messaging. É possível criar uma política de caixa de correio usando um comando semelhante ao seguinte:
  
```powershell
New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"
```

E é possível habilitar um usuário para unified messaging utilizando um comando semelhante ao seguinte:
  
```powershell
Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"
```

No comando anterior, o parâmetro Extensions representa o número de extensão telefônica do usuário. Neste exemplo, o usuário possui o número de extensão 100.
  
Após habilitar esta caixa de correio, o usuário kenmyer@litwareinc.com deve poder usar o Exchange unified messaging. Você pode verificar se o usuário pode se conectar à UM do Exchange executando o cmdlet [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps) de dentro do Shell de Gerenciamento do Skype for Business Server:
  
```powershell
$credential = Get-Credential "litwareinc\kenmyer"
Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential
```

Se você possui um segundo usuário habilitado para unified messaging, é possível usar o cmdlet [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps) para verificar se este segundo usuário pode deixar uma mensagem de caixa postal para o primeiro usuário.
  
```powershell
$credential = Get-Credential "litwareinc\pilar"
Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential
```



## <a name="configuring-unified-messaging-on-microsoft-exchange-server"></a>Configurando a Unificação de Mensagens no Microsoft Exchange Server 
> [!IMPORTANT]
> Se você quiser usar a Unificação de Mensagens (UM) do Exchange para fornecer atendimento de chamadas, Outlook Voice Access ou serviços de atendedores automáticos para usuários do Enterprise Voice, leia Planejar a integração da Unificação de Mensagens do Exchange no [Skype for Business](../../plan-your-deployment/integrate-with-exchange/unified-messaging.md)e siga as instruções nesta seção. 

Para configurar a Unificação de Mensagens (UM) do Exchange para funcionar com o Enterprise Voice, você precisará executar as seguintes tarefas:

- Configurar certificados no servidor que executa serviços de Unificação de Mensagens (UM) do Exchange
  > [!NOTE]
  > Adicione todos os servidores de Acesso para Cliente e de Caixa de Correio a todos os planos de discagem URI sip da UM. Caso não funcione, o roteamento de chamadas de saída não funcionará conforme o esperado. 
- Crie um ou mais planos de discagem URI sip de UM, juntamente com os números de telefone de acesso do assinante, conforme necessário, e crie planos de discagem L correspondentes.

- Use o exchucutil.ps1 script para:
    - Criar gateways IP da UM.
    - Criar grupos de busca da UM.
    - Conceda ao Skype for Business Server permissão para ler objetos dos Serviços de Domínio do Active Directory da UM.
- Criar um objeto de atendimento automático de UM.
- Criar um objeto de acesso de assinante.
- Crie um URI do SIP para cada usuário e associe usuários a um plano de discagem URI SIP da UM.

### <a name="requirements-and-recommendations"></a>Requisitos e recomendações

Antes de começar, a documentação nesta seção pressupo que você implantou as seguintes funções do Exchange: Acesso para Cliente e Caixa de Correio. No Microsoft Exchange Server, a UM do Exchange é executado como um serviço nesses servidores.

Também observe o seguinte:
- Se a UM do Exchange estiver instalada em várias florestas, as etapas de integração do Exchange Server deverão ser executadas para cada floresta de UM. Além disso, cada floresta de UM deve ser configurada para confiar na floresta na qual o Skype for Business Server está implantado, e a floresta na qual oSkype for Business Server está implantado deve ser configurada para confiar em cada floresta de UM.
- As etapas de integração são executadas nas funções do Exchange Server onde os serviços de Unificação de Mensagens estão sendo executados e no servidor que executa o Skype for Business Server. Você deve executar as etapas de integração da Unificação de Mensagens do Exchange Server antes de executar as etapas de integração do Lync Server 2013.
  > [!NOTE]
  > Para ver quais etapas de integração são executadas em quais servidores e por quais funções de administrador, consulte Deployment  [process overview for integrating on-premises Unified Messaging and Skype for Business](../../plan-your-deployment/integrate-with-exchange/deployment-overview.md). 

As ferramentas a seguir devem estar disponíveis em cada servidor que executa a UM do Exchange:
- Shell de Gerenciamento do Exchange
- O script exchucutil.ps1, o qual realiza as tarefas a seguir:
    - Cria um gateway IP de UM para cada Skype for Business Server.
    - Cria um grupo de busca para cada gateway. O identificador piloto de cada grupo de busca especifica o plano de discagem URI sip da UM usado pelo pool de front-end ou servidor Standard Edition associado ao gateway.
    - Concede ao Skype for Business Server permissão para ler objetos UM do Exchange nos Serviços de Domínio do Active Directory.



### <a name="configure-unified-messaging-on-microsoft-exchange-with-exchucutilps1"></a>Configurar a Unificação de Mensagens no Microsoft Exchange com ExchUCUtil.ps1 

Ao integrar o Microsoft Skype for Business Server à Unificação de Mensagens (UM) do Exchange, você precisa executar o script ExchUcUtil.ps1 no Shell. O script ExchUcUtil.ps1 faz o seguinte:

- Cria um gateway IP de UM para cada pool do Skype for Business Server.

> [!IMPORTANT]
> O script ExchUcUtil.ps1 cria um ou mais gateways IP de UM. Você deve desativar as chamadas de saída em todos os gateways IP de UM com exceção o gateway criado pelo script. Isto inclui a desativação de chamadas de saída em gateways IP de UM que foram criados antes de você executar o script. 

- Crie um grupo de busca de UM para cada gateway IP de UM. O identificador piloto de cada grupo de busca especifica o plano de discagem URI sip de UM usado pelo pool de front-end do Skype for Business Server ou servidor Standard Edition associado ao gateway IP da UM.
- Concede ao Skype for Business Server permissão para ler objetos de contêiner de UM do Active Directory, como planos de discagem de UM, atendentes automáticos, gateways IP de UM e grupos de busca de UM.
  > [!IMPORTANT]
  > Cada floresta de UM deve ser configurada para confiar na floresta na qual o Skype for Business Server está implantado, e a floresta na qual o Skype for Business Server 2013 está implantado deve ser configurada para confiar em cada floresta de UM. Se a UM do Exchange estiver instalada em várias florestas, as etapas de integração do Exchange Server deverão ser executadas para cada floresta de UM ou você terá que especificar o domínio do Skype for Business Server. Por exemplo, ExchUcUtil.ps1 –Forest:<lync-domain-controller-fqdn>. 

### <a name="use-the-shell-to-run-the-exchucutilps1-script"></a>Use o Shell para executar o script ExchUcUtil.ps1

Execute o ExchUcUtil.ps1 script em qualquer servidor exchange em sua organização que está na mesma topologia que o Skype for Business Server. Você pode executar o script a partir de um servidor de Caixa de Correio usando o Shell ou você pode executar o script usando o Windows PowerShell Remoto em um servidor de Acesso do Cliente. Se você executar o script em um servidor de Acesso do Cliente na sua organização, o servidor de Acesso do Cliente irá usar um proxy da sessão do Windows PowerShell Remoto para um servidor de Caixa de Correio na organização.
> [!IMPORTANT]
> O script ExchUcUtil.ps1 cria um ou mais gateways IP de UM. Você deve desativar as chamadas de saída em todos os gateways IP de UM com exceção o gateway criado pelo script. Isto inclui a desativação de chamadas de saída em gateways IP de UM que foram criados antes de você executar o script. Para desativar as chamadas de saída em um gateway IP de UM, consulte Desabilitar as chamadas de saída nos gateways IP de UM. 
> [!IMPORTANT]
> Você deve possuir as permissões da função de Gerenciamento da Organização do Exchange ou ser um membro do grupo de segurança dos Administradores da Organização do Exchange para executar o script. 

1. Abra o Shell de Gerenciamento do Exchange Management Shell.
2. No prompt C:\Windows\System32, digite **cd \<drive letter> :\Arquivos de Programas\Microsoft\Exchange Server\V15\Scripts>.ExchUcUtil.ps1** e pressione Enter.

#### <a name="how-do-you-know-this-worked"></a>Como saber se funcionou?

Para verificar se o script ExchUcUtul.ps1 foi finalizado com sucesso, faça o seguinte:
- Use o cmdlet Get-UMIPGateway ou o EAC para exibir o gateway de IP de UM ou os gateways que foram criados.
- Use o cmdlet Get-UMHuntGroup ou o EAC para exibir o novo grupo ou os novos grupos de busca de UM que foram criados.

### <a name="configure-certificates-on-the-server-running-exchange-server-unified-messaging"></a>Configurar certificados no servidor que executa a Unificação de Mensagens do Exchange Server
 
Se você implantou a Unificação de Mensagens (UM) do Exchange, conforme descrito no Planning for Exchange Unified Messaging integration in Skype for Business Server na documentação de Planejamento e deseja fornecer recursos de UM do Exchange para usuários do Enterprise Voice em sua organização, você pode usar os procedimentos a seguir para configurar o certificado no servidor que executa a UM do Exchange.

> [!IMPORTANT]
> Para certificados internos, os servidores que executam o Skype for Business Server e os servidores que executam o Microsoft Exchange devem ter certificados de autoridade raiz confiáveis que sejam mutuamente confiáveis. A autoridade de certificação (CA) pode ser a mesma ou uma autoridade de certificação diferente, desde que os servidores tenham o certificado raiz da autoridade de certificação registrado em seu armazenamento de certificados de autoridade raiz confiável. 

O Exchange Server deve ser configurado com um certificado de servidor para se conectar ao Skype for Business Server:
1. Baixe o certificado da autoridade de certificação do Exchange Server.
2. Instale o certificado da autoridade de certificação do Exchange Server.
3. Verifique se a autoridade de certificação está na lista de autoridades de certificação raiz confiáveis do Exchange Server.
4. Crie uma solicitação de certificado do Exchange Server e instale o certificado. 
5. Atribua o certificado do Exchange Server.


**Para baixar o certificado de ac:**

1. No servidor que está executando a UM do Exchange, clique em **Iniciar,** em **Executar,** **digite http:// \<name of your Issuing CA Server> /certsrv** e clique em **OK.**
2. Em Selecionar uma tarefa, clique **em Baixar um certificado de ac, cadeia de certificados ou CRL**.
3. Em Baixar um Certificado de Ac, Cadeia de Certificados ou **CRL,** selecione Método de Codificação para **Base 64** e clique em **Baixar certificado de ac.**
   > [!NOTE]
   > Você também pode especificar a codificação de Regras de Codificação Distinta (DER) nesta etapa. Se você selecionar a codificação DER, o tipo de arquivo na próxima etapa deste procedimento e na etapa 10 de **Para instalar o Certificado de autoridade de certificação** é. p7b, em vez de .cer. 
4. Na caixa de diálogo **Download de Arquivo**, clique em **Salvar** e salve o arquivo no disco rígido no servidor. (O arquivo terá um .cer ou uma extensão de arquivo .p7b, dependendo da codificação que você selecionou na etapa anterior).

**Para instalar o certificado de ac:**

1. No servidor que está executando a UM do Exchange, abra o Console de Gerenciamento Microsoft (MMC) clicando em **Iniciar,** em **Executar,** digitando **mmc** na caixa Abrir e clicando em **OK.**
2. No menu **Arquivo**, clique em **Adicionar/Remover Snap-in** e em **Adicionar**.
3. Na caixa **Adicionar Snap-in Autônomo**, clique em **Certificados** e em **Adicionar**.
4. Na caixa de diálogo **Snap-in de certificados**, clique em **Conta de computador** e em **Avançar**.
5. Na caixa **de diálogo** Selecionar Computador, verifique se a caixa de seleção Computador **local: (o** computador em que este console está sendo executado) está marcada e clique em **Concluir.**
6. Clique em **Fechar** e em **OK**. 
7. Na árvore de console, expanda **Certificados (Computador Local)**, expanda **Autoridades de Certificação Raiz Confiáveis** e clique em **Certificados**.
8. Clique com o botão direito do mouse em **Certificados**, clique em **Todas as Tarefas** e em **Importar**.
9. Clique em **Avançar**. 
10. Clique em **Procurar** para localizar o arquivo e clique em **Avançar**. (O arquivo terá uma extensão de arquivo .cer ou .p7b, dependendo da codificação que você selecionou na etapa 3 de **Para baixar o certificado de autoridade de certificação**.
11. Clique **em Colocar Todos os Certificados** no armazenamento a seguir.
12. Clique em **Procurar** e selecione **Autoridades de Certificação Raiz Confiáveis**. 
13. Clique em **Avançar** para verificar as configurações e, em seguida, clique em **Concluir**. 


**Para verificar se a AC está na lista de CAs raiz confiáveis:**

1. No servidor que executa a UM do Exchange, no MMC expanda Certificados (Computador Local), expanda Autoridades de Certificação Raiz Confiáveis e clique em Certificados.
2. No painel de detalhes, verifique se a autoridade de certificação está na lista de autoridades de certificação confiáveis.


