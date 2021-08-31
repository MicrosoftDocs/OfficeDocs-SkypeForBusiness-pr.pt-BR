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
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: As seções a seguir descrbiem como configurar um ambiente com várias florestas em um modelo de floresta de recurso/usuário para fornecer funcionalidade em um cenário híbrido.
ms.openlocfilehash: 5a6ca7c559a2c79979a44d8ca7c8555abf432b4d
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58727050"
---
# <a name="deploy-a-resource-forest-topology"></a>Implantar uma topologia de floresta de recursos

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

 
As seções a seguir descrevem como configurar um ambiente com várias florestas em um modelo de floresta de recurso/usuário para fornecer funcionalidade em um cenário híbrido. 
  
![Ambiente de várias florestas para híbridos.](../../sfbserver/media/5f079435-b252-4a6a-9638-3577d55b2873.png)
  
## <a name="topology-requirements"></a>Requisitos de topologia

Há suporte para várias florestas de usuários. Lembre-se do seguinte: 
    
- Para versões com suporte do Lync Server e Skype for Business Server em uma configuração híbrida, consulte [Plan hybrid connectivity](plan-hybrid-connectivity.md).
    
- Exchange Server pode ser implantado em uma ou mais florestas, que podem ou não incluir a floresta que contém Skype for Business Server. Certifique-se de ter aplicado a atualização cumulativa mais recente.
    
- Para obter detalhes sobre a co-existência com o Exchange Server, incluindo critérios e limitações de suporte em várias combinações de locais e online, consulte [Suporte](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support) a recursos em [Plan to integrate Skype for Business and Exchange](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).
    
  
## <a name="user-homing-considerations"></a>Considerações sobre a localização do usuário

Skype for Business usuários que estão no local podem ter Exchange no local ou online. Teams os usuários devem usar Exchange Online para uma experiência ideal; no entanto, isso não é necessário. Exchange local não é necessário implementar Skype for Business em ambos os casos.
  
## <a name="configure-forest-trusts"></a>Configurar confianças de floresta

Em uma topologia de floresta de recursos, as florestas de recursos que hospedam Skype for Business Server devem confiar em cada floresta de conta que contém as contas dos usuários que a acessarão. 

Se você tiver várias florestas de usuários, para habilitar a autenticação entre florestas, é importante que o Roteamento de Sufixo de Nome seja habilitado para cada uma dessas confianças de floresta. Para obter instruções, consulte [Managing Forest Trusts](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772440(v=ws.11)). 

Se você tiver Exchange Server implantado em uma outra floresta e o Exchange fornece funcionalidade para usuários Skype for Business, o Exchange de hospedagem da floresta deve confiar na Skype for Business Server. Por exemplo, se Exchange foram implantados na floresta de conta, uma confiança de duas vias entre a conta e as florestas Skype for Business é necessária.
  
## <a name="synchronize-accounts-into-the-forest-hosting-skype-for-business"></a>Sincronizar contas no site de hospedagem de Skype for Business

Suponha Skype for Business Server seja implantado em uma floresta (uma floresta de recursos), mas fornece funcionalidade aos usuários em uma ou mais florestas (florestas de conta). Nesse caso, os usuários nas outras florestas devem ser representados como objetos de usuário desabilitados na floresta onde Skype for Business Server é implantado.

Você precisa usar um produto de gerenciamento de identidade, como Microsoft Identity Manager, para provisionar e sincronizar os usuários das florestas de conta na floresta onde o Skype for Business Server é implantado. Os usuários devem ser sincronizados na floresta que hospeda Skype for Business Server como objetos de usuário desabilitados. Os usuários não podem ser sincronizados como objetos de contato do Active Directory, porque Azure Active Directory Conexão não sincronizam corretamente os contatos no Azure AD para uso com Skype.
  
Independentemente de qualquer configuração de várias florestas, a Skype for Business Server de hospedagem de floresta também pode fornecer funcionalidade para todos os usuários habilitados que existam na mesma floresta.
  
Para obter a sincronização de identidade adequada, os seguintes atributos precisam ser sincronizados: 
  
|**Florestas de usuários**|**Florestas de recursos**|
|:-----|:-----|
|atributo de link de conta escolhido  <br/> |atributo de link de conta escolhido  <br/> |
|email  <br/> |email  <br/> |
|ProxyAddresses  <br/> |ProxyAddresses  <br/> |
|ObjectSID  <br/> |msRTCSIP-OriginatorSID  <br/> |
   
