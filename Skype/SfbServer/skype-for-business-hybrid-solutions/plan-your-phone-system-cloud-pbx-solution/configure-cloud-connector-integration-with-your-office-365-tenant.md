---
title: Configurar a integração do Cloud Connector com seu locatário do Office 365
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
description: Saiba como configurar a integração do Cloud Connector com seu locatário do Office 365.
ms.openlocfilehash: cf683743064ec377c827fe0c52a59e464f65ae19
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050203"
---
# <a name="configure-cloud-connector-integration-with-your-office-365-tenant"></a>Configurar a integração do Cloud Connector com seu locatário do Office 365
 
Saiba como configurar a integração do Cloud Connector com seu locatário do Office 365.
  
Depois que a instalação do Skype for Business Cloud Connector Edition estiver concluída, execute as etapas desta seção para configurar sua implantação e conectá-la ao seu locatário do Office 365.
  
## <a name="configure-firewall-settings"></a>Configurar definições de firewall

Defina as configurações de firewall para suas configurações de firewall internas e externas para sua rede de perímetro para abrir as portas necessárias descritas em [portas e protocolos](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) em [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md).
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a>Configurar gateways PSTN (rede telefônica pública comutada)

Configure troncos em cada gateway PSTN para apontar de volta para servidores de mediação para todos os dispositivos. Como o FQDN do pool é o mesmo para todos os servidores no pool, cada tronco deve apontar para um FQDN do servidor de mediação ou endereço IP em vez do FQDN do pool do servidor de mediação. Os troncos devem ser definidos com a mesma prioridade.
  
Se você estiver usando o TLS entre servidores de mediação e gateways, será necessário configurar os gateways e os servidores de mediação para suportar MTLS da seguinte maneira:
  
1. Exporte a autoridade de certificação raiz do computador do Active Directory do Cloud Connector.
    
2. Siga as instruções do fornecedor do gateway PSTN para importar a AC raiz.
    
