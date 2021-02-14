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
description: Saiba como configurar o bypass de mídia com o Roteamento Direto do Sistema de Telefone para o Microsoft Teams, alternando todos os usuários de uma só vez ou implementando um ajuste de fases (recomendado).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 41e5aae3f91c13653119b04fb88364ce93a4d90c
ms.sourcegitcommit: 1e7bc16969db01317ee482cabf681febae0ef51f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/29/2020
ms.locfileid: "44416891"
---
# <a name="configure-media-bypass-with-direct-routing"></a>Configurar o bypass de mídia com Roteamento Direto

Antes de configurar o bypass de mídia com Roteamento Direto, certifique-se de que você leu o Plano de bypass de [mídia com Roteamento Direto.](direct-routing-plan-media-bypass.md)

Para ativar o bypass de mídia, as seguintes condições devem ser atendidas:

1.    Certifique-se de que o fornecedor de controle de borda de sessão (SBC) de preferência seja compatível com bypass de mídia e fornece instruções sobre como configurar o bypass no SBC. Consulte a página de certificação para saber mais sobre SBCs, quais são suportados pelo bypass de mídia e para obter instruções.

2.    Você precisa ativar o bypass de mídia no tronco usando o seguinte comando: **Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass $true.**

3.    Certifique-se de que as portas necessárias sejam abertas. 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a>Migrar de troncos não ignorados para troncos habilitados para bypass

Você pode alternar todos os usuários de uma só vez ou implementar uma fase (recomendada).

- **Alternar todos os usuários de uma só vez.** Se todas as condições são atendidas, você pode ativar o modo de bypass. No entanto, todos os seus usuários de produção serão mudados ao mesmo tempo. Como você pode ter alguns problemas inicialmente ao configurar troncos e portas, sua experiência de usuário de produção pode ser afetada. 

- **Abordagem em fases. (Recomendado)**.  Crie um novo tronco para o mesmo SBC (com uma porta diferente), teste-o e altere a política de roteamento de voz online para que os usuários apontem para o novo tronco. 

  Essa é a abordagem recomendada porque permite uma transição mais tranquila e uma experiência de usuário ininterrupta. Essa abordagem requer configuração do SBC, um novo nome FQDN e configuração do firewall. Observe que você precisará garantir que seu certificado seja compatível com ambos os troncos. Em SAN, você precisa ter dois nomes (**sbc1.contoso.com** e **sbc2.contoso.com**) ou ter um certificado curinga.

![Migrar de troncos não ignorados para troncos habilitados para bypass)](media/direct-routing-media-bypass-8.png)

Para obter instruções sobre como configurar os troncos e executar a migração, consulte a documentação do seu fornecedor SBC:

- [Documentação de implantação de AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Documentação de implantação oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Documentação de implantação de Comunicações da Faixa de Opções](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Documentação de implantação do TE-Systems (qualquernode)](https://www.anynode.de/anynode-and-microsoft-teams/)

Para ver uma lista de SBCs (Controladores de Borda de Sessão) certificados para Roteamento Direto, consulte Lista de Controladores de Rota de Sessão [certificados para Roteamento Direto.](direct-routing-border-controllers.md)



## <a name="related-topics"></a>Tópicos relacionados

[Planejar bypass de mídia com Roteamento Direto](direct-routing-plan-media-bypass.md)



