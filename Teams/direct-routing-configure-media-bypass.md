---
title: Configurar o bypass de mídia com Roteamento Direto
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Saiba como configurar o bypass de mídia com o roteamento direto do sistema telefônico ao alternar todos os usuários de uma só vez ou implementar uma abordagem em fases (recomendado).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2d6bb25296b7a98e6fea7a59a5dd9406622dbd96
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904833"
---
# <a name="configure-media-bypass-with-direct-routing"></a>Configurar o bypass de mídia com Roteamento Direto

Antes de configurar o bypass de mídia com roteamento direto, certifique-se de ter lido [plano de bypass de mídia com roteamento direto](direct-routing-plan-media-bypass.md).

Para ativar o bypass de mídia, as seguintes condições devem ser atendidas:

1.    Verifique se o seu fornecedor de Border Border Controller (SBC) de escolha oferece suporte a bypass de mídia e fornece instruções sobre como configurar bypass no SBC. Consulte a página de certificação para saber mais sobre SBCs, quais são compatíveis com o bypass de mídia e para obter instruções.

2.    Você precisa ativar o bypass de mídia no tronco usando o seguinte comando: **set-CSOnlinePSTNGateway-Identity <sbc_FQDN>-MediaBypass $true**.

3.    Verifique se as portas necessárias estão abertas. 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a>Migrar de troncos não ignorados para troncos compatíveis com bypass

Você pode alternar todos os usuários de uma só vez ou pode implementar uma abordagem em fases (recomendado).

- **Alternar todos os usuários de uma só vez.** Se todas as condições forem atendidas, você poderá ativar o modo de bypass. No entanto, todos os usuários de produção serão trocados ao mesmo tempo. Como você pode ter alguns problemas inicialmente ao configurar troncos e portas, a experiência do usuário de produção pode ser afetada. 

- **Abordagem em fases. (Recomendado)**.  Crie um novo tronco para o mesmo SBC (com uma porta diferente), teste-o e altere a política de roteamento de voz online para que os usuários apontem para o novo tronco. 

  Essa é a abordagem recomendada porque permite uma transição mais suave e uma experiência do usuário ininterrupta. Essa abordagem requer a configuração do SBC, um novo nome FQDN e a configuração do firewall. Observação Você precisará verificar se o seu certificado dá suporte a ambos troncos. Na SAN, você precisa ter dois nomes (**sbc1.contoso.com** e **sbc2.contoso.com**) ou ter um certificado curinga.

![Migrar de troncos não ignorados para troncos compatíveis com bypass)](media/direct-routing-media-bypass-8.png)

Para obter instruções sobre como configurar os troncos e executar a migração, consulte a documentação do seu fornecedor de SBC:

- [Documentação de implantação do AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Documentação de implantação do Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Documentação da implantação de comunicações da faixa de opções](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Documentação de implantação do anynode (File-Systems)](https://www.anynode.de/anynode-and-microsoft-teams/)

Para obter uma lista de controladores de borda de sessão (SBCs) certificados para roteamento direto, consulte [lista de controladores de bordas de sessão certificados para roteamento direto](direct-routing-border-controllers.md).



## <a name="related-topics"></a>Tópicos relacionados

[Ignorar a mídia de plano com roteamento direto](direct-routing-plan-media-bypass.md)



