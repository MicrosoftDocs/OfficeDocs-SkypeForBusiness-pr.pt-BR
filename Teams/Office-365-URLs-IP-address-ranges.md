---
title: URLs e intervalos de endereços IP do Office 365
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
description: Saiba como configurar corretamente URLs do Office 365 e intervalos de endereços IP, desviar o proxy direto quando estiver disponível para conexões com o serviço Microsoft Teams e as exigências das políticas de rede e segurança.
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 228376fb8cbfe65ba9b7c34a659489bad0f09116
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2018
ms.locfileid: "25011933"
---
<a name="office-365-urls-and-ip-address-ranges"></a>URLs e intervalos de endereços IP do Office 365
=====================================

Vá para o [Office 365 URLs e intervalos de endereços IP](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges) para uma lista detalhada e atualizada de URLs, endereços IP, portas e protocolos que devem estar corretamente configurados para equipes. A Microsoft está continuamente aperfeiçoando o serviço Office 365 e adicionar a nova funcionalidade, que significa que as portas necessárias, URLs, e endereços IP podem mudar ao longo do tempo. Recomendamos que você [Inscreva-se via RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) para receber notificações quando esta informação é atualizada ou alterada.

As equipes a experiência de chamada e reuniões é baseada da próxima geração baseado em nuvem de infra-estrutura que também é usada pelo Skype e Skype para negócios. Esses investimentos em tecnologia incluem serviços em nuvem baseados no Azure para processamento e sinalização de mídia, codecs de vídeo H.264, codecs de áudio SILK e Opus, resiliência de rede, telemetria e diagnósticos de qualidade. Assim, existem URLs e IPs obrigatórios que podem estar associados tanto ao Skype quanto ao Skype for Business.

Para todas as cargas de trabalho do Office 365, o método recomendado de conexão aos serviços de equipes é ignorando o proxy de encaminhamento onde for possível. Quando um servidor proxy fica entre um cliente e os centros de dados do Office 365, mídia será forçada sobre TCP em vez de UDP, que afetaria qualidade de mídia. Baixe arquivos de PAC de proxy de amostra que podem ser usados para configurar o bypass de tráfego de [pontos de extremidade de gerenciamento do Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a).

Se suas políticas de rede e segurança exigirem que o tráfego do Office 365 flua através de um servidor proxy, certifique-se de que as exigências acima estejam cumpridas antes de colocar o Teams em produção (veja [Servidores Proxy para o Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/proxy-servers-for-skype-for-business-online) para obter orientações.)
