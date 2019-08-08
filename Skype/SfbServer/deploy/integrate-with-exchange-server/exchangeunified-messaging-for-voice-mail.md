---
title: Configurar a Unificação de Mensagens do Exchange Server para a caixa postal do Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/11/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
description: 'Resumo: configurar o recurso de mensagens de voz do Exchange Server Unified para o Skype for Business Server.'
ms.openlocfilehash: 514b2159c3836aee4bd6bcfad2b85311280277c4
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238002"
---
# <a name="configure-exchange-server-unified-messaging-for-skype-for-business-server-voice-mail"></a>Configurar a Unificação de Mensagens do Exchange Server para a caixa postal do Skype for Business Server
 
**Resumo:** Configure a Unificação de mensagens do Exchange Server para a caixa postal do Skype for Business Server.
  
O Skype for Business Server permite que você tenha mensagens de correio de voz armazenadas no Exchange Server 2016 ou no Exchange Server 2013; essas mensagens de correio de voz serão exibidas como mensagens de email nas caixas de entrada dos usuários. 

> [!NOTE]
> A Unificação de mensagens do Exchange como anteriormente conhecida não está mais disponível no Exchange 2019, mas você ainda pode usar o sistema telefônico para gravar mensagens de correio de voz e deixar a gravação na caixa de correio do Exchange de um usuário. Para obter mais informações, consulte [planejar o serviço de correio de voz na nuvem](../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) .
  
Se você já configurou a autenticação de servidor para servidor entre o Skype for Business Server e o Exchange Server 2016 ou o Exchange Server 2013, então você está pronto para configurar a Unificação de mensagens. Para fazer isso, primeiro você deve criar e atribuir um novo plano de discagem de Unificação de mensagens no Exchange Server. Por exemplo, esses dois comandos (executados dentro do Shell de gerenciamento do Exchange) configuram um novo plano de discagem de 3 dígitos para o Exchange:
  
```
New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"
```

No primeiro comando do exemplo, o parâmetro VoIPSecurity e o valor do parâmetro "Secured" indica que o canal de sinalização está criptografado usando TLS (Transport Layer Security). O URIType "SipName" indica que as mensagens serão enviadas e recebidas usando o protocolo SIP e o CountryOrRegionCode de 1 indica que o plano de discagem se aplica aos EUA.
  
No segundo comando, o valor do parâmetro para o parâmetro ConfiguredInCountryOrRegionGroups especifica os grupos no país que podem ser usados com este plano de discagem. O valor do parâmetro "em\*qualquer\*lugar\*,", define o seguinte:
  
- Nome do grupo ("Anywhere")
    
- AllowedNumberString (\*, um caractere curinga indicando que qualquer cadeia de caracteres de número é permitida)
    
- DialNumberString (\*, um caractere curinga indicando que qualquer número discado é permitido)
    
- Textcomment (\*, um caractere curinga indicando que qualquer comando de texto é permitido)
    
> [!NOTE]
> Criar um novo plano de discagem também criará uma Política de Caixa de Correio Padrão. 
  
Após criar e configurar o novo plano de discagem, você deve adicionar esse plano ao seu servidor do unificação de mensagens e modificar o modo de inicialização do servidor; em particular, você deve definir o modo de inicialização para "Dual". Você pode executar essas duas tarefas dentro do Shell de gerenciamento do Exchange:
  
```
Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"
```

Após a configuração do servidor de Unificação de mensagens, você deve executar o cmdlet Enable-ExchangeCertificate para garantir que seu certificado do Exchange seja aplicado ao serviço de Unificação de mensagens:
  
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
  
Após habilitar esta caixa de correio, o usuário kenmyer@litwareinc.com poderá usar a unificação de mensagens do Exchange. Você pode verificar se o usuário pode se conectar ao Exchange UM executando o cmdlet [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps) de dentro do Shell de gerenciamento do Skype for Business Server:
  
```
$credential = Get-Credential "litwareinc\kenmyer"
Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential
```

