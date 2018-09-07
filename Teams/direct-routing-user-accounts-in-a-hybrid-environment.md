---
title: Contas de usuário em um ambiente híbrido com conectividade PSTN
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: ''
description: Saiba mais sobre os diferentes combinações de criação de usuário e quais combinações são ou não suporte.
ms.openlocfilehash: 8690d294755ed75b1c79a2c1fa61a4df196bc070
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23851307"
---
# <a name="user-accounts-in-a-hybrid-environment-with-pstn-connectivity"></a>Contas de usuário em um ambiente híbrido com conectividade PSTN

## <a name="about-the-environment"></a>Sobre o ambiente

Este artigo se aplica a ambientes nos quais você tem todos os seguintes itens: 
 
- Skype para Business Server 2015 ou o Lync Server 2013 
- Um locatário do Office 365 
- Conectividade híbrida configurada entre o Skype para Business Server e Skype para locatário Business Online ou equipes 
- Usuários habilitados para fazer e receber chamadas de rede de telefônica pública comutada (PSTN) para e do cliente

 
Se você tiver um ambiente diferente (por exemplo, o Skype para o conector de nuvem Business Edition), híbrida não estiver configurada ou os usuários não serão habilitados para chamadas PSTN, a matriz de suporte serão diferente.  

## <a name="about-the-combinations-and-the-supportability-statement"></a>Sobre as combinações e a declaração de suporte  

Um Skype para ambiente híbrido de negócios com conectividade PSTN fornece flexibilidade sobre onde, são fornecidos serviços de usuário e como as contas de usuário são configuradas e gerenciadas. Mas as várias opções podem criar algumas combinações sem suporte. Esta seção explica diferentes combinações de criação de usuário, seguido por uma instrução de suporte.


**Definições:**   
- **Enterprise Voice:** Opção para fornecer acesso à PSTN para usuários com Skype local para a conta de usuário de negócios. Skype local para o servidor de mediação de negócios fornece interconectividade para PSTN.  
- **Conectividade de voz híbrido:** Opção para fornecer acesso à PSTN para com Skype on-line para a conta de negócios. Skype local para o servidor de mediação de negócios fornece interconectividade para PSTN. 
- **Direcionar circulação:** Opção para fornecer acesso à PSTN para usuários com Skype online para conta de negócios, licença Teams da Microsoft, usando o cliente do Microsoft Teams. O SBC está conectado ao Proxy SIP no Office 365 sem necessidade de nenhum software no local da Microsoft.

  
**O ambiente suporta as seguintes combinações:**
- **Cenário 1:** Skype for Business no local de conta de usuário e usará o Skype para clientes corporativos com o Enterprise Voice
- **Cenário 2:** Usuário conta Skype para negócios on-line e usará o Skype para o cliente de negócios com conectividade de voz híbrida
- **Cenário 3:** Usuário conta com licença de Teams Microsoft Skype para negócios on-line e usará o cliente de equipes
 
### <a name="supportability-matrix"></a>Matriz de suporte


|**Objeto de usuário criado no**  |**Skype do usuário para o provedor de serviços corporativos**|**Cliente do usuário**|**Opção de voz**|**Compatível**|
|---------|---------|---------|---------|--------|
|No AD local| No local |Skype for Business   | Enterprise Voice   |Sim|
|No AD local|Online| Skype for Business  | Conectividade de voz híbrida   |Sim |
|No AD local|Online |Microsoft Teams |Direcionar circulação  |Sim |
|**Combinações sem suporte**    | |         |         |
|Azure AD.| No local/online | Skype para equipes de negócios/Microsoft|Conectividade/Direct roteamento de voz de voz/híbrido de empresa  |Não, o objeto de usuário deve ser criado no AD local pela primeira vez |
|No AD local  |No local| Microsoft Teams| Conectividade/Direct roteamento de voz de voz/híbrido de empresa   |Não, o cliente Microsoft Teams não é suportado com Skype local for Business |
|No AD local  |Online |Skype for Business | Direcionar circulação  | Não, não é suportado Skype para o cliente de negócios com o roteamento direto  |
|No AD local  |Online |Skype for Business  | Direcionar circulação  |Não, roteamento direto não é suportado com Skype para o cliente de negócios e usuário deve estar habilitado para o Enterprise Voice no Skype para negócios primeiro  |
|   |         |         |         ||

### <a name="supportability-statement-for-the-hybrid-environment-with-pstn"></a>Instrução de suporte para o ambiente híbrido com PSTN

Para todos os usuários, o usuário objeto **deve** ser criado no local AD e sincronizadas com o Azure AD usando a ferramenta de conectar do Azure AD. Habilitando usuários para equipes/Skype para o Business **não é suportado** se o objeto de usuário é criado diretamente no Azure AD em uma configuração híbrida. Para novos usuários, como uma nova contratação, que será habilitado diretamente para equipes, o usuário deve ser hospedado no Skype for Business no local inicialmente e movido para o registrador online. Criando usuários no Skype online para equipes ou comercial sem primeiro ativá-las em pool de local com o Enterprise Voice **não é suportada**.
  

O usuário deve ser habilitado para Skype para negócios e usando o Enterprise Voice no local Skype para ferramentas de gerenciamento de usuário de negócios. Habilitando usuários para o Skype para negócios online única **não é suportada**. Consulte [Este artigo](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises#special-considerations-when-enabling-users-for-enterprise-voice-on-premises) para obter mais detalhes sobre como habilitar usuários para Skype para negócios na configuração híbrida.