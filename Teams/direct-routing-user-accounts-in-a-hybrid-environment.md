---
title: Contas de usuário em ambiente híbrido com PSTN
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Saiba mais sobre diferentes combinações de criação de usuário e quais combinações são suportadas ou sem suporte.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d55f72bc9b22a3bb1e1ba889f24cf7a7ea0cbb53
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096321"
---
# <a name="user-accounts-in-a-hybrid-environment-with-pstn-connectivity"></a>Contas de usuário em um ambiente híbrido com conectividade PSTN

## <a name="about-the-environment"></a>Sobre o ambiente

Este artigo se aplica a ambientes nos quais você tem todos os seguintes: 
 
- Skype for Business Server ou Lync Server 2013 
- Uma Microsoft 365 ou Office 365 organização 
- Conectividade híbrida configurada entre o Skype for Business Server e Skype for Business Online ou Microsoft Teams locatário 
- Usuários habilitados para fazer e receber chamadas PSTN (Rede Telefônica Pública Comucionada) de e para o cliente

 
Se você tiver um ambiente diferente (como Skype for Business Cloud Connector Edition), híbrido não será configurado ou seus usuários não estarão habilitados para chamadas PSTN, a matriz de suporte será diferente.  

## <a name="about-the-combinations-and-the-supportability-statement"></a>Sobre as combinações e a instrução de suporte  

Um Skype for Business híbrido com conectividade PSTN fornece flexibilidade em relação ao local onde os serviços de usuário são fornecidos e como as contas de usuário são provisionadas e gerenciadas. Mas a abundância de opções pode criar algumas combinações sem suporte. Esta seção explica diferentes combinações de criação do usuário, seguidas por uma instrução de suporte.


**Definições:**   
- **Enterprise Voice:** Opção para fornecer acesso à PSTN para usuários com uma conta Skype for Business usuário local. O servidor de mediação Skype for Business local fornece interconectividade ao PSTN.  
- **Conectividade de Voz Híbrida:** Opção para fornecer acesso à PSTN para usuários com Skype for Business online. O servidor de mediação Skype for Business local fornece interconectividade ao PSTN. 
- **Roteamento direto:** Opção para fornecer acesso à PSTN para usuários com conta Skype for Business online, Microsoft Teams licença, usando Microsoft Teams cliente. O SBC está conectado ao Proxy SIP em Microsoft 365 ou Office 365 sem a necessidade de qualquer software local da Microsoft.

  
**O ambiente dá suporte às seguintes combinações:**
- **Cenário 1:** Conta de usuário Skype for Business local e usará o cliente Skype for Business com Enterprise Voice
- **Cenário 2:** Conta de usuário no Skype para empresas online e usará o cliente Skype for Business com Conectividade de Voz Híbrida
- **Cenário 3:** Conta de usuário Skype for Business online com Microsoft Teams licença e usará Teams cliente
 
### <a name="supportability-matrix"></a>Matriz de suporte


|**Objeto User criado em**  |**Provedor de serviços Skype for Business usuário**|**Cliente do usuário**|**Opção Voz**|**Compatível**|
| ------------ | --------- | --------- | --------- | -------- |
|AD local| No local |Skype for Business   | Enterprise Voice   |Sim|
|AD local|Online| Skype for Business  | Conectividade de Voz Híbrida   |Sim |
|AD local|Online |Microsoft Teams |Roteamento Direto  |Sim |
|**Combinações sem suporte**    | |         |         |      |
|Azure AD| Local/online | Skype for Business/Microsoft Teams|Enterprise Voice/Conectividade de Voz Híbrida/Roteamento Direto  |Não, o objeto user DEVE ser criado no AD local primeiro |
|AD local  |No local| Microsoft Teams| Enterprise Voice/Conectividade de Voz Híbrida/Roteamento Direto   |Não, Microsoft Teams cliente não tem suporte com Skype for Business |     
|AD local  |Online |Skype for Business  | Roteamento Direto  |Não, o Roteamento Direto não é suportado com Skype for Business cliente  |


### <a name="supportability-statement-for-the-hybrid-environment-with-pstn"></a>Instrução de suporte para o ambiente híbrido com PSTN

Para todos os usuários, o objeto do usuário deve ser criado no AD local e sincronizado com o Azure AD usando a ferramenta de Conexão do Azure AD.  Não há suporte para Teams/Skype for Business  se o objeto do usuário for criado diretamente no Azure AD em uma configuração híbrida. Para novos usuários, como um novo contratado, que será habilitado diretamente para Teams, o usuário deve estar habilitado para Skype for Business usando ferramentas de gerenciamento locais Skype for Business locais. A criação de usuários em Skype for Business ou Teams online sem primeiro habilita-los no pool local com Enterprise Voice **não é suportado**. Para obter mais informações sobre isso, confira Plan Sistema de Telefonia com conectividade [PSTN](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)local em Skype for Business Server .