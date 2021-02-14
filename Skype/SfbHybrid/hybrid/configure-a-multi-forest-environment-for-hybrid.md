---
title: Implantar uma topologia de floresta de recursos
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: As seções a seguir fornecem orientações sobre como configurar um ambiente com várias florestas em um modelo de floresta de recurso/usuário para fornecer a funcionalidade do Skype for Business em um cenário híbrido.
ms.openlocfilehash: cf3a162001756661afd0f204e9968713d9db0f5b
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221475"
---
# <a name="deploy-a-resource-forest-topology"></a>Implantar uma topologia de floresta de recursos
 
As seções a seguir fornecem orientações sobre como configurar um ambiente com várias florestas em um modelo de floresta de recurso/usuário para fornecer a funcionalidade do Skype for Business em um cenário híbrido. 
  
![Ambiente de várias florestas para híbridos](../../sfbserver/media/5f079435-b252-4a6a-9638-3577d55b2873.png)
  
## <a name="topology-requirements"></a>Requisitos de topologia

Há suporte para várias florestas de usuários. Lembre-se do seguinte: 
    
- Para versões suportadas do Lync Server e do [](plan-hybrid-connectivity.md#server-version-requirements) Skype for Business Server em uma configuração híbrida, consulte Requisitos de versão do servidor em Planejar conectividade híbrida entre o Skype for Business Server e o [Microsoft 365 ou Office 365.](plan-hybrid-connectivity.md)
    
- O Exchange Server pode ser implantado em uma ou mais florestas, o que pode ou não incluir a floresta que contém o Skype for Business Server. Certifique-se de que você aplicou a atualização cumulativa mais recente.
    
- Para obter detalhes sobre a co-existência com o Exchange Server, incluindo critérios de [](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support) suporte e limitações em várias combinações de local e online, consulte Suporte a recursos em Plano para integrar o Skype for Business e o [Exchange.](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)
    
  
## <a name="user-homing-considerations"></a>Considerações sobre a localização do usuário

Os usuários do Skype for Business que estão no local podem ter o Exchange instalado no local ou online. Os usuários do Skype for Business Online devem usar o Exchange Online para uma experiência ideal; no entanto, isso não é necessário. O Exchange local não é necessário para implementar o Skype for Business em ambos os casos.
  
## <a name="configure-forest-trusts"></a>Configurar confianças de floresta

Em uma topologia de floresta de recursos, as florestas de recursos que hospedam o Skype for Business Server devem confiar em cada floresta de conta que contenha contas de usuários que irão acessá-la. Se você tiver várias florestas de usuários, para habilitar a autenticação entre florestas, é importante que o Roteamento de Sufixo de Nome seja habilitado para cada uma dessas confianças de floresta. Para obter instruções, consulte [Gerenciando confianças de floresta.](https://technet.microsoft.com/library/cc772440.aspx) Se você tiver o Exchange Server implantado em uma outra floresta e ele fornece funcionalidade para usuários do Skype for Business, a floresta que hospeda o Exchange deve confiar na floresta que hospeda o Skype for Business Server. Por exemplo, se o Exchange foi implantado na floresta da conta, isso efetivamente significa uma confiança de duas vias entre a conta e as florestas do Skype for Business é necessária nessa configuração.
  
## <a name="synchronize-accounts-into-the-forest-hosting-skype-for-business"></a>Sincronizar contas na floresta que hospeda o Skype for Business

Quando o Skype for Business Server é implantado em uma floresta (uma floresta de recursos), mas fornece funcionalidade aos usuários em uma ou mais florestas (florestas de contas), os usuários nas outras florestas devem ser representados como objetos de usuário desabilitados na floresta onde o Skype for Business Server está implantado. Um produto de gerenciamento de identidade, como o Microsoft Identity Manager, precisa ser implantado e configurado para provisionar e sincronizar os usuários das florestas de conta na floresta onde o Skype for Business Server está implantado. Os usuários devem ser sincronizados na floresta que hospeda o Skype for Business Server como objetos de usuário desabilitados. Os usuários não podem ser sincronizados como objetos de contato do Active Directory, pois o Azure Active Directory Connect não sincroniza corretamente os contatos no Azure AD para uso com o Skype.
  
Independentemente de qualquer configuração de várias florestas, a floresta que hospeda o Skype for Business Server também pode fornecer funcionalidade para todos os usuários habilitados que existam na mesma floresta.
  
Para obter a sincronização de identidade adequada, os seguintes atributos precisam ser sincronizados: 
  
|**Florestas de usuários**|**Florestas de recursos**|
|:-----|:-----|
|atributo de link de conta escolhido  <br/> |atributo de link de conta escolhido  <br/> |
|email  <br/> |email  <br/> |
|ProxyAddresses  <br/> |ProxyAddresses  <br/> |
|ObjectSID  <br/> |msRTCSIP-OriginatorSID  <br/> |
   
O [atributo de link da conta escolhida](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts) será usado como âncora de origem. Se você tiver um atributo diferente e imutável que prefira usar, poderá fazê-lo; apenas certifique-se de editar a regra de declarações do AD FS e selecionar o atributo durante a configuração do AAD Connect.
  
Não sincronize os UPNs entre as florestas. Descobrimos durante o teste que precisamos usar um UPN exclusivo para cada floresta de usuário, pois você não pode usar o mesmo UPN em várias florestas. Como resultado, duas possibilidades foram apresentadas para sincronizar o UPN ou não sincronizar. 
  
- Se o UPN exclusivo de cada floresta de usuário não tiver sido sincronizado com o objeto desabilitado associado na floresta de recursos, o SSO (single sign-on) será desfeito pelo menos para a tentativa de login inicial (supondo que o usuário tenha selecionado a opção de salvar senha). No cliente Skype for Business, presumimos que os valores SIP/UPN sejam os mesmos. Como o endereço SIP neste cenário é user@company.com, mas o UPN do objeto habilitado na floresta do usuário é, na verdade, user@contoso.company.com, a tentativa de logon inicial falhará e o usuário será solicitado a inserir credenciais. Ao inserir o UPN correto/real, a solicitação de autenticação seria concluída em relação aos controladores de domínio na floresta do usuário, e a entrada seria bem-sucedida.
    
- Se o UPN exclusivo de cada floresta de usuário tiver sido sincronizado com o objeto desabilitado associado na floresta de recursos, a autenticação do AD FS falhará. A regra correspondente encontrará o UPN no objeto na floresta de recursos, que foi desabilitado e não pôde ser usado para autenticação. 
    
## <a name="create-a-microsoft-365-or-office-365-organization"></a>Criar uma organização do Microsoft 365 ou Office 365

Em seguida, você precisará provisionar uma organização do Microsoft 365 ou Office 365 para usar com sua implantação. Para saber mais, confira [Assinaturas, licenças, contas e locatários para ofertas de nuvem da Microsoft.](https://docs.microsoft.com/office365/enterprise/subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings) 
  
## <a name="configure-active-directory-federation-services"></a>Configurar os Serviços de Federação do Active Directory (AD FS)

Depois de ter um locatário, você precisará configurar os Serviços de Federação do Active Directory (AD FS) em cada uma das florestas de usuários. Supõe-se que você tenha um SIP e um endereço SMTP exclusivos e um UPN (Nome UpN) para cada floresta. O AD FS é opcional e é usado aqui para obter o SSO (single sign-on). DirSync com sincronização de senha também é suportado e também pode ser usado no lugar do AD FS. 
  
Somente implantações com SIP/SMTP e UPNs correspondentes foram testadas. Não ter SIP/SMTP/UPNs correspondentes pode resultar em funcionalidade reduzida, como problemas com integração do Exchange e SSO. 
  
A menos que você use um SIP/SMTP/UPN exclusivo para os usuários de cada floresta, você ainda pode ter problemas de SSO, independentemente de onde o AD FS está implantado: 
  
- Confianças de uma ou duas vias entre florestas de recursos/usuários com o farm do AD FS implantado em cada floresta de usuário, todos os usuários compartilham um domínio SIP/SMTP comum, mas um UPN exclusivo para cada floresta de usuário. 
    
- Confianças de duas vias entre florestas de recurso/usuário com o farm do AD FS implantado somente na floresta de recursos, todos os usuários compartilham o domínio SIP/SMTP comum, mas o UPN exclusivo para cada floresta de usuário. 
    
Ao colocar um farm do AD FS em cada floresta de usuário e usar um SIP/SMTP/UPN exclusivo para cada floresta, resolveremos ambos os problemas. Somente as contas nessa floresta de usuário específica seriam pesquisadas e correspondedas durante as tentativas de autenticação. Isso ajudará a fornecer um processo de autenticação mais contínuo. 
  
Esta será uma implantação padrão do Windows Server 2012 R2 AD FS e deve estar funcionando antes de continuar. Para obter instruções, [consulte Como instalar o AD FS 2012 R2 para Microsoft 365 ou Office 365.](https://blogs.technet.com/b/rmilne/archive/2014/04/28/how-to-install-adfs-2012-r2-for-office-365.aspx) 
  
Depois de implantado, você terá que editar a regra de declarações para corresponder à Âncora de Origem selecionada anteriormente. In the AD FS MMC, under Relying Party Trusts, right-click **Microsoft 365 Identity Platform** or Microsoft Office **365 Identity Platform**, and then select Edit Claim **Rules**. Edite a primeira regra e altere ObjectSID para **employeeNumber**. 
  
![Tela Editar Regras de Várias Florestas](../../sfbserver/media/f5d485bd-52cc-437f-ba71-217f8902056c.png)
  
## <a name="configure-aad-connect"></a>Configurar o AAD Connect

Em topologias de floresta de recursos, é necessário que os atributos do usuário da floresta de recursos e de qualquer floresta de conta sejam sincronizados no Azure AD. A maneira mais simples e recomendada de fazer isso é fazer o Azure AD Connect sincronizar e mesclar identidades de usuário de todas as florestas que tenham contas de usuário habilitadas e a floresta que contém o Skype for Business.  Para obter detalhes, [consulte Configurar o Azure AD Connect para o Skype for Business e o Teams.](configure-azure-ad-connect.md)

Observe que o AAD Connect não fornece sincronização local entre a conta e florestas de recursos. Isso deve ser configurado separadamente usando o Microsoft Identity Manager ou produto semelhante, conforme descrito anteriormente.
  
Quando terminar e o AAD Connect estiver mesclando, se você olhar para um objeto no metaverso, verá algo semelhante a isso: 
  
![Tela do objeto Metaverso de várias florestas](../../sfbserver/media/16379880-2de3-4c43-b219-1551f5dec5f6.png)
  
Os atributos verdes realçados foram mesclados do Microsoft 365 ou Office 365, os amarelos são da floresta do usuário e o azul é da floresta de recursos. 
  
Este é um usuário de teste, e você pode ver que o AAD Connect identificou o sourceAnchor e o cloudSourceAnchor do usuário e os objetos de floresta de recursos do Microsoft 365 ou Office 365, no nosso caso 1101, que é o employeeNumber selecionado anteriormente. Em seguida, ele foi capaz de mesclar esse objeto com o que você vê acima. 
  
Para saber mais, confira [Integrar seus diretórios locais com o Azure Active Directory.](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/) 
  
O AAD Connect deve ser instalado usando os padrões, exceto os seguintes: 
  
1. Single sign-in - with AD FS already deployed and working: Select **Do not configure**.
    
2. Conecte seus diretórios: Adicione todos os domínios.
    
3. Identifique os usuários em diretórios locais: selecione as identidades de usuário existentes em vários diretórios e selecione os atributos **ObjectSID** e **msExchangeMasterAccountSID.**
    
4. Identificar usuários no Azure AD: Âncora de origem: selecione o atributo escolhido após ler Selecionando um bom atributo [sourceAnchor](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts#selecting-a-good-sourceanchor-attribute), Nome Principal do Usuário - **userPrincipalName**.
    
5.  Recursos opcionais: selecione se você implantou o Exchange híbrido.
    
    > [!NOTE]
    >  Se você tiver apenas o Exchange Online, pode haver um problema com falhas OAuth durante a descoberta automática devido ao redirecionamento CNAME. Para corrigir isso, você precisará definir a URL de Descoberta Automática do Exchange executando o seguinte cmdlet do Shell de Gerenciamento do Skype for Business Server:
    >
    > ```powershell
    > Set-CsOAuthConfiguration -ExchangeAutoDiscoverURL https://autodiscover-s.outlook.com/autodiscover/autodiscover.svc 
    > ```
    
6.  Farm do AD FS: selecione Usar um farm existente do **Windows Server 2012 R2 AD FS** e insira o nome do servidor do AD FS.
    
7.  Finalize o assistente e execute as validações necessárias.
    
## <a name="configure-hybrid-connectivity-for-skype-for-business-server"></a>Configurar conectividade híbrida para o Skype for Business Server

Siga as práticas recomendadas para configurar o Skype for Business híbrido. Para obter mais informações, consulte [Planejar conectividade híbrida e](plan-hybrid-connectivity.md) configurar a conectividade [híbrida.](configure-hybrid-connectivity.md) 
  
## <a name="configure-hybrid-connectivity-for-exchange-server"></a>Configurar conectividade híbrida para o Exchange Server

Se necessário, siga as práticas recomendadas para configurar o Exchange híbrido. Para obter mais informações, consulte [Implantações Híbridas do Exchange Server.](https://docs.microsoft.com/exchange/exchange-hybrid) 
  
