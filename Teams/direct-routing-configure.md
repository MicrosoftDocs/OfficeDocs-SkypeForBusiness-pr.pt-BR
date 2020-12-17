---
title: Configurar o Roteamento Direto
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Saiba como configurar o roteamento direto do sistema de telefone da Microsoft para conectar sua infraestrutura de telefonia local ao Microsoft Teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5388c93e741323d3dc9eda0fc51968b8b344d2cb
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701289"
---
# <a name="configure-direct-routing"></a>Configurar o Roteamento Direto

O roteamento direto do Microsoft Phone System permite que você conecte sua infraestrutura de telefonia local ao Microsoft Teams. O artigo lista as etapas de alto nível necessárias para conectar um controlador de borda de sessão local (SBC) com suporte para roteamento direto e como configurar os usuários do teams para usar o roteamento direto para se conectar à rede telefônica pública comutada (PSTN). Este artigo contém links para artigos associados para obter detalhes.  

Para saber se o roteamento direto é a solução certa para a sua organização, consulte [Roteamento direto do sistema telefônico](direct-routing-landing-page.md). Para obter informações sobre pré-requisitos e planejar sua implantação, consulte [planejar roteamento direto](direct-routing-plan.md).

> [!Tip]
> Você também pode assistir à sessão a seguir para saber mais sobre os benefícios de roteamento direto, como planejar e como implantá-lo: [Roteamento direto no Microsoft Teams](https://aka.ms/teams-direct-routing).

Para concluir as etapas explicadas neste artigo, os administradores precisam estar familiarizados com cmdlets do PowerShell. Para obter mais informações sobre como usar o PowerShell, consulte [configurar seu computador para Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell). 

Antes de executar as etapas nestes artigos, a Microsoft recomenda que você confirme que o seu SBC já foi configurado como recomendado pelo fornecedor do SBC: 

- [Documentação de implantação do AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Documentação de implantação do Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Documentação da implantação de comunicações da faixa de opções](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Documentação de implantação do anynode (File-Systems)](https://www.anynode.de/anynode-and-microsoft-teams/)
- [Documentação da implantação do metaswitch](https://www.metaswitch.com/products/core-network/perimeta-sbc)

Para obter uma lista completa do SBCs compatível, consulte [lista de controladores de borda de sessão certificados para roteamento direto](direct-routing-border-controllers.md).

Para configurar o Microsoft Phone System e permitir que os usuários usem o roteamento direto, siga estas etapas: 

- **Etapa 1.** [Conectar o SBC com o sistema Microsoft Phone e validar a conexão](direct-routing-connect-the-sbc.md)
- **Etapa 2.** [Habilite os usuários para roteamento direto, voz e correio de voz](direct-routing-enable-users.md)
- **Etapa 3.** [Configurar roteamento de voz](direct-routing-voice-routing.md)
- **Etapa 4.** [Converter números em um formato alternativo](direct-routing-translate-numbers.md) 

Se você estiver configurando um SBC para vários locatários, também vai querer ler [configurar um SBC para vários locatários](direct-routing-sbc-multiple-tenants.md).


## <a name="related-topics"></a>Tópicos relacionados

[Roteamento Direto do Sistema Telefônico](direct-routing-landing-page.md)

[Planejar o Roteamento Direto](direct-routing-plan.md)

