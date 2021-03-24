---
title: URLs e intervalos de endereços IP e URLs do Microsoft 365 e Office 365
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 08/21/2018
ms.topic: article
audience: admin
ms.service: msteams
description: Saiba como configurar corretamente as URLs e intervalos de endereços IP do Microsoft 365 ou Office 365 e ignorar o proxy de encaminhamento quando possível para conexões com o serviço do Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingsettings.network.ports
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9a29984b0b389bacb50a9aa6512a9ccc8bfe07de
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094513"
---
<a name="microsoft-365-and-office-365-urls-and-ip-address-ranges"></a>URLs e intervalos de endereços IP e URLs do Microsoft 365 e Office 365
=======================================================

Acesse URLs e intervalos de endereços IP e [URLs do Microsoft 365 e Office 365](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) para uma lista detalhada e atualizada das URLs, endereços IP, portas e protocolos que devem ser configurados corretamente para o Teams. A Microsoft está aprimorando continuamente o serviço do Microsoft 365 e do Office 365 e acrescentando novas funcionalidades; assim, as portas, as URLs e os endereços IP necessários podem mudar com o passar do tempo. Recomendamos que você [se inscreva via RSS](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) para receber notificações quando essas informações forem atualizadas ou alteradas.

O Teams também oferece uma experiência de chamadas e reuniões construída em uma infraestrutura de última geração baseada em nuvem, que também é utilizada para o Skype e o Skype for Business. Esses investimentos em tecnologia incluem serviços em nuvem baseados no Azure para processamento e sinalização de mídia, codecs de vídeo H.264, codecs de áudio SILK e Opus, resiliência de rede, telemetria e diagnósticos de qualidade. Assim, existem URLs e IPs obrigatórios que podem estar associados tanto ao Skype quanto ao Skype for Business.

Para todas as cargas de trabalho do Microsoft 365 e do Office 365, o método de conexão recomendado para os serviços do Teams está ignorando o proxy de encaminhamento sempre que possível. Quando um servidor proxy fica entre um cliente e os datacenters do Office 365, a mídia pode ser forçada em TCP em vez de UDP, o que afetaria a qualidade da mídia. Baixe arquivos PAC de proxy de exemplo que podem ser usados para configurar o desvio de tráfego a partir do Gerenciamento de pontos de extremidade do [Microsoft 365 e do Office 365.](/office365/enterprise/managing-office-365-endpoints)

Se suas políticas de rede e segurança exigirem que o tráfego do Microsoft 365 ou do Office 365 flua através de um servidor proxy, certifique-se de que os requisitos acima já estão atendidos antes de implantar o Teams na produção. Para obter mais informações, leia [Proxy Servers for Teams ou Skype for Business Online](proxy-servers-for-skype-for-business-online.md).