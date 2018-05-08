---
title: Configurar um ambiente de várias floresta para o híbrido Skype para negócios
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/17/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 960ab8a3-352d-4b18-bc01-55b35f30ca0d
description: As seções a seguir fornecem orientação sobre como configurar um ambiente que possui várias florestas em um modelo de floresta de usuário/recurso para fornecer Skype para a funcionalidade de negócios em um cenário híbrido.
ms.openlocfilehash: 7dfbdf8348d5bf5ec51ee33d4dbd67574c509855
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
---
# <a name="configure-a-multi-forest-environment-for-hybrid-skype-for-business"></a>Configurar um ambiente de várias floresta para o híbrido Skype para negócios
 
As seções a seguir fornecem orientação sobre como configurar um ambiente que possui várias florestas em um modelo de floresta de usuário/recurso para fornecer Skype para a funcionalidade de negócios em um cenário híbrido. 
  
![Ambiente de Várias Florestas para Híbrido](../../media/5f079435-b252-4a6a-9638-3577d55b2873.png)
  
## <a name="validate-the-forest-topology"></a>Validar a topologia de floresta

Há compatibilidade para múltiplas florestas de usuários. Considere o seguinte:   
  
- Para uma floresta de usuário único ou vários implantação de floresta de usuário, deve haver uma única implantação do Skype para Business Server.
    
