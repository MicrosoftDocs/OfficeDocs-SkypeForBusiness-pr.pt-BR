---
title: Configurar a integração do Cloud Connector com sua Microsoft 365 ou Office 365 organização
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0e2f2395-b890-4d16-aa2d-99d52438b89c
description: Saiba como configurar a integração do Cloud Connector com sua Microsoft 365 ou Office 365 organização.
ms.openlocfilehash: b3b8b13669a2e52ed5146e1bd0ca179a5542e43d
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58733370"
---
# <a name="configure-cloud-connector-integration-with-your-microsoft-365-or-office-365-organization"></a>Configurar a integração do Cloud Connector com sua Microsoft 365 ou Office 365 organização

> [!Important] 
> O Cloud Connector Edition se aposentará em 31 de julho de 2021 junto com Skype for Business Online. Depois que sua organização tiver sido atualizada para Teams, saiba como conectar sua rede de telefonia local ao Teams usando [Roteamento Direto.](/MicrosoftTeams/direct-routing-landing-page)

Saiba como configurar a integração do Cloud Connector com sua Microsoft 365 ou Office 365 organização.
  
Depois que Skype for Business Cloud Connector Edition instalação do Skype for Business Cloud Connector Edition for concluída, execute as etapas nesta seção para configurar sua implantação e conectá-la à sua Microsoft 365 ou Office 365 organização.
  
## <a name="configure-firewall-settings"></a>Configurar configurações de firewall