O [atributo de link de conta](/azure/active-directory/hybrid/plan-connect-design-concepts) escolhido será usado como Âncora de Origem. Se você tiver um atributo diferente e imutável que prefira usar, pode fazê-lo; basta editar a regra de declarações do AD FS e selecionar o atributo durante a configuração do AAD Conexão.
  
Não sincronize os UPNs entre as florestas. Você precisa usar um UPN exclusivo para cada floresta de usuário, pois não pode usar o mesmo UPN em várias florestas. Como resultado, há duas possibilidades: sincronizar o UPN ou não sincronizar. 
  
- Se o UPN exclusivo de cada floresta de usuário não estiver sincronizado com o objeto desabilitado associado na floresta de recursos, o SSO (login único) será quebrado para pelo menos a tentativa inicial de entrar (supondo que o usuário selecionou a opção para salvar a senha). No cliente Skype for Business, presumimos que os valores SIP/UPN sejam os mesmos. Como o endereço SIP neste cenário é user@company.com, mas o UPN do objeto habilitado na floresta do usuário é de fato user@contoso.company.com, a tentativa de logon inicial falharia e o usuário seria solicitado a inserir credenciais. Ao inserir o UPN correto, a solicitação de autenticação seria concluída em relação aos controladores de domínio na floresta do usuário, e a entrada seria bem-sucedida.
    
- Se o UPN exclusivo de cada floresta de usuário fosse sincronizado com o objeto desabilitado associado na floresta de recursos, a autenticação do AD FS falharia. A regra correspondente encontrará o UPN no objeto na floresta de recursos, que foi desabilitado e não pôde ser usado para autenticação. 
    
## <a name="create-a-microsoft-365-organization"></a>Criar uma Microsoft 365 de usuário

Você precisará provisionar uma organização Microsoft 365 para usar com sua implantação. Para obter mais informações, consulte [Assinaturas, licenças, contas e locatários](/office365/enterprise/subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings)para ofertas de nuvem da Microsoft. 
  
## <a name="configure-active-directory-federation-services"></a>Configurar os Serviços de Federação do Active Directory

Depois de ter um locatário, você precisará configurar os Serviços de Federação do Active Directory (AD FS) em cada uma das florestas do usuário. Isso supõe que você tenha um endereço SIP e SMTP exclusivo e Um Nome de Entidade de Usuário (UPN) para cada floresta. O AD FS é opcional e é usado aqui para obter SSO (sign-on único). DirSync com Sincronização de Senhas também é suportado e também pode ser usado no lugar do AD FS. 
  
Somente implantações com SIP/SMTP e UPNs correspondentes foram testadas. Não ter SIP/SMTP/UPNs correspondentes pode resultar em funcionalidade reduzida, como problemas com Exchange integração e SSO. 
  
A menos que você use um SIP/SMTP/UPN exclusivo para usuários de cada floresta, você ainda pode executar problemas de SSO, independentemente de onde o AD FS está implantado: 
  
- Confianças únicas ou de duas vias entre florestas de recursos/usuários com o farm do AD FS implantado em cada floresta de usuários, todos os usuários compartilham domínio SIP/SMTP comum, mas UPN exclusivo para cada floresta de usuário. 
    
- Confianças de duas vias entre florestas de recursos/usuários com o farm do AD FS implantado somente na floresta de recursos, todos os usuários compartilham domínio SIP/SMTP comum, mas UPN exclusivo para cada floresta de usuário. 
    
Colocando um farm do AD FS em cada floresta de usuário e usando um SIP/SMTP/UPN exclusivo para cada floresta, resolveremos ambos os problemas. Somente as contas nessa floresta de usuário específica seriam pesquisadas e corresponderiam durante as tentativas de autenticação. Isso ajudará a fornecer um processo de autenticação mais contínuo. 
  
