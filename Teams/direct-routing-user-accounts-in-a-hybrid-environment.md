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
description: Saiba mais sobre diferentes combinações de criação de usuários e quais combinações têm suporte ou não são suportadas.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 8bdab33d6f1f009ce51afe999923f4f6f5d1905a
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43141074"
---
# <a name="user-accounts-in-a-hybrid-environment-with-pstn-connectivity"></a>Contas de usuário em um ambiente híbrido com conectividade PSTN

## <a name="about-the-environment"></a>Sobre o ambiente

Este artigo se aplica a ambientes nos quais você tem todas as seguintes opções: 
 
- Skype for Business Server ou Lync Server 2013 
- Um locatário do Office 365 
- Conectividade híbrida configurada entre o Skype for Business Server e o Skype for Business online ou o Microsoft Teams locatário 
- Usuários que estão habilitados para fazer e receber chamadas PSTN (rede telefônica pública comutada) para e do cliente

 
Se você tem um ambiente diferente (como o Skype for Business Cloud Connector Edition), híbrido não está configurado ou os usuários não estão habilitados para chamadas PSTN, a matriz de suporte será diferente.  

## <a name="about-the-combinations-and-the-supportability-statement"></a>Sobre as combinações e a declaração de suporte  

Um ambiente híbrido do Skype for Business com conectividade PSTN fornece flexibilidade quanto ao local em que os serviços do usuário são oferecidos e como as contas de usuário são provisionadas e gerenciadas. Mas a abundância de opções pode criar algumas combinações sem suporte. Esta seção explica diferentes combinações de criação de usuário, seguidas por uma declaração de suporte.


**Definições**   
- **Enterprise Voice:** Opção para fornecer acesso à PSTN para usuários com conta de usuário local do Skype for Business. O servidor de mediação do Skype for Business local fornece interconectividade à PSTN.  
- **Conectividade de voz híbrida:** Opção para fornecer acesso à PSTN para usuários com a conta do Skype for Business online. O servidor de mediação do Skype for Business local fornece interconectividade à PSTN. 
- **Roteamento direto:** Opção para fornecer acesso à PSTN para usuários com uma conta do Skype for Business Online, licença do Microsoft Teams, usando o cliente do Microsoft Teams. O SBC está conectado ao proxy SIP no Office 365 sem necessidade de qualquer software local da Microsoft.

  
**O ambiente tem suporte para as seguintes combinações:**
- **Cenário 1:** Conta de usuário no Skype for Business local e usará o cliente Skype for Business com Enterprise Voice
- **Cenário 2:** Conta de usuário no Skype for Business Online e usará o cliente Skype for Business com conectividade de voz híbrida
- **Cenário 3:** Conta de usuário no Skype for Business online com licença do Microsoft Teams e usará o cliente do Microsoft Teams
 
### <a name="supportability-matrix"></a>Matriz de suporte


|**Objeto de usuário criado em**  |**Provedor de serviços do Skype for Business do usuário**|**Cliente do usuário**|**Opção de voz**|**Compatível**|
| ------------ | --------- | --------- | --------- | -------- |
|No anúncio local| No local |Skype for Business   | Enterprise Voice   |Sim|
|No anúncio local|Online| Skype for Business  | Conectividade de voz híbrida   |Sim |
|No anúncio local|Online |Microsoft Teams |Roteamento Direto  |Sim |
|**Combinações sem suporte**    | |         |         |      |
|Azure AD| Local/online | Skype for Business/Microsoft Teams|Conectividade de voz do Enterprise Voice/Hybrid/roteamento direto  |Não, o objeto do usuário deve ser criado primeiro no AD local |
|No anúncio local  |No local| Microsoft Teams| Conectividade de voz do Enterprise Voice/Hybrid/roteamento direto   |Não, o cliente do Microsoft Teams não é compatível com o Skype for Business local |     
|No anúncio local  |Online |Skype for Business  | Roteamento Direto  |Não, o roteamento direto não é compatível com o cliente Skype for Business, e o usuário deve ser habilitado para o Enterprise Voice no Skype for Business primeiro.  |


### <a name="supportability-statement-for-the-hybrid-environment-with-pstn"></a>Instrução de suporte para o ambiente híbrido com PSTN

Para todos os usuários, o objeto de usuário **deve** ser criado no anúncio local e sincronizado com o Azure ad usando a ferramenta Azure ad Connect. **Não há suporte** para habilitar usuários do teams/Skype for Business se o objeto do usuário for criado diretamente no Azure AD em uma configuração híbrida. Para novos usuários, como uma nova contratação, que será habilitada diretamente para o Teams, o usuário deverá estar habilitado para o Skype for Business usando as ferramentas de gerenciamento do Skype for Business locais. **Não há suporte para**a criação de usuários no Skype for Business ou em equipes online sem antes habilitá-las no pool local com o Enterprise Voice. Para obter mais informações sobre isso, confira [planejar o sistema telefônico no Office 365 com conectividade PSTN local no Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity).