3. Importe o certificado de autoridade de certificação raiz do certificado emitido para o seu gateway nos servidores de mediação. Se for necessário obter um certificado SSL para o gateway, você poderá fazer isso usando o serviço da autoridade de certificação em execução no computador do Active Directory do Cloud Connector, da seguinte maneira:
    
   - Modifique o modelo de servidor Web existente para permitir que os usuários autenticados se inscrevam ou criem um novo modelo de servidor Web para configurar outras propriedades e permitir que os usuários autenticados se inscrevam. Para obter instruções detalhadas, consulte [Certificate Templates](https://technet.microsoft.com/library/cc730705.aspx).
    
   - Solicitar um certificado usando snap-in de certificado selecionando o modelo de servidor Web que você habilitou. Certifique-se de adicionar o nome comum ao nome de entidade e DNS em nome alternativo com FQDN do gateway e confirme se a chave privada que torna a chave privada exportável está selecionada em opções de chave. 
    
4. Exporte o certificado SSL com a chave privada e siga as instruções do seu fornecedor de gateway PSTN para importar o certificado.
    
## <a name="update-the-domain-for-your-tenant"></a>Atualizar o domínio para o locatário

Certifique-se de ter concluído as etapas para atualizar seu domínio no Office 365 e ter a capacidade de adicionar registros DNS. Para obter mais informações sobre como configurar seu domínio no Office 365, consulte [Adicionar um domínio ao office 365](https://support.office.com/article/Add-a-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
  
## <a name="add-dns-records-in-office-365-for-your-edge"></a>Adicionar registros DNS no Office 365 para sua borda

Adicione os seguintes registros DNS ao seu locatário do Office 365. Para obter informações sobre como adicionar registros DNS ao seu locatário do Office 365, consulte [Adicionar ou editar registros DNS personalizados no Office 365](https://support.office.com/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).
  
1. Adicionar um registro DNS A para borda de acesso.
    
2. Os registros SRV serão criados automaticamente pelo Office 365 e os scripts de implantação. Confirme que você pode pesquisar os dois serviços SIP a seguir na borda: _sip e _sipfederationtls.
    
     ![Confirmação de registros SRV](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-office-365"></a>Configurar a conectividade híbrida entre o Cloud Connector Edition e o Office 365

Para configurar a conectividade híbrida entre sua implantação do Skype for Business Cloud Connector Edition e seu locatário do Office 365, execute o cmdlet a seguir em uma sessão remota do PowerShell. Para saber como estabelecer uma sessão remota do PowerShell, consulte: [configurar seu computador para o Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx).
  
O cmdlet define o FQDN externo da borda de acesso. No primeiro dos comandos, o \<FQDN\> de borda de acesso externo deve ser aquele para a função de borda de acesso SIP. Por padrão, isso deve ser AP.\<nome\>do domínio.
  
```powershell
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> O FQDN de borda de acesso externo usado para o destino de par deve ser definido como um site PSTN que será usado apenas como fallback, caso um usuário não esteja atribuído a um site PSTN. Para obter mais informações, consulte [implantar um único site no Cloud Connector](deploy-a-single-site-in-cloud-connector.md) e [implantar vários sites no Cloud Connector](deploy-multiple-sites-in-cloud-connector.md). 
  
## <a name="set-up-pstn-gateways"></a>Configurar gateways PSTN

Configure troncos em cada gateway PSTN para apontar de volta para servidores de mediação para todos os dispositivos. Cada tronco deve apontar para um FQDN do servidor de mediação ou endereço IP em vez do FQDN do pool do servidor de mediação porque o FQDN do pool é o mesmo para todos os servidores do pool. Os troncos devem ser definidos com a mesma prioridade.
  
Se você estiver usando o TLS entre servidores de mediação e gateways, será necessário configurar os gateways e os servidores de mediação para suportar MTLS da seguinte maneira:
  
1. Exporte a autoridade de certificação raiz do computador do Active Directory do Cloud Connector.
    
2. Siga as instruções do fornecedor do gateway PSTN para importar a AC raiz.
    
3. Importe o certificado de autoridade de certificação raiz do certificado emitido para o seu gateway nos servidores de mediação. Se for necessário obter um certificado SSL para o gateway, você poderá fazer isso usando o serviço da autoridade de certificação em execução no computador do Active Directory do Cloud Connector, da seguinte maneira:
    
   - Modifique o modelo de servidor Web existente para permitir que os usuários autenticados se inscrevam ou criem um novo modelo de servidor Web para configurar outras propriedades e permitir que os usuários autenticados se inscrevam. Para obter instruções detalhadas, consulte [Certificate Templates](https://technet.microsoft.com/library/cc730705.aspx).
    
   - Solicitar um certificado usando snap-in de certificado selecionando o modelo de servidor Web que você habilitou. Certifique-se de adicionar o nome comum ao nome de entidade e DNS em nome alternativo com FQDN do gateway e confirme se a chave privada que torna a chave privada exportável está selecionada em opções de chave. 
    
4. Exporte o certificado SSL com a chave privada e siga as instruções do seu fornecedor de gateway PSTN para importar o certificado.
    
5. Os gateways PSTN em um site PSTN só devem se conectar ao (s) servidor (es) de mediação no mesmo site.
    
## <a name="set-up-your-users-in-office-365"></a>Configurar seus usuários no Office 365

Faça logon no portal de administração do Office 365, adicione os usuários que serão habilitados para serviços de voz online e atribua uma licença E5 ou sistema de telefonia no Office 365 complemento à licença E3 para esses usuários. Para obter informações sobre como adicionar usuários, consulte [Adicionar usuários ao Office 365 for Business](https://support.office.com/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).
  
## <a name="enable-users-for-phone-system-in-office-365-voice-and-voicemail-services"></a>Habilitar usuários para o sistema de telefonia no Office 365 voz e serviços de caixa postal

Depois de adicionar os usuários ao Office 365, habilite suas contas de sistema de telefonia no Office 365 Voice Services, incluindo a caixa postal. Para habilitar esses recursos, você deve fazer logon no locatário do Office 365 com uma conta que seja uma função de administrador global do Office 365 e poder executar o PowerShell remoto. Para saber como estabelecer uma sessão remota do PowerShell, consulte: [configurar seu computador para o Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx)
  
- Atribua a política ao usuário e configure o número de telefone comercial do usuário, que você especifica com o valor do parâmetro **Identity** :
    
  ```powershell
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > Uma identidade de usuário pode ser especificada usando o endereço SIP do usuário, o nome do usuário principal (UPN) ou o nome de exibição do Active Directory do usuário (por exemplo, "Bob Kelly"). O caractere asterisco\*() também pode ser usado com o nome de exibição como a identidade do usuário. Por exemplo, a identidade "\*Smith" retorna todos os usuários que têm um nome de exibição que termina com o valor de cadeia de caracteres "Smith".
  
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

Você precisará decidir se seus usuários devem ser capazes de fazer chamadas internacionais. Por padrão, a chamada internacional está habilitada. Você pode desabilitar ou habilitar usuários para discagem internacional usando o centro de administração do Skype for Business online.
  
Para desabilitar a chamada internacional em uma base por usuário, execute o seguinte cmdlet no PowerShell do Skype for Business Online:
  
```powershell
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

Para habilitar novamente a chamada internacional por usuário depois que ela tiver sido desabilitada, execute o mesmo cmdlet, mas altere o valor de **PolicyName** para *InternationalCallsAllowed* .
  
## <a name="assign-users-to-pstn-sites"></a>Atribuir usuários a sites PSTN

Use o PowerShell remoto do locatário para atribuir um site aos usuários, mesmo se você implantou apenas um único site. Para saber como estabelecer uma sessão remota do PowerShell, consulte: [configurar seu computador para o Windows PowerShell](https://technet.microsoft.com/library/dn362831%28v=ocs.15%29.aspx).
  
```powershell
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> Se nenhum site PSTN for atribuído a um usuário, a conectividade híbrida entre sua implantação do Skype for Business Cloud Connector Edition e seu locatário do Office 365 será revertida para usar o padrão de nível de locatário (destino de par) para que as chamadas possam ser concluídas. 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a>Definir configurações do servidor de mediação híbrida online
<a name="BKMK_ConfigureMediationServer"> </a>

Quando uma chamada P2P é escalonada para uma conferência PSTN, o servidor de conferência do Skype for Business online enviará um convite para o servidor de mediação do Cloud Connector. Para garantir que o Office 365 possa encaminhar esse convite com êxito, você precisa definir uma configuração no seu locatário online para cada servidor de mediação do Cloud Connector da seguinte maneira: 
  
1. Crie um usuário no portal de administração do Office 365. Use o nome de usuário desejado, como "MediationServer1".
    
    Use o domínio SIP padrão do Cloud Connector (o primeiro domínio SIP no arquivo. ini) como o domínio do usuário.
    
    Observe que a atribuição de licenças só é necessária para a propagação do usuário no diretório do Skype for Business online. Atribuir licenças do Office 365 (como E5) à conta criada, permitir até uma hora para que as alterações sejam propagadas, verifique se as contas de usuário foram provisionadas corretamente para o diretório do Skype for Business online executando o cmdlet a seguir e remova o licença dessa conta.
    ```powershell
   Get-CsOnlineUser -Identity <UserPrincipalName>
   ```
    
2. Inicie uma sessão do PowerShell remoto do Azure AD do locatário usando suas credenciais de administrador global ou de usuário e execute o seguinte cmdlet para definir o departamento da conta de usuário do Azure AD configurada na etapa 1 como "HybridMediationServer":

   ```powershell
   Set-MsolUser -UserPrincipalName <UserPrincipalName> -Department "HybridMediationServer"
   ```

3. Inicie uma sessão do PowerShell remoto do Skype for Business locatário usando suas credenciais de administrador de locatário do Skype for Business e, em seguida, execute o seguinte cmdlet para definir o servidor de mediação e \<o\> FQDN do servidor de borda para essa conta de usuário, substituindo DisplayName pelo nome de exibição do usuário para a conta que você criou na etapa 1:
    
   ```powershell
   Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
   ```

    Para identidade, use o nome de exibição da conta de usuário do Office 365 que você criou para este servidor de mediação.
    
    Para o *MediationServerFQDN* , use o FQDN interno definido para o servidor de mediação.
    
    Para o *EdgeServerExternalFQDN* , use o FQDN externo definido para o proxy de acesso do servidor de borda. Se houver vários sites PSTN do Cloud Connector, escolha o FQDN do proxy de acesso do servidor de borda atribuído ao site onde o servidor de mediação está localizado.
    
4. Se houver vários servidores de mediação do Cloud Connector (vários sites, alta disponibilidade), repita as etapas anteriores para cada um deles.
    

