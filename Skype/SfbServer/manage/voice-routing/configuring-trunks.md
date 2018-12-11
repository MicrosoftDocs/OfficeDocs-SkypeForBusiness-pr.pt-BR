---
title: Configurando troncos no Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Como parte da implantação do Enterprise Voice, você pode configurar um tronco entre um servidor de mediação e um ou mais pares para fornecer conectividade PSTN (rede) telefônica pública comutada clientes Enterprise Voice e dispositivos em sua organização.
ms.openlocfilehash: 34391e09bb87144252634b572bf0eac6a10fe1d9
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222860"
---
# <a name="configuring-trunks-in-skype-for-business-server"></a>Configurando troncos no Skype para Business Server

Como parte da implantação do Enterprise Voice, você pode configurar um tronco entre um servidor de mediação e um ou mais dos seguintes computadores para fornecer conectividade PSTN (rede) telefônica pública comutada clientes Enterprise Voice e dispositivos em sua organização:

- Conexão tronco SIP em um provedor de serviço de telefonia por Internet (ITSP)
- Gateway PSTN
- Central privada de comutação telefônica (PBX)

Para obter detalhes, consulte [Planejar a conectividade PSTN em Skype para Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).

> [!IMPORTANT]
> Antes de começar a configuração do tronco, verifique se a topologia foi criada e que o servidor de mediação e seu ponto tiverem sido configuradas e associadas umas com as outras. Para obter detalhes, consulte [Define um gateway no construtor de topologia no Skype para Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).

> [!NOTE]
> Como parte da configuração de tronco, é possível habilitar o Skype para o recurso de bypass de mídia Business Server, que permite a mídia ignorar o servidor de mediação. Troncos podem ser configurados com ou sem o bypass de mídia habilitado, mas é altamente recomendável habilitá-lo. Para obter detalhes, consulte [Plan for mídia que o desvio Skype para negócios](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).