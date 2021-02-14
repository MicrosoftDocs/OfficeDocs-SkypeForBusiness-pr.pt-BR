---
title: Configurar a integração do Cloud Connector com sua organização do Microsoft 365 ou Office 365
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
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0e2f2395-b890-4d16-aa2d-99d52438b89c
description: Saiba como configurar a integração do Cloud Connector com sua organização do Microsoft 365 ou Office 365.
ms.openlocfilehash: bf5d8c4fb9684a205670701428fa8db30835a871
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359067"
---
# <a name="configure-cloud-connector-integration-with-your-microsoft-365-or-office-365-organization"></a>Configurar a integração do Cloud Connector com sua organização do Microsoft 365 ou Office 365

> [!Important] 
> O Cloud Connector Edition será destivado em 31 de julho de 2021 junto com o Skype for Business Online. Depois que sua organização atualizou para o Teams, saiba como conectar sua rede de telefonia local ao Teams usando o [Roteamento Direto.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)

Saiba como configurar a integração do Cloud Connector com sua organização do Microsoft 365 ou Office 365.
  
Quando a instalação do Skype for Business Cloud Connector Edition for concluída, execute as etapas nesta seção para configurar sua implantação e conectá-la à sua organização do Microsoft 365 ou Office 365.
  
## <a name="configure-firewall-settings"></a>Definir configurações de firewall

Configure as configurações de firewall para suas configurações de firewall interno e externo para que sua rede de perímetro abra as portas necessárias, conforme descrito em Portas e [protocolos](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) no Plano do [Skype for Business Cloud Connector Edition.](plan-skype-for-business-cloud-connector-edition.md)
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a>Configurar gateways PSTN (Rede Telefônica Pública Comucionária)

Configurar troncos em cada gateway PSTN para que eles apontem para os Servidores de Mediação de todos os dispositivos. Como o FQDN do pool é o mesmo para todos os servidores no pool, cada tronco deve apontar para um FQDN ou endereço IP do Servidor de Mediação em vez do FQDN do pool do Servidor de Mediação. Os troncos devem ser definidos com a mesma prioridade.
  
Se você estiver usando o TLS entre os Servidores de Mediação e gateways, será necessário configurar os gateways e os Servidores de Mediação para dar suporte a MTLS da seguinte forma:
  
1. Exporte a AC raiz do computador do Active Directory do Cloud Connector.
    
2. Siga as instruções do fornecedor do gateway PSTN para importar a AC raiz.
    
