---
title: Configurar o Roteamento Direto
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
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
description: Saiba como configurar o Telefone Microsoft Roteamento Direto do Sistema para conectar sua infraestrutura de telefonia local a Microsoft Teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 05e3152c13b0cf6559964d3926d7c66e7cf376e8
ms.sourcegitcommit: 197debacdcd1f7902f6e16940ef9bec8b07641af
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/02/2021
ms.locfileid: "60634890"
---
# <a name="configure-direct-routing"></a>Configurar o Roteamento Direto

Telefone Microsoft O Roteamento Direto do Sistema permite que você conecte sua infraestrutura de telefonia local a Microsoft Teams. O artigo lista as etapas de alto nível necessárias para conectar um Controlador de Borda de Sessão (SBC) local com suporte ao Roteamento Direto e como configurar usuários do Teams para usar o Roteamento Direto para se conectar à PSTN (Rede Telefônica Pública Comucionada). Este artigo vincula-se aos artigos associados para obter detalhes.  

Para obter informações sobre se o Roteamento Direto é a solução certa para sua organização, [consulte Sistema de Telefonia Roteamento Direto.](direct-routing-landing-page.md) Para obter informações sobre pré-requisitos e planejar sua implantação, consulte [Plan Direct Routing](direct-routing-plan.md).

> [!Tip]
> Você também pode assistir à sessão a seguir para saber mais sobre os benefícios do Roteamento Direto, como planejar e como implantá-la: Roteamento Direto [no](https://aka.ms/teams-direct-routing)Microsoft Teams .

Para concluir as etapas explicadas neste artigo, os administradores precisam de alguma familiaridade com cmdlets do PowerShell. Para obter mais informações sobre como usar o PowerShell, consulte [Configurar seu computador para Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell). 

Antes de executar as etapas nestes artigos, a Microsoft recomenda que você confirme se seu SBC já foi configurado conforme recomendado pelo fornecedor SBC: 

- [Documentação de implantação de AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Documentação de implantação do Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Documentação de implantação do Ribbon Communications](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Documentação de implantação do TE-Systems (anynode)](https://www.anynode.de/anynode-and-microsoft-teams/)
- [Documentação de implantação de metaswitch](https://www.metaswitch.com/products/core-network/perimeta-sbc)

Para ver uma lista completa de SBCs com suporte, consulte Lista de Controladores de Borda de Sessão [certificados para Roteamento Direto.](direct-routing-border-controllers.md)

Para configurar Telefone Microsoft Sistema e permitir que os usuários usem Roteamento Direto, siga estas etapas: 

- **Etapa 1.** [Conexão SBC com Telefone Microsoft System e validar a conexão](direct-routing-connect-the-sbc.md)
- **Etapa 2.** [Habilitar usuários para Roteamento Direto, voz e caixa postal](direct-routing-enable-users.md)
- **Etapa 3.** [Configurar roteamento de chamadas](direct-routing-voice-routing.md)
- **Etapa 4.** [Traduzir números para um formato alternativo](direct-routing-translate-numbers.md) 

Se você estiver configurando um SBC para vários locatários, você também vai querer ler Configurar um [SBC para vários locatários](direct-routing-sbc-multiple-tenants.md).


## <a name="related-topics"></a>Tópicos relacionados

[Roteamento Direto do Sistema Telefônico](direct-routing-landing-page.md)

[Planejar o Roteamento Direto](direct-routing-plan.md)