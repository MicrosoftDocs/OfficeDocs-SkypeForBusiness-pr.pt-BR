---
title: Configurar o bypass de mídia com Roteamento Direto
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
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
description: Leia este tópico para saber como configurar o bypass de mídia com o roteamento direto do sistema telefônico.
ms.openlocfilehash: a9769e921ff493e67614cf903ca9206f6f50bac8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34290449"
---
# <a name="configure-media-bypass-with-direct-routing"></a>Configurar o bypass de mídia com Roteamento Direto

Antes de configurar o bypass de mídia com roteamento direto, certifique-se de ter lido [plano de bypass de mídia com roteamento direto](direct-routing-plan-media-bypass.md).

Para ativar o bypass de mídia, as seguintes condições devem ser atendidas:

1.  Verifique se o seu fornecedor de Border Border Controller (SBC) de escolha oferece suporte a bypass de mídia e fornece instruções sobre como configurar bypass no SBC. Consulte a página de certificação para saber mais sobre SBCs, quais são compatíveis com o bypass de mídia e para obter instruções.

2.  Você precisa ativar o bypass de mídia no tronco usando o seguinte comando: **set-CSOnlinePSTNGateway-Identity <sbc_FQDN>-MediaBypass $true**.

3.  Verifique se as portas necessárias estão abertas. 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a>Migrar de troncos não ignorados para troncos compatíveis com bypass

Você pode alternar todos os usuários de uma só vez ou pode implementar uma abordagem em fases (recomendado).

- **Alternar todos os usuários de uma só vez.** Se todas as condições forem atendidas, você poderá ativar o modo de bypass. No entanto, todos os usuários de produção serão trocados ao mesmo tempo. Como você pode ter alguns problemas inicialmente ao configurar troncos e portas, a experiência do usuário de produção pode ser afetada. 

- **Abordagem em fases. (Recomendado)**.  Crie um novo tronco para o mesmo SBC (com uma porta diferente), teste-o e altere a política de roteamento de voz online para que os usuários apontem para o novo tronco. 

  Essa é a abordagem recomendada porque permite uma transição mais suave e uma experiência do usuário ininterrupta. Essa abordagem requer a configuração do SBC, um novo nome FQDN e a configuração do firewall. Observação Você precisará verificar se o seu certificado dá suporte a ambos troncos. Na SAN, você precisa ter dois nomes (**sbc1.contoso.com** e **sbc2.contoso.com**) ou ter um certificado curinga.

![Migrar de troncos não ignorados para troncos compatíveis com bypass)](media/direct-routing-media-bypass-8.png)

Para obter instruções sobre como configurar os troncos e executar a migração, consulte a documentação do seu fornecedor de SBC:

- AudioCodes
- Faixa
- AnyNode (SMS)    

Para obter uma lista de controladores de borda de sessão (SBCs) certificados para roteamento direto, consulte [lista de controladores de bordas de sessão certificados para roteamento direto](direct-routing-border-controllers.md).



## <a name="see-also"></a>Confira também

[Ignorar a mídia de plano com roteamento direto](direct-routing-plan-media-bypass.md)



