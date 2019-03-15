---
title: Configurar o bypass de mídia com o roteamento direto
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service:
- msteams
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: Leia este tópico para saber como configurar o bypass de mídia com roteamento direto de sistema do telefone.
ms.openlocfilehash: 405f71fd0a1e0ea3e8fec6ee1061786c93fabf1b
ms.sourcegitcommit: 260635a24b282fbdf4a4aeffdb0f4f9be5407ec6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/14/2019
ms.locfileid: "30631006"
---
# <a name="configure-media-bypass-with-direct-routing"></a>Configurar o bypass de mídia com o roteamento direto

Antes de o bypass de mídia configurando com o roteamento direto, certifique-se de que você leu [Plan for media bypass com o roteamento direto](direct-routing-plan-media-bypass.md).

Para ativar o desvio de mídia, as seguintes condições devem ser atendidas:

1.  Certifique-se de que o seu fornecedor de controlador de borda de sessão (SBC) de escolha suporta bypass de mídia e fornece instruções sobre como configurar o desvio no SBC. Consulte a página de certificação para saber mais sobre SBCs, bypass de mídia de suporte que aquelas, e para obter instruções.

2.  Você precisa ativar o bypass de mídia no tronco usando o seguinte comando: **Set-CSOnlinePSTNGateway-Identity <sbc_FQDN> - MediaBypass $true**.

3.  Certifique-se de que as portas necessárias sejam abertas. 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a>Migrar do troncos não desviada para troncos desvio habilitado

Você pode alternar todos os usuários ao mesmo tempo ou você pode implementar fases abordadas (recomendado).

- **Alterne a todos os usuários ao mesmo tempo.** Se todas as condições forem atendidas, você pode ativar o modo de desvio. No entanto, todos os usuários de produção serão transferidos ao mesmo tempo. Porque você pode sofrer alguns problemas inicialmente quando você configura troncos e portas, sua experiência do usuário de produção pode ser afetada. 

- Abordagem **Phased. (Recomendado)**.  Criar um novo tronco para o mesmo SBC (com uma porta diferente), testá-lo e alterar a política de roteamento de voz online para os usuários apontar para o novo tronco. 

  Esta é a abordagem recomendada porque ela permite para uma transição mais suave e a experiência do usuário ininterrupto. Essa abordagem exige a configuração do SBC, um novo nome FQDN e a configuração do firewall. Observe que você precisará certificar-se de que seu certificado suporta ambos os troncos. Em SAN, você precisa ter dois nomes (**sbc1.contoso.com** e **sbc2.contoso.com**) ou ter um certificado curinga.

![Migrar do troncos não desviada para o desvio habilitado troncos)](media/direct-routing-media-bypass-8.png)

Para obter instruções sobre como configurar os troncos e realizar a migração, consulte a documentação do seu fornecedor de SBC:

- AudioCodes
- Faixa de opções
- TE-Systems (AnyNode)    

No momento deste comunicado, SBCs a seguir são totalmente testadas e certificados para trabalhar com o bypass de mídia:

- AudioCodes 9000 V7.20A.204.222, AudioCodes M800B-SBC / V7.20A.250.003

-   Faixa de opções
    - 5210 v06.02.xx-xxx 
    - v06.02.xx-xxx 5400,
    - v06.02.xx-xxx 5110,

-   Sistema de TE AnyNode v 3.16.2 


## <a name="see-also"></a>Consulte Também

[Planejar o bypass de mídia com o roteamento direto](direct-routing-plan-media-bypass.md)



