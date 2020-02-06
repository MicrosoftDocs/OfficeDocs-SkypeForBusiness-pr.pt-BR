---
title: Definir um Novo Tronco
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
description: 'Você define um novo tronco de protocolo SIP fornecendo as seguintes informações:'
ms.openlocfilehash: 9b3d42500c57723b13d9c74668b3c4ad7159301b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820213"
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
