---
title: Configurar o Azure AD conectar
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Instruções para configurar o Azure Connect da AD em um ambiente híbrido.
ms.openlocfilehash: 5d27de4786c588d5d2f2a276dc20c25436bada98
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/13/2018
ms.locfileid: "27244113"
---
# <a name="configure-azure-ad-connect-for-skype-for-business-and-teams"></a>Configurar o Azure AD conectar para Skype para equipes e de negócios 
 
As organizações que possuem Skype para Business Server (ou o Lync Server) no local e quem está planejando usar equipes ou Skype para Business Online devem configurar o Azure Connect do AD para sincronizar seu diretório local com o Office 365, conforme descrito neste documento.  Isso inclui as organizações que mover diretamente do Skype para negócios local para equipes. Em particular, as organizações com Skype para negócios local devem assegurar que os atributos msRTCSIP adequadas são sincronizados no Azure AD. 

> [!NOTE]
> Os usuários de equipes existentes que também têm Skype para negócios local serão necessário ter seu Skype para conta local de negócios movida para a nuvem para obter funcionalidade completa – como a capacidade de interoperar com Skype para usuários empresariais e para se comunicar com usuários em organizações federadas. Mesmo que o usuário apenas usando equipes, este Skype on-line para a conta comercial é necessário para a infraestrutura para oferecer a funcionalidade adicional.  Para este migração ocorrer, você deve assegurar que Connect do Azure AD está configurada corretamente para que você pode habilitar híbrida.
 

## <a name="background-information"></a>Informações de plano de fundo

Azure Active Directory se conectar mantém o seu Active Directory local sincronizado continuamente com o Office 365.  Seu diretório local permanece a origem autoritativa de identidade e alterações do seu ambiente local são sincronizadas no Azure AD. Para obter mais informações, consulte [Sincronização de conectar-se do Azure AD](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/how-to-connect-sync-whatis).  Mesmo se você não estiver movendo todos os usuários no local para a nuvem, todos os usuários que usam equipes, Skype para negócios local ou Skype para Business Online devem ser sincronizados do local no Windows Azure AD para garantir a comunicação entre usuários no local e online . *Usuários em sua organização serão representados no seu local e de diretórios online.*


## <a name="configuring-azure-ad-when-you-have-skype-for-business-server"></a>Configurando o Azure AD quando você tiver Skype para Business Server 

Se você tiver uma floresta do Active Directory no local ou várias florestas, Connect do Azure AD pode ser usado em uma variedade de topologias com suporte, conforme descrito em [topologias para conectar do Azure AD](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/plan-connect-topologies).  Da perspectiva do Skype para Business Server, há três variações principais: 

1. Uma única floresta, que contém as identidades de usuário autoritativas e hospeda Skype para Business Server. 

2. Várias florestas, apenas um deles hospeda Skype para Business Server, bem como um ou mais outras florestas que contêm as identidades de usuário autoritativas (as florestas de conta). 

3. Várias implantações do Skype para Business Server em várias florestas. Desde que certos requisitos sejam atendidos, as organizações podem consolidar essas várias implantações em um único locatário do Office 365.

### <a name="single-forest"></a>Floresta única 

Se contas de usuário e Skype para negócios estiverem hospedados em uma única floresta, você deve garantir que o Azure Connect da AD está configurado para sincronizar os usuários da floresta no Azure AD.  Embora o Assistente de instalação do Windows Azure Connect da AD possui uma variedade de opções, os atributos apropriados serão sincronizados automaticamente para o Windows Azure Active Directory. Recomenda contra modificando as regras de sincronização integrada e/ou conectores que gerenciem a configuração (que não é possível a partir do Assistente de instalação).  

### <a name="multiple-forests-with-one-skype-for-business-deployment"></a>Várias florestas com um Skype para implantação de negócios 

Esse cenário geralmente é conhecido como uma topologia de floresta de recursos. As identidades de autoritativa dos usuários hospedadas em um ou mais florestas de conta e Skype para negócios é implantado em uma floresta de recurso separado (que por si só pode também hospedar as identidades de usuário autoritativo). Em geral, Skype para identidades de autoritativa dos usuários corporativos pode ser na mesma floresta do Skype para Business Server e/ou em outra floresta, fornecidas: 

- Usuários com identidades autoritativos da floresta a conta são representados na floresta de recursos (onde Skype para Business Server é implantado) como objetos de usuário desabilitado e o atributo msRTCSIP-OriginatorSID na floresta de recursos corresponde o SID no floresta de conta. Para obter mais detalhes, consulte [Configurar um ambiente de várias floresta para o híbrido Skype para negócios](configure-a-multi-forest-environment-for-hybrid.md).

