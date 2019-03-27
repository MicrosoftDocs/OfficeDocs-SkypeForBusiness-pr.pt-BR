---
title: Configurar a Unificação de Mensagens do Exchange Server para a caixa postal do Skype for Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/11/2019
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
description: 'Resumo: Configure o Unificação de mensagens do Exchange Server para Skype para caixa postal Business Server.'
ms.openlocfilehash: 60f9398b7a35ad211ede22ee0e0e7f9689bbc8d7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887897"
---
# <a name="configure-exchange-server-unified-messaging-for-skype-for-business-server-voice-mail"></a>Configurar a Unificação de Mensagens do Exchange Server para a caixa postal do Skype for Business Server
 
**Resumo:** Configure Unificação de mensagens do Exchange Server do Skype para caixa postal Business Server.
  
Skype para Business Server permite que você tenha mensagens da caixa postal armazenadas no Exchange Server 2016 ou Exchange Server 2013; Essas mensagens de caixa postal aparecerão como mensagens de email nas caixas de entrada dos usuários. 

> [!NOTE]
> Unificação de mensagens do Exchange como conhecido anteriormente não está mais disponível no Exchange 2019, mas você pode ainda usar o sistema telefônico para mensagens de caixa postal de registro e, em seguida, deixar a gravação na caixa de correio do Exchange do usuário. Consulte o [serviço de caixa postal de nuvem planejar](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) para obter mais informações.
  
Se você já tiver configurado a autenticação de servidor-para-servidor entre o Skype para Business Server e o Exchange Server 2016 ou o Exchange Server 2013, em seguida, você estará pronto para configurar a Unificação de mensagens. Para fazer isso, você deve primeiro criar e atribuir um novo plano de discagem mensagens unificadas em seu servidor Exchange. Por exemplo, estes dois comandos (executados de dentro do Shell de gerenciamento do Exchange) configurar um novo plano de discagem de 3 dígitos para o Exchange:
  
```
New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"
```

No primeiro comando no exemplo, o parâmetro VoIPSecurity e o valor do parâmetro "Seguro" indica que o canal de sinalização é criptografado usando a segurança de camada de transporte (TLS). O URIType "SipName" indica que as mensagens serão enviadas e recebidas usando o protocolo SIP e o CountryOrRegionCode de 1 indica que o plano de discagem se aplica aos EUA.
  
No segundo comando, o valor do parâmetro para o parâmetro ConfiguredInCountryOrRegionGroups especifica os grupos no país que podem ser usados com este plano de discagem. O valor do parâmetro "em qualquer lugar,\*,\*,\*" define o seguinte:
  
- Nome do grupo ("Anywhere")
    
- AllowedNumberString (\*, um caractere curinga indicando que qualquer sequência numérica é permitida)
    
- DialNumberString (\*, um caractere curinga indicando que qualquer número discado é permitido)
    
- TextComment (\*, um caractere curinga indicando que qualquer comando de texto é permitido)
    
> [!NOTE]
> Criar um novo plano de discagem também criará uma Política de Caixa de Correio Padrão. 
  
Após criar e configurar o novo plano de discagem, você deve adicionar esse plano ao seu servidor do unificação de mensagens e modificar o modo de inicialização do servidor; em particular, você deve definir o modo de inicialização para "Dual". Você pode executar essas tarefas de dentro do Shell de gerenciamento do Exchange:
  
```
Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"
```

Após o servidor do unified messaging ter sido configurado, você Avançar deve executar o cmdlet Enable-ExchangeCertificate para garantir que o seu certificado do Exchange é aplicado ao serviço do unified messaging:
  
```
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"
```

Após o certificado ter sido atribuído corretamente, você deve parar e reiniciar o serviço MsExchangeUM no servidor do unified messaging. Este serviço deve ser parado e reiniciado a qualquer momento que você alterar o modo de inicialização.
  
Após finalizar a configuração do servidor do unified messaging, é possível configurar o Roteador de Chamada UM:
  
```
Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"
```

Como o modo de inicialização foi alterado, você deve parar e reiniciar o serviço do MsExchangeUMCR no computador hospedando o Roteador de Chamada UM.
  
Para concluir a configuração do unified messaging, você precisa criar uma política de caixa de correio do UM e usar essa política para habilitar os usuários para o unified messaging. É possível criar uma política de caixa de correio usando um comando semelhante ao seguinte:
  
