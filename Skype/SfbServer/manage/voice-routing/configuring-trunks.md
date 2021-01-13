---
title: Configurando troncos no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Como parte da implantação do Enterprise Voice, você pode configurar um tronco entre um Servidor de Mediação e um ou mais pares para fornecer conectividade PSTN (rede telefônica pública comutado) para clientes e dispositivos Enterprise Voice em sua organização.
ms.openlocfilehash: 57b8635d635c0fd0b8c41c95f92af768ff84dfd4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800111"
---
# <a name="configuring-trunks-in-skype-for-business-server"></a>Configurando troncos no Skype for Business Server

Como parte da implantação do Enterprise Voice, você pode configurar um tronco entre um Servidor de Mediação e um ou mais dos seguintes pares para fornecer conectividade PSTN (rede telefônica pública comutado) para clientes e dispositivos Enterprise Voice em sua organização:

- Conexão tronco SIP em um provedor de serviço de telefonia por Internet (ITSP)
- Gateway PSTN
- Central privada de comutação telefônica (PBX)

Para obter detalhes, [consulte Plano para conectividade PSTN no Skype for Business Server.](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md)

> [!IMPORTANT]
> Antes de começar a configuração do tronco, verifique se a topologia foi criada e se o Servidor de Mediação e seu par foram configurados e associados um ao outro. Para obter detalhes, [consulte Definir um gateway no Construtor de Topologias no Skype for Business Server.](../../deploy/deploy-enterprise-voice/define-a-gateway.md)

> [!NOTE]
> Como parte da configuração de tronco, você pode habilitar o recurso de bypass de mídia do Skype for Business Server, que permite que a mídia ignore o Servidor de Mediação. Os troncos podem ser configurados com ou sem o desvio de mídia habilitado, mas recomendamos fortemente que você o habilite. Para obter detalhes, [consulte Plano para bypass de mídia no Skype for Business.](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
