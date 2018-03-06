---
title: "URLs e intervalos de endereços IP do Office 365"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Saiba como configurar corretamente URLs do Office 365 e intervalos de endereços IP, desviar o proxy direto quando estiver disponível para conexões com o serviço Microsoft Teams e as exigências das políticas de rede e segurança."
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 597d9ceb2f72fcd624b3071d26264ce74650cc0c
ms.sourcegitcommit: 85105cb4e42ae8eb6e7e76eaf6d4dd5b9568cf41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2018
---
<a name="office-365-urls-and-ip-address-ranges"></a>URLs e intervalos de endereços IP do Office 365
=====================================

Analise o link a seguir para obter uma lista de dados detalhada e atualizada das portas e IPs exatos que precisam ser configurados corretamente: [URLs e intervalos de endereços IP do Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&rs=en-US&ad=US). A Microsoft está aprimorando continuamente o serviço do Office 365 e acrescentando novas funcionalidades; assim, as portas, URLs e endereços IP necessários podem mudar com o passar do tempo. Consulte o guia de [URLs e intervalos de endereços IP do Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) para obter as versões mais recentes de portas e protocolos. É também altamente recomendável [inscrever-se via RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) para receber notificações quando os endpoints forem atualizados ou modificados.

Conforme mencionado, a experiência de chamadas e reuniões do Microsoft Teams é construída em uma infraestrutura de última geração baseada em nuvem, que também é utilizada para o Skype e o Skype for Business. Esses investimentos em tecnologia incluem serviços em nuvem baseados no Azure para processamento e sinalização de mídia, codecs de vídeo H.264, codecs de áudio SILK e Opus, resiliência de rede, telemetria e diagnósticos de qualidade. Assim, existem URLs e IPs obrigatórios que podem estar associados tanto ao Skype quanto ao Skype for Business.

Para todas as cargas de trabalho do Office 365, o método de conexão recomendado para os serviços Microsoft Teams é o desvio do proxy direto sempre que possível. Quando um servidor proxy fica entre um cliente e os datacenters do Office 365, a mídia pode ser forçada em TCP em vez de UDP, o que afetaria a qualidade da mídia. Um exemplo de arquivos PAC do proxy que podem ser utilizados para configurar o desvio de tráfego pode ser baixado de [Gerenciamento dos endpoints do Office 365](https://support.office.com/article/managing-Office-365-endpoints-99cab9d4-ef59-4207-9f2b-3728eb46bf9a) guide.

Se suas políticas de rede e segurança exigirem que o tráfego do Office 365 flua através de um servidor proxy, certifique-se de que as exigências acima já estão cumpridas antes de colocar o Microsoft Teams em produção (veja [Servidores Proxy para o Skype for Business Online](https://support.office.com/article/Proxy-Servers-for-Skype-for-Business-Online-7acaf2c2-35fa-490f-84cd-822e446e0fc7?ui=en-US&rs=en-US&ad=US) para obter orientações.)
