---
title: Definir um Novo Tronco
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
description: 'Você define um novo tronco de protocolo SIP fornecendo as seguintes informações:'
ms.openlocfilehash: c66d5999d6aa5bad0e9c16f8d466d82b941a630b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305918"
---
# <a name="define-a-new-trunk"></a>Definir um Novo Tronco

Você define um novo tronco de protocolo SIP fornecendo as seguintes informações:

- **Nome do tronco**: nome exclusivo na sua topologia que identificará esse tronco

- **Gateway PSTN associado**: selecione um gateway PSTN implantado e configurado na sua implantação na lista

- **Porta de escuta do gateway IP/PSTN**: porta na qual o PBX IP ou o gateway PSTN escutará. Deve ser exclusivo de todas as outras portas de escuta de tronco configuradas na sua implantação

- **Protocolo de transporte SIP**: selecione na lista o TCP ou o TLS

- **Servidor de mediação associado**: selecione na lista um servidor de mediação que é implantado e configurado em sua implantação

- **Porta do servidor de mediação associada**: defina o valor de porta igual ao valor de porta TCP ou TLS do servidor de mediação que o tronco SIP usará

## <a name="see-also"></a>Confira também

[Tronco M:N no Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[Como faço para implementar o entroncamento SIP?](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)
