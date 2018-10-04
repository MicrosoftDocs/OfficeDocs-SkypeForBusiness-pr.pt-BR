---
title: Configurar um ambiente de várias floresta para o híbrido Skype para negócios
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: As seções a seguir fornecem orientação sobre como configurar um ambiente que possui várias florestas em um modelo de floresta de usuário/recurso para fornecer Skype para a funcionalidade de negócios em um cenário híbrido.
ms.openlocfilehash: 72c0a91c3a5a90b4ec83eb5f71a5601ccfb48bb1
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375103"
---
# <a name="configure-a-multi-forest-environment-for-hybrid-skype-for-business"></a>Configurar um ambiente de várias floresta para o híbrido Skype para negócios
 
As seções a seguir fornecem orientação sobre como configurar um ambiente que possui várias florestas em um modelo de floresta de usuário/recurso para fornecer Skype para a funcionalidade de negócios em um cenário híbrido. 
  
![Ambiente de Várias Florestas para Híbrido](../../sfbserver/media/5f079435-b252-4a6a-9638-3577d55b2873.png)
  
## <a name="validate-the-forest-topology"></a>Validar a topologia de floresta

Há compatibilidade para múltiplas florestas de usuários. Considere o seguinte:   
  
- Para uma floresta de usuário único ou implantação de floresta de vários usuários, deve haver uma única implantação do Skype para Business Server.
    