Essa implantação será uma implantação padrão do Windows Server 2012 R2 AD FS e deve estar funcionando antes de continuar. Para obter instruções, [consulte How to Install AD FS 2012 R2 for Microsoft 365](https://blogs.technet.com/b/rmilne/archive/2014/04/28/how-to-install-adfs-2012-r2-for-office-365.aspx). 
  
Depois de implantado, você precisa editar a regra de declarações para corresponder à Âncora de Origem selecionada anteriormente. No MMC do AD FS, em Confianças de Parte Confiável, clique com o botão direito do mouse em Microsoft 365 **Identity Platform** ou Microsoft Office 365 **Identity Platform** e selecione Editar Regras de **Declaração.** Edite a primeira regra e altere ObjectSID para **employeeNumber**. 
  
![Tela editar regras de várias florestas.](../../sfbserver/media/f5d485bd-52cc-437f-ba71-217f8902056c.png)
  
## <a name="configure-aad-connect"></a>Configurar o AAD Conexão

Em topologias de floresta de recursos, é necessário que os atributos do usuário da floresta de recursos e quaisquer florestas de conta sejam sincronizados no Azure AD. A Microsoft recomenda que o Azure AD Conexão sincronizar e mesclar identidades de usuários de todas as florestas que tenham habilitado contas de usuário e a floresta que contém Skype for Business.  Para obter detalhes, [consulte Configure Azure AD Conexão for Skype for Business and Teams](configure-azure-ad-connect.md).

Observe que o Azure AD Conexão não fornece sincronização no local entre a conta e florestas de recursos. Isso deve ser configurado usando Microsoft Identity Manager ou um produto semelhante, conforme descrito anteriormente.
  
Quando terminar e o Azure AD Conexão estiver mesclando, se você olhar para um objeto no metaverso, verá algo semelhante ao seguinte: 
  
![Tela do objeto Metaverso de várias florestas.](../../sfbserver/media/16379880-2de3-4c43-b219-1551f5dec5f6.png)
  
Os atributos realçados em verde foram mesclados Microsoft 365, os amarelos são da floresta do usuário e o azul é da floresta de recursos. 
  
Neste exemplo, o Azure AD Conexão identificou o sourceAnchor e o cloudSourceAnchor do usuário e os objetos de floresta de recursos do Microsoft 365, neste caso 1101-- o employeeNumber selecionado anteriormente. Os Conexão do Azure AD foram capazes de mesclar esse objeto no que você vê acima. 
  
Para obter mais informações, consulte [Integrar seus diretórios](/azure/active-directory/hybrid/whatis-hybrid-identity)locais com Azure Active Directory . 
  
Os Conexão do Azure AD devem ser instalados usando os padrões, exceto pelo seguinte: 
  
1. Login único - com o AD FS já implantado e funcionando: Selecione **Não configurar**.
    
2. Conexão seus diretórios: Adicione todos os domínios.
    
3. Identifique usuários em diretórios locais: Selecione Identidades de usuário existem em vários diretórios **e** selecione os atributos **ObjectSID** e **msExchangeMasterAccountSID.**
    
4. Identificar usuários no Azure AD: Âncora de origem: Selecione o atributo escolhido após ler Selecionar um bom [atributo sourceAnchor](/azure/active-directory/hybrid/plan-connect-design-concepts#selecting-a-good-sourceanchor-attribute), Nome principal do usuário - **userPrincipalName**.
    
5.  Recursos opcionais: selecione se você Exchange implantado híbrido.
    
    > [!NOTE]
    >  Se você tiver apenas Exchange Online, pode haver um problema com falhas OAuth durante a descoberta automática por causa do redirecionamento CNAME. Para corrigir isso, você precisará definir a URL Exchange Descoberta Automática executando o seguinte cmdlet no Shell de Gerenciamento Skype for Business Server:
    >
    > ```powershell
    > Set-CsOAuthConfiguration -ExchangeAutoDiscoverURL https://autodiscover-s.outlook.com/autodiscover/autodiscover.svc 
    > ```
    
6.  Farm do AD FS: Selecione Usar um farm Windows Server 2012 **R2 AD FS** existente e insira o nome do servidor do AD FS.
    
7.  Termine o assistente e execute as validações necessárias.
    
## <a name="configure-hybrid-connectivity-for-skype-for-business-server"></a>Configurar conectividade híbrida para Skype for Business Server

Siga as práticas recomendadas para configurar Skype for Business híbrido. Para obter mais informações, consulte [Plan hybrid connectivity and](plan-hybrid-connectivity.md) Configure hybrid [connectivity](configure-hybrid-connectivity.md). 
  
## <a name="configure-hybrid-connectivity-for-exchange-server"></a>Configurar conectividade híbrida para Exchange Server

Se necessário, siga as práticas recomendadas para configurar Exchange híbrido. Para obter mais informações, [consulte Exchange Server Implantações Híbridas.](/exchange/exchange-hybrid) 
