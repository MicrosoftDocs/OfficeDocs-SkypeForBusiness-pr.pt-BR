---
title: Configurar o Azure AD Conexão
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
search.appverid: MET150
description: Instruções para configurar o Azure AD Conexão em um ambiente híbrido.
ms.openlocfilehash: cfb290ecc6892001a9e20d9260c54c076a51dfe3
ms.sourcegitcommit: 11a803d569a57410e7e648f53b28df80a53337b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2021
ms.locfileid: "60887209"
---
# <a name="configure-azure-ad-connect-for-teams-and-skype-for-business"></a>Configurar o Azure AD Connect para o Teams e o Skype for Business

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

 
Para usar o Teams, as organizações com uma implantação local do Skype for Business Server ou do Lync Server 2013 devem configurar o Azure AD Conexão para sincronizar seu diretório local com o Microsoft 365. As organizações Skype for Business Server locais devem garantir que os atributos msRTCSIP apropriados sejam sincronizados no Azure AD. Neste artigo, qualquer referência a "Skype for Business Server" também se aplica ao Lync Server 2013.

> [!NOTE]
> - Para obter a funcionalidade completa, os usuários Teams existentes que também têm Skype for Business local precisarão ter sua conta Skype for Business local movida para a nuvem. Por exemplo, para obter funcionalidades como a capacidade de interoperar com Skype for Business usuários e se comunicar com usuários em organizações federadas. Se o usuário local estiver usando apenas Teams, você ainda deverá mover o usuário para a nuvem para fornecer a funcionalidade completa Teams como um usuário do TeamsOnly. Para que essa migração seja realizada, você deve configurar o Azure AD Conexão para que possa habilitar o híbrido.
> - Se você não estiver planejando mover os usuários do local para a nuvem em breve, você ainda deve configurar o Azure AD Conexão para que as contas Teams e Skype for Business Server sejam co-existentes.
 

## <a name="background-information"></a>Informações gerais

Azure Active Directory Conexão mantém o Active Directory local continuamente sincronizado com Microsoft 365. Seu diretório local permanece a fonte autoritativa de identidade, enquanto as alterações do seu ambiente local são sincronizadas no Azure AD. Para obter mais informações, consulte [Azure AD Conexão Sync](/azure/active-directory/hybrid/how-to-connect-sync-whatis).  *Os usuários em sua organização serão representados em seus diretórios* locais e online.  Todos os usuários que usam Teams ou Skype for Business local devem ser sincronizados no local no Azure AD para garantir a coexistência dessas contas. Além disso, você pode facilitar a comunicação entre usuários locais e online por meio Skype for Business conectividade híbrida, o que também requer a configuração do Azure AD Conexão.


## <a name="configuring-azure-ad-when-you-have-skype-for-business-server"></a>Configurar o Azure AD quando tiver o Skype for Business Server 

### <a name="general-requirements"></a>Requisitos gerais 

