---
title: Configurar a integração do Cloud Connector com seu locatário do Office 365
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Hybrid
ms.assetid: 0e2f2395-b890-4d16-aa2d-99d52438b89c
description: Saiba como configurar a integração do Cloud Connector com seu locatário do Office 365.
ms.openlocfilehash: c8e74353bc9b1201d8e4ff11f27a3542f24cb373
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-cloud-connector-integration-with-your-office-365-tenant"></a>Configurar a integração do Cloud Connector com seu locatário do Office 365
 
Saiba como configurar a integração do Cloud Connector com seu locatário do Office 365.
  
Ao concluir a instalação do Skype for Business Cloud Connector Edition, realize o procedimento apresentado nesta seção para configurar sua implantação e conectá-la a seu locatário do Office 365.
  
## <a name="configure-firewall-settings"></a>Definir as configurações do firewall

Defina as configurações de firewall para as suas configurações de firewall interno e externo para a rede de perímetro abrir as portas necessárias, conforme descrito em [portas e protocolos](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) no [Planejar Skype para o conector de nuvem Business Edition](plan-skype-for-business-cloud-connector-edition.md).
  
## <a name="set-up-public-switched-telephone-network-pstn-gateways"></a>Gateways de PSTN (Rede Telefônica Pública Comutada)

Configure os troncos em cada gateway PSTN para que eles apontem para os Servidores de Mediação de todos os aplicativos. Como o FQDN do pool é o mesmo para todos os servidores no pool, cada tronco deve apontar para o endereço IP ou FQDN do Servidor de Mediação e não para o FQDN do pool do Servidor de Mediação. Os troncos devem ser definidos com a mesma prioridade.
  
Se você usa o protocolo TLS entre os Servidores de Mediação e os gateways, é necessário configurá-los para dar suporte a MTLS, da seguinte maneira:
  
1. Exporte a Autoridade de Certificação raiz do computador que executa o Active Directory do Cloud Connector.
    
2. Siga as instruções do fornecedor do gateway PSTN para importar a AC raiz.
    
