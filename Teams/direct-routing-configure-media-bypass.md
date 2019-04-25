---
title: Configurar o bypass de mídia com Roteamento Direto
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
ms.openlocfilehash: 459ebd80a175fbf2c213a016436a2bf130ae9982
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32232687"
---
# <a name="configure-media-bypass-with-direct-routing"></a>Configurar o bypass de mídia com Roteamento Direto

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

Para obter uma lista de controladores de borda de sessão (SBCs) certificados para o roteamento direta, consulte a [lista de controladores de Broder sessão certified para roteamento direto](direct-routing-border-controllers.md).



## <a name="see-also"></a>Confira também

[Planejar o bypass de mídia com o roteamento direto](direct-routing-plan-media-bypass.md)



