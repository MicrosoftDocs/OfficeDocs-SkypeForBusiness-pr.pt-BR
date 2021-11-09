---
title: Configurando troncos em Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Como parte da implantação Enterprise Voice, você pode configurar um tronco entre um Servidor de Mediação e um ou mais pares para fornecer conectividade PSTN (rede telefônica pública comutado) para Enterprise Voice clientes e dispositivos em sua organização.
ms.openlocfilehash: 318b049c8ebaaa1a2df445bf1158184e3b150a84
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60838513"
---
# <a name="configuring-trunks-in-skype-for-business-server"></a>Configurando troncos em Skype for Business Server

Como parte da implantação Enterprise Voice, você pode configurar um tronco entre um Servidor de Mediação e um ou mais dos seguintes pares para fornecer conectividade PSTN (rede telefônica pública comutado) para clientes e dispositivos Enterprise Voice em sua organização:

- Conexão tronco SIP em um provedor de serviço de telefonia por Internet (ITSP)
- Gateway PSTN
- Central privada de comutação telefônica (PBX)

Para obter detalhes, [consulte Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).

> [!IMPORTANT]
> Antes de começar a configuração do tronco, verifique se a topologia foi criada e se o Servidor de Mediação e seus pares foram configurados e associados um ao outro. Para obter detalhes, [consulte Define a gateway in Topology Builder in Skype for Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).

> [!NOTE]
> Como parte da configuração do tronco, você pode habilitar o recurso Skype for Business Server de desvio de mídia, que permite que a mídia ignore o Servidor de Mediação. Os troncos podem ser configurados com ou sem o desvio de mídia habilitado, mas recomendamos fortemente que você o habilite. Para obter detalhes, consulte [Plan for media bypass in Skype for Business](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).