Se você possui um segundo usuário habilitado para unificação de mensagens, é possível usar o cmdlet [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps) para verificar se este segundo usuário pode deixar uma mensagem de caixa postal para o primeiro usuário.
  
```
$credential = Get-Credential "litwareinc\pilar"
Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential
```



## <a name="configuring-unified-messaging-on-microsoft-exchange-server"></a>Configurando a Unificação de mensagens no Microsoft Exchange Server 
> [!IMPORTANT]
> Se você quiser usar a UM (Unificação de mensagens) do Exchange para fornecer atendimento de chamada, Outlook Voice Access ou serviços de atendedor automático para usuários de Enterprise Voice, leia [plano para a integração de Unificação de mensagens do Exchange no Skype for Business](../../plan-your-deployment/integrate-with-exchange/unified-messaging.md)e, em seguida, siga as instruções desta seção. 

Para configurar a UM (Exchange Unified Messaging) para funcionar com o Enterprise Voice, você precisará executar as seguintes tarefas:

- Configurar certificados no servidor que executa os serviços da Unificação de mensagens (UM) do Exchange
  > [!NOTE]
  > Adicione todos os servidores de caixa de correio e acesso de cliente a todos os planos de discagem URI de UM SIP. Caso contrário, o roteamento de chamadas de saída não funcionará como esperado. 
- Crie um ou mais planos de discagem de URI SIP do UM, juntamente com os números de telefone de acesso ao Assinante, conforme necessário e crie os planos de discagem da L correspondentes.

- Use o script exchucutil. ps1 para:
    - Crie gateways IP de UM.
    - Criar grupos de números coletivos da UM.
    - Conceda permissão do Skype for Business Server para ler objetos dos serviços de domínio do Active Directory da UM.
- Criar um objeto de atendedor automático da UM.
- Crie um objeto de acesso do Assinante.
- Crie um URI SIP para cada usuário e associando os usuários a um plano de discagem URI do UM SIP.

### <a name="requirements-and-recommendations"></a>Requisitos e recomendações

Antes de começar, a documentação desta seção pressupõe que você implantou as seguintes funções do Exchange: acesso de cliente e caixa de correio. No Microsoft Exchange Server, o Exchange UM é executado como um serviço nesses servidores.

Observe também o seguinte:
- Se o Exchange UM estiver instalado em várias florestas, as etapas de integração do Exchange Server deverão ser realizadas para cada floresta do UM. Além disso, cada floresta do UM deve ser configurada para confiar na floresta na qual o Skype for Business Server está implantado, e a floresta no whichSkype for Business Server é implantada deve ser configurada para confiar em cada floresta do UM.
- As etapas de integração são executadas nas funções do Exchange Server em que os serviços de mensagens unificadas estão em execução e no servidor que executa o Skype for Business Server. Você deve executar as etapas de integração de Unificação de mensagens do Exchange Server antes de executar as etapas de integração do Lync Server 2013.
  > [!NOTE]
  > Para ver quais etapas de integração são executadas em quais servidores e com quais funções de administrador, consulte [visão geral do processo de implantação para integrar a Unificação de mensagens local e o Skype for Business](../../plan-your-deployment/integrate-with-exchange/deployment-overview.md). 

As seguintes ferramentas devem estar disponíveis em cada servidor que executa o Exchange UM:
- Shell de gerenciamento do Exchange
- O script exchucutil. ps1, que executa as seguintes tarefas:
    - Cria um gateway IP de UM para cada servidor do Skype for Business.
    - Cria um grupo coletivo para cada gateway. O identificador piloto de cada número coletivo especifica o plano de discagem do URI SIP usado pelo pool de front-ends ou do servidor Standard Edition associado ao gateway.
    - Concede permissão do Skype for Business Server para ler objetos do Exchange UM nos serviços de domínio do Active Directory.



### <a name="configure-unified-messaging-on-microsoft-exchange-with-exchucutilps1"></a>Configure Unified Messaging on Microsoft Exchange with ExchUCUtil.ps1 

Ao integrar o Microsoft Skype for Business Server com o Exchange Unified Messaging (UM), você precisa executar o script ExchUcUtil. ps1 no Shell. O script ExchUcUtil. ps1 faz o seguinte:

