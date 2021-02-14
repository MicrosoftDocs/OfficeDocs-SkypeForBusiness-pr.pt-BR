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
description: Saiba como configurar o Roteamento Direto do Sistema De Telefonia do Microsoft Phone para conectar sua infraestrutura de telefonia local ao Microsoft Teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5388c93e741323d3dc9eda0fc51968b8b344d2cb
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701289"
---
# <a name="configure-direct-routing"></a>Configurar o Roteamento Direto

O Roteamento Direto do Sistema De Telefonia do Microsoft Phone permite conectar sua infraestrutura de telefonia local ao Microsoft Teams. O artigo lista as etapas de alto nível necessárias para conectar um SBC (Controlador de Borda de Sessão) local com suporte ao Roteamento Direto e como configurar os usuários do Teams para usar o Roteamento Direto para se conectar à PSTN (Rede Telefônica Pública Comuada). Este artigo vincula-se aos artigos associados para obter detalhes.  

Para saber mais sobre se o Roteamento Direto é a solução certa para sua organização, consulte [Roteamento Direto do Sistema de Telefonia.](direct-routing-landing-page.md) Para obter informações sobre pré-requisitos e planejar sua implantação, consulte [Planejar Roteamento Direto.](direct-routing-plan.md)

> [!Tip]
> Você também pode assistir à sessão a seguir para saber mais sobre os benefícios do Roteamento Direto, como planejar e como implantá-lo: Roteamento Direto [no Microsoft Teams.](https://aka.ms/teams-direct-routing)

Para concluir as etapas explicadas neste artigo, os administradores precisam de alguma familiaridade com cmdlets do PowerShell. Para obter mais informações sobre como usar o PowerShell, consulte [Configurar seu computador para Windows PowerShell.](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) 

Antes de executar as etapas nestes artigos, a Microsoft recomenda que você confirme que seu SBC já foi configurado conforme recomendado pelo fornecedor SBC: 

- [Documentação de implantação de AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Documentação de implantação oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Documentação de implantação de Comunicações da Faixa de Opções](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Documentação de implantação do TE-Systems (qualquernode)](https://www.anynode.de/anynode-and-microsoft-teams/)
- [Documentação de implantação metaswstat](https://www.metaswitch.com/products/core-network/perimeta-sbc)

Para ver uma lista completa de SBCs com suporte, consulte Lista de Controladores de Borda de Sessão [certificados para Roteamento Direto.](direct-routing-border-controllers.md)

Para configurar o Microsoft Phone System e permitir que os usuários usem o Roteamento Direto, siga estas etapas: 

- **Etapa 1.** [Conectar o SBC ao Microsoft Phone System e validar a conexão](direct-routing-connect-the-sbc.md)
- **Etapa 2.** [Habilitar usuários para Roteamento Direto, voz e caixa postal](direct-routing-enable-users.md)
- **Etapa 3.** [Configurar roteamento de voz](direct-routing-voice-routing.md)
- **Etapa 4.** [Traduzir números para um formato alternativo](direct-routing-translate-numbers.md) 

Se você estiver configurando um SBC para vários locatários, também vai querer ler Configurar um [SBC para vários locatários.](direct-routing-sbc-multiple-tenants.md)


## <a name="related-topics"></a>Tópicos relacionados

[Roteamento Direto do Sistema Telefônico](direct-routing-landing-page.md)

[Planejar o Roteamento Direto](direct-routing-plan.md)

