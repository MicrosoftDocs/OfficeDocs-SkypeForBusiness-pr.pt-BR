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
- highpri
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Saiba como configurar o Roteamento Direto da Microsoft para conectar sua infraestrutura de telefonia local ao Sistema de Telefonia do Teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2adb6e9263cb573d661677b1a36b5cd24d2c8065
ms.sourcegitcommit: 401cee68d4f6f9470d614dda12b9cb023f382ff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2022
ms.locfileid: "67999366"
---
# <a name="configure-direct-routing"></a>Configurar o Roteamento Direto

O Roteamento Direto permite que você conecte sua infraestrutura de telefonia local ao Microsoft Teams. O artigo lista as etapas de alto nível necessárias para conectar um SBC (Controlador de Borda de Sessão) local com suporte ao Roteamento Direto e como configurar os usuários do Teams para usar o Roteamento Direto para se conectar à PSTN (Rede Telefônica Pública Comuada). Este artigo contém links para artigos associados para obter detalhes.  

Para obter informações sobre se o Roteamento Direto é a solução certa para sua organização, consulte as [opções de conectividade PSTN](pstn-connectivity.md). Para obter informações sobre pré-requisitos e planejar sua implantação, consulte [Planejar Roteamento Direto](direct-routing-plan.md).

Para concluir as etapas explicadas neste artigo, os administradores precisam de alguma familiaridade com os cmdlets do PowerShell. Para obter mais informações sobre como usar o PowerShell, [consulte Configurar seu computador para Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell). 

Antes de executar as etapas nestes artigos, a Microsoft recomenda que você confirme se o SBC já foi configurado conforme recomendado pelo fornecedor do SBC: 

- [Documentação de implantação do AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Documentação de implantação do Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [Documentação de implantação do Ribbon Communications](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [Documentação de implantação do TE-Systems (anynode)](https://www.anynode.de/anynode-and-microsoft-teams/)
- [Documentação de implantação do Metaswitch](https://www.metaswitch.com/products/core-network/perimeta-sbc)

Para obter uma lista completa de SBCs com suporte, consulte [Controladores de Borda de Sessão certificados para Roteamento Direto](direct-routing-border-controllers.md).

Para configurar o Sistema de Telefonia e permitir que os usuários usem o Roteamento Direto, siga estas etapas: 

- **Etapa 1.** [Conectar o SBC ao Sistema de Telefonia e validar a conexão](direct-routing-connect-the-sbc.md)
- **Etapa 2.** [Habilitar usuários para Roteamento Direto, voz e caixa postal](direct-routing-enable-users.md)
- **Etapa 3.** [Configurar o roteamento de chamadas](direct-routing-voice-routing.md)
- **Etapa 4.** [Traduzir números para um formato alternativo](direct-routing-translate-numbers.md) 

Se você estiver configurando um SBC para vários locatários, também desejará ler Configurar um [SBC para vários locatários](direct-routing-sbc-multiple-tenants.md).

## <a name="support-boundaries"></a>Limites de suporte
A Microsoft só dá suporte ao Sistema de Telefonia com Roteamento Direto quando usado com dispositivos certificados. Se houver problemas, entre em contato com o atendimento ao cliente do fornecedor SBC primeiro. Se necessário, o fornecedor do SBC encaminhará o problema para a Microsoft por meio de canais internos. A Microsoft reserva-se o direito de rejeitar casos de suporte em que um dispositivo não certificado está conectado ao Sistema de Telefonia por meio do Roteamento Direto. Se a Microsoft determinar que o problema de Roteamento Direto de um cliente é com o dispositivo SBC de um fornecedor, o cliente precisará reengajar o fornecedor SBC para obter suporte.

## <a name="related-topics"></a>Tópicos relacionados

[Planejar sua solução de voz](cloud-voice-landing-page.md)

[Opções de conectividade PSTN](pstn-connectivity.md)

[Planejar o Roteamento Direto](direct-routing-plan.md)