- Cria um gateway IP de UM para cada pool do Skype for Business Server.

> [!IMPORTANT]
> O script ExchUcUtil. ps1 cria um ou mais gateways IP do UM. Você deve desabilitar as chamadas feitas em todos os gateways IP de UM, exceto um gateway que o script criou. Isso inclui desabilitar chamadas feitas em gateways IP de UM que foram criados antes de você executar o script. 

- Cria um grupo coletivo de UM para cada gateway IP do UM. O identificador piloto de cada número coletivo especifica o plano de discagem do URI SIP do UM usado pelo pool de front-end do Skype for Business Server ou do servidor Standard Edition associado ao gateway de IP do UM.
- Concede permissão do Skype for Business Server para ler objetos do contêiner de UM do Active Directory, como planos de discagem da UM, atendedores automáticos, gateways IP do um e grupos coletivos de UM.
  > [!IMPORTANT]
  > Cada floresta do UM deve ser configurada para confiar na floresta em que o Skype for Business Server está implantado, e a floresta na qual o Skype for Business Server 2013 está implantado deve ser configurada para confiar em cada floresta do UM. Se o Exchange UM estiver instalado em várias florestas, as etapas de integração do Exchange Server deverão ser realizadas para cada floresta do UM ou você precisará especificar o domínio do Skype for Business Server. Por exemplo, ExchUcUtil. ps1 – Forest: <Lync-Domain-Controller-FQDN>. 

### <a name="use-the-shell-to-run-the-exchucutilps1-script"></a>Use o Shell para executar o script ExchUcUtil. ps1

Execute o script ExchUcUtil. ps1 em qualquer servidor Exchange em sua organização que esteja na mesma topologia do Skype for Business Server. Você pode executar o script de um servidor de caixa de correio usando o Shell ou pode executar o script usando o Windows PowerShell remoto em um servidor de acesso para cliente. Se você executar o script em um servidor de acesso para cliente em sua organização, o servidor de acesso para cliente fará o proxy da sessão remota do Windows PowerShell para um servidor de caixa de correio na organização.
> [!IMPORTANT]
> O script ExchUcUtil. ps1 cria um ou mais gateways IP do UM. Você deve desabilitar as chamadas feitas em todos os gateways IP de UM, exceto um gateway que o script criou. Isso inclui desabilitar chamadas feitas em gateways IP de UM que foram criados antes de você executar o script. Para desabilitar as chamadas de saída em um gateway IP de UM, consulte desabilitar chamadas feitas em gateways IP de UM. 
> [!IMPORTANT]
> Você deve ter as permissões da função de gerenciamento de organização do Exchange ou ser membro do grupo de segurança Administradores da organização do Exchange para executar o script. 

1. Abra o Shell de gerenciamento do Exchange.
2. No prompt C:\Windows\System32, digite a **letra \<da unidade de CD>: \Arquivos de Files\Microsoft\Exchange Server\V15\Scripts>. ExchUcUtil. ps1**e, em seguida, pressione Enter.

#### <a name="how-do-you-know-this-worked"></a>Como saber se funcionou?

Para verificar se o script ExchUcUtul. ps1 foi concluído com êxito, faça o seguinte:
- Use o cmdlet Get-UMIPGateway ou a Eat para exibir o novo gateway ou gateways IP do UM que foram criados.
- Use o cmdlet Get-UMHuntGroup ou o Eat para exibir o novo grupo ou grupos de números de UM que foram criados.

### <a name="configure-certificates-on-the-server-running-exchange-server-unified-messaging"></a>Configurar certificados no servidor que executa a Unificação de mensagens do Exchange Server
 
Se você implantou UM (a) da Exchange Unified Messaging (UM), conforme descrito em planejando a integração de Unificação de mensagens do Exchange no Skype for Business Server na documentação de planejamento e deseja fornecer recursos de UM do Exchange para usuários do Enterprise Voice em seu organização, você pode usar os procedimentos a seguir para configurar o certificado no servidor que executa o Exchange UM.

