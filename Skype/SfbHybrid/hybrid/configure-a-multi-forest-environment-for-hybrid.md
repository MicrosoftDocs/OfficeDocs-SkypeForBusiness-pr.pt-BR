---
title: Implantar uma topologia de floresta de recursos
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: As seções a seguir fornecem orientação sobre como configurar um ambiente com várias florestas em um modelo de floresta de recursos/usuários para fornecer a funcionalidade do Skype for Business em um cenário híbrido.
ms.openlocfilehash: 7ef895648c044dc5d1f3f907ad4f75d950a4253a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36160380"
---
# <a name="deploy-a-resource-forest-topology"></a>Implantar uma topologia de floresta de recursos
 
As seções a seguir fornecem orientação sobre como configurar um ambiente com várias florestas em um modelo de floresta de recursos/usuários para fornecer a funcionalidade do Skype for Business em um cenário híbrido. 
  
![Ambiente de várias florestas para híbrido](../../sfbserver/media/5f079435-b252-4a6a-9638-3577d55b2873.png)
  
## <a name="topology-requirements"></a>Requisitos de topologia

Há suporte para várias florestas de usuários. Lembre-se do seguinte: 
    
- Para as versões suportadas do Lync Server e do Skype for Business Server em uma configuração híbrida, consulte [Server Version requirements](plan-hybrid-connectivity.md#server-version-requirements) in [Plan Hybrid Connectivity between Skype for Business Server e Office 365](plan-hybrid-connectivity.md).
    
- O Exchange Server pode ser implantado em uma ou mais florestas, que podem ou não incluir a floresta que contém o Skype for Business Server. Verifique se você aplicou a atualização cumulativa mais recente.
    
- Para obter detalhes sobre a coexistência com o Exchange Server, incluindo critérios e limitações de suporte em várias combinações de local e online, consulte [recurso suporte](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support) em [planejar para integrar o Skype for Business e o Exchange](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).
    
  
## <a name="user-homing-considerations"></a>Considerações de Hospedagem de usuário

Os usuários do Skype for Business hospedados no local podem ter o Exchange hospedado no local ou online. Os usuários do Skype for Business online devem usar o Exchange Online para uma experiência ideal; no entanto, isso não é necessário. O Exchange no local não é necessário para implementar o Skype for Business em ambos os casos.
  
## <a name="configure-forest-trusts"></a>Configurar relações de confiança de floresta

Em uma topologia de floresta de recursos, as florestas de recursos que hospedam o Skype for Business Server devem confiar em cada floresta de conta que contenha contas de usuários que irão acessá-la. Se você tiver várias florestas de usuários, para habilitar a autenticação entre florestas, é importante que o roteamento de sufixo de nome esteja habilitado para cada uma dessas relações de confiança de floresta. Para obter instruções, consulte [Gerenciando relações de confiança de floresta](https://technet.microsoft.com/en-us/library/cc772440.aspx). Se você tem o Exchange Server implantado em outra floresta e fornece funcionalidade para usuários do Skype for Business, a floresta que hospeda o Exchange deve confiar na floresta que hospeda o Skype for Business Server. Por exemplo, se o Exchange foi implantado na floresta da conta, isso significaria efetivamente uma relação de confiança bidirecional entre a conta e as florestas do Skype for Business são necessárias nessa configuração.
  
## <a name="synchronize-accounts-into-the-forest-hosting-skype-for-business"></a>Sincronizar contas com a floresta que hospeda o Skype for Business

Quando o Skype for Business Server é implantado em uma floresta (uma floresta de recursos), mas fornece funcionalidade aos usuários em uma ou mais florestas (florestas de contas), os usuários nas outras florestas devem ser representados como objetos de usuário desabilitados na floresta onde o Skype for O Business Server é implantado. Um produto de gerenciamento de identidades, como o Microsoft Identity Manager, precisa ser implantado e configurado para provisionar e sincronizar os usuários das florestas de contas na floresta onde o Skype for Business Server está implantado. Os usuários devem ser sincronizados na floresta que hospeda o Skype for Business Server como objetos de usuário desabilitados. Os usuários não podem ser sincronizados como objetos de contato do Active Directory, pois o Azure Active Directory Connect não sincronizará corretamente os contatos com o Azure AD para uso com o Skype.
  
Independentemente de qualquer configuração de várias florestas, a floresta que hospeda o Skype for Business Server também pode fornecer funcionalidade para qualquer usuário habilitado que exista na mesma floresta.
  
Para obter a sincronização de identidade adequada, os seguintes atributos precisam ser sincronizados: 
  
|**Florestas de usuários**|**Florestas de recursos**|
|:-----|:-----|
|atributo de link da conta escolhida  <br/> |atributo de link da conta escolhida  <br/> |
|Email  <br/> |Email  <br/> |
|ProxyAddresses  <br/> |ProxyAddresses  <br/> |
|ObjectSID  <br/> |msRTCSIP-OriginatorSID  <br/> |
   
O [atributo de link da conta escolhida](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-design-concepts/) será usado como a âncora de origem. Se você tiver um atributo diferente e imutável que prefere usar, você pode fazê-lo; apenas não deixe de editar a regra de declarações do AD FS e selecione o atributo durante a configuração do AAD Connect.
  
Não sincronize os UPNs entre as florestas. Encontramos durante os testes que precisávamos usar um UPN exclusivo para cada floresta de usuário, já que não é possível usar o mesmo UPN em várias florestas. Como resultado, foram apresentadas duas possibilidades, para sincronizar o UPN ou para não sincronizar. 
  
- Se o UPN exclusivo de cada floresta de usuário não tiver sido sincronizado com o objeto desabilitado associado na floresta de recursos, o logon único (SSO) será quebrado por pelo menos a tentativa de entrada inicial (supondo que o usuário selecionou a opção de salvar senha). No cliente Skype for Business, presumimos que os valores SIP/UPN são os mesmos. Como o endereço SIP neste cenário é user@company.com, mas o UPN do objeto habilitado na floresta do usuário é na verdade user@contoso.company.com, a tentativa de logon inicial falharia e o usuário será solicitado a inserir credenciais. Após a inserção do UPN correto/real, a solicitação de autenticação será concluída em relação aos controladores de domínio na floresta do usuário e a entrada será bem-sucedida.
    
- Se o UPN exclusivo de cada floresta de usuário foi sincronizado com o objeto desabilitado associado na floresta de recursos, a autenticação do AD FS falhará. A regra de correspondência localizaria o UPN no objeto na floresta de recursos, que foi desabilitado e não pôde ser usado para autenticação. 
    
## <a name="create-an-office-365-tenant"></a>Criar um locatário do Office 365

Em seguida, você precisará provisionar um locatário do Office 365 para usar com sua implantação. Para obter mais informações, consulte [assinaturas, licenças, contas e locatários para ofertas de nuvem da Microsoft](https://docs.microsoft.com/office365/enterprise/subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings). 
  
## <a name="configure-active-directory-federation-services"></a>Configurar serviços de Federação do Active Directory

Depois de ter um locatário, você precisará configurar os serviços de Federação do Active Directory (AD FS) em cada uma das florestas de usuários. Isso pressupõe que você tenha um endereço SIP e SMTP exclusivo e o UPN (nome principal de usuário) para cada floresta. O AD FS é opcional e é usado aqui para obter logon único (SSO). O DirSync com a sincronização de senha também tem suporte e também pode ser usado no lugar do AD FS. 
  
Somente implantações com SIP/SMTP e UPNs correspondentes foram testadas. A não correspondência de SIP/SMTP/UPNs pode resultar em uma funcionalidade reduzida, como problemas com a integração com o Exchange e o SSO. 
  
A menos que você use um SIP/SMTP/UPN exclusivo para usuários de cada floresta, ainda poderá ter problemas de SSO, independentemente de onde o AD FS está implantado: 
  
- Relação de confiança unidirecional ou bidirecional entre florestas de recursos/usuários com o farm do AD FS implantado em cada floresta de usuário, todos os usuários compartilham o domínio SIP/SMTP comum, mas o UPN exclusivo para cada floresta de usuário. 
    
- Relações de confiança bidirecionais entre florestas de recursos/usuários com o farm do AD FS implantado somente na floresta de recursos, todos os usuários compartilham o domínio SIP/SMTP comum, mas o UPN exclusivo para cada floresta de usuário. 
    
Ao colocar um farm do AD FS em cada floresta de usuário e usar um SIP/SMTP/UPN exclusivo para cada floresta, resolvemos os dois problemas. Somente as contas dessa floresta de usuário específico seriam pesquisadas e correspondidas durante as tentativas de autenticação. Isso ajudará a fornecer um processo de autenticação mais contínuo. 
  
Essa será uma implantação padrão do Windows Server 2012 R2 AD FS e deve estar funcionando antes de continuar. Para obter instruções, consulte [como instalar o AD FS 2012 R2 para o Office 365](https://blogs.technet.com/b/rmilne/archive/2014/04/28/how-to-install-adfs-2012-r2-for-office-365.aspx). 
  
Depois de implantado, você terá que editar a regra de declarações para corresponder à âncora de origem selecionada anteriormente. No MMC do AD FS, em relações de confiança de terceira parte confiável, clique com o botão direito em **plataforma de identidade do Microsoft Office 365**e clique em **Editar regras de declaração**. Edite a primeira regra e altere ObjectID para **employeeNumber**. 
  
![Tela de regras de edição de várias florestas](../../sfbserver/media/f5d485bd-52cc-437f-ba71-217f8902056c.png)
  
## <a name="configure-aad-connect"></a>Configurar o AAD Connect

Nas topologias de floresta de recursos, é necessário que os atributos de usuário da floresta de recursos e de quaisquer florestas de conta estejam sincronizados com o Azure AD. A maneira mais simples e recomendada de fazer isso é fazer com que o Azure AD Connect Sincronize e mescle as identidades de usuário de *todas as* florestas que têm as contas de usuário e a floresta que contêm o Skype for Business. Para obter detalhes, confira [Configurar o Azure ad Connect para o Skype for Business e](configure-azure-ad-connect.md)o Microsoft Teams.

Observe que o AAD Connect não fornece sincronização local entre as florestas de conta e de recurso. Isso deve ser configurado separadamente usando o Microsoft Identity Manager ou produto semelhante, conforme descrito anteriormente.
  
Quando concluído e o AAD Connect estiver mesclando, se você examinar um objeto no metaverso, deverá ver algo semelhante a isso: 
  
![Tela de objeto do metaverso de várias florestas](../../sfbserver/media/16379880-2de3-4c43-b219-1551f5dec5f6.png)
  
Os atributos realçados verdes foram mesclados do Office 365, o amarelo é da floresta do usuário e o azul é da floresta de recursos. 
  
Este é um usuário de teste, e você pode ver que o AAD Connect identificou o atributo e o cloudSourceAnchor do usuário e os objetos de floresta de recursos do Office 365, em nosso caso 1101, que é o employeeNumber selecionado anteriormente. Em seguida, ele pôde mesclar este objeto no que você vê acima. 
  
Para obter mais informações, consulte [integrar seus diretórios locais com o Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/). 
  
O AAD Connect deve ser instalado usando os padrões, exceto o seguinte: 
  
1. Logon único-com o AD FS já implantado e funcionando: selecione não **Configurar**.
    
2. Conecte seus diretórios: Adicione todos os domínios.
    
3. Identificar usuários nos diretórios locais: selecione as identidades do **usuário em vários diretórios**e selecione os atributos **** **msExchangeMasterAccountSID** e.
    
4. Identificar usuários no Azure AD: âncora de origem: selecione o atributo que você escolheu após a leitura [selecionando um bom atributo atributo](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-design-concepts/), nome principal do usuário- **userPrincipalName**.
    
5.  Recursos opcionais: selecione se você tem o Exchange híbrido implantado.
    
    > [!NOTE]
    >  Se você tiver apenas o Exchange Online, pode haver um problema com falhas do OAuth durante a descoberta automática por causa do redirecionamento de CNAME. Para corrigir isso, será necessário definir a URL de descoberta automática do Exchange executando o seguinte cmdlet do Shell de gerenciamento do Skype for Business Server:
  
    Set-CsOAuthConfiguration-ExchangeAutoDiscoverURL https://<span>autodiscover-s.Outlook.com/autodiscover/autodiscover.svc 
    
6.  Farm do AD FS: selecione **usar um farm existente do AD FS do Windows Server 2012 R2** e digite o nome do servidor do AD FS.
    
7.  Finalize o assistente e execute as validações necessárias.
    
## <a name="configure-hybrid-connectivity-for-skype-for-business-server"></a>Configurar a conectividade híbrida para o Skype for Business Server

Siga as práticas recomendadas para configurar o Skype for Business híbrido. Para obter mais informações, consulte [Plan Hybrid Connectivity](plan-hybrid-connectivity.md) e [Configure Hybrid Connectivity](configure-hybrid-connectivity.md). 
  
## <a name="configure-hybrid-connectivity-for-exchange-server"></a>Configurar a conectividade híbrida para o Exchange Server

Se necessário, siga as práticas recomendadas para configurar o Exchange híbrido. Para obter mais informações, consulte implantações híbridas do [Exchange Server](https://docs.microsoft.com/en-us/exchange/exchange-hybrid). 
  

