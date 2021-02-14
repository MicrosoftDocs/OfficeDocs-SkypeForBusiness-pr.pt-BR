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
description: Saiba mais sobre diferentes combinações de criação do usuário e quais combinações são suportadas ou sem suporte.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a7b41eb474d7574aa23b5fa195219794ed715424
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44690867"
---
# <a name="user-accounts-in-a-hybrid-environment-with-pstn-connectivity"></a>Contas de usuário em um ambiente híbrido com conectividade PSTN

## <a name="about-the-environment"></a>Sobre o ambiente

Este artigo se aplica aos ambientes nos quais você tem todos os seguintes: 
 
- Skype for Business Server ou Lync Server 2013 
- Uma organização do Microsoft 365 ou do Office 365 
- Conectividade híbrida configurada entre o Skype for Business Server e o Skype for Business Online ou o locatário do Microsoft Teams 
- Usuários habilitados para fazer e receber chamadas PSTN (Rede Telefônica Pública Comutado) para e para o cliente

 
Se você tiver um ambiente diferente (como o Skype for Business Cloud Connector Edition), a versão híbrida não está configurada ou os usuários não estão habilitados para chamadas PSTN, a matriz de suporte será diferente.  

## <a name="about-the-combinations-and-the-supportability-statement"></a>Sobre as combinações e a instrução de suporte  

Um ambiente híbrido do Skype for Business com conectividade PSTN fornece flexibilidade sobre onde os serviços de usuário são fornecidos e como as contas de usuário são provisionadas e gerenciadas. Mas a quantidade de opções pode criar algumas combinações sem suporte. Esta seção explica diferentes combinações de criação do usuário, seguidas por uma instrução de suporte.


**Definições:**   
- **Enterprise Voice:** Opção para fornecer acesso ao PSTN para usuários com uma conta de usuário local do Skype for Business. O servidor de Mediação do Skype for Business local fornece interconexão com o PSTN.  
- **Conectividade de Voz Híbrida:** Opção para fornecer acesso ao PSTN para usuários com a conta do Skype for Business Online. O servidor de Mediação do Skype for Business local fornece interconexão com o PSTN. 
- **Roteamento direto:** Opção para fornecer acesso ao PSTN para usuários com conta online do Skype for Business, licença do Microsoft Teams, usando o cliente microsoft teams. O SBC está conectado ao Proxy SIP no Microsoft 365 ou no Office 365 sem a necessidade de qualquer software local da Microsoft.

  
**O ambiente dá suporte às seguintes combinações:**
- **Cenário 1:** Conta de usuário no Skype for Business local e usará o cliente Skype for Business com o Enterprise Voice
- **Cenário 2:** Conta de usuário no Skype for business online e usará o cliente Skype for Business com Conectividade de Voz Híbrida
- **Cenário 3:** Conta de usuário no Skype for Business online com licença do Microsoft Teams e usará o cliente teams
 
### <a name="supportability-matrix"></a>Matriz de suporte


|**Objeto do usuário criado em**  |**Provedor de serviços do Skype for Business do usuário**|**Cliente do Usuário**|**Opção de voz**|**Compatível**|
| ------------ | --------- | --------- | --------- | -------- |
|AD local| No local |Skype for Business   | Enterprise Voice   |Sim|
|AD local|Online| Skype for Business  | Conectividade de Voz Híbrida   |Sim |
|AD local|Online |Microsoft Teams |Roteamento Direto  |Sim |
|**Combinações sem suporte**    | |         |         |      |
|Azure AD| Local/online | Skype for Business/Microsoft Teams|Enterprise Voice/Hybrid Voice Connectivity/Direct Routing  |Não, o objeto do usuário DEVE ser criado no AD local primeiro |
|AD local  |No local| Microsoft Teams| Enterprise Voice/Hybrid Voice Connectivity/Direct Routing   |Não, o cliente microsoft teams não tem suporte no Skype for Business local |     
|AD local  |Online |Skype for Business  | Roteamento Direto  |Não, o Roteamento Direto não é suportado com o cliente Skype for Business  |


### <a name="supportability-statement-for-the-hybrid-environment-with-pstn"></a>Declaração de suporte para o ambiente híbrido com PSTN

Para todos os usuários, o objeto do usuário deve ser criado no AD local e sincronizado com o Azure AD usando a ferramenta Azure AD Connect.  Não há suporte para a habilitação de usuários do Teams/Skype for **Business** se o objeto do usuário for criado diretamente no Azure AD em uma configuração híbrida. Para novos usuários, como uma nova contratação, que serão habilitados diretamente para o Teams, o usuário deve estar habilitado para o Skype for Business usando as ferramentas de gerenciamento locais do Skype for Business. Não há suporte para a criação de usuários no Skype for Business ou no Teams online sem primeiro habilita-los no pool local com o Enterprise **Voice.** Para obter mais informações sobre isso, confira o Sistema de Telefonia Do Plano com conectividade [PSTN](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)local no Skype for Business Server.