- Para as versões suportadas do Lync Server e Skype para Business Server em uma configuração híbrida, consulte [requisitos de topologia](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md#BKMK_Topology) em [Planejar a conectividade híbrida entre Skype para Business Server e do Skype para negócios Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md).
    
- Exchange Server podem ser implantado em uma ou mais florestas, que podem ou não incluir a floresta que contém o Skype para Business Server. Verifique se que você aplicou a atualização cumulativa mais recente.
    
- Para obter detalhes sobre a coexistência com o Exchange Server, incluindo suporte critérios e limitações em várias combinações de local e online, consulte [suporte de recurso](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support) em [Planejar a integração do Skype para Exchange e de negócios](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).
    
Para obter mais informações, consulte [requisitos de ambiente para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).
  
## <a name="user-homing-considerations"></a>Considerações de hospedagem do usuário

Skype para usuários comerciais hospedagem no local pode ter Exchange hospedado no local ou online. Skype para usuários corporativos Online deve usar o Exchange Online para uma experiência ideal; No entanto, isso não é necessário. Exchange no local não é necessário para implementar o Skype para negócios em ambos os casos.
  
## <a name="configure-forest-trusts"></a>Configurar relações de confiança da floresta

As relações de confiança exigidas são relações bidirecionais transitivas entre a floresta de recursos e cada floresta de usuário. Se você tiver várias florestas de usuários, é importante que o Roteamento de sufixo de nome esteja habilitado para cada relação de confiança para habilitar a autenticação entre florestas. Para obter instruções, consulte [Gerenciando de confiança de floresta](https://technet.microsoft.com/en-us/library/cc772440.aspx). 
  
## <a name="synchronize-accounts-into-the-forest-hosting-skype-for-business"></a>Sincronizar contas para a floresta Skype para a empresa de hospedagem

Quando Skype para Business Server é implantado em uma floresta (uma floresta de recursos), mas oferece funcionalidade aos usuários em um ou mais outras florestas (florestas conta), os usuários nas outras florestas devem ser representados como objetos de usuário desabilitado na floresta onde Skype para Servidor de negócios é implantado. Um produto de gerenciamento de identidade, como o Microsoft Identity Manager, precisa ser implantado e configurado para provisionar e sincronizar os usuários de florestas de conta para a floresta onde o Skype para Business Server está implantado. Os usuários devem ser sincronizados para a floresta hospedagem Skype para Business Server como objetos de usuário desabilitadas. Os usuários não podem ser sincronizados como objetos de contato do Active Directory, porque o Azure Active Directory Connect não adequadamente sincronizará contatos no Azure AD para uso com Skype.
  
Independentemente de qualquer configuração de várias floresta, floresta hospedagem Skype para Business Server também pode fornecer funcionalidade para quaisquer usuários habilitados que existem na mesma floresta.
  
Para obter a sincronização de identidades, os seguintes atributos precisam ser sincronizados: 
  
|**Florestas de usuário**|**Florestas de recursos**|
|:-----|:-----|
|atributo de link da conta escolhida  <br/> |atributo de link da conta escolhida  <br/> |
|email   <br/> |email   <br/> |
|ProxyAddresses  <br/> |ProxyAddresses  <br/> |
|ObjectSID  <br/> |msRTCSIP-OriginatorSID  <br/> |
   
O [atributo de vínculo de conta foi escolhido](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect-design-concepts/) será usada como a âncora de origem. Se você tiver um atributo diferente e imutável atributo que preferir usar, você pode fazê-lo, certifique-se apenas de editar a regra de declaração do AD FS e selecionar o atributo durante a configuração do AAD Connect.
  
Não sincronize o UPN entre as florestas. Durante os testes, descobrimos que precisávamos usar um único UPN para cada floresta de usuário, pois não é possível usar o mesmo UPN para várias florestas. Como resultado, chegamos a duas possibilidades: sincronizar ou não sincronizar o UPN. 
  
-  Se o UPN exclusivo de cada floresta de usuário não for sincronizado ao objeto desabilitado associado na floresta de recurso, o Logon Único não funciona pelo menos na tentativa de conexão inicial (presumindo que o usuário selecionou a opção de salvar senha). No cliente SfB, supomos que os valores de SIP/UPN são os mesmos. Como o endereço SIP nessa situação é user@company.com, mas o UPN do objeto habilitado na floresta do usuário é na verdade user@contoso.company.com, a tentativa de logon inicial falhará e o usuário será solicitado a inserir as credenciais. Ao entrar seu UPN correto/real, a solicitação de autenticação será concluída para os controladores de domínio na floresta do usuário e a conexão será bem-sucedida.
    
- Se o UPN exclusivo de cada floresta de usuário for sincronizado ao objeto desabilitado associado na floresta de recurso, a autenticação do AD FS falhará. A regra correspondente encontrará o UPN do objeto na floresta de recurso, que foi desabilitado e não pode ser utilizado para a autenticação. 
    
## <a name="create-an-office-365-tenant"></a>Criar um locatário do Office 365

Em seguida, você precisará provisionar um locatário do Office 365 para usar em sua implantação. Para obter mais informações, consulte [As etapas de provisionamento do Office 365](https://social.technet.microsoft.com/wiki/contents/articles/22808.office-365-provisioning-steps.aspx). 
  
## <a name="configure-ad-fs"></a>Configurar o AD FS

Depois de criar um locatário, você precisará configurar os Serviços de Federação do Active Directory (AD FS) em cada uma das florestas de usuários. Isto assume que você tem um SIP e endereço SMTP exclusivos, além de um UPN (nome principal de usuário) para cada floresta. O AD FS é opcional e é usado aqui para Logon Único. O DirSync com sincronização de senha também é suportado e também pode ser usado no lugar do AD FS. 
  
Testamos somente implantações com SIP, SMPT e UPNs correspondentes. Não ter SIP/SMTP/UPNs correspondentes pode resultar em uma redução da funcionalidade, como problemas com a integração do Exchange e com o Logon Único. 
  
A menos que você use um SIP/SMTP/UPN exclusivo para usuários de cada floresta, você ainda pode executar problemas Single Sign-on (SSO) - independentemente de onde o AD FS está implantado: 
  
- Relações de uma ou duas vias entre florestas de recursos/usuários com o farm AD FS implantado em cada floresta de usuário, todos os usuários compartilham um domínio SIP/SMTP mas, o UPN é exclusivo para cada floresta de usuário. 
    
- Relações de duas vias entre florestas de recursos/usuários com o farm AD FS implantado somente na floresta de recurso, todos os usuários compartilham um domínio SIP/SMTP mas, o UPN é exclusivo para cada floresta de usuário. 
    
Solucionamos os dois problemas ao usar um farm AD FS em cada floresta de usuário e um SIP/SMTP/UPN exclusivo para cada floresta. Apenas as contas dessa floresta de usuário específico poderiam ser pesquisadas e pareadas durante as tentativas de autenticação. Isso ajudará a oferecer um processo de autenticação mais contínuo. 
  
Essa será uma implantação padrão do AD FS do Windows Server 2012 R2 e deverá estar funcionando antes de continuar. Para obter instruções, consulte [como instalar R2 2012 do AD FS para o Office 365](https://blogs.technet.com/b/rmilne/archive/2014/04/28/how-to-install-adfs-2012-r2-for-office-365.aspx). 
  
Depois da implantação, você terá que editar a regra de declaração para corresponder à âncora de origem selecionada anteriormente. No AD FS MMC, em Confianças de terceiras partes confiáveis, clique com o botão direito do mouse em Plataforma de Identidade do Microsoft Office 365 e em Editar Regras de Declaração. Edite a primeira regra e altere ObjectSID para employeeNumber. 
  
![Tela de Edição de Regras de Várias Florestas](../../media/f5d485bd-52cc-437f-ba71-217f8902056c.png)
  
## <a name="configure-aad-connect"></a>Configurar o AAD Connect

O AAD Connect será usado para mesclar as contas entre as diferentes florestas e entre as florestas e o Office 365. Você deve implantar o AAD Connect na floresta de recursos. Ele é necessário para poder sincronizar várias florestas e o Office 365, que não é suportado pelo DirSync. 
  
O AAD Connect não sincroniza as contas entre florestas locais. Ele usa conectores AD para ler objetos já sincronizados entre florestas locais (com FIM ou produtos similares). Em seguida, ele aproveita as regras de filtragem para criar uma única representação para os objetos habilitado e desabilitado correspondentes no metaverso e replica esse único objeto mesclado para o Office 365. 
  
Quando terminar e o AAD Connect estiver no processo de mesclagem, se você vir um objeto no metaverso, deve ver algo semelhante a isto: 
  
![Tela de Objeto Metaverso de Várias Florestas](../../media/16379880-2de3-4c43-b219-1551f5dec5f6.png)
  
Os atributos verdes destacados foram mesclados do Office 365, os amarelos são da floresta do usuário e os azuis são da floresta de recursos. 
  
Este é um usuário de teste, é possível ver que o AAD Connect identificou o sourceAnchor e o cloudSourceAnchor do usuário e os objetos da floresta de recursos e do Office 365. Em nosso caso, 1101, que é o employeeNumber selecionado anteriormente. Em seguida, ele conseguiu mesclar esse objeto no que você vê acima. 
  
Para obter mais informações, consulte [integrando suas identidades no local com o Windows Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect/). 
  
A maior parte da instalação do AAD Connect é padrão, exceto pelas seguintes etapas: 
  
1.  Single sign-on - com o AD FS já implantado e trabalho, selecione não configurar
    
2. Conectar seus diretórios - adicionar todos os domínios 
    
3.  Identificar usuários em diretórios no local: selecione **as identidades de usuário existirem em vários diretórios** e atributos **ObjectSID** e **msExchangeMasterAccountSID**
    
4. Identificar usuários no Windows Azure AD: âncora de origem - selecionar o atributo que você escolheu após ler [selecionando um atributo sourceAnchor bom](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect-design-concepts/), o nome Principal de usuário - **userPrincipalName**
    
5.  Recursos opcionais - selecione se você tiver o Exchange híbrido implantado ou não.
    
    > [!NOTE]
    >  Se você tiver somente o Exchange Online, pode haver um problema com falhas de OAuth durante a descoberta automática devido ao redirecionamento de CNAME. Para corrigir esse problema, você precisará definir a URL de descoberta automática do Exchange executando o seguinte cmdlet do Skype do Shell de gerenciamento do servidor de negócios:
  
    Set-CsOAuthConfiguration - ExchangeAutoDiscoverURLhttps://autodiscover-s.outlook.com/autodiscover/autodiscover.svc 
    
6.  Farm AD FS: selecione **Usar um farm do AD FS do Windows Server 2012 R2 existente** e insira o nome do servidor do AD FS.
    
7.  Conclua o assistente e realize as validações necessárias.
    
## <a name="configure-hybrid-mode-for-skype-for-business-server"></a>Configurar o modo híbrido para o Skype for Business Server

Siga as práticas recomendadas para configuração Skype para o híbrido de negócios. Para mais informações de planejamento, consulte [planejar sua implantação híbrida para Skype para Business Server 2015](https://technet.microsoft.com/en-us/library/jj205403.aspx)e para obter informações de configuração, consulte [Configure híbrida com Skype para negócios Online](https://technet.microsoft.com/en-us/library/jj204669.aspx). 
  
## <a name="configure-hybrid-mode-for-exchange-server"></a>Configurar o modo híbrido para o Exchange Server

Se necessário, siga as práticas recomendadas para configuração híbrida do Exchange. Para obter mais informações, consulte [Implantações híbridas do Exchange Server](https://technet.microsoft.com/en-us/library/jj200581%28v=exchg.150%29.aspx). 
  