Para uma implantação local do Skype for Business Server para co-existir com o Teams, determinados atributos do Active Directory da implantação local devem ser sincronizados no Azure AD usando o Azure AD Conexão. A instalação do Azure AD Conexão configura automaticamente os atributos necessários a serem sincronizados por padrão quando detecta a presença de Skype for Business Server em seu ambiente local. Esses atributos incluem atributos de identidade gerais, como o nome principal do usuário, bem como atributos prefigurados com "msRTCSIP", que são específicos do Skype For Business Server. O conjunto completo de atributos é listado na sincronização de Conexão [do Azure AD: Atributos sincronizados com](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized#teams-and-skype-for-business-online)Azure Active Directory .

Se você optar por personalizar as configurações de sincronização no Azure AD Conexão, certifique-se de que os seguintes atributos sejam sincronizados para objetos do usuário:
</br>

|Atributo|Descrição|
|---|---|
|msRTCSIP-PrimaryUserAddress| O endereço sip do usuário no ambiente local|
|msRTCSIP-DeploymentLocator| Indica se o usuário está no local ou na nuvem|
|msRTCSIP-UserEnabled| Se o usuário está habilitado para a funcionalidade SIP|
|||

</br>
</br>
Além disso, se você estiver gerenciando atributos do sistema de telefonia por meio de sua implantação local, também deverá sincronizar os seguintes atributos:

|Atributo|Descrição|
|:---|:---|
|msRTCSIP-Line| O número de telefone do usuário|
|msRTCSIP-OptionFlags| Indica se o usuário está habilitado para funcionalidade de voz|
|msRTCSIP-OwnerUrn| Usado para identificar pontos de extremidade de aplicativo híbrido|
|||

</br>
A Microsoft recomenda sincronizar todas as florestas que contenham identidades de usuário, bem como quaisquer florestas que contenham Skype for Business Server. Se as identidades dos usuários existirem em várias florestas, o Azure AD Connect deve fazer a mesclagem. Quando essas diretrizes forem seguidas, o Azure AD Connect sincronizará automaticamente os atributos corretos, desde que você não modifique os conectores ou as regras de sincronização no Azure AD Connect. 
  
Se você não sincronizar de todas as florestas que contêm identidades de usuário e Skype for Business Server implantação, você deve garantir que a identidade relevante e os atributos Skype for Business sejam preenchidos corretamente no Azure AD para qualquer usuário que use Teams ou Skype for Business (se no local ou online). Isso provavelmente exigirá sincronização de diretório local adicional. Para obter mais informações, consulte [Azure AD Conexão sincronização: Atributos sincronizados com Azure Active Directory](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized).

É responsabilidade do cliente garantir a configuração adequada para preencher os atributos no Azure AD. Lembre-se do seguinte: 

- Usar uma configuração não padrão para sincronizar com o Azure AD é arriscado. Configurações não padrão podem causar corrupção de dados no diretório online.

- À medida que os produtos evoluem, a Microsoft continuará a verificar as configurações de sincronização padrão nas quais todas as florestas relevantes são sincronizadas. Clientes com configurações de sincronização personalizadas são responsáveis por garantir que suas configurações forneçam os atributos e valores corretos para o Azure AD. 

Se você tiver uma floresta local do Active Directory ou várias florestas, o Azure AD Conexão pode ser usado em uma variedade de topologias com suporte, conforme descrito em Topologias do [Azure AD Conexão](/azure/active-directory/hybrid/plan-connect-topologies). Na perspectiva da Skype for Business Server, há três variações: 

1. Uma única floresta, que contém identidades de usuário autoritativo e hospeda o Skype for Business Server. 

2. Várias florestas, apenas uma das quais hospedam o Skype for Business Server, além de uma ou mais florestas que contenham identidades de usuário autoritativo (as florestas de conta). 

3. Várias implantações do Skype for Business Server em várias florestas. Desde que determinados requisitos sejam atendidos, as organizações podem consolidar essas várias implantações em uma única Microsoft 365 organização.

### <a name="single-forest"></a>Floresta única 

Se o Skype for Business e as contas de usuário forem todas hospedadas em uma única floresta, certifique-se de que o Azure AD Connect esteja configurado para sincronizar os usuários dessa floresta no Azure AD.  Por padrão, os atributos apropriados serão sincronizados automaticamente em Azure Active Directory. Os clientes são aconselhados a não modificar as regras de sincronização e/ou conectores integrados que gerenciam a configuração (o que não é possível no assistente de instalação).  

### <a name="multiple-forests-with-one-skype-for-business-deployment"></a>Várias florestas com uma implantação do Skype for Business 

Esse cenário geralmente é chamado de topologia de floresta de recursos. As identidades autoritativas dos usuários são hospedadas em uma ou mais florestas de contas, e o Skype for Business é implantado em uma floresta de recursos separada (que, por si só, pode hospedar identidades de usuário autoritativo). Em geral, as identidades autoritativas dos usuários do Skype for Business podem estar na mesma floresta do Skype for Business Server e/ou em outra floresta, desde que: 

- Os usuários com identidades autoritativas das florestas de conta são representados na floresta de recursos (onde Skype for Business Server é implantado) como objetos de usuário desabilitados. O atributo msRTCSIP-OriginatorSID na floresta de recursos deve corresponder ao SID na floresta de conta. Para obter mais detalhes, [consulte Configure a multi-forest environment for hybrid Skype for Business](configure-a-multi-forest-environment-for-hybrid.md).

- A floresta de recursos que hospeda o Skype for Business Server confia na(s) floresta(s) de conta.  

- Todos os objetos e atributos de usuário relevantes para a identidade (de florestas de conta) e Skype for Business (da floresta de recursos) são sincronizados no Azure AD com os valores corretos por meio do Azure AD Conexão.  

  Para obter a sincronização adequada de objetos e atributos no Azure AD em um cenário local de várias [florestas,](configure-a-multi-forest-environment-for-hybrid.md)a Microsoft recomenda usar o Azure AD Conexão para sincronizar todas as florestas que tenham habilitado contas de usuário e a floresta que contém Skype for Business. Supondo que você sincronize de todas as florestas, configure o Azure AD Connect para mesclar essas identidades e sincronizar com o Azure AD. O Azure AD Connect foi projetado para lidar com esse cenário e fornece uma opção interna no assistente de instalação para configurar isso, incluindo a configuração de âncoras para participar de identidades. Escolha o seguinte: As identidades de usuário existem em vários **diretórios** e Corresponder usando **--> ObjectSID e atributos msExchangeMasterAccountSID**.


### <a name="multiple-skype-for-business-server-deployments-in-multiple-forests"></a>Várias implantações do Skype for Business Server em várias florestas 

Nesse cenário, há várias florestas, cada uma contendo Skype for Business Server e uma única Microsoft 365 organização. Cada floresta que Skype for Business Server pode ser sincronizada no Azure AD para essa organização usando o Azure AD Conexão. No máximo, somente uma floresta pode ser configurada para a versão híbrida do Skype for Business em um determinado momento. Antes de habilizar o híbrido em uma floresta, todos os domínios SIP de todas as outras florestas devem ser desabilitados usando [disable-csonlineSipDomain](/powershell/module/skype/disable-csonlinesipdomain). Para obter mais informações, consulte [Consolidação de nuvem para Teams e Skype for Business](cloud-consolidation.md).


## <a name="related-information"></a>Informações relacionadas

- [O que é identidade híbrida](/azure/active-directory/hybrid/whatis-hybrid-identity)

- [Sincronização do Azure Active Directory Connect](/azure/active-directory/hybrid/how-to-connect-sync-whatis): Entender e personalizar a sincronização

- [Topologias para o Azure AD Connect](/azure/active-directory/hybrid/plan-connect-topologies)

- [Sincronização do Azure AD Conexão: Atributos sincronizados com Azure Active Directory](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)