```
New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"
```

E é possível habilitar um usuário para unified messaging utilizando um comando semelhante ao seguinte:
  
```
Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"
```

No comando anterior, o parâmetro Extensions representa o número de extensão telefônica do usuário. Neste exemplo, o usuário possui o número de extensão 100.
  
Após habilitar esta caixa de correio, o usuário kenmyer@litwareinc.com poderá usar a unificação de mensagens do Exchange. Você pode verificar se o usuário pode se conectar a UM do Exchange executando o cmdlet [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps) do dentro do Skype do Shell de gerenciamento do servidor de negócios:
  
```
$credential = Get-Credential "litwareinc\kenmyer"
Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential
```

Se você possui um segundo usuário habilitado para unificação de mensagens, é possível usar o cmdlet [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps) para verificar se este segundo usuário pode deixar uma mensagem de caixa postal para o primeiro usuário.
  
```
$credential = Get-Credential "litwareinc\pilar"
Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential
```



## <a name="configuring-unified-messaging-on-microsoft-exchange-server"></a>Configurando o Unified Messaging no Microsoft Exchange Server 
> [!IMPORTANT]
> Se desejar usar o Exchange Unified Messaging (UM) para fornecer atendimento de chamadas, Outlook Voice Access ou serviços de atendedor automático para usuários do Enterprise Voice, leia [Planejar integração de Unificação de mensagens do Exchange no Skype para negócios](../../plan-your-deployment/integrate-with-exchange/unified-messaging.md)e siga o instruções desta seção. 

Para configurar a Unificação de mensagens (UM) do Exchange para funcionar com o Enterprise Voice, você precisará executar as seguintes tarefas:

- Configurar certificados no servidor executando os serviços do Exchange Unified Messaging (UM)
  > [!NOTE]
  > Adicione todos os servidores de caixa de correio e de acesso para cliente a todos os planos de discagem SIP URI de UM. Se não, o roteamento de chamadas de saída não funcionarão como esperado. 
- Crie um ou mais SIP URI de UM planos de discagem, juntamente com os números de telefone de acesso do assinante, conforme necessário e criar planos de discagem L correspondentes.

- Use o script ExchUCUtil. ps1 para:
    - Crie gateways IP de UM.
    - Crie grupos de busca de UM.
    - Conceder Skype para permissão Business Server ler objetos UM do Active Directory Domain Services.
- Crie um objeto de atendedor automático da Unificação de mensagens.
- Crie um objeto de acesso do assinante.
- Crie um URI do SIP para cada usuário e para os usuários com um plano de discagem SIP URI de UM.

### <a name="requirements-and-recommendations"></a>Requisitos e recomendações

Antes de começar, a documentação desta seção pressupõe que você implantou as seguintes funções do Exchange: acesso para cliente e caixa de correio. No Microsoft Exchange Server, UM do Exchange é executado como um serviço nesses servidores.

Também observe o seguinte:
- Se UM do Exchange estiver instalado em várias florestas, as etapas de integração do Exchange Server devem ser executadas para cada floresta de Unificação de mensagens. Além disso, cada floresta de Unificação de mensagens deve ser configurada para confiar na floresta na qual Skype para Business Server é implantado e floresta em whichSkype para Business Server é implantado deve ser configurada para confiar na floresta de cada UM.
- Etapas de integração são realizadas em ambas as funções de Exchange Server onde estão executando os serviços de Unificação de mensagens e no servidor executando o Skype para Business Server. Você deve executar as etapas de integração da Unificação de mensagens do Exchange Server antes de executar as etapas de integração do Lync Server 2013.
  > [!NOTE]
  > Para ver quais etapas de integração são realizadas em quais servidores e por quais funções de administrador, consulte [Visão geral do processo de implantação para integrar o local de Unificação de mensagens e Skype para negócios](../../plan-your-deployment/integrate-with-exchange/deployment-overview.md). 

As seguintes ferramentas devem estar disponíveis em cada servidor executando o UM do Exchange:
- Shell de gerenciamento do Exchange
- O script ExchUCUtil. ps1, que executa as seguintes tarefas:
    - Cria um gateway IP de UM para cada Skype para Business Server.
    - Cria um grupo de busca para cada gateway. O identificador piloto de cada grupo de busca Especifica o plano de discagem SIP URI de UM usado pelo pool de Front-End ou servidor Standard Edition que está associado ao gateway.
    - Concede Skype para Server de negócios permissão para ler objetos UM do Exchange nos serviços de domínio Active Directory.