3. Importe o certificado ac raiz do certificado emitido para seu gateway nos Servidores de Mediação. Se você precisar obter um certificado SSL para o gateway, use o serviço de Autoridade de Certificação em execução no computador do Active Directory do Cloud Connector da seguinte forma:
    
   - Modifique o modelo de Servidor Web existente para permitir que usuários autenticados se inscrevam ou crie um novo modelo de Servidor Web para configurar outras propriedades e permitir que os usuários autenticados se inscrevam. Para obter instruções detalhadas, consulte [Modelos de Certificado.](https://technet.microsoft.com/library/cc730705.aspx)
    
   - Solicite um certificado usando o snap-in Certificado selecionando o modelo de Servidor Web que você habilitar. Certifique-se de adicionar o nome comum no assunto e no nome DNS no nome alternativo com o FQDN do gateway e confirme se a chave privada que torna a chave privada exportável está selecionada nas opções de chave. 
    
4. Exporte o certificado SSL com chave privada e siga as instruções do fornecedor do gateway PSTN para importar o certificado.
    
## <a name="update-the-domain-for-your-tenant"></a>Atualizar o domínio para seu locatário

Certifique-se de ter concluído as etapas para atualizar seu domínio no Microsoft 365 ou Office 365 e ter a capacidade de adicionar registros DNS. Para obter mais informações sobre como configurar seu domínio no Microsoft 365 ou Office 365, confira Adicionar um domínio ao [Microsoft 365 ou Office 365.](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)
  
## <a name="add-dns-records-for-your-edge"></a>Adicionar registros DNS para sua Borda

Adicione os seguintes registros DNS à sua organização do Microsoft 365 ou Office 365. Para obter informações sobre como adicionar registros DNS, consulte Adicionar ou editar registros DNS personalizados no [Microsoft 365 ou no Office 365.](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)
  
1. Adicione um registro DNS A à Borda de Acesso.
    
2. Os registros SRV serão criados automaticamente pelo Microsoft 365 ou Office 365 e os scripts de implantação. Confirme se você pode procurar os dois serviços SIP a seguir na Borda: \_ sip \_ e sipfederationtls.
    
     ![Confirmação de registros SRV](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-microsoft-365-or-office-365"></a>Configurar a conectividade híbrida entre o Cloud Connector Edition e o Microsoft 365 ou o Office 365

Para configurar a conectividade híbrida entre sua implantação do Skype for Business Cloud Connector Edition e sua organização do Microsoft 365 ou Office 365, execute o seguinte cmdlet em uma sessão remota do PowerShell. Para saber como estabelecer uma sessão remota do PowerShell, confira: [Configurar seu computador para o Windows PowerShell.](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx)
  
O cmdlet define o FQDN externo da Borda de Acesso. No primeiro dos comandos, ele deve ser aquele para a função de Borda \<External Access Edge FQDN\> de Acesso SIP. Por padrão, deve ser \<Domain Name\> ap.
  
```powershell
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> O FQDN da Borda de Acesso Externo usado para Destino Par deve ser definido como um site PSTN que será usado apenas como fallback caso um usuário não seja atribuído a um site PSTN. Para obter mais informações, [consulte Implantar um único site no Cloud Connector](deploy-a-single-site-in-cloud-connector.md) e implantar vários sites no Cloud [Connector.](deploy-multiple-sites-in-cloud-connector.md) 
  
## <a name="set-up-pstn-gateways"></a>Configurar gateways PSTN

Configurar troncos em cada gateway PSTN para que eles apontem para os Servidores de Mediação de todos os dispositivos. Cada tronco deve apontar para um FQDN ou endereço IP do Servidor de Mediação em vez do FQDN do pool do Servidor de Mediação porque o FQDN do pool é o mesmo para todos os servidores no pool. Os troncos devem ser definidos com a mesma prioridade.
  
Se você estiver usando o TLS entre os Servidores de Mediação e gateways, será necessário configurar os gateways e os Servidores de Mediação para dar suporte a MTLS da seguinte forma:
  
1. Exporte a AC raiz do computador do Active Directory do Cloud Connector.
    
2. Siga as instruções do fornecedor do gateway PSTN para importar a AC raiz.
    
3. Importe o certificado ac raiz do certificado emitido para seu gateway nos Servidores de Mediação. Se você precisar obter um certificado SSL para o gateway, use o serviço de Autoridade de Certificação em execução no computador do Active Directory do Cloud Connector da seguinte forma:
    
   - Modifique o modelo de Servidor Web existente para permitir que usuários autenticados se inscrevam ou crie um novo modelo de Servidor Web para configurar outras propriedades e permitir que os usuários autenticados se inscrevam. Para obter instruções detalhadas, consulte [Modelos de Certificado.](https://technet.microsoft.com/library/cc730705.aspx)
    
   - Solicite um certificado usando o snap-in Certificado selecionando o modelo de Servidor Web que você habilitar. Certifique-se de adicionar o nome comum no assunto e no nome DNS no nome alternativo com o FQDN do gateway e confirme se a chave privada que torna a chave privada exportável está selecionada nas opções de chave. 
    
4. Exporte o certificado SSL com chave privada e siga as instruções do fornecedor do gateway PSTN para importar o certificado.
    
5. Os gateways PSTN em um site PSTN devem se conectar apenas aos Servidores de Mediação no mesmo site.
    
## <a name="set-up-your-users"></a>Configurar seus usuários

Entre no centro de administração do Microsoft 365, adicione os usuários que serão habilitados para serviços de voz online e atribua uma licença E5 ou um complemento do Sistema de Telefonia à licença E3 para esses usuários. Para saber mais sobre como adicionar usuários, [confira Adicionar usuários ao Microsoft 365 para empresas.](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc)
  
## <a name="enable-users-for-phone-system-voice-and-voicemail-services"></a>Habilitar usuários para serviços de voz e caixa postal do Sistema de Telefonia
 
Depois de adicionar seus usuários ao Microsoft 365 ou Office 365, habilita suas contas para os serviços de voz do Sistema de Telefonia, incluindo a caixa postal. Para habilitar esses recursos, você deve entrar na sua organização do Microsoft 365 ou Office 365 com uma conta que seja uma função de Administrador Global e poder executar o PowerShell remoto. Para saber como estabelecer uma sessão remota do PowerShell, confira: [Configurar seu computador para o Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx)
  
- Atribua a política ao usuário e configure o número de telefone de voz comercial do usuário, que você especifica com o valor do **parâmetro Identity:**
    
  ```powershell
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > Uma identidade de usuário pode ser especificada usando o endereço SIP do usuário, o nome UPN ou o nome de exibição do Active Directory do usuário (por exemplo, "Bob Kelly"). O caractere de asterisco ( ) também pode ser usado com o nome de exibição \* como identidade do usuário. Por exemplo, a Identidade " Smith" retorna todos os usuários que têm um nome de exibição terminando com o valor de cadeia \* de caracteres "Smith".
  
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

Você precisará decidir se os usuários poderão fazer chamadas internacionais. Por padrão, as chamada internacional estão habilitadas. Você pode desabilitar ou habilitar usuários para discagem internacional usando o Centro de administração do Skype for Business online.
  
Para desabilitar as chamadas internacionais por usuário, execute o seguinte cmdlet no PowerShell do Skype for Business Online:
  
```powershell
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

Para reabilitar as chamadas internacionais por usuário depois que ela tiver sido desabilitada, execute o mesmo cmdlet, mas altere o valor de **PolicyName** para *InternationalCallsAllowed*  .
  
## <a name="assign-users-to-pstn-sites"></a>Atribuir usuários a sites PSTN

Use o PowerShell remoto do locatário para atribuir um site aos usuários, mesmo que você só implantou um único site. Para saber como estabelecer uma sessão remota do PowerShell, confira: [Configurar seu computador para o Windows PowerShell.](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx)
  
```powershell
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> Se nenhum site PSTN for atribuído a um usuário, a conectividade híbrida entre sua implantação do Skype for Business Cloud Connector Edition e sua organização do Microsoft 365 ou Office 365 voltará a usar o nível de locatário padrão um (Destino par) para que as chamadas possam ser concluídas. 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a>Definir configurações do Servidor de Mediação híbrido online
<a name="BKMK_ConfigureMediationServer"> </a>

Quando uma chamada P2P é escalonada para uma conferência PSTN, o servidor de conferência do Skype for Business Online enviará um convite para o Servidor de Mediação do Cloud Connector. Para garantir que o Microsoft 365 ou o Office 365 possa rotear esse convite com êxito, você precisa definir uma configuração em seu locatário online para cada Servidor de Mediação do Cloud Connector da seguinte maneira: 
  
1. Crie um usuário no centro de administração do Microsoft 365. Use qualquer nome de usuário que você quiser, como "MediationServer1".
    
    Use o domínio SIP padrão do Cloud Connector (o primeiro domínio SIP no arquivo .ini) como o domínio do usuário.
    
    Observe que a atribuição de licença só é necessária para a propagação do usuário para o diretório online do Skype for Business. Atribua uma licença do Microsoft 365 ou Office 365 (como o E5) à conta que você criar, permita até uma hora para que as alterações se propaguem, verifique se as contas de usuário foram provisionadas corretamente para o diretório online do Skype for Business executando o seguinte cmdlet e, em seguida, remova a licença dessa conta.
    ```powershell
   Get-CsOnlineUser -Identity <UserPrincipalName>
   ```
    
2. Inicie uma sessão remota do PowerShell do Azure AD do locatário usando suas credenciais de administrador global ou de usuário e execute o seguinte cmdlet para definir o departamento da conta de usuário do Azure AD configurada na etapa 1 como "HybridMediationServer":

   ```powershell
   Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
   ```

3. Inicie uma sessão remota do PowerShell do Skype for Business de locatário usando suas credenciais de administrador de locatários do Skype for Business e execute o seguinte cmdlet para definir o Servidor de Mediação e o FQDN do Servidor de Borda para essa conta de usuário, substituindo pelo Nome de Exibição do usuário para a conta que você criou na etapa \<DisplayName\> 1:
    
   ```powershell
   Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
   ```

    Para Identidade, use o Nome de Exibição da conta de usuário que você criou para este Servidor de Mediação.
    
    Para  *MediationServerFQDN*  , use o FQDN interno definido para seu Servidor de Mediação.
    
    Para  *EdgeServerExternalFQDN*  , use o FQDN externo definido para o Proxy de Acesso do Servidor de Borda. Se houver vários sites PSTN do Cloud Connector, escolha o FQDN do Proxy de Acesso do Servidor de Borda atribuído ao site onde o Servidor de Mediação está localizado.
    
4. Se houver vários Servidores de Mediação do Cloud Connector (vários sites, HA), repita as etapas anteriores para cada um deles.
    