3. Importe o Certificado de Autoridade de Certificação raiz emitido para seu gateway nos Servidores de Mediação. Para obter um certificado SSL para o gateway, use o serviço da Autoridade de Certificação em execução no computador do Active Directory do Cloud Connector, da seguinte maneira:
    
  - Modifique o modelo do servidor web existente para permitir que os usuários autenticados se inscrevam ou crie um novo modelo de servidor web para configurar outras propriedades e permitir que os usuários autenticados se inscrevam. Para obter instruções detalhadas, consulte [Modelos de certificado](https://technet.microsoft.com/en-us/library/cc730705.aspx).
    
  - Solicite um certificado usando o snap-in certificado selecionando o modelo de servidor Web que você habilitou. Certifique-se de adicionar o nome comum no assunto e o nome DNS no nome alternativo com o FQDN do gateway e confirmar a chave privada que tornam a chave privada exportável está selecionada em Opções de chave. Para obter instruções detalhadas, consulte [solicitar um certificado](https://technet.microsoft.com/en-us/library/cc730689.aspx).
    
4. Exporte o certificado SSL com a chave privada e siga as instruções do fornecedor do gateway PSTN para importar o certificado.
    
## <a name="update-the-domain-for-your-tenant"></a>Atualizar o domínio do locatário

Confira se você concluiu as etapas de atualização de seu domínio no Office 365 e se é capaz de adicionar registros DNS. Para obter mais informações sobre como configurar seu domínio no Office 365, consulte [vídeo: configurar seu domínio no Office 365](https://support.office.com/en-us/article/Video-Set-up-your-domain-in-Office-365-703dfec1-882d-4e33-b647-937f731887b7?ui=en-US&amp;rs=en-US&amp;ad=US).
  
## <a name="add-dns-records-in-office-365-for-your-edge"></a>Adicionar registros DNS ao Office 365 para borda

Adicione os seguintes registros DNS a seu locatário do Office 365. Para obter informações sobre como adicionar registros DNS para seu locatário do Office 365, consulte [Adicionar ou editar registros DNS personalizados no Office 365](https://support.office.com/en-us/article/Add-or-edit-custom-DNS-records-in-Office-365-AF00A516-DD39-4EDA-AF3E-1EAF686C8DC9?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).
  
1. Adicionar um registro DNS A à Borda de Acesso
    
2. Os registros SRV serão criados automaticamente pelo Office 365 e os scripts de implantação. Confira se é possível pesquisar os dois serviços SIP a seguir na Borda: _sip and _sipfederationtls.
    
     ![Confirmação de registros SRV](../../media/3c353a29-6dcc-4ed3-98db-3a6bed3e929e.png)
  
## <a name="set-up-hybrid-connectivity-between-cloud-connector-edition-and-office-365"></a>Configure a conectividade híbrida entre o Cloud Connector Edition e o Office 365

Para configurar a conectividade híbrida entre seu Skype para implantação do conector de nuvem Business Edition e seu locatário do Office 365, execute o seguinte cmdlet em uma sessão PowerShell remota. Para saber como estabelecer uma sessão PowerShell remota, consulte: [Using Windows PowerShell para gerenciar Skype para negócios Online](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).
  
O cmdlet define o FQDN externo da Borda de Acesso. No primeiro dos comandos, o \<FQDN de borda de acesso externo\> deve ser um para a função de borda de acesso SIP. Por padrão, este deve ser ap.\<nome de domínio\>.
  
```
Set-CsTenantHybridConfiguration -PeerDestination <External Access Edge FQDN> -UseOnPremDialPlan $false
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $True
```

> [!NOTE]
> O FQDN de borda de acesso externo usados para o destino de ponto deve ser definido como um site PSTN que será usado apenas como fallback no caso de um usuário não for atribuído a um site PSTN. Para obter mais informações, consulte [implantar um único site no conector de nuvem](deploy-a-single-site-in-cloud-connector.md) e [implantar vários sites em nuvem de conector](deploy-multiple-sites-in-cloud-connector.md). 
  
## <a name="set-up-pstn-gateways"></a>Configurar gateways PSTN

Configure os troncos em cada gateway PSTN para que eles apontem para os Servidores de Mediação de todos os dispositivos. Cada tronco deve apontar para o endereço IP ou FQDN do Servidor de Mediação e não para o FQDN do pool do Servidor de Mediação, pois o FQDN do pool é o mesmo para todos os servidores no pool. Os troncos devem ser definidos com a mesma prioridade.
  
Se você usa o protocolo TLS entre os Servidores de Mediação e os gateways, é necessário configurá-los para dar suporte a MTLS, da seguinte maneira:
  
1. Exporte a Autoridade de Certificação raiz do computador que executa o Active Directory do Cloud Connector.
    
2. Siga as instruções do fornecedor do gateway PSTN para importar a AC raiz.
    
3. Importe o Certificado de Autoridade de Certificação raiz emitido para seu gateway nos Servidores de Mediação. Para obter um certificado SSL para o gateway, use o serviço da Autoridade de Certificação em execução no computador do Active Directory do Cloud Connector, da seguinte maneira:
    
  - Modificar o modelo de servidor Web existente para permitir que os usuários autenticados registrar ou criar um novo modelo de servidor Web para configurar outras propriedades e permitir que os usuários autenticados que se inscrevam. Para obter instruções detalhadas, consulte [Modelos de certificado](https://technet.microsoft.com/library/cc730705.aspx).
    
  - Solicite um certificado usando o snap-in certificado selecionando o modelo de servidor Web que você habilitou. Certifique-se de adicionar o nome comum no assunto e o nome DNS no nome alternativo com o FQDN do gateway e confirmar a chave privada que tornam a chave privada exportável está selecionada em Opções de chave. Para obter instruções detalhadas, consulte [solicitar um certificado](https://technet.microsoft.com/library/cc730689.aspx).
    
4. Exporte o certificado SSL com a chave privada e siga as instruções do fornecedor do gateway PSTN para importar o certificado.
    
5. Os gateways PSTN em cada site PSTN devem se conectar apenas aos Servidores de Mediação no mesmo site.
    
## <a name="set-up-your-users-in-office-365"></a>Configurar usuários no Office 365

Faça logon no portal de administração do Office 365, adicione os usuários que serão habilitados para serviços de voz online e atribua a licença E5 ou o complemento do Sistema de Telefonia do Office 365 à licença E3 para esses usuários. Para obter informações sobre como adicionar usuários, consulte [Adicionar usuários para o Office 365 para empresas](https://support.office.com/en-US/article/Add-users-to-Office-365-for-business-435ccec3-09dd-4587-9ebd-2f3cad6bc2bc).
  
## <a name="enable-users-for-phone-system-in-office-365-voice-and-voicemail-services"></a>Habilitar usuários para os serviços de voz e de caixa postal do Sistema de Telefonia do Office 365

Depois de adicionar os usuários ao Office 365, habilite suas contas para os serviços de voz do Sistema de Telefonia do Office 365, incluindo a caixa postal. Para habilitar essas funcionalidades, faça logon no locatário do Office 365 usando uma conta com função de Administrador Global do Office 365 e que seja capaz de executar o PowerShell remoto. Para saber como estabelecer uma sessão PowerShell remota, consulte: [Using Windows PowerShell para gerenciar Skype para negócios Online](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx)
  
- Atribuir a política ao usuário e configure voz número de telefone comercial do usuário, que você especificar com o valor do parâmetro **Identity** :
    
  ```
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI <tel:+phonenumber>
  ```

    > [!NOTE]
    > Você também pode especificar a identidade do usuário pelo endereço SIP, nome UPN, nome de domínio e nome de usuário (domínio\nome de usuário) e nome de exibição no Active Directory ("Diogo Martins").  
  
Em seguida, é possível verificar se os usuários foram adicionados e habilitados usando o seguinte script:
  
```
# Input the user name you want to verify
$user = Get-CsOnlineUser <User name>

# For a hybrid user, the value of $user.EnterpriseVoiceEnabled should be True
$user.EnterpriseVoiceEnabled

# For a hybrid user, the value of $user.HostedVoiceMail should be True
$user.HostedVoiceMail

# For a hybrid user, the value of $user.VoicePolicy should be "HybridVoice"
$user.VoicePolicy
```

Você deverá decidir se os usuários poderão ou não fazer chamadas internacionais. Por padrão, as chamadas internacionais são permitidas. As chamadas internacionais podem ser habilitadas ou desabilitadas para os usuários no Centro de Administração online do Skype for Business.
  
Para desabilitar as chamadas internacionais por usuário, execute o seguinte cmdlet no Powershell do Skype for Business Online:
  
```
Grant-CsVoiceRoutingPolicy -PolicyName InternationalCallsDisallowed -Identity $user
```

Para reabilitar internacional chamar em uma base por usuário depois que ele tiver sido desabilitado, execute o cmdlet mesmo, mas altere o valor de **PolicyName** para *InternationalCallsAllowed* .
  
## <a name="assign-users-to-pstn-sites"></a>Atribuir usuários a sites PSTN

Use o PowerShell remoto do locatário para atribuir o site aos usuários, mesmo que você tenha implantado um único site. Para saber como estabelecer uma sessão PowerShell remota, consulte: [Using Windows PowerShell para gerenciar Skype para negócios Online](https://technet.microsoft.com/en-us/library/dn362831%28v=ocs.15%29.aspx).
  
```
# Set the site to users
Set-CsUserPstnSettings -Identity <User Name> -HybridPstnSite <PSTN Site Name>

# Review the site setting for a user
Get-CsUserPstnSettings -Identity <User Name> 

# See all the user settings in one tenant
Get-CsOnlineUser | Get-CsUserPstnSettings
```

> [!NOTE]
> Se nenhum site PSTN estiver atribuído a um usuário, será feito fallback da conectividade híbrida entre a implantação do Skype for Business Cloud Connector Edition e seu locatário do Office 365 para usar o nível de locatário padrão um (destino par) de modo a possibilitar a realização de chamadas. 
  
## <a name="configure-online-hybrid-mediation-server-settings"></a>Definir configurações do servidor de mediação híbrido online
<a name="BKMK_ConfigureMediationServer"> </a>

Quando uma chamada de P2P será escalonada para uma conferência PSTN, o Skype para o servidor de conferência Business Online enviará um convite para o servidor de mediação do conector de nuvem. Para garantir que o Office 365 pode direcionar a esse convite com êxito, você precisa definir uma configuração no seu locatário online para cada servidor de mediação do conector de nuvem da seguinte maneira: 
  
1. Crie um usuário no portal de administração do O365. Usar qualquer nome de usuário que você deseja, como "MediationServer1".
    
    Use o domínio SIP padrão do conector de nuvem (o primeiro domínio SIP do arquivo. ini) como o domínio do usuário.
    
    Não atribua nenhuma licença do O365 (como a E5) à conta criada. Espere a conclusão da sincronização do AD do O365.
    
2. Iniciar uma sessão de PowerShell remota do inquilino usando suas credenciais de administrador de locatário e execute o seguinte cmdlet para definir o servidor de mediação e o FQDN do servidor de borda para o usuário da conta, substituir \<DisplayName\> com o nome de exibição do usuário para o conta criada:
    
  ```
  Set-CsHybridMediationServer -Identity <DisplayName> -Fqdn <MediationServerFQDN> -AccessProxyExternalFqdn <EdgeServerExternalFQDN>
  ```

    Para identificação, use o Nome de Exibição da conta do usuário do Office 365 criada para este Servidor de Mediação.
    
    Para *MediationServerFQDN* , use o FQDN interno definido para seu servidor de mediação.
    
    Para *EdgeServerExternalFQDN* , use o FQDN externo definido para o Proxy de acesso do servidor de borda. Se houver vários sites PSTN do Cloud Connector, escolha o FQDN do Proxy de Acesso do Servidor de Borda atribuído ao site que contém a localização do Servidor de Mediação.
    
3. Se houver vários Servidores de Mediação do Cloud Connector (vários sites, alta disponibilidade), repita as etapas anteriores para cada um deles.
    