- A floresta de recursos de hospedagem Skype para Business Server relações de confiança de floresta de conta.  

- Todos os objetos de usuário relevantes e atributos para identidade tanto (de florestas de conta) e Skype para negócios (de floresta de recursos) são sincronizados no Azure AD com os valores corretos por meio do Connect do Azure AD.  

 Para obter o objeto adequado e a sincronização de atributo no Azure AD em uma [floresta de várias cenário local](configure-a-multi-forest-environment-for-hybrid.md), a Microsoft recomenda usando Connect do Azure AD para sincronizar a partir de todas as florestas que ativou contas de usuário e a floresta que contém Skype para negócios.  Supondo que você sincroniza a partir de todas as florestas, você deve configurar então Azure Connect do AD para mesclar essas identidades e sincronizar com o Azure AD. Conectar do Azure AD foi projetado para manipular esse cenário e fornece uma opção incorporada no Assistente de instalação para configurar isso, incluindo a configuração âncoras para ingressar identidades.  Escolha o seguinte: identidades de usuário existirem em vários diretórios. Correspondência usando--> atributos ObjectSID e msExchangeMasterAccountSID.


### <a name="multiple-skype-for-business-server-deployments-in-multiple-forests"></a>Vários Skype para implantações de servidor de negócios em várias florestas 

Neste cenário, há várias florestas, cada contendo Skype para Business Server e um único locatário do Office 365.  Cada floresta contendo Skype para Business Server pode ser sincronizada no Azure AD para esse inquilino usando AAD se conectar. No máximo, somente uma floresta pode ser configurada para Skype para o híbrido de negócios em um determinado momento. Antes de habilitar híbrida em uma floresta, todos os domínios SIP de todas as outras florestas deverá ser desabilitados usando [disable-csonlineSipDomain](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain). Para obter mais detalhes sobre como consolidar tal ambiente ao Office 365, consulte [consolidação de nuvem para equipes e Skype para negócios](cloud-consolidation.md).

## <a name="general-requirements"></a>Requisitos gerais 

As equipes e do Skype para serviços corporativos Online exigem que os atributos do Active Directory corretos existirem e estiver preenchidos no Azure AD.  Recomendação geral da Microsoft deve sincronizar todas as florestas que contêm as identidades de usuário, bem como qualquer florestas que contenham Skype para Business Server.

 Se identidades dos usuários existirem em várias florestas, Connect do Azure AD deve fazer a mesclagem. Quando esta orientação é seguida, Connect do Azure AD sincronizará automaticamente os atributos corretos, desde que você não modifique o conectores ou regras de sincronização no Connect do Azure AD. 
  
Se você não sincronizar de todas as florestas que contêm o Skype para implantação de servidor de negócios e identidades de usuário, você ainda deve verificar a identidade relevante e Skype dos atributos de negócios sejam preenchidos corretamente no Azure AD para qualquer usuário usando equipes ou Skype para negócios (se local ou online) – que provavelmente precisarão adicionais local sincronização de diretórios. Para obter mais informações, consulte [sincronização do Azure Connect da AD: atributos são sincronizados com o Windows Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized).

Nesses cenários, é responsabilidade do cliente para garantir uma configuração adequada para popular os atributos no Azure AD. Considere o seguinte: 

- O uso de uma configuração não padrão para sincronizar com o Azure AD é riscado porque ele poderá levar à configuração incorreta, o que pode causar corrupção de dados em seu diretório online.

- Evolução de produtos, Microsoft continuará verificar as configurações de sincronização padrão no qual todas as florestas relevantes são sincronizadas. Clientes com as configurações de sincronização personalizadas são responsáveis por garantir que suas configurações fornecem os corretos atributos e valores no Azure AD. 

## <a name="related-information"></a>Informações relacionadas

- [Qual é a identidade híbrida](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/whatis-hybrid-identity?toc=%2Fen-us%2Fazure%2Factive-directory%2Fhybrid%2FTOC.json&bc=%2Fen-us%2Fazure%2Fbread%2Ftoc.json)

- [Sincronização do Azure AD Connect: compreender e personalizar a sincronização](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/how-to-connect-sync-whatis)

- [Conecte-se de topologias do Azure AD.](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/plan-connect-topologies)

- [Sincronização do Azure AD Connect: atributos são sincronizados com o Active Directory do Windows Azure](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)
