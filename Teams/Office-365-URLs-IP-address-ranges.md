---
title: URLs e intervalos de endereços IP do Office 365
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
description: Saiba como configurar corretamente URLs do Office 365 e intervalos de endereços IP, desviar o proxy direto quando estiver disponível para conexões com o serviço Microsoft Teams e as exigências das políticas de rede e segurança.
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: f946bc45fae230c0fd0ead9c06d0ced537bc7f92
ms.sourcegitcommit: 0c2d1766b96b99d9985f5a0f4f90b8d8bd9aa3ef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/08/2018
ms.locfileid: "18998969"
---
<a name="office-365-urls-and-ip-address-ranges"></a>URLs e intervalos de endereços IP do Office 365
=====================================

Vá para o [Office 365 URLs e intervalos de endereços IP](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_teams) para uma lista detalhada e atualizada de URLs, endereços IP, portas e protocolos que devem estar corretamente configurados para equipes. A Microsoft está continuamente aperfeiçoando o serviço Office 365 e adicionar a nova funcionalidade, que significa que as portas necessárias, URLs, e endereços IP podem mudar ao longo do tempo. Recomendamos que você [Inscreva-se via RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) para receber notificações quando esta informação é atualizada ou alterada.

As equipes a experiência de chamada e reuniões é baseada da próxima geração baseado em nuvem de infra-estrutura que também é usada pelo Skype e Skype para negócios. Esses investimentos em tecnologia incluem serviços em nuvem baseados no Azure para processamento e sinalização de mídia, codecs de vídeo H.264, codecs de áudio SILK e Opus, resiliência de rede, telemetria e diagnósticos de qualidade. Assim, existem URLs e IPs obrigatórios que podem estar associados tanto ao Skype quanto ao Skype for Business.

Para todas as cargas de trabalho do Office 365, o método recomendado de conexão aos serviços de equipes é ignorando o proxy de encaminhamento onde for possível. Quando um servidor proxy fica entre um cliente e os centros de dados do Office 365, mídia será forçada sobre TCP em vez de UDP, que afetaria qualidade de mídia. Baixe arquivos de PAC de proxy de amostra que podem ser usados para configurar o bypass de tráfego de [pontos de extremidade de gerenciamento do Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a).

Se suas políticas de segurança e rede exigem o tráfego do Office 365 para fluem através de um servidor proxy, certifique-se de que os requisitos acima já sejam atendidos antes de implantar equipes em produção (revise [Servidores Proxy para Skype para Business Online](https://support.office.com/article/Proxy-Servers-for-Skype-for-Business-Online-7acaf2c2-35fa-490f-84cd-822e446e0fc7?ui=en-US&rs=en-US&ad=US) para orientação).
