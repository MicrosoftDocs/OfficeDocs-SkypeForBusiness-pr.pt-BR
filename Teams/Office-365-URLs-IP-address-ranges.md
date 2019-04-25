---
title: URLs e intervalos de endereços IP do Office 365
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
description: Saiba como configurar corretamente URLs do Office 365 e intervalos de endereços IP, desviar o proxy direto quando estiver disponível para conexões com o serviço Microsoft Teams e as exigências das políticas de rede e segurança.
localization_priority: Normal
search.appverid: MET150
f1keywords: ms.teamsadmincenter.meetingsettings.network.ports
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e375452e236e38e036a5fe2413ba0848845587ab
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32225924"
---
<a name="office-365-urls-and-ip-address-ranges"></a>URLs e intervalos de endereços IP do Office 365
=====================================

Vá para [ URLs do Office 365 e intervalos de endereço IP](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)para obter uma lista detalhada e atualizada das URLs, dos endereços IP, das portas e dos protocolos que precisam ser configurados corretamente para o Teams. A Microsoft está aprimorando continuamente o serviço do Office 365 e acrescentando novas funcionalidades; assim, as portas, as URLs e os endereços IP necessários podem mudar com o passar do tempo. Recomendamos que você [se inscreva via RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) para receber notificações quando essas informações forem atualizadas ou alteradas.

O Teams também oferece uma experiência de chamadas e reuniões construída em uma infraestrutura de última geração baseada em nuvem, que também é utilizada para o Skype e o Skype for Business. Esses investimentos de tecnologia incluem os serviços de nuvem baseada no Windows Azure para sinalização e processamento de mídia, h. 264 codec de vídeo, SILK e Opus codec de áudio, resiliência de rede, telemetria e diagnósticos de qualidade. Assim, existem URLs e IPs obrigatórios que podem estar associados tanto ao Skype quanto ao Skype for Business.

Para todas as cargas de trabalho do Office 365, o método de conexão recomendado para os serviços do Teams é o desvio do proxy direto sempre que possível. Quando um servidor proxy fica entre um cliente e os datacenters do Office 365, a mídia pode ser forçada em TCP em vez de UDP, o que afetaria a qualidade da mídia. Baixe um exemplo de arquivos PAC do proxy que podem ser utilizados para configurar o desvio de tráfego em [Gerenciamento dos pontos de extremidade do Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a).

Se suas políticas de segurança e rede exigem o tráfego do Office 365 para fluem através de um servidor proxy, certifique-se de que os requisitos acima já sejam atendidos antes de implantar equipes em produção (revisão [Servidores Proxy para equipes ou Skype para negócios Online](proxy-servers-for-skype-for-business-online.md) Para obter orientação).