> [!IMPORTANT]
> Para certificados internos, os servidores que executam o Skype for Business Server e os servidores que executam o Microsoft Exchange devem ter certificados de autoridade raiz confiáveis que sejam confiáveis mutuamente. A autoridade de certificação (CA) pode ser a mesma ou uma autoridade de certificação diferente, desde que os servidores tenham o certificado raiz da autoridade de certificação registrado no repositório de certificados da autoridade raiz confiável. 

O servidor Exchange deve ser configurado com um certificado de servidor para se conectar ao Skype for Business Server:
1. Baixe o certificado da CA para o servidor Exchange.
2. Instale o certificado da CA para o servidor Exchange.
3. Verifique se a CA está na lista de autoridades de certificação raiz confiáveis do servidor Exchange.
4. Crie uma solicitação de certificado para o servidor Exchange e instale o certificado. 
5. Atribua o certificado para o servidor Exchange.


**Para baixar o certificado da CA:**

1. No servidor que executa o Exchange UM, clique em **Iniciar**, clique em **executar**, digite **http://\<nome do seu servidor da CA de emissão>/certsrv**e, em seguida, clique em **OK**.
2. Em Selecione uma tarefa, clique em **baixar um certificado de autoridade de certificação, uma cadeia de certificados ou uma CRL**.
3. Em **baixar um certificado de autoridade de certificação, uma cadeia de certificados ou uma CRL**, selecione **método de codificação para base 64**e, em seguida, clique em**baixar certificado da CA**.
   > [!NOTE]
   > Você também pode especificar a codificação de regras de codificação diferenciadas (DER) nesta etapa. Se você selecionar codificação DER, o tipo de arquivo na próxima etapa deste procedimento e na etapa 10 da **para instalar o certificado da CA** será. p7b em vez de. cer. 
4. Na caixa de diálogo **download de arquivo** , clique em **salvar**e salve o arquivo no disco rígido no servidor. (O arquivo terá uma extensão de arquivo. cer ou. p7b, dependendo da codificação que você selecionou na etapa anterior.)

**Para instalar o certificado de CA:**

1. No servidor que executa o Exchange UM, abra o MMC (console de gerenciamento Microsoft) clicando em **Iniciar**, em **executar**, digitando **MMC** na caixa abrir e, em seguida, clicando em **OK**.
2. No menu **arquivo** , clique em **Adicionar/remover snap-in**e, em seguida, clique em **Adicionar**.
3. Na caixa **Adicionar Snap-ins Autônomos** , clique em **certificados**e, em seguida, clique em **Adicionar**.
4. Na caixa de diálogo  **Snap-in de certificados**, clique em  **Conta de computador**e, em seguida, clique em  **Avançar**.
5. Na caixa de diálogo **Selecionar computador** , verifique se a caixa de seleção **computador local: (o computador em que este console está sendo executado)** está marcada e clique em **concluir**.
6. Clique em **fechar**e, em seguida, clique em **OK**. 
7. Na árvore de console, expanda **certificados (computador local)**, expanda **autoridades de certificação raiz confiáveis**e clique em **certificados**.
8. Clique com o botão direito do mouse em **certificados**, clique em **todas as tarefas**e clique em **importar**.
9. Click **Next**. 
10. Clique em **procurar** para localizar o arquivo e, em seguida, clique em **Avançar**. (O arquivo terá uma extensão de arquivo. cer ou. p7b, dependendo da codificação selecionada na etapa 3 de **para baixar o certificado da autoridade de certificação**.
11. Clique em **colocar todos os certificados** no repositório a seguir.
12. Clique em **procurar**e, em seguida, selecione **autoridades de certificação raiz confiáveis**. 
13. Clique em **Avançar** para verificar as configurações e, em seguida, clique em **concluir**. 


**Para verificar se a CA está na lista de autoridades de certificação raiz confiáveis:**

1. No servidor que executa o Exchange UM, no MMC expanda Certificados (computador local), expanda autoridades de certificação raiz confiáveis e clique em certificados.
2. No painel detalhes, verifique se a sua CA está na lista de CAs confiáveis.