### <a name="configure-unified-messaging-on-microsoft-exchange-with-exchucutilps1"></a>Configure Unified Messaging on Microsoft Exchange with ExchUCUtil.ps1 

Quando você estiver integrando Microsoft Skype para Business Server com Unificação de mensagens (UM) do Exchange, você precisa executar o script ExchUCUtil. Ps1 no Shell. O script ExchUCUtil. Ps1 faz o seguinte:

- Cria um gateway IP de UM para cada Skype para pool de servidores de negócios.

> [!IMPORTANT]
> O script ExchUCUtil. Ps1 cria um ou mais gateways IP de UM. Você deve desativar as chamadas de saída em todos os gateways IP de UM, exceto um gateway que criou o script. Isso inclui a desativação de chamadas de saída nos gateways IP de UM que foram criados antes de você executar o script. 

- Cria um grupo de busca de UM para cada gateway IP de UM. O identificador piloto de cada grupo de busca Especifica o plano de discagem SIP URI de UM usado pelo Skype para pool Business servidor Front-End ou servidor Standard Edition que está associado ao gateway IP de UM.
- Skype concede permissão de Business Server ler objetos UM do Active Directory de contêiner, como UM discagem planos, atendentes automáticos, gateways IP de UM e grupos de busca de UM.
  > [!IMPORTANT]
  > Cada floresta de Unificação de mensagens deve ser configurada para confiar na floresta na qual Skype para Business Server é implantado e a floresta na qual Skype para Business Server 2013 é implantado deve ser configurada para confiar na floresta de cada UM. Se UM do Exchange estiver instalado em várias florestas, as etapas de integração do Exchange Server devem ser executadas para cada floresta de UM, ou você precisará especificar o Skype para o domínio do servidor de negócios. Por exemplo, o ExchUCUtil. Ps1 – floresta: <lync-domínio-controlador-fqdn>. 

### <a name="use-the-shell-to-run-the-exchucutilps1-script"></a>Usar o Shell para executar o script ExchUCUtil. Ps1

Execute o script ExchUCUtil. Ps1 em qualquer servidor do Exchange em sua organização que esteja na mesma topologia como Skype para Business Server. Você pode executar o script de um servidor de caixa de correio usando o Shell ou é possível executar o script usando o Windows PowerShell remoto em um servidor de acesso para cliente. Se você executar o script em um servidor de acesso para cliente em sua organização, o servidor de acesso para cliente será proxy a sessão do Windows PowerShell remoto para um servidor de caixa de correio na organização.
> [!IMPORTANT]
> O script ExchUCUtil. Ps1 cria um ou mais gateways IP de UM. Você deve desativar as chamadas de saída em todos os gateways IP de UM, exceto um gateway que criou o script. Isso inclui a desativação de chamadas de saída nos gateways IP de UM que foram criados antes de você executar o script. Para desabilitar as chamadas de saída em um gateway IP de UM, consulte Disable chamadas nos gateways IP de UM. 
> [!IMPORTANT]
> Você deve ter as permissões da função de gerenciamento de organização do Exchange ou ser membro do grupo de segurança Administradores de organização do Exchange para executar o script. 

1. Abra o Shell de gerenciamento do Exchange.
2. No prompt do C:\Windows\System32, digite cd ** \<letter>:\Program Files\Microsoft\Exchange Server\V15\Scripts> de unidade. ExchUCUtil. Ps1**, e pressione Enter.

#### <a name="how-do-you-know-this-worked"></a>Como saber se isso funcionou?

Para verificar se o script ExchUcUtul.ps1 foi concluída com êxito, faça o seguinte:
- Use o cmdlet Get-UMIPGateway ou o EAC para exibir o novo gateway IP de UM ou os gateways que foram criados.
- Use o cmdlet Get-UMHuntGroup ou o EAC para exibir o novo grupo de busca ou grupos que foram criados.

### <a name="configure-certificates-on-the-server-running-exchange-server-unified-messaging"></a>Configurar certificados no servidor executando a Unificação de mensagens do Exchange Server
 
Se você tiver implantado o Exchange Unified Messaging (UM), conforme descrito em Planning for Exchange Unified Messaging integration na Skype para Business Server na documentação de planejamento, e você deseja fornecer recursos de UM do Exchange para usuários do Enterprise Voice em sua organização, você pode usar os procedimentos a seguir para configurar o certificado no servidor que executa o UM do Exchange.

