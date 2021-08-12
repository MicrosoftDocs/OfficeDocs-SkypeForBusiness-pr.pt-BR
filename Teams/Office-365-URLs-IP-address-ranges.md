---
title: Microsoft 365 e Office 365 URLs e intervalos de endereços IP
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 08/21/2018
ms.topic: article
audience: admin
ms.service: msteams
description: Saiba como configurar corretamente Microsoft 365 ou Office 365 URLs e intervalos de endereço IP e ignorar o proxy de encaminhamento quando possível para conexões com Microsoft Teams serviço.
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
ms.openlocfilehash: 9e5925a8896667adde58d71d01a062d975ea2fe1c5c1aec629af8db88c79b623
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54302036"
---
<a name="microsoft-365-and-office-365-urls-and-ip-address-ranges"></a>Microsoft 365 e Office 365 URLs e intervalos de endereços IP
=======================================================

Vá para Microsoft 365 e [Office 365 URLs](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) e intervalos de endereços IP para uma lista detalhada e atualizada das URLs, endereços IP, portas e protocolos que devem ser configurados corretamente para Teams. A Microsoft está aprimorando continuamente o serviço do Microsoft 365 e do Office 365 e acrescentando novas funcionalidades; assim, as portas, as URLs e os endereços IP necessários podem mudar com o passar do tempo. Recomendamos que você [se inscreva via RSS](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) para receber notificações quando essas informações forem atualizadas ou alteradas.

O Teams também oferece uma experiência de chamadas e reuniões construída em uma infraestrutura de última geração baseada em nuvem, que também é utilizada para o Skype e o Skype for Business. Esses investimentos em tecnologia incluem serviços em nuvem baseados no Azure para processamento e sinalização de mídia, codecs de vídeo H.264, codecs de áudio SILK e Opus, resiliência de rede, telemetria e diagnósticos de qualidade. Assim, existem URLs e IPs obrigatórios que podem estar associados tanto ao Skype quanto ao Skype for Business.

Para todas as Microsoft 365 e Office 365, o método de conexão recomendado Teams serviços está ignorando o proxy de encaminhamento sempre que possível. Quando um servidor proxy fica entre um cliente e os datacenters do Office 365, a mídia pode ser forçada em TCP em vez de UDP, o que afetaria a qualidade da mídia. Baixe arquivos PAC de proxy de exemplo que podem ser usados para configurar o desvio de tráfego do [Managing Microsoft 365 e Office 365 endpoints](/office365/enterprise/managing-office-365-endpoints).

Se suas políticas de rede e segurança exigirem que Microsoft 365 ou Office 365 de tráfego fluam por um servidor proxy, certifique-se de que os requisitos acima já estão atendidos antes de implantar Teams na produção. Para obter mais informações, leia [Proxy Servers for Teams ou Skype for Business Online](proxy-servers-for-skype-for-business-online.md).