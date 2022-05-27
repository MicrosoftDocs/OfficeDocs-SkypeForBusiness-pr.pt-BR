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
description: Saiba como configurar corretamente urLs Microsoft 365 ou Office 365 intervalos de endereços IP e ignorar o proxy de encaminhamento quando possível para conexões com Microsoft Teams serviço.
ms.localizationpriority: medium
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
ms.openlocfilehash: 1ebcf7c6595da3e1774571be4c65a796838115b3
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675713"
---
# <a name="microsoft-365-and-office-365-urls-and-ip-address-ranges"></a>Microsoft 365 e Office 365 URLs e intervalos de endereços IP

Vá para [Microsoft 365 e Office 365 URLs e intervalos de endereços IP](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) para obter uma lista detalhada e atualizada das URLs, endereços IP, portas e protocolos que devem ser configurados corretamente para Teams. A Microsoft está aprimorando continuamente o serviço do Microsoft 365 e do Office 365 e acrescentando novas funcionalidades; assim, as portas, as URLs e os endereços IP necessários podem mudar com o passar do tempo. Recomendamos que você [se inscreva via RSS](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) para receber notificações quando essas informações forem atualizadas ou alteradas.

O Teams também oferece uma experiência de chamadas e reuniões construída em uma infraestrutura de última geração baseada em nuvem, que também é utilizada para o Skype e o Skype for Business. Esses investimentos em tecnologia incluem serviços em nuvem baseados no Azure para processamento e sinalização de mídia, codecs de vídeo H.264, codecs de áudio SILK e Opus, resiliência de rede, telemetria e diagnósticos de qualidade. Assim, existem URLs e IPs obrigatórios que podem estar associados tanto ao Skype quanto ao Skype for Business.

Para todas as Microsoft 365 e Office 365, o método de conexão recomendado para Teams serviços está ignorando o proxy de encaminhamento sempre que possível. Quando um servidor proxy fica entre um cliente e os datacenters do Office 365, a mídia pode ser forçada em TCP em vez de UDP, o que afetaria a qualidade da mídia. Baixe arquivos PAC de proxy de exemplo que podem ser usados para configurar o bypass de [tráfego do gerenciamento Microsoft 365 e Office 365 de extremidade](/office365/enterprise/managing-office-365-endpoints).

Se suas políticas de rede e segurança exigirem que Microsoft 365 ou Office 365 fluam por meio de um servidor proxy, verifique se os requisitos acima já foram atendidos antes de implantar Teams em produção. Para obter mais informações, leia [Servidores Proxy para Teams ou Skype for Business Online](proxy-servers-for-skype-for-business-online.md).