> [!IMPORTANT]
> Para os certificados internos, tanto os servidores que executam o Skype para Business Server e os servidores que executam o Microsoft Exchange devem ter certificados raiz confiáveis autoridade que são mutuamente confiáveis. A autoridade de certificação (CA) pode ser o mesmo ou uma autoridade de certificação diferente, desde que os servidores têm um certificado de raiz da autoridade de certificação registrado no seu repositório de certificados de autoridade raiz confiável. 

O Exchange Server deve ser configurado com um certificado de servidor para se conectar à Skype para Business Server:
1. Baixe o certificado de autoridade de certificação do servidor do Exchange.
2. Instale o certificado de autoridade de certificação do servidor do Exchange.
3. Verifique se a autoridade de certificação está na lista de certificação raiz confiáveis do Exchange Server.
4. Criar uma solicitação de certificado para o Exchange Server e instalar o certificado. 
5. Atribua o certificado do servidor do Exchange.


**Para baixar o certificado de autoridade de certificação:**

1. No servidor executando o UM do Exchange, clique em **Iniciar**, clique em **Executar**, tipo **http://\<nome de sua autoridade de certificação emitindo Server>/certsrv**e clique em **Okey**.
2. Em selecionar uma tarefa, clique em **baixar um certificado de autoridade de certificação, cadeia de certificados ou lista de certificados Revogados**.
3. Em **baixar um certificado de autoridade de certificação, cadeia de certificados ou lista de certificados Revogados**, selecione **O método de codificação em Base 64**e clique em**certificado de autoridade de certificação baixar**.
   > [!NOTE]
   > Você também pode especificar a codificação DER (regras distintas) codificação nesta etapa. Se você selecionar a codificação DER, o tipo de arquivo na próxima etapa deste procedimento e na etapa 10 de **para instalar a autoridade de certificação certificado** é. p7b, em vez de. cer. 
4. Na caixa de diálogo **Download de arquivo** , clique em **Salvar**e salve o arquivo no disco rígido do servidor. (O arquivo terá. cer ou uma extensão de arquivo. p7b, dependendo da codificação selecionada na etapa anterior.)

**Para instalar o certificado de autoridade de certificação:**

1. No servidor executando o UM do Exchange, abra o Console de gerenciamento Microsoft (MMC) clicando em **Iniciar**, clicando em **Executar**, digitando **mmc** na caixa Abrir e clicando em **Okey**.
2. No menu **arquivo** , clique em **Adicionar/Remover Snap-in**e, em seguida, clique em **Adicionar**.
3. Na caixa **Adicionar Snap-in autônomo** , clique em **certificados**e, em seguida, clique em **Adicionar**.
4. Na caixa de diálogo  **Snap-in de certificados**, clique em  **Conta de computador**e, em seguida, clique em  **Avançar**.
5. Na caixa de diálogo **Selecionar computador** , verifique se o **computador Local: (o computador em que este console está sendo executado)** caixa de seleção está selecionada e clique em **Concluir**.
6. Clique em **Fechar**e, em seguida, clique em **Okey**. 
7. Na árvore de console, expanda **certificados (computador Local)**, expanda **Autoridades de certificação raiz confiáveis**e clique em **certificados**.
8. Clique com o botão **certificados**, clique em **All Tasks**e clique em **Importar**.
9. Click **Next**. 
10. Clique em **Procurar** para localizar o arquivo e clique em **Avançar**. (O arquivo terá. cer ou uma extensão de arquivo. p7b, dependendo da codificação selecionada na etapa 3 de **para baixar o certificado de autoridade de certificação**.
11. Clique em **Colocar todos os certificados** no armazenamento a seguir.
12. Clique em **Procurar**e selecione **Autoridades de certificação raiz confiáveis**. 
13. Clique em **Avançar** para verificar as configurações e clique em **Concluir**. 


**Para verificar se a autoridade de certificação está na lista de certificação raiz confiáveis:**

1. No servidor executando o UM do Exchange, no MMC, expanda certificados (computador Local), expanda autoridades de certificação raiz confiáveis e clique em certificados.
2. No painel de detalhes, verifique se a autoridade de certificação na lista de autoridades de certificação confiáveis.


