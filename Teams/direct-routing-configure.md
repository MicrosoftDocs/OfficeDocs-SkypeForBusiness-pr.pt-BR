---
title: Configurar o Roteamento Direto
ms.reviewer: filippse
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
description: Saiba como configurar o Roteamento Direto da Microsoft para conectar sua infraestrutura de telefonia local a Teams Sistema de Telefonia.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b72a51008e2a5d55b57809ab5e8ae989f4ed3ec7
ms.sourcegitcommit: 5e9b50cd1b513f06734be6c024ac06d293b27089
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/10/2022
ms.locfileid: "62518573"
---
# <a name="configure-direct-routing"></a>Configurar o Roteamento Direto

O Roteamento Direto permite que você conecte sua infraestrutura de telefonia local a Microsoft Teams. O artigo lista as etapas de alto nível necessárias para conectar um Controlador de Borda de Sessão (SBC) local com suporte ao Roteamento Direto e como configurar usuários do Teams para usar o Roteamento Direto para se conectar à PSTN (Rede Telefônica Pública Comucionada). Este artigo vincula-se aos artigos associados para obter detalhes.  

Para obter informações sobre se o Roteamento Direto é a solução certa para sua organização, consulte [Opções de conectividade PSTN](pstn-connectivity.md). Para obter informações sobre pré-requisitos e planejar sua implantação, consulte [Plan Direct Routing](direct-routing-plan.md).

Para concluir as etapas explicadas neste artigo, os administradores precisam de alguma familiaridade com cmdlets do PowerShell. Para obter mais informações sobre como usar o PowerShell, consulte [Configurar seu computador para Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell). 

Antes de executar as etapas nestes artigos, a Microsoft recomenda que você confirme se seu SBC já foi configurado conforme recomendado pelo fornecedor SBC: 

- [Documentação de implantação de AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Documentação de implantação do Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Documentação de implantação do Ribbon Communications](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Documentação de implantação do TE-Systems (anynode)](https://www.anynode.de/anynode-and-microsoft-teams/)
- [Documentação de implantação de metaswitch](https://www.metaswitch.com/products/core-network/perimeta-sbc)

Para ver uma lista completa de SBCs com suporte, consulte [Controladores de Borda de Sessão certificados para Roteamento Direto](direct-routing-border-controllers.md).

Para configurar Sistema de Telefonia e permitir que os usuários usem Roteamento Direto, siga estas etapas: 

- **Etapa 1.** [Conexão SBC com Sistema de Telefonia validar a conexão](direct-routing-connect-the-sbc.md)
- **Etapa 2.** [Habilitar usuários para Roteamento Direto, voz e caixa postal](direct-routing-enable-users.md)
- **Etapa 3.** [Configurar roteamento de chamadas](direct-routing-voice-routing.md)
- **Etapa 4.** [Traduzir números para um formato alternativo](direct-routing-translate-numbers.md) 

Se você estiver configurando um SBC para vários locatários, também vai querer ler Configurar um [SBC para vários locatários](direct-routing-sbc-multiple-tenants.md).


## <a name="related-topics"></a>Tópicos relacionados

[Planejar sua solução de voz](cloud-voice-landing-page.md)

[Opções de conectividade PSTN](pstn-connectivity.md)

[Planejar o Roteamento Direto](direct-routing-plan.md)