Configure as configurações de firewall para suas configurações internas e externas de firewall para que você perímetro a rede para abrir as portas necessárias, conforme descrito em Portas e [protocolos](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) em [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a>Configurar gateways PSTN (Rede Telefônica Pública Comutado)

Configurar troncos em cada gateway PSTN para apontar de volta para Servidores de Mediação para todos os dispositivos. Como o FQDN do pool é o mesmo para todos os servidores no pool, cada tronco deve apontar para um FQDN do Servidor de Mediação ou um endereço IP em vez do FQDN do pool do Servidor de Mediação. Os troncos devem ser definidos na mesma prioridade.
  
Se você estiver usando TLS entre servidores de mediação e gateways, será necessário configurar os gateways e servidores de mediação para dar suporte a MTLS da seguinte forma:
  
1. Exporte a CA raiz do computador do Active Directory do Cloud Connector.
    
2. Siga as instruções do fornecedor de gateway PSTN para importar a AC raiz.
    
3. Importe o certificado de AC raiz do certificado emitido para o gateway nos Servidores de Mediação. Se você precisar obter um certificado SSL para o gateway, pode fazer isso usando o serviço autoridade de certificado em execução no computador do Cloud Connector Active Directory da seguinte forma:
    
   - Modifique o modelo de Servidor Web existente para permitir que usuários autenticados se inscrevam ou criem um novo modelo de Servidor Web para configurar outras propriedades e permitir que os usuários autenticados se inscrevam. Para obter instruções detalhadas, consulte [Modelos de Certificados](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc730705(v=ws.11)).
    
   - Solicite um certificado usando o snap-in certificado selecionando o modelo do Servidor Web habilitado. Certifique-se de adicionar Nome comum em Assunto e nome DNS em Nome alternativo com FQDN do gateway e confirme na Chave Privada que Tornar chave privada exportável está selecionada em opções de chave. 
    
4. Exporte o certificado SSL com chave privada e siga as instruções do fornecedor de gateway PSTN para importar o certificado.
    
## <a name="update-the-domain-for-your-tenant"></a>Atualizar o domínio para seu locatário

Certifique-se de que você concluiu as etapas para atualizar seu domínio Microsoft 365 ou Office 365 e tenha a capacidade de adicionar registros DNS. Para obter mais informações sobre como configurar seu domínio em Microsoft 365 ou Office 365, consulte Adicionar um domínio a Microsoft 365 [ou Office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
  
## <a name="add-dns-records-for-your-edge"></a>Adicionar registros DNS para seu Edge

Adicione os seguintes registros DNS à sua Microsoft 365 ou Office 365 organização. Para obter informações sobre como adicionar registros DNS, consulte [Add or edit custom DNS records in Microsoft 365 or Office 365](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).
  
1. Adicione um registro DNS A para Borda de Acesso.
    
2. Os registros SRV serão criados automaticamente por Microsoft 365 ou Office 365 e os scripts de implantação. Confirme se você pode procurar os dois seguintes serviços SIP na Borda: \_ sip e \_ sipfederationtls.
    
     ![Confirmação de Registros SRV.](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-microsoft-365-or-office-365"></a>Configurar conectividade híbrida entre o Cloud Connector Edition e Microsoft 365 ou Office 365

Para configurar a conectividade híbrida entre sua implantação Skype for Business Cloud Connector Edition e sua organização Microsoft 365 ou Office 365, execute o seguinte cmdlet em uma sessão remota do PowerShell. Para saber como estabelecer uma sessão remota do PowerShell, consulte: [Configurar o computador para](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)Windows PowerShell .
  
O cmdlet define o FQDN externo de Borda de Acesso. No primeiro dos comandos, o deve ser o da função de Borda de \<External Access Edge FQDN\> Acesso SIP. Por padrão, isso deve ser ap. \<Domain Name\> .
  
```powershell
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> O FQDN de Borda de Acesso Externo usado para Destino Par deve ser definido como um site PSTN que só será usado como fallback caso um usuário não seja atribuído a um site PSTN. Para obter mais informações, [consulte Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) and Deploy multiple sites in Cloud [Connector](deploy-multiple-sites-in-cloud-connector.md). 
  
## <a name="set-up-pstn-gateways"></a>Configurar gateways PSTN

Configurar troncos em cada gateway PSTN para apontar de volta para Servidores de Mediação para todos os dispositivos. Cada tronco deve apontar para um FQDN do Servidor de Mediação ou um endereço IP em vez do FQDN do pool do Servidor de Mediação porque o FQDN do pool é o mesmo para todos os servidores no pool. Os troncos devem ser definidos na mesma prioridade.
  
Se você estiver usando TLS entre servidores de mediação e gateways, será necessário configurar os gateways e servidores de mediação para dar suporte a MTLS da seguinte forma:
  
1. Exporte a CA raiz do computador do Active Directory do Cloud Connector.
    
2. Siga as instruções do fornecedor de gateway PSTN para importar a AC raiz.
    
3. Importe o certificado de AC raiz do certificado emitido para o gateway nos Servidores de Mediação. Se você precisar obter um certificado SSL para o gateway, pode fazer isso usando o serviço autoridade de certificado em execução no computador do Cloud Connector Active Directory da seguinte forma:
    
   - Modifique o modelo de Servidor Web existente para permitir que usuários autenticados se inscrevam ou criem um novo modelo de Servidor Web para configurar outras propriedades e permitir que os usuários autenticados se inscrevam. Para obter instruções detalhadas, consulte [Modelos de Certificados](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc730705(v=ws.11)).
    
   - Solicite um certificado usando o snap-in certificado selecionando o modelo do Servidor Web habilitado. Certifique-se de adicionar Nome comum em Assunto e nome DNS em Nome alternativo com FQDN do gateway e confirme na Chave Privada que Tornar chave privada exportável está selecionada em opções de chave. 
    
4. Exporte o certificado SSL com chave privada e siga as instruções do fornecedor de gateway PSTN para importar o certificado.
    
5. Os gateways PSTN em um site PSTN devem se conectar apenas aos Servidores de Mediação no mesmo site.
    
## <a name="set-up-your-users"></a>Configurar seus usuários

Entre no Centro de administração do Microsoft 365, adicione os usuários que serão habilitados para serviços de voz online e atribua uma licença E5 ou um complemento Sistema de Telefonia à licença E3 a esses usuários. Para obter informações sobre como adicionar usuários, consulte [Add users to Microsoft 365 for business](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).
  
## <a name="enable-users-for-phone-system-voice-and-voicemail-services"></a>Habilitar usuários para Sistema de Telefonia de voz e caixa postal
 
Depois de adicionar seus usuários Microsoft 365 ou Office 365, habilita suas contas para serviços de Sistema de Telefonia de voz, incluindo caixa postal. Para habilitar esses recursos, você deve fazer logoff na sua organização Microsoft 365 ou Office 365 com uma conta que seja uma função de Administrador Global e poder executar o PowerShell remoto. Para saber como estabelecer uma sessão remota do PowerShell, consulte: [Configurar seu computador para](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) Windows PowerShell
  
- Atribua a política ao usuário e configure o número de telefone de voz comercial do usuário, que você especificará com o valor do parâmetro **Identity:**
    
  ```powershell
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > Uma identidade de usuário pode ser especificada usando o endereço SIP do usuário, o nome principal do usuário (UPN) ou o nome de exibição do Active Directory do usuário (por exemplo, "Bob Kelly"). O caractere asterisco ( \* ) também pode ser usado com o Nome de Exibição como a Identidade do usuário. Por exemplo, a Identidade " Smith" retorna todos os usuários que têm um nome de exibição que termina com o valor \* de cadeia de caracteres "Smith".
  
Em seguida, você pode verificar se os usuários foram adicionados e habilitados usando o seguinte script:
  
```powershell
# Input the user name you want to verify
$user = Get-CsOnlineUser <User name>

# For a hybrid user, the value of $user.EnterpriseVoiceEnabled should be True
$user.EnterpriseVoiceEnabled

# For a hybrid user, the value of $user.HostedVoiceMail should be True
$user.HostedVoiceMail

# For a hybrid user, the value of $user.VoicePolicy should be "HybridVoice"
$user.VoicePolicy
```

Você precisará decidir se seus usuários devem ser capazes de fazer chamadas internacionais. Por padrão, a chamada internacional está habilitada. Você pode desabilitar ou habilitar usuários para discagem internacional usando o centro de administração de Skype for Business online.
  
Para desabilitar a chamada internacional por usuário, execute o seguinte cmdlet Skype for Business PowerShell Online:
  
```powershell
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

Para habilitar a chamada internacional por usuário depois de desabilitada, execute o mesmo cmdlet, mas altere o valor de **PolicyName** para *InternationalCallsAllowed*  .
  
## <a name="assign-users-to-pstn-sites"></a>Atribuir usuários a sites PSTN

Use o PowerShell remoto do locatário para atribuir um site aos usuários, mesmo que você só implantou um único site. Para saber como estabelecer uma sessão remota do PowerShell, consulte: [Configurar o computador para](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)Windows PowerShell .
  
```powershell
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> Se nenhum site PSTN for atribuído a um usuário, a conectividade híbrida entre sua implantação do Skype for Business Cloud Connector Edition e sua organização Microsoft 365 ou Office 365 retornará para usar o nível de locatário padrão um (Destino Par) para que as chamadas possam ser concluídas. 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a>Configurar o servidor de mediação híbrido online Configurações
<a name="BKMK_ConfigureMediationServer"> </a>

Quando uma chamada P2P é escalonada para uma conferência PSTN, o servidor de conferência Skype for Business Online enviará um convite para o Servidor de Mediação do Cloud Connector. Para garantir que Microsoft 365 ou Office 365 possa rotear esse convite com êxito, você precisa configurar uma configuração em seu locatário online para cada Servidor de Mediação do Cloud Connector da seguinte maneira: 
  
1. Crie um usuário no Centro de administração do Microsoft 365. Use qualquer nome de usuário que quiser, como "MediationServer1".
    
    Use o domínio SIP padrão do Cloud Connector (o primeiro domínio SIP no arquivo .ini) como o domínio do usuário.
    
    Observe que a atribuição de licença só é necessária para a propagação do usuário no diretório Skype for Business online. Atribua uma licença de Microsoft 365 ou Office 365 (como o E5) à conta que você criar, permita até uma hora para que as alterações se propaguem, verifique se as contas de usuário foram provisionadas corretamente para o diretório online do Skype for Business executando o cmdlet a seguir e remova a licença dessa conta.
    ```powershell
   Get-CsOnlineUser -Identity <UserPrincipalName>
   ```
    
2. Inicie uma sessão remota do PowerShell do Azure AD de locatário usando suas credenciais de administrador global ou de usuário e execute o seguinte cmdlet para definir o departamento para a conta de usuário do Azure AD configurada na etapa 1 como "HybridMediationServer":

   ```powershell
   Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
   ```

3. Inicie um locatário Skype for Business sessão remota do PowerShell usando suas credenciais de administrador de locatários do Skype for Business e execute o cmdlet a seguir para definir o FQDN do Servidor de Mediação e do Servidor de Borda para essa conta de usuário, substituindo pelo Nome de Exibição do usuário para a conta que você criou na etapa \<DisplayName\> 1:
    
   ```powershell
   Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
   ```

    Para Identidade, use o Nome de Exibição da conta de usuário que você criou para este Servidor de Mediação.
    
    Para  *MediationServerFQDN*  , use o FQDN interno definido para seu Servidor de Mediação.
    
    Para  *EdgeServerExternalFQDN,*  use o FQDN externo definido para Proxy de Acesso para Servidor de Borda. Se houver vários sites PSTN do Cloud Connector, escolha o FQDN do Proxy de Acesso para Servidor de Borda atribuído ao site onde o Servidor de Mediação está localizado.
    
4. Se houver vários Servidores de Mediação do Cloud Connector (vários sites, HA), repita as etapas anteriores para cada um deles.
