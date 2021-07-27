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
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Instruções para configurar o Azure AD Conexão em um ambiente híbrido.
ms.openlocfilehash: 71775a112dffff8d4a5215f4eeccda130ea313fb
ms.sourcegitcommit: 3f1635d1915561798ea764c3e33d7db55f7e49da
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2021
ms.locfileid: "53574066"
---
# <a name="configure-azure-ad-connect-for-teams-and-skype-for-business"></a>Configurar o Azure AD Connect para o Teams e o Skype for Business

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

 
As organizações que têm um Skype for Business Server (ou Lync Server) local e que estão planejando usar o Teams devem configurar o Azure AD Conexão para sincronizar seu diretório local com Microsoft 365. Esse requisito inclui organizações que se movem diretamente do Skype for Business local para o Teams. As organizações Skype for Business local devem garantir que os atributos msRTCSIP apropriados sejam sincronizados no Azure AD.

[!INCLUDE [sfbo-retirement-skype](../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]
> Os usuários Teams existentes que também têm um Skype for Business local precisarão ter sua conta local do Skype for Business movida para a nuvem para obter funcionalidade completa, como a capacidade de interoperar com usuários Skype for Business e se comunicar com usuários em organizações federadas. Mesmo que o usuário só esteja usando o Teams, essa conta online do Skype for Business é exigida pela infraestrutura para oferecer a funcionalidade adicional. Para que a migração ocorra, certifique-se de que o Azure AD Connect está configurado corretamente para ser possível habilitar o híbrido.
 

## <a name="background-information"></a>Informações gerais

Azure Active Directory Conexão mantém o Active Directory local continuamente sincronizado com Microsoft 365. O diretório no local mantém a fonte de identidade autoritativa e as alterações do ambiente local são sincronizadas no Azure AD. Para obter mais informações, consulte [Azure AD Conexão Sync](/azure/active-directory/hybrid/how-to-connect-sync-whatis).  

Se você não estiver movendo todos os usuários do local para a nuvem, todos os usuários que usam o Teams ou o Skype for Business local devem ser sincronizados do local para o Azure AD para garantir a comunicação entre usuários locais e online. *Os usuários em sua organização serão representados nos diretórios locais e online.*


## <a name="configuring-azure-ad-when-you-have-skype-for-business-server"></a>Configurar o Azure AD quando tiver o Skype for Business Server 

Se você tiver uma floresta local do Active Directory ou várias florestas, o Azure AD Conexão pode ser usado em uma variedade de topologias com suporte, conforme descrito em Topologias do [Azure AD Conexão](/azure/active-directory/hybrid/plan-connect-topologies). Na perspectiva da Skype for Business Server, há três variações: 

1. Uma única floresta, que contém identidades de usuário autoritativo e hospeda o Skype for Business Server. 

2. Várias florestas, apenas uma das quais hospedam o Skype for Business Server, além de uma ou mais florestas que contenham identidades de usuário autoritativo (as florestas de conta). 

3. Várias implantações do Skype for Business Server em várias florestas. Desde que determinados requisitos sejam atendidos, as organizações podem consolidar essas várias implantações em uma única Microsoft 365 organização.

### <a name="single-forest"></a>Floresta única 

Se o Skype for Business e as contas de usuário forem todas hospedadas em uma única floresta, certifique-se de que o Azure AD Connect esteja configurado para sincronizar os usuários dessa floresta no Azure AD.  Embora o assistente de instalação do Azure AD Connect tenha várias opções, os atributos apropriados serão automaticamente sincronizados com o Azure Active Directory. Os clientes são aconselhados a não modificar as regras de sincronização e/ou conectores integrados que gerenciam a configuração (o que não é possível no assistente de instalação).  

### <a name="multiple-forests-with-one-skype-for-business-deployment"></a>Várias florestas com uma implantação do Skype for Business 

Esse cenário geralmente é chamado de topologia de floresta de recursos. As identidades autoritativas dos usuários são hospedadas em uma ou mais florestas de contas, e o Skype for Business é implantado em uma floresta de recursos separada (que, por si só, pode hospedar identidades de usuário autoritativo). Em geral, as identidades autoritativas dos usuários do Skype for Business podem estar na mesma floresta do Skype for Business Server e/ou em outra floresta, desde que: 

- Os usuários com identidades autoritativas das florestas de conta são representados na floresta de recursos (onde Skype for Business Server é implantado) como objetos de usuário desabilitados. O atributo msRTCSIP-OriginatorSID na floresta de recursos deve corresponder ao SID na floresta de conta. Para obter mais detalhes, [consulte Configure a multi-forest environment for hybrid Skype for Business](configure-a-multi-forest-environment-for-hybrid.md).

- A floresta de recursos que hospeda o Skype for Business Server confia na(s) floresta(s) de conta.  

- Todos os objetos e atributos de usuário relevantes para a identidade (de florestas de conta) e Skype for Business (da floresta de recursos) são sincronizados no Azure AD com os valores corretos por meio do Azure AD Conexão.  

  Para obter a sincronização adequada de objetos e atributos no Azure AD em um cenário local de várias [florestas,](configure-a-multi-forest-environment-for-hybrid.md)a Microsoft recomenda usar o Azure AD Conexão para sincronizar de todas as florestas que tenham contas de usuário habilitadas e a floresta que contém Skype for Business. Supondo que você sincronize de todas as florestas, configure o Azure AD Connect para mesclar essas identidades e sincronizar com o Azure AD. O Azure AD Connect foi projetado para lidar com esse cenário e fornece uma opção interna no assistente de instalação para configurar isso, incluindo a configuração de âncoras para participar de identidades. Escolha o seguinte: As identidades de usuário existem em vários **diretórios** e Corresponder usando **--> ObjectSID e atributos msExchangeMasterAccountSID**.


### <a name="multiple-skype-for-business-server-deployments-in-multiple-forests"></a>Várias implantações do Skype for Business Server em várias florestas 

Nesse cenário, há várias florestas, cada uma contendo Skype for Business Server e uma única Microsoft 365 organização. Cada floresta que contém Skype for Business Server pode ser sincronizada no Azure AD para essa organização usando o AAD Conexão. No máximo, somente uma floresta pode ser configurada para a versão híbrida do Skype for Business em um determinado momento. Antes de habilizar o híbrido em uma floresta, todos os domínios SIP de todas as outras florestas devem ser desabilitados usando [disable-csonlineSipDomain](/powershell/module/skype/disable-csonlinesipdomain). Para obter mais informações, consulte [Consolidação de nuvem para Teams e Skype for Business](cloud-consolidation.md).

## <a name="general-requirements"></a>Requisitos gerais 

Os Teams exigem que os atributos corretos do Active Directory existam e sejam preenchidos no Azure AD. A Microsoft recomenda sincronizar todas as florestas que contenham identidades de usuário, bem como quaisquer florestas que contenham Skype for Business Server.

 Se as identidades dos usuários existirem em várias florestas, o Azure AD Connect deve fazer a mesclagem. Quando essas diretrizes forem seguidas, o Azure AD Connect sincronizará automaticamente os atributos corretos, desde que você não modifique os conectores ou as regras de sincronização no Azure AD Connect. 
  
Se você não sincronizar de todas as florestas que contenham identidades de usuário e a implantação do Skype for Business Server, você deve garantir que a identidade relevante e os atributos do Skype for Business sejam preenchidos corretamente no Azure AD para qualquer usuário que use Teams ou Skype for Business (local ou online). Isso provavelmente exigirá sincronização de diretório local adicional. Para obter mais informações, consulte [Azure AD Conexão sincronização: Atributos sincronizados com Azure Active Directory](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized).

Nesses cenários, é responsabilidade do cliente garantir a configuração adequada para preencher os atributos no Azure AD. Lembre-se do seguinte: 

- Usar uma configuração não padrão para sincronizar com o Azure AD é arriscado porque pode levar a uma configuração incorreta, o que pode causar corrupção de dados no seu diretório online.

- À medida que os produtos evoluem, a Microsoft continuará a verificar as configurações de sincronização padrão nas quais todas as florestas relevantes são sincronizadas. Clientes com configurações de sincronização personalizadas são responsáveis por garantir que suas configurações forneçam os atributos e valores corretos para o Azure AD. 

## <a name="related-information"></a>Informações relacionadas

- [O que é identidade híbrida](/azure/active-directory/hybrid/whatis-hybrid-identity)

- [Sincronização do Azure AD Conexão: compreender e personalizar a sincronização](/azure/active-directory/hybrid/how-to-connect-sync-whatis)

- [Topologias para o Azure AD Connect](/azure/active-directory/hybrid/plan-connect-topologies)

- [Sincronização do Azure AD Conexão: Atributos sincronizados com Azure Active Directory](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)