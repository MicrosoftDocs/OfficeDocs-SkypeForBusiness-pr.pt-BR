---
title: Configurar o Azure AD Connect
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
description: Instruções para configurar o Azure AD Connect em um ambiente híbrido.
ms.openlocfilehash: 7ae6fb7d3df6d955437a51224637264033bfa662
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41982986"
---
# <a name="configure-azure-ad-connect-for-teams-and-skype-for-business"></a>Configurar o Azure AD Connect para o Teams e o Skype for Business
 
As organizações que têm o Skype for Business Server (ou o Lync Server) no local e que planejam usar o Teams ou o Skype for Business online devem configurar o Azure AD Connect para sincronizar seu diretório local com o Office 365, conforme descrito neste documento.  Isso inclui organizações que se movem diretamente do Skype for Business no local para o Microsoft Teams. Em particular, as organizações com o Skype for Business no local devem garantir que os atributos apropriados do msRTCSIP sejam sincronizados com o Azure AD. 

> [!NOTE]
> Os usuários existentes do teams que também têm o Skype for Business local precisarão ter sua conta local do Skype for Business movida para a nuvem para obter a funcionalidade completa, como a capacidade de interoperar com os usuários do Skype for Business e para comunicar-se com usuários em organizações federadas. Mesmo que o usuário esteja apenas usando o Microsoft Teams, essa conta do Skype for Business Online é exigida pela infraestrutura para fornecer a funcionalidade adicional.  Para que essa migração tenha efeito, você deve garantir que o Azure AD Connect esteja configurado corretamente para que você possa habilitar o híbrido.
 

## <a name="background-information"></a>Informações gerais

O Azure Active Directory Connect mantém seu Active Directory local sincronizado continuamente com o Office 365.  Seu diretório local permanece com a fonte autoritativa de identidade, e as alterações de seu ambiente local são sincronizadas no Azure AD. Para obter mais informações, consulte [Azure ad Connect Sync](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).  Mesmo que você não esteja movendo todos os usuários do local para a nuvem, todos os usuários que usam o Microsoft Teams, o Skype for Business no local ou o Skype for Business online devem ser sincronizados no local no Azure AD para garantir a comunicação entre usuários locais e online. *Os usuários da sua organização serão representados em seus diretórios locais e online.*


## <a name="configuring-azure-ad-when-you-have-skype-for-business-server"></a>Configurando o Azure AD quando você tiver o Skype for Business Server 

Independentemente de você ter uma floresta local do Active Directory ou várias florestas, o Azure AD Connect pode ser usado em uma variedade de topologias com suporte, conforme descrito em [topologias para o Azure ad Connect](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-topologies).  Da perspectiva do Skype for Business Server, há três variações principais: 

1. Uma única floresta, que contém identidades de usuário autoritativa e hospeda o Skype for Business Server. 

2. Várias florestas, apenas uma das quais hospeda o Skype for Business Server, bem como uma ou mais florestas que contêm identidades de usuário autoritativa (as florestas de contas). 

3. Várias implantações do Skype for Business Server em várias florestas. Desde que determinados requisitos sejam atendidos, as organizações podem consolidar essas várias implantações em um único locatário do Office 365.

### <a name="single-forest"></a>Floresta única 

Se as contas de usuário e o Skype for Business estiverem hospedados em uma única floresta, você deverá garantir que o Azure AD Connect esteja configurado para sincronizar os usuários dessa floresta no Azure AD.  Embora o assistente de instalação do Azure AD Connect tenha várias opções, os atributos apropriados serão automaticamente sincronizados no Azure Active Directory. Os clientes são aconselhados a modificar as regras de sincronização internas e/ou conectores que gerenciam a configuração (o que não é possível do assistente de instalação).  

### <a name="multiple-forests-with-one-skype-for-business-deployment"></a>Várias florestas com uma implantação do Skype for Business 

Este cenário geralmente é conhecido como uma topologia de floresta de recursos. As identidades autoritativas dos usuários são hospedadas em uma ou mais florestas de contas, e o Skype for Business é implantado em uma floresta de recursos separada (o que também pode hospedar identidades de usuário autoritativo). Em geral, as identidades autoritativas dos usuários do Skype for Business podem estar na mesma floresta que o Skype for Business Server e/ou em outra floresta, contanto: 

- Os usuários com identidades autoritativas das florestas de contas são representados na floresta de recursos (onde o Skype for Business Server é implantado) como objetos de usuário desabilitados e o atributo msRTCSIP-OriginatorSID na floresta de recursos corresponde ao SID no floresta de contas. Para obter mais detalhes, consulte [configurar um ambiente de várias florestas para o Skype for Business híbrido](configure-a-multi-forest-environment-for-hybrid.md).

- A floresta de recursos que hospeda o Skype for Business Server confia nas florestas de conta.  

- Todos os objetos e atributos de usuário relevantes para a identidade (de florestas de contas) e o Skype for Business (da floresta de recursos) são sincronizados no Azure AD com os valores corretos por meio do Azure AD Connect.  

 Para obter uma sincronização adequada de objeto e de atributo para o Azure AD em um [cenário de várias florestas no local](configure-a-multi-forest-environment-for-hybrid.md), a Microsoft recomenda usar o Azure ad Connect para sincronizar de todas as florestas que possuem contas de usuário e floresta que contenham o Skype for Business.  Supondo que você sincronize de todas as florestas, você deve configurar o Azure AD Connect para mesclar essas identidades e sincronizar com o Azure AD. O Azure AD Connect foi projetado para lidar com esse cenário e fornece uma opção interna no assistente de instalação para configurar isso, incluindo a configuração de âncoras para ingressar em identidades.  Escolha o seguinte: as identidades de usuário existem em vários diretórios. Match usando--> ObjectID e atributos msExchangeMasterAccountSID.


### <a name="multiple-skype-for-business-server-deployments-in-multiple-forests"></a>Várias implantações do Skype for Business Server em várias florestas 

Neste cenário, há várias florestas, cada uma contendo o Skype for Business Server e um único locatário do Office 365.  Cada floresta que contém o Skype for Business Server pode ser sincronizada no Azure AD para esse locatário usando o AAD Connect. No máximo, apenas uma floresta pode ser configurada para o Skype for Business híbrido em um determinado momento. Antes de habilitar o híbrido em uma floresta, todos os domínios SIP de todas as outras florestas devem ser desabilitados usando [Disable-csonlineSipDomain](https://docs.microsoft.com/powershell/module/skype/disable-csonlinesipdomain). Para obter mais detalhes sobre como consolidar tal ambiente no Office 365, consulte [Cloud Consolidation for Teams and Skype for Business](cloud-consolidation.md).

## <a name="general-requirements"></a>Requisitos gerais 

Tanto o Teams quanto o Skype for Business Online Services exigem que os atributos corretos do Active Directory existam e estejam preenchidos no Azure AD.  A recomendação geral da Microsoft é sincronizar todas as florestas que contêm identidades de usuário, bem como quaisquer florestas que contenham o Skype for Business Server.

 Se as identidades dos usuários existirem em várias florestas, o Azure AD Connect deve fazer a mesclagem. Quando esta orientação for seguida, o Azure AD Connect sincronizará automaticamente os atributos corretos, desde que você não modifique os conectores ou as regras de sincronização no Azure AD Connect. 
  
Se você não sincronizar de todas as florestas que contêm identidades de usuário e a implantação do Skype for Business Server, ainda deverá garantir que os atributos relevantes de identidade e Skype for Business sejam preenchidos corretamente no Azure AD para qualquer usuário que use o Microsoft Teams ou o Skype for Business (seja no local ou online), o que provavelmente exigirá a sincronização de diretório local adicional. Para obter mais informações, confira [sincronização do Azure ad Connect: atributos sincronizados com o Azure Active Directory](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized).

Nesses cenários, é responsabilidade do cliente garantir uma configuração adequada para preencher os atributos no Azure AD. Lembre-se do seguinte: 

- O uso de uma configuração não padrão para sincronização com o Azure AD é arriscado porque pode levar a uma configuração incorreta, o que pode causar corrupção de dados no seu diretório online.

- À medida que os produtos evoluem, a Microsoft continuará verificando as configurações de sincronização padrão nas quais todas as florestas relevantes estão sincronizadas. Os clientes com configurações de sincronização personalizadas são responsáveis por garantir que suas configurações forneçam os atributos e valores corretos no Azure AD. 

## <a name="related-information"></a>Informações relacionadas

- [O que é a identidade híbrida](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-hybrid-identity?toc=%2Fen-us%2Fazure%2Factive-directory%2Fhybrid%2FTOC.json&bc=%2Fen-us%2Fazure%2Fbread%2Ftoc.json)

- [Sincronização do Azure AD Connect: compreender e personalizar a sincronização](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)

- [Topologias para o Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-topologies)

- [Sincronização do Azure AD Connect: atributos sincronizados com o Azure Active Directory](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)
