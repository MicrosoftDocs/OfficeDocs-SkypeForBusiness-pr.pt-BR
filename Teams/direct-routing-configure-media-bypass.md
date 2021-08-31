---
title: Configurar o bypass de mídia com Roteamento Direto
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Saiba como configurar o bypass de mídia com Sistema de Telefonia Roteamento Direto para Microsoft Teams alternando todos os usuários de uma só vez ou implementando uma abordagem em fases (recomendado).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c0f0ad9d25157058c048b0f12cf72b3755e65e11
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58728680"
---
# <a name="configure-media-bypass-with-direct-routing"></a>Configurar o bypass de mídia com Roteamento Direto

Antes de configurar o bypass de mídia com Roteamento Direto, certifique-se de ter lido [Plan for media bypass with Direct Routing](direct-routing-plan-media-bypass.md).

Para ativar o bypass de mídia, as seguintes condições devem ser atendidas:

1.    Certifique-se de que o fornecedor de opção do Controlador de Borda de Sessão (SBC) oferece suporte ao bypass de mídia e fornece instruções sobre como configurar o bypass no SBC. Consulte a página de certificação para saber mais sobre SBCs, quais suportam bypass de mídia e para obter instruções.

2.    Você precisa ativar o bypass de mídia no tronco usando o seguinte comando:  **Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass $true**.

3.    Certifique-se de que as portas necessárias estão abertas. 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a>Migrar de troncos não ignorados para troncos habilitados para bypass

Você pode alternar todos os usuários de uma só vez ou implementar uma abordagem em fases (recomendada).

- **Alternar todos os usuários de uma só vez.** Se todas as condições são atendidas, você pode ativar o modo de desvio. No entanto, todos os usuários de produção serão trocados ao mesmo tempo. Como você pode ter alguns problemas inicialmente ao configurar troncos e portas, sua experiência de usuário de produção pode ser afetada. 

- **Abordagem em fases. (Recomendado)**.  Crie um novo tronco para o mesmo SBC (com uma porta diferente), teste-o e altere a política de roteamento de voz online para que os usuários apontem para o novo tronco. 

  Essa é a abordagem recomendada porque permite uma transição mais suave e uma experiência de usuário ininterrupta. Essa abordagem requer a configuração do SBC, um novo nome FQDN e configuração do firewall. Observe que você precisará certificar-se de que seu certificado dá suporte a ambos os troncos. Em SAN, você precisa ter dois nomes (**sbc1.contoso.com** e **sbc2.contoso.com**) ou ter um certificado curinga.

![Migrar de troncos não ignorados para troncos habilitados para bypass).](media/direct-routing-media-bypass-8.png)

Para obter instruções sobre como configurar os troncos e executar a migração, consulte a documentação do fornecedor SBC:

- [Documentação de implantação de AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Documentação de implantação do Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Documentação de implantação do Ribbon Communications](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Documentação de implantação do TE-Systems (anynode)](https://www.anynode.de/anynode-and-microsoft-teams/)

Para uma lista de Controladores de Borda de Sessão (SBCs) certificados para Roteamento Direto, consulte Lista de Controladores de Broder de Sessão [certificados para Roteamento Direto](direct-routing-border-controllers.md).



## <a name="related-topics"></a>Tópicos relacionados

[Planejar bypass de mídia com Roteamento Direto](direct-routing-plan-media-bypass.md)