- Para as versões suportadas do Lync Server e Skype para Business Server em uma configuração híbrida, consulte [requisitos de topologia](plan-hybrid-connectivity.md#BKMK_Topology) em [Planejar a conectividade híbrida entre Skype para Business Server e Office 365](plan-hybrid-connectivity.md).
    
- Exchange Server podem ser implantado em uma ou mais florestas, que podem ou não incluir a floresta que contém o Skype para Business Server. Verifique se que você aplicou a atualização cumulativa mais recente.
    
- Para obter detalhes sobre a coexistência com o Exchange Server, incluindo suporte critérios e limitações em várias combinações de local e online, consulte [suporte de recurso](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support) em [Planejar a integração do Skype para Exchange e de negócios](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).
    
Para obter mais informações, consulte requisitos do [sistema](../plan/system-requirements.md).
  
## <a name="user-homing-considerations"></a>Considerações de hospedagem do usuário

Skype para usuários comerciais hospedagem no local pode ter Exchange hospedado no local ou online. Skype para usuários corporativos Online deve usar o Exchange Online para uma experiência ideal; No entanto, isso não é necessário. Exchange no local não é necessário para implementar o Skype para negócios em ambos os casos.
  
## <a name="configure-forest-trusts"></a>Configurar relações de confiança de floresta

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
   
O [atributo de vínculo de conta foi escolhido](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect-design-concepts/) será usada como a âncora de origem. Se você tiver um atributo diferente e imutável que você prefere usar, você poderá fazê-lo; Certifique-se apenas editar a regra de declarações do AD FS e selecione o atributo durante a configuração AAD se conectar.
  
Não sincronize os UPNs entre as florestas. Durante os testes, descobrimos que precisávamos usar um único UPN para cada floresta de usuário, pois não é possível usar o mesmo UPN para várias florestas. Como resultado, chegamos a duas possibilidades: sincronizar ou não sincronizar o UPN. 
  
- Se o UPN exclusivo de cada floresta de usuário não foi sincronizado para o objeto associado desabilitado na floresta de recursos, logon único (SSO) poderia ser quebrado pelo menos a tentativa de entrada inicial (supondo que o usuário selecionou a opção Salvar senha). Skype para o cliente de negócios, assumimos que os valores SIP/UPN são os mesmos. Como o endereço SIP nessa situação é user@company.com, mas o UPN do objeto habilitado na floresta do usuário é na verdade user@contoso.company.com, a tentativa de logon inicial falhará e o usuário será solicitado a inserir as credenciais. Ao entrar seu UPN correto/real, a solicitação de autenticação será concluída para os controladores de domínio na floresta do usuário e a conexão será bem-sucedida.
    
- Se o UPN exclusivo de cada floresta de usuário foi sincronizado para o objeto associado desabilitado na floresta de recursos, a autenticação do AD FS falhará. A regra correspondente encontrará o UPN do objeto na floresta de recurso, que foi desabilitado e não pode ser utilizado para a autenticação. 
    
## <a name="create-an-office-365-tenant"></a>Criar um locatário do Office 365

Em seguida, você precisará provisionar um locatário do Office 365 para usar em sua implantação. Para obter mais informações, consulte [assinaturas, licenças, contas e inquilinos para as ofertas de nuvem da Microsoft](https://docs.microsoft.com/en-us/office365/enterprise/subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings). 
  
## <a name="configure-active-directory-federation-services"></a>Configurar os serviços de Federação do Active Directory

Depois que você tiver um locatário, você precisará configurar os serviços de Federação do Active Directory (AD FS) em cada uma das florestas de usuário. Isto assume que você tem um SIP e endereço SMTP exclusivos, além de um UPN (nome principal de usuário) para cada floresta. O AD FS é opcional e é usado aqui para fazer o logon único (SSO). O DirSync com sincronização de senha também é suportado e também pode ser usado no lugar do AD FS. 
  
Testamos somente implantações com SIP, SMPT e UPNs correspondentes. Sem a necessidade de correspondentes em SMTP/SIP/UPNs pode resultar em modo de funcionalidade reduzido, como problemas relacionados à integração do Exchange e o SSO. 
  
A menos que você use um SIP/SMTP/UPN exclusivo para usuários de cada floresta, você ainda pode executar em problemas SSO, independentemente de onde o AD FS está implantado: 
  
- Relações de uma ou duas vias entre florestas de recursos/usuários com o farm AD FS implantado em cada floresta de usuário, todos os usuários compartilham um domínio SIP/SMTP mas, o UPN é exclusivo para cada floresta de usuário. 
    
- Relações de duas vias entre florestas de recursos/usuários com o farm AD FS implantado somente na floresta de recurso, todos os usuários compartilham um domínio SIP/SMTP mas, o UPN é exclusivo para cada floresta de usuário. 
    
Solucionamos os dois problemas ao usar um farm AD FS em cada floresta de usuário e um SIP/SMTP/UPN exclusivo para cada floresta. Apenas as contas dessa floresta de usuário específico poderiam ser pesquisadas e pareadas durante as tentativas de autenticação. Isso ajudará a oferecer um processo de autenticação mais contínuo. 
  
Essa será uma implantação padrão do AD FS do Windows Server 2012 R2 e deverá estar funcionando antes de continuar. Para obter instruções, consulte [como instalar R2 2012 do AD FS para o Office 365](https://blogs.technet.com/b/rmilne/archive/2014/04/28/how-to-install-adfs-2012-r2-for-office-365.aspx). 
  
Depois da implantação, você terá que editar a regra de declaração para corresponder à âncora de origem selecionada anteriormente. No MMC AD FS, em confianças de terceiros, clique com o botão **Plataforma de identidade do Microsoft Office 365**e, em seguida, clique em **Editar regras de declaração**. Edite a primeira regra e altere o ObjectSID para **employeeNumber**. 
  
![Tela de Edição de Regras de Várias Florestas](../../sfbserver/media/f5d485bd-52cc-437f-ba71-217f8902056c.png)
  
## <a name="configure-aad-connect"></a>Configurar o AAD Connect

O AAD Connect será usado para mesclar as contas entre as diferentes florestas e entre as florestas e o Office 365. Você deve implantar o AAD Connect na floresta de recursos. Ele é necessário para poder sincronizar várias florestas e o Office 365, que não é suportado pelo DirSync. 
  
O AAD Connect não sincroniza as contas entre florestas locais. Ele usa conectores AD para ler objetos já sincronizados entre florestas locais (com FIM ou produtos similares). Em seguida, ele aproveita as regras de filtragem para criar uma única representação para os objetos habilitado e desabilitado correspondentes no metaverso e replica esse único objeto mesclado para o Office 365. 
  
Quando terminar e o AAD Connect estiver no processo de mesclagem, se você vir um objeto no metaverso, deve ver algo semelhante a isto: 
  
![Tela de Objeto Metaverso de Várias Florestas](../../sfbserver/media/16379880-2de3-4c43-b219-1551f5dec5f6.png)
  
O verde realçados atributos foram mesclados do Office 365, o amarelo são da floresta de usuário e o azul são na floresta de recursos. 
  
Este é um usuário de teste e você pode ver que conecte AAD identificou o sourceAnchor e o cloudSourceAnchor do usuário e os objetos da floresta de recursos do Office 365, no nosso caso 1101, que é employeeNumber selecionada anteriormente. Em seguida, ele foi capaz de mesclar esse objeto em o que aparece acima. 
  
Para obter mais informações, consulte [os diretórios de seu local integra-se com o Windows Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect/). 
  
Conectar AAD deve ser instalado usando os padrões, exceto para o seguinte: 
  
1. Single sign-in - com o AD FS já implantado e trabalho: selecione **não configurar**.
    
2. Conectar seus diretórios: adicionar todos os domínios.
    
3. Identificar usuários em diretórios no local: selecione **as identidades de usuário existirem em vários diretórios**e os atributos **ObjectSID** e **msExchangeMasterAccountSID** .
    
4. Identificar usuários no Windows Azure AD: âncora de origem: selecione o atributo que você escolheu após ler [selecionando um atributo sourceAnchor bom](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect-design-concepts/), Nome Principal de usuário - **userPrincipalName**.
    
5.  Recursos opcionais: selecione se você tiver implantado do Exchange híbrido.
    
    > [!NOTE]
    >  Se você tiver somente o Exchange Online, pode haver um problema com falhas de OAuth durante a descoberta automática devido ao redirecionamento de CNAME. Para corrigir esse problema, você precisará definir a URL de descoberta automática do Exchange executando o seguinte cmdlet do Skype do Shell de gerenciamento do servidor de negócios:
  
    Set-CsOAuthConfiguration - ExchangeAutoDiscoverURL https://<span>autodiscover-s.outlook.com/autodiscover/autodiscover.svc 
    
6.  Farm AD FS: selecione **Usar um farm do AD FS do Windows Server 2012 R2 existente** e insira o nome do servidor do AD FS.
    
7.  Conclua o assistente e realize as validações necessárias.
    
## <a name="configure-hybrid-connectivity-for-skype-for-business-server"></a>Configurar conectividade híbrida do Skype para Business Server

Siga as práticas recomendadas para configuração Skype para o híbrido de negócios. Para mais informações, consulte [Planejar a conectividade híbrida](plan-hybrid-connectivity.md) e [conectividade de híbrida Configure](configure-hybrid-connectivity.md). 
  
## <a name="configure-hybrid-connectivity-for-exchange-server"></a>Configurar a conectividade híbrida do Exchange Server

Se necessário, siga as práticas recomendadas para configuração híbrida do Exchange. Para obter mais informações, consulte [Implantações híbridas do Exchange Server](https://technet.microsoft.com/en-us/library/jj200581%28v=exchg.150%29.aspx). 
